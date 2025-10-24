<div align=center>

# Exploración de frameworks para Server Side Rendering (SSR) y creación de una app SSR con Nuxt.js
### Módulo 7 | Actividad Práctica 5 | Actividad 2

</div>

## 📋 Descripción
Esta aplicación demuestra las características y ventajas del Server Side Rendering (SSR) utilizando Nuxt.js, comparándolo con el enfoque tradicional de Client Side Rendering (CSR).

## 🚀 Características Implementadas

### Tarea 1: Contenido Estático
- **Página de contenido estático** demostrando renderizado SSR
- **Comparación detallada** entre Nuxt.js (SSR) y Vue.js tradicional (CSR)
- **Tablas comparativas** con ventajas y desventajas
- **Componentes estáticos** renderizados en servidor

### Tarea 2: Comparación SSR vs CSR
- **Análisis técnico completo** de ambos enfoques
- **Tabla comparativa** con métricas específicas
- **Casos de uso recomendados** para cada tecnología
- **Comparación con Quasar Framework**
- **Métricas de performance** comparativas

### Tarea 3: Datos Dinámicos
- **Fetch de datos con SSR** usando `useAsyncData`
- **Integración con APIs externas** (JSONPlaceholder, Dog API)
- **Manejo de estados** (loading, error, success)
- **Renderizado de listas y tablas** con datos reales
- **Actualización dinámica** de contenido

## 🛠️ Tecnologías Utilizadas

- **Nuxt.js 3** - Framework para SSR
- **Vue.js 3** - Framework de JavaScript
- **Bootstrap 5** - Framework de CSS
- **TypeScript** - Tipado estático
- **APIs externas** - JSONPlaceholder, Dog CEO API

## 📁 Estructura del Proyecto

actividad-ssr/
├── assets/
│ └── css/
│ └── styles.css # Estilos personalizados con Bootstrap
├── components/
│ └── Navbar.vue # Componente de navegación
├── layouts/
│ └── default.vue # Layout principal
├── pages/
│ ├── index.vue # Página de inicio
│ ├── static-content.vue # Tarea 1 - Contenido estático
│ ├── dynamic-data.vue # Tarea 3 - Datos dinámicos
│ └── comparacion.vue # Tarea 2 - Comparación SSR
├── nuxt.config.ts # Configuración de Nuxt
└── app.vue # Componente raíz

text

## 🏃‍♂️ Instalación y Ejecución

```bash
# Instalar dependencias
npm install

# Servidor de desarrollo
npm run dev

# Build para producción
npm run build

# Preview de producción
npm run preview

# La aplicación estará en http://localhost:3000

```

## 📊 Aprendizajes Clave
### Beneficios del SSR (Nuxt.js)
- ✅ Mejor SEO - Contenido completamente renderizado para motores de búsqueda
- ✅ Performance inicial - Tiempo hasta primer contenido visible más rápido
- ✅ Mejor experiencia en conexiones lentas y dispositivos móviles
- ✅ Meta tags dinámicos - Optimización SEO por página

### Casos de Uso Recomendados

**Usar SSR (Nuxt.js) cuando:**
* SEO es crítico (e-commerce, blogs, sitios de contenido)
* Performance inicial es importante
* Aplicaciones públicas accesibles para todos los usuarios
* Mejor preview al compartir en redes sociales

**Usar CSR (Vue.js) cuando:**
* Aplicaciones internas (dashboards, admin panels)
* Alta interactividad y lógica compleja en cliente
* Desarrollo rápido de prototipos y MVPs
* SEO no es prioritario

## 🌐 URLs de la Aplicación
* `/` - Página de inicio con overview
* `/static-content` - Tarea 1: Contenido estático
* `/dynamic-data` - Tarea 3: Datos dinámicos desde APIs
* `/comparacion` - Tarea 2: Comparación SSR vs CSR

## 🔧 Funcionalidades Técnicas
### SSR con Nuxt.js
- Renderizado en servidor automático
- File-based routing intuitivo
- Data fetching con useAsyncData y useFetch
- Meta tags dinámicos para SEO
- Hydration automático en el cliente

### APIs Integradas
- JSONPlaceholder - Posts y usuarios de ejemplo
- Dog CEO API - Imágenes aleatorias de perros
- Manejo de estados - Loading, error y success states

## 📝 Conclusiones
1. **Nuxt.js** simplifica el SSR con convenciones inteligentes y configuración mínima
2. **SSR** es ideal para aplicaciones que requieren buen SEO y performance inicial
3. **CSR** sigue siendo válido para aplicaciones internas y de alta interactividad
4. La elección depende de los requisitos específicos del proyecto


### Responsables
<h4 align="center"> 
  <a href="https://github.com/CaroHernz">Carolina Hernández</a> | 
	<a href="https://github.com/gurrutia15">Gonzalo Urrutia</a> | 
	<a href="https://github.com/jlmansilla">Juan Luis Mansilla</a> | 
	<a href="https://github.com/lcarrilloq">Luis Carrillo</a> | 
</h4>