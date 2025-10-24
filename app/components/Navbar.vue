<template>
  <nav class="navbar navbar-expand-lg navbar-dark custom-navbar sticky-top">
    <div class="container">
      <NuxtLink class="navbar-brand fw-bold" to="/">
        Módulo 7 | SSR con Nuxt.js
      </NuxtLink>
      
      <button 
        class="navbar-toggler" 
        type="button" 
        data-bs-toggle="collapse" 
        data-bs-target="#navbarNav"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <NuxtLink to="/" class="nav-link" active-class="active">
              Inicio
            </NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/static-content" class="nav-link" active-class="active">
              Contenido Estático
            </NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/dynamic-data" class="nav-link" active-class="active">
              Datos Dinámicos
            </NuxtLink>
          </li>
          <li class="nav-item">
            <NuxtLink to="/comparacion" class="nav-link" active-class="active">
              Comparación SSR
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>