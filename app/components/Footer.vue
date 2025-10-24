<template>
  <footer class="custom-footer">
    <div class="container">
      <div class="row align-items-center py-4">

        <div class="col-md-6 text-center text-md-start">
          <div class="d-flex align-items-center justify-content-center justify-content-md-start">
            <div class="footer-brand me-3">
              <span class="fs-4">🚀</span>
            </div>
            <div>
              <h5 class="fw-bold mb-1">Módulo 7 ABP5 - SSR con Nuxt.js</h5>
              <p class="mb-0 small text-muted">Trabajo realizado por el <strong>Grupo 5</strong></p>
            </div>
          </div>
        </div>

        <div class="col-md-6 text-center text-md-end mt-3 mt-md-0">
          <div class="tech-stack">
            <span class="badge bg-light text-dark me-2">Nuxt.js 3</span>
            <span class="badge bg-light text-dark me-2">Vue.js 3</span>
            <span class="badge bg-light text-dark">Bootstrap 5</span>
          </div>
          <p class="small text-muted mt-2 mb-0">
            UNAB - Desarrollo Front End Trainne - {{ currentYear }}
          </p>
        </div>
      </div>

      
    </div>
  </footer>
</template>

<script setup>
const currentYear = new Date().getFullYear()
</script>

<style scoped>
.custom-footer {
  background: #2c3e50;
  color: white;
  border-top: 4px solid #20c997;
}

.footer-brand {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 50%;
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  backdrop-filter: blur(10px);
}

.tech-stack .badge {
  font-size: 0.7em;
  padding: 0.4em 0.8em;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.custom-footer .text-muted {
  color: #bdc3c7 !important;
}

.custom-footer .border-top {
  border-color: rgba(255, 255, 255, 0.1) !important;
}
</style>