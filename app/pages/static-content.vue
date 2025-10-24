<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-12">
        <header class="text-center mb-5">
          <h1 class="display-4 fw-bold text-dark mb-4">Contenido Estático</h1>
          <p class="lead text-muted">
            Demostración de renderizado de contenido estático con Nuxt.js SSR
          </p>
        </header>

        <div class="row g-4 mb-5">
          <div class="col-lg-6">
            <div class="card h-100 shadow-sm">
              <div class="card-body p-4">
                <h2 class="card-title h4 fw-bold text-primary mb-4">Contenido Estático en Nuxt.js</h2>
                
                <div class="space-y-4">
                  <div>
                    <h3 class="h5 fw-semibold text-dark mb-3">¿Cómo funciona el SSR con contenido estático?</h3>
                    <p class="text-muted mb-3">
                      En Nuxt.js, el contenido estático se renderiza completamente en el servidor. 
                      Cuando un usuario visita la página, recibe el HTML completo directamente, 
                      lo que mejora el tiempo de carga inicial y el SEO.
                    </p>
                    <p class="text-muted">
                      El servidor ejecuta Vue.js, genera el HTML final y lo envía al cliente. 
                      Esto significa que el contenido es visible inmediatamente, incluso antes 
                      de que se descargue y ejecute el JavaScript.
                    </p>
                  </div>

                  <div class="alert alert-info">
                    <h4 class="alert-heading h6 fw-bold">🚀 Beneficios del SSR para contenido estático:</h4>
                    <ul class="mb-0 ps-3">
                      <li><strong>Mejor performance de carga inicial</strong> - HTML listo inmediatamente</li>
                      <li><strong>Óptimo para motores de búsqueda (SEO)</strong> - Contenido indexable al instante</li>
                      <li><strong>Mejor experiencia en dispositivos lentos</strong> - Menos dependencia del JavaScript</li>
                      <li><strong>Mejor métricas Core Web Vitals</strong> - LCP y FCP optimizados</li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Comparación con Vue -->
          <div class="col-lg-6">
            <div class="card h-100 shadow-sm">
              <div class="card-body p-4">
                <h2 class="card-title h4 fw-bold text-success mb-4">Comparación: Nuxt.js vs Vue.js tradicional</h2>
                
                <div class="table-responsive">
                  <table class="table table-hover">
                    <thead class="table-light">
                      <tr>
                        <th class="fw-semibold">Característica</th>
                        <th class="fw-semibold text-primary">Nuxt.js (SSR)</th>
                        <th class="fw-semibold text-success">Vue.js (CSR)</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <td class="fw-medium">Renderizado inicial</td>
                        <td class="text-success fw-semibold">Servidor</td>
                        <td class="text-muted">Cliente</td>
                      </tr>
                      <tr>
                        <td class="fw-medium">SEO</td>
                        <td class="text-success fw-semibold">Excelente</td>
                        <td class="text-warning">Requiere configuración</td>
                      </tr>
                      <tr>
                        <td class="fw-medium">Tiempo de carga inicial</td>
                        <td class="text-success fw-semibold">Más rápido</td>
                        <td class="text-muted">Depende del bundle</td>
                      </tr>
                      <tr>
                        <td class="fw-medium">Complejidad</td>
                        <td class="text-warning">Media</td>
                        <td class="text-success fw-semibold">Baja</td>
                      </tr>
                      <tr>
                        <td class="fw-medium">Carga en servidor</td>
                        <td class="text-warning">Alta</td>
                        <td class="text-success fw-semibold">Baja</td>
                      </tr>
                    </tbody>
                  </table>
                </div>

                <div class="alert alert-warning mt-4">
                  <h4 class="alert-heading h6 fw-bold">💡 Punto clave:</h4>
                  <p class="mb-0">
                    Nuxt.js es ideal para aplicaciones que requieren buen SEO y performance inicial, 
                    mientras que Vue.js tradicional es suficiente para aplicaciones internas o donde el SEO no es crítico.
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Demostración práctica -->
        <div class="card shadow-sm">
          <div class="card-body p-5">
            <h2 class="card-title h3 fw-bold text-purple mb-5 text-center">Demostración Práctica - Componentes Estáticos</h2>
            <div class="row g-4">
              <div class="col-md-4 text-center">
                <div class="border border-2 border-dashed rounded-3 p-4 h-100 feature-card">
                  <div class="card-icon bg-purple bg-opacity-10 text-purple mx-auto mb-4">
                    ⚡
                  </div>
                  <h3 class="h5 fw-semibold text-dark mb-3">Renderizado en Servidor</h3>
                  <p class="text-muted small">Este contenido se renderiza completamente en el servidor antes de llegar al cliente</p>
                </div>
              </div>
              
              <div class="col-md-4 text-center">
                <div class="border border-2 border-dashed rounded-3 p-4 h-100 feature-card">
                  <div class="card-icon bg-purple bg-opacity-10 text-purple mx-auto mb-4">
                    🔍
                  </div>
                  <h3 class="h5 fw-semibold text-dark mb-3">SEO Optimizado</h3>
                  <p class="text-muted small">Motores de búsqueda indexan el contenido inmediatamente sin necesidad de JavaScript</p>
                </div>
              </div>
              
              <div class="col-md-4 text-center">
                <div class="border border-2 border-dashed rounded-3 p-4 h-100 feature-card">
                  <div class="card-icon bg-purple bg-opacity-10 text-purple mx-auto mb-4">
                    🚀
                  </div>
                  <h3 class="h5 fw-semibold text-dark mb-3">Carga Inmediata</h3>
                  <p class="text-muted small">Los usuarios ven el contenido instantáneamente, mejorando la experiencia</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
useSeoMeta({
  title: 'Contenido Estático | Nuxt.js SSR',
  description: 'Demostración de renderizado de contenido estático con Server Side Rendering en Nuxt.js'
})
</script>