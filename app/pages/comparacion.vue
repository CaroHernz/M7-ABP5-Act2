<template>
  <div class="container py-5">
    <div class="row">
      <div class="col-12">
        <header class="text-center mb-5">
          <h1 class="display-4 fw-bold text-dark mb-4">Comparación SSR vs CSR</h1>
          <p class="lead text-muted">
            Análisis completo de cuándo usar Server Side Rendering y sus beneficios frente a Client Side Rendering
          </p>
        </header>
        <section class="card shadow-sm mb-5">
          <div class="card-body p-5">
            <h2 class="text-center mb-5 fw-bold text-primary">Comparación Técnica: SSR vs CSR</h2>
            
            <div class="table-responsive mb-5">
              <table class="table table-hover">
                <thead class="table-light">
                  <tr>
                    <th class="fw-semibold">Aspecto</th>
                    <th class="fw-semibold text-primary">Server Side Rendering (SSR)</th>
                    <th class="fw-semibold text-success">Client Side Rendering (CSR)</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="item in comparisonData" :key="item.aspect">
                    <td class="fw-medium text-dark">{{ item.aspect }}</td>
                    <td :class="item.ssr.favorability">
                      {{ item.ssr.description }}
                      <span v-if="item.ssr.note" class="small text-muted d-block mt-1">{{ item.ssr.note }}</span>
                    </td>
                    <td :class="item.csr.favorability">
                      {{ item.csr.description }}
                      <span v-if="item.csr.note" class="small text-muted d-block mt-1">{{ item.csr.note }}</span>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>

            <div class="row g-4">
              <div class="col-md-6">
                <div class="card border-primary h-100">
                  <div class="card-body">
                    <h3 class="h5 fw-semibold text-primary mb-4 d-flex align-items-center">
                      <span class="badge bg-primary me-3">🔁</span>
                      Flujo SSR (Nuxt.js)
                    </h3>
                    <ol class="list-group list-group-numbered">
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Usuario solicita página</strong>
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Servidor ejecuta Vue.js</strong> y prepara datos
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Renderizado completo en servidor</strong>
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>HTML + CSS enviados al cliente</strong>
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Hydration en el cliente</strong>
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Aplicación completamente interactiva</strong>
                        </div>
                      </li>
                    </ol>
                  </div>
                </div>
              </div>
              
              <div class="col-md-6">
                <div class="card border-success h-100">
                  <div class="card-body">
                    <h3 class="h5 fw-semibold text-success mb-4 d-flex align-items-center">
                      <span class="badge bg-success me-3">🔄</span>
                      Flujo CSR (Vue.js tradicional)
                    </h3>
                    <ol class="list-group list-group-numbered">
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Usuario solicita página</strong>
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Servidor envía HTML vacío</strong>
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Cliente descarga JavaScript</strong>
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Vue.js se inicializa en navegador</strong>
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Renderizado en el navegador</strong>
                        </div>
                      </li>
                      <li class="list-group-item d-flex justify-content-between align-items-start border-0 px-0">
                        <div class="ms-2 me-auto">
                          <strong>Aplicación interactiva</strong>
                        </div>
                      </li>
                    </ol>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- Uso -->
        <section class="card shadow-sm mb-5">
          <div class="card-body p-5">
            <h2 class="text-center mb-5 fw-bold text-purple">📋 Casos de Uso Recomendados</h2>
            
            <div class="row g-4">
              <div class="col-md-6">
                <div class="card border-primary h-100">
                  <div class="card-body">
                    <h3 class="h4 fw-semibold text-primary mb-4 d-flex align-items-center">
                      <span class="badge bg-primary me-3">✅</span>
                      Usar SSR (Nuxt.js) cuando:
                    </h3>
                    <div class="space-y-3">
                      <div class="d-flex align-items-start p-3 bg-primary bg-opacity-10 rounded">
                        <span class="text-success fs-5 me-3 mt-1">✓</span>
                        <div>
                          <strong class="text-primary">SEO es crítico</strong>
                          <p class="text-muted small mb-0">E-commerce, blogs, sitios de contenido, landing pages</p>
                        </div>
                      </div>
                      <div class="d-flex align-items-start p-3 bg-primary bg-opacity-10 rounded">
                        <span class="text-success fs-5 me-3 mt-1">✓</span>
                        <div>
                          <strong class="text-primary">Performance inicial importante</strong>
                          <p class="text-muted small mb-0">Usuarios con conexiones lentas o móviles</p>
                        </div>
                      </div>
                      <div class="d-flex align-items-start p-3 bg-primary bg-opacity-10 rounded">
                        <span class="text-success fs-5 me-3 mt-1">✓</span>
                        <div>
                          <strong class="text-primary">Redes sociales</strong>
                          <p class="text-muted small mb-0">Mejor preview al compartir enlaces</p>
                        </div>
                      </div>
                      <div class="d-flex align-items-start p-3 bg-primary bg-opacity-10 rounded">
                        <span class="text-success fs-5 me-3 mt-1">✓</span>
                        <div>
                          <strong class="text-primary">Aplicaciones públicas</strong>
                          <p class="text-muted small mb-0">Sitios accesibles para todos los usuarios</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              
              <div class="col-md-6">
                <div class="card border-success h-100">
                  <div class="card-body">
                    <h3 class="h4 fw-semibold text-success mb-4 d-flex align-items-center">
                      <span class="badge bg-success me-3">✅</span>
                      Usar CSR (Vue.js) cuando:
                    </h3>
                    <div class="space-y-3">
                      <div class="d-flex align-items-start p-3 bg-success bg-opacity-10 rounded">
                        <span class="text-primary fs-5 me-3 mt-1">✓</span>
                        <div>
                          <strong class="text-success">Aplicaciones internas</strong>
                          <p class="text-muted small mb-0">Dashboards, herramientas empresariales, admin panels</p>
                        </div>
                      </div>
                      <div class="d-flex align-items-start p-3 bg-success bg-opacity-10 rounded">
                        <span class="text-primary fs-5 me-3 mt-1">✓</span>
                        <div>
                          <strong class="text-success">Alta interactividad</strong>
                          <p class="text-muted small mb-0">Aplicaciones tipo SPA complejas con mucha lógica cliente</p>
                        </div>
                      </div>
                      <div class="d-flex align-items-start p-3 bg-success bg-opacity-10 rounded">
                        <span class="text-primary fs-5 me-3 mt-1">✓</span>
                        <div>
                          <strong class="text-success">Desarrollo rápido</strong>
                          <p class="text-muted small mb-0">Prototipos, MVPs y proyectos con tiempo limitado</p>
                        </div>
                      </div>
                      <div class="d-flex align-items-start p-3 bg-success bg-opacity-10 rounded">
                        <span class="text-primary fs-5 me-3 mt-1">✓</span>
                        <div>
                          <strong class="text-success">SEO no es prioritario</strong>
                          <p class="text-muted small mb-0">Aplicaciones behind login o sistemas internos</p>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- Métricas -->
        <section class="card shadow-sm mb-5">
          <div class="card-body p-5">
            <h2 class="text-center mb-5 fw-bold text-warning">📊 Métricas de Performance Comparativas</h2>
            
            <div class="row g-4">
              <div class="col-6 col-md-3">
                <div class="text-center p-4 bg-primary bg-opacity-10 rounded-3 border border-primary">
                  <div class="h2 fw-bold text-primary">1.2s</div>
                  <div class="small text-muted">First Contentful Paint</div>
                  <div class="small text-primary fw-semibold mt-2">SSR +40% más rápido</div>
                </div>
              </div>
              <div class="col-6 col-md-3">
                <div class="text-center p-4 bg-success bg-opacity-10 rounded-3 border border-success">
                  <div class="h2 fw-bold text-success">95/100</div>
                  <div class="small text-muted">Lighthouse SEO</div>
                  <div class="small text-success fw-semibold mt-2">SSR Excelente</div>
                </div>
              </div>
              <div class="col-6 col-md-3">
                <div class="text-center p-4 bg-danger bg-opacity-10 rounded-3 border border-danger">
                  <div class="h2 fw-bold text-danger">2.1s</div>
                  <div class="small text-muted">Time to Interactive</div>
                  <div class="small text-danger fw-semibold mt-2">CSR -25% más lento</div>
                </div>
              </div>
              <div class="col-6 col-md-3">
                <div class="text-center p-4 bg-warning bg-opacity-10 rounded-3 border border-warning">
                  <div class="h2 fw-bold text-warning">75/100</div>
                  <div class="small text-muted">Lighthouse Performance</div>
                  <div class="small text-warning fw-semibold mt-2">CSR Requiere optimización</div>
                </div>
              </div>
            </div>
            
            <div class="mt-4 alert alert-warning">
              <p class="text-center mb-0 small">
                💡 <strong>Nota:</strong> Las métricas pueden variar según la complejidad de la aplicación y la infraestructura
              </p>
            </div>
          </div>
        </section>

        <!-- Quasar Framework -->
        <section class="card shadow-sm">
          <div class="card-body p-5">
            <h2 class="text-center mb-5 fw-bold text-info">🚀 Quasar Framework - Alternativa Multiplataforma</h2>
            
            <div class="row g-4">
              <div class="col-md-6">
                <div class="h-100">
                  <h3 class="h4 fw-semibold text-info mb-4">¿Qué es Quasar Framework?</h3>
                  <p class="text-muted mb-4">
                    Quasar es un framework Vue.js que permite construir aplicaciones para múltiples plataformas 
                    (web, móvil, desktop) desde una sola base de código. Ofrece SSR integrado junto con capacidades 
                    para aplicaciones nativas.
                  </p>
                  
                  <h4 class="h5 fw-semibold text-dark mb-3">Características principales:</h4>
                  <ul class="list-group list-group-flush">
                    <li class="list-group-item px-0">
                      <strong>SSR integrado</strong> con configuración simple
                    </li>
                    <li class="list-group-item px-0">
                      <strong>Generación de aplicaciones móviles</strong> (Cordova, Capacitor)
                    </li>
                    <li class="list-group-item px-0">
                      <strong>Aplicaciones de escritorio</strong> (Electron)
                    </li>
                    <li class="list-group-item px-0">
                      <strong>Componentes UI optimizados</strong> para todas las plataformas
                    </li>
                    <li class="list-group-item px-0">
                      <strong>Build system avanzado</strong> con tree-shaking automático
                    </li>
                    <li class="list-group-item px-0">
                      <strong>Internationalization (i18n)</strong> integrado
                    </li>
                  </ul>
                </div>
              </div>
              
              <div class="col-md-6">
                <div class="h-100">
                  <h3 class="h4 fw-semibold text-info mb-4">SSR en Quasar vs Nuxt.js</h3>
                  <div class="space-y-4">
                    <div class="card border-info">
                      <div class="card-body">
                        <h4 class="h5 fw-semibold text-info mb-3">Quasar Framework</h4>
                        <p class="text-muted mb-3">
                          <strong>Ideal para:</strong> Aplicaciones multi-plataforma que necesitan SSR + capacidades móviles/desktop.
                        </p>
                        <ul class="list-unstyled small text-muted">
                          <li class="mb-1">• Mismo código para web, móvil y desktop</li>
                          <li class="mb-1">• SSR + PWA + Mobile App + Desktop App</li>
                          <li>• Menos configuración para multi-plataforma</li>
                        </ul>
                      </div>
                    </div>
                    
                    <div class="card border-primary">
                      <div class="card-body">
                        <h4 class="h5 fw-semibold text-primary mb-3">Nuxt.js</h4>
                        <p class="text-muted mb-3">
                          <strong>Ideal para:</strong> Aplicaciones web con fuerte enfoque en SSR y SEO.
                        </p>
                        <ul class="list-unstyled small text-muted">
                          <li class="mb-1">• Especializado en SSR para web</li>
                          <li class="mb-1">• Mejor ecosistema y documentación para renderizado</li>
                          <li class="mb-1">• File-based routing más intuitivo</li>
                          <li>• Mejor integración con el ecosistema Vue</li>
                        </ul>
                      </div>
                    </div>
                  </div>
                  
                  <div class="mt-4 alert alert-warning">
                    <h4 class="alert-heading h6 fw-bold">💡 Recomendación:</h4>
                    <p class="mb-0 small">
                      <strong>Usa Nuxt.js</strong> para aplicaciones web con fuerte enfoque en SSR y SEO. 
                      <strong>Elige Quasar</strong> cuando necesites construir para múltiples plataformas (web + móvil + desktop) desde un solo código base.
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup>
const comparisonData = [
  {
    aspect: 'Renderizado Inicial',
    ssr: { 
      description: 'HTML completo desde servidor', 
      favorability: 'text-success fw-semibold',
      note: 'Mejor primera impresión - Contenido visible inmediatamente'
    },
    csr: { 
      description: 'HTML vacío, renderizado en cliente', 
      favorability: 'text-danger',
      note: 'Loading visible hasta que se descargue JS'
    }
  },
  {
    aspect: 'SEO (Search Engine Optimization)',
    ssr: { 
      description: 'Excelente - Contenido indexable inmediatamente', 
      favorability: 'text-success fw-semibold',
      note: 'Ideal para sitios públicos y contenido'
    },
    csr: { 
      description: 'Complejo - Requiere configuración adicional', 
      favorability: 'text-warning',
      note: 'Necesita pre-rendering o dynamic rendering'
    }
  },
  {
    aspect: 'Performance Inicial',
    ssr: { 
      description: 'Más rápida - Contenido visible inmediatamente', 
      favorability: 'text-success fw-semibold',
      note: 'Mejor para conexiones lentas y móviles'
    },
    csr: { 
      description: 'Más lenta - Espera descarga de JS', 
      favorability: 'text-danger',
      note: 'Depende del bundle size y conexión'
    }
  },
  {
    aspect: 'Complejidad de Desarrollo',
    ssr: { 
      description: 'Media - Configuración de servidor necesaria', 
      favorability: 'text-warning',
      note: 'Nuxt.js simplifica mucho esta complejidad'
    },
    csr: { 
      description: 'Baja - Solo frontend', 
      favorability: 'text-success fw-semibold',
      note: 'Más simple de implementar y deployar'
    }
  },
  {
    aspect: 'Carga en Servidor',
    ssr: { 
      description: 'Alta - Cada request ejecuta Vue.js', 
      favorability: 'text-danger',
      note: 'Necesita buen hosting y escalabilidad'
    },
    csr: { 
      description: 'Baja - Servidor solo sirve archivos estáticos', 
      favorability: 'text-success fw-semibold',
      note: 'Carga distribuida en clientes'
    }
  },
  {
    aspect: 'Interactividad Post-Carga',
    ssr: { 
      description: 'Después de hydration (pequeño delay)', 
      favorability: 'text-warning',
      note: 'Hydration necesaria para interactividad'
    },
    csr: { 
      description: 'Inmediata después de carga inicial', 
      favorability: 'text-success fw-semibold',
      note: 'Una vez cargado el JS, es muy rápido'
    }
  },
  {
    aspect: 'Caché y CDN',
    ssr: { 
      description: 'Complejo - Depende de contenido dinámico', 
      favorability: 'text-warning',
      note: 'Cache más difícil de implementar'
    },
    csr: { 
      description: 'Simple - Archivos estáticos en CDN', 
      favorability: 'text-success fw-semibold',
      note: 'Fácil cache con servicios como Cloudflare'
    }
  }
]

useSeoMeta({
  title: 'Tarea 2 - Comparación SSR vs CSR | Nuxt.js',
  description: 'Análisis completo de Server Side Rendering vs Client Side Rendering, casos de uso recomendados y comparación con Quasar Framework'
})
</script>

<style scoped>

.space-y-3 > * + * {
  margin-top: 0.75rem;
}

.space-y-4 > * + * {
  margin-top: 1rem;
}
</style>