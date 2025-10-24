<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-12">
        <header class="text-center mb-5">
          <h1 class="display-4 fw-bold text-dark mb-4">Datos Dinámicos</h1>
          <p class="lead text-muted">
            Fetch de datos desde API externa usando el sistema de Nuxt.js SSR
          </p>
        </header>

        <div class="row g-4 mb-5">
          <div class="col-lg-6">
            <div class="card h-100 shadow-sm">
              <div class="card-body p-4">
                <h2 class="card-title h4 fw-bold text-primary mb-4">Fetch de Datos en Nuxt.js</h2>
                <div class="space-y-4">
                  <div>
                    <p class="text-muted">
                      Nuxt.js proporciona <code class="bg-light px-2 py-1 rounded">useAsyncData</code> y 
                      <code class="bg-light px-2 py-1 rounded">useFetch</code> para manejar datos 
                      asíncronos con SSR.
                    </p>
                    
                    <h4 class="h5 fw-semibold text-dark mt-4 mb-3">Comportamiento SSR:</h4>
                    <ul class="list-unstyled text-muted">
                      <li class="mb-2">
                        <span class="text-success me-2">•</span>
                        Los datos se fetchean en el <strong>servidor</strong> durante el renderizado
                      </li>
                      <li class="mb-2">
                        <span class="text-success me-2">•</span>
                        El HTML llega con los datos <strong>ya incluidos</strong>
                      </li>
                      <li class="mb-2">
                        <span class="text-success me-2">•</span>
                        Mejor SEO y performance inicial
                      </li>
                      <li>
                        <span class="text-success me-2">•</span>
                        Hydration automático en el cliente
                      </li>
                    </ul>
                  </div>

                  <div class="alert alert-success">
                    <h4 class="alert-heading h6 fw-bold">🚀 Comportamiento SSR:</h4>
                    <ul class="mb-0 ps-3 small">
                      <li>Los datos se fetchean en el servidor durante el renderizado</li>
                      <li>El HTML llega con los datos ya incluidos</li>
                      <li>Mejor SEO y performance inicial</li>
                      <li>Hydration automático en el cliente</li>
                    </ul>
                  </div>

                  <div class="alert alert-info">
                    <h4 class="alert-heading h6 fw-bold">📡 APIs utilizadas:</h4>
                    <ul class="mb-0 ps-3 small">
                      <li><strong>JSONPlaceholder:</strong> Datos de ejemplo (posts y usuarios)</li>
                      <li><strong>Dog API:</strong> Imágenes aleatorias de perros</li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Estadísticas en tiempo real -->
          <div class="col-lg-6">
            <div class="card h-100 shadow-sm">
              <div class="card-body p-4">
                <h2 class="card-title h4 fw-bold text-success mb-4">Estadísticas de Renderizado</h2>
                <div class="row g-3">
                  <div class="col-6 text-center">
                    <div class="p-4 bg-primary bg-opacity-10 rounded-3">
                      <div class="h3 fw-bold text-primary">{{ renderTime }}ms</div>
                      <div class="small text-muted">Tiempo de renderizado</div>
                    </div>
                  </div>
                  <div class="col-6 text-center">
                    <div class="p-4 bg-success bg-opacity-10 rounded-3">
                      <div class="h3 fw-bold text-success">{{ posts?.length || 0 }}</div>
                      <div class="small text-muted">Posts cargados</div>
                    </div>
                  </div>
                  <div class="col-6 text-center">
                    <div class="p-4 bg-warning bg-opacity-10 rounded-3">
                      <div class="h3 fw-bold text-warning">{{ users?.length || 0 }}</div>
                      <div class="small text-muted">Usuarios</div>
                    </div>
                  </div>
                  <div class="col-6 text-center">
                    <div class="p-4 bg-info bg-opacity-10 rounded-3">
                      <div class="h3 fw-bold text-info">SSR</div>
                      <div class="small text-muted">Modo renderizado</div>
                    </div>
                  </div>
                </div>
                
                <div class="mt-4 p-3 bg-light rounded">
                  <p class="small text-muted text-center mb-0">
                    💡 Estos datos se cargaron en el <strong>servidor</strong> usando SSR
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Posts desde API -->
        <div class="card shadow-sm mb-4">
          <div class="card-body p-4">
            <div class="d-flex flex-column flex-md-row justify-content-between align-items-start align-items-md-center gap-3 mb-4">
              <h2 class="card-title h4 fw-bold text-purple mb-0">Posts desde JSONPlaceholder API</h2>
              <button 
                @click="refreshPosts" 
                :disabled="pending"
                class="btn btn-primary d-flex align-items-center gap-2"
              >
                <span v-if="pending" class="loading-spinner"></span>
                <span>{{ pending ? 'Cargando...' : '🔄 Actualizar' }}</span>
              </button>
            </div>

            <div v-if="pending" class="text-center py-5">
              <div class="loading-spinner mx-auto mb-3" style="width: 40px; height: 40px;"></div>
              <p class="text-muted">Cargando posts desde API...</p>
              <p class="small text-muted">(Renderizado en servidor con SSR)</p>
            </div>

            <div v-else class="row g-4">
              <div 
                v-for="post in posts" 
                :key="post.id"
                class="col-md-6 col-lg-4"
              >
                <div class="post-card card h-100">
                  <div class="card-body">
                    <h3 class="card-title h6 fw-bold text-dark line-clamp-2">{{ post.title }}</h3>
                    <p class="card-text text-muted small line-clamp-3">{{ post.body }}</p>
                    <div class="d-flex justify-content-between align-items-center mt-auto">
                      <span class="badge bg-secondary">Post #{{ post.id }}</span>
                      <span class="badge bg-success">User {{ post.userId }}</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Usuarios desde API -->
        <div class="card shadow-sm mb-4">
          <div class="card-body p-4">
            <h2 class="card-title h4 fw-bold text-success mb-4">Usuarios desde API</h2>
            
            <div class="table-responsive">
              <table class="table table-hover">
                <thead class="table-light">
                  <tr>
                    <th class="fw-semibold">ID</th>
                    <th class="fw-semibold">Nombre</th>
                    <th class="fw-semibold">Email</th>
                    <th class="fw-semibold">Ciudad</th>
                    <th class="fw-semibold">Teléfono</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="user in users" :key="user.id">
                    <td class="fw-medium">{{ user.id }}</td>
                    <td class="fw-medium">{{ user.name }}</td>
                    <td class="text-muted">{{ user.email }}</td>
                    <td class="text-muted">{{ user.address.city }}</td>
                    <td class="text-muted">{{ user.phone }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
            
            <div class="mt-3 text-center">
              <p class="small text-muted mb-0">
                💡 Datos cargados con <code class="bg-light px-2 py-1 rounded">useAsyncData</code> en el servidor
              </p>
            </div>
          </div>
        </div>

        <!-- Imágenes dinámicas -->
        <div class="card shadow-sm">
          <div class="card-body p-4">
            <h2 class="card-title h4 fw-bold text-warning mb-4">Imágenes Dinámicas desde Dog API</h2>
            
            <div class="row g-3">
              <div 
                v-for="(dog, index) in dogs" 
                :key="index"
                class="col-6 col-md-3 text-center"
              >
                <img 
                  :src="dog" 
                  :alt="`Dog image ${index + 1}`"
                  class="img-fluid rounded shadow-sm mb-2"
                  style="height: 120px; width: 100%; object-fit: cover;"
                />
                <button 
                  @click="refreshDogImage(index)"
                  class="btn btn-outline-secondary btn-sm w-100 d-flex align-items-center justify-content-center gap-1"
                >
                  <span>🔄</span>
                  <span>Actualizar</span>
                </button>
              </div>
            </div>
            
            <div class="mt-4 alert alert-warning">
              <p class="small text-center mb-0">
                🐕 Estas imágenes se cargan dinámicamente desde <strong>Dog CEO API</strong>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Fetch de datos con SSR - se ejecuta en el servidor
const { data: posts, pending, refresh: refreshPosts } = await useAsyncData(
  'posts',
  () => $fetch('https://jsonplaceholder.typicode.com/posts?_limit=6')
)

// Otro fetch para usuarios
const { data: users } = await useAsyncData(
  'users',
  () => $fetch('https://jsonplaceholder.typicode.com/users')
)

// Estado reactivo para imágenes de perros
const dogs = ref([])

// Función para cargar imágenes de perros
const loadDogImages = async () => {
  const promises = Array.from({ length: 4 }, () => 
    $fetch('https://dog.ceo/api/breeds/image/random')
  )
  const results = await Promise.all(promises)
  dogs.value = results.map(result => result.message)
}

// Cargar imágenes iniciales
await loadDogImages()

// Función para actualizar una imagen específica
const refreshDogImage = async (index) => {
  const result = await $fetch('https://dog.ceo/api/breeds/image/random')
  dogs.value[index] = result.message
}

// Tiempo de renderizado (simulado)
const renderTime = ref(Math.floor(Math.random() * 100) + 50)

useSeoMeta({
  title: 'Tarea 3 - Datos Dinámicos | Nuxt.js SSR',
  description: 'Fetch de datos desde APIs externas usando Server Side Rendering en Nuxt.js'
})
</script>