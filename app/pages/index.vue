<template>
  <div>
    <section class="custom-hero text-white">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-lg-8 mx-auto text-center">
            <h1 class="display-4 fw-bold mb-4 hero-title">
              Actividad 2: Server Side Rendering con Nuxt.js
            </h1>
            <p class="lead mb-4 fs-5">
              Exploración práctica del renderizado del lado del servidor (SSR) y sus beneficios
              en comparación con el renderizado del lado del cliente (CSR).
            </p>
          </div>
        </div>
      </div>
    </section>

    <section class="py-5 bg-light">
      <div class="container">
        <div class="row">
          <div class="col-12">
            <div class="card shadow-sm">
              <div class="card-body p-5">
                <h2 class="text-center mb-5 fw-bold">¿Qué es Server Side Rendering?</h2>
                <div class="row g-4">
                  <div class="col-md-6">
                    <div class="feature-card card h-100 border-0">
                      <div class="card-body">
                        <h3 class="h5 fw-semibold text-primary mb-4">
                          <span class="badge bg-primary me-2">SSR</span>
                          Server Side Rendering
                        </h3>
                        <ul class="list-unstyled">
                          <li class="mb-3">
                            <span class="text-success me-2">✓</span>
                            <strong>Renderizado en el servidor</strong> - HTML completo generado antes de enviar al cliente
                          </li>
                          <li class="mb-3">
                            <span class="text-success me-2">✓</span>
                            <strong>Mejor SEO</strong> - Los motores de búsqueda ven contenido completo inmediatamente
                          </li>
                          <li class="mb-3">
                            <span class="text-success me-2">✓</span>
                            <strong>Performance inicial</strong> - Contenido visible más rápido para el usuario
                          </li>
                          <li>
                            <span class="text-success me-2">✓</span>
                            <strong>Mejor para conexiones lentas</strong> - Menos dependencia del JavaScript del cliente
                          </li>
                        </ul>
                      </div>
                    </div>
                  </div>
                  
                  <div class="col-md-6">
                    <div class="feature-card card h-100 border-0">
                      <div class="card-body">
                        <h3 class="h5 fw-semibold text-success mb-4">
                          <span class="badge bg-success me-2">CSR</span>
                          Client Side Rendering
                        </h3>
                        <ul class="list-unstyled">
                          <li class="mb-3">
                            <span class="text-primary me-2">✓</span>
                            <strong>Renderizado en el navegador</strong> - JavaScript genera el HTML después de la carga
                          </li>
                          <li class="mb-3">
                            <span class="text-primary me-2">✓</span>
                            <strong>Interactividad rápida</strong> - Una vez cargado, la aplicación es muy responsiva
                          </li>
                          <li class="mb-3">
                            <span class="text-primary me-2">✓</span>
                            <strong>Menos carga en servidor</strong> - El servidor solo sirve archivos estáticos
                          </li>
                          <li>
                            <span class="text-primary me-2">✓</span>
                            <strong>Ideal para aplicaciones internas</strong> - Donde el SEO no es crítico
                          </li>
                        </ul>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="pb-5 bg-light">
      <div class="container">
        <div class="row g-4">
          <div class="col-md-6 col-lg-4">
            <NuxtLink to="/static-content" class="nav-card card">
              <div class="card-body text-center p-4">
                <div class="card-icon bg-primary bg-opacity-10 text-primary mx-auto">
                  📄
                </div>
                <h3 class="card-title h5 fw-bold text-dark mb-3">Tarea 1: Contenido Estático</h3>
                <p class="card-text text-muted">
                  Implementación de páginas con contenido estático y comparación con Vue.js tradicional.
                  Demostración de beneficios SSR para SEO y performance inicial.
                </p>
              </div>
            </NuxtLink>
          </div>

          <div class="col-md-6 col-lg-4">
            <NuxtLink to="/dynamic-data" class="nav-card card">
              <div class="card-body text-center p-4">
                <div class="card-icon bg-success bg-opacity-10 text-success mx-auto">
                  🔄
                </div>
                <h3 class="card-title h5 fw-bold text-dark mb-3">Tarea 3: Datos Dinámicos</h3>
                <p class="card-text text-muted">
                  Fetch de datos desde API externa utilizando el sistema de rutas de Nuxt.js.
                  Demostración de SSR con datos asíncronos y hydratación.
                </p>
              </div>
            </NuxtLink>
          </div>

          <div class="col-md-6 col-lg-4 ">
            <NuxtLink to="/comparacion" class="nav-card card">
              <div class="card-body text-center p-4">
                <div class="card-icon bg-warning bg-opacity-10 text-warning mx-auto">
                  ⚖️
                </div>
                <h3 class="card-title h5 fw-bold text-dark mb-3">Tarea 2: Comparación SSR</h3>
                <p class="card-text text-muted">
                  Análisis completo de casos de uso, ventajas y desventajas del SSR vs CSR.
                  Incluye comparación con Quasar Framework.
                </p>
              </div>
            </NuxtLink>
          </div>
        </div>
      </div>
    </section>
    
  </div>
</template>

<script setup>
useSeoMeta({
  title: 'Actividad 2 - SSR con Nuxt.js',
  description: 'Exploración del Server Side Rendering con Nuxt.js - Comparación SSR vs CSR'
})
</script>