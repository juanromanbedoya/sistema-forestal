# 🌲 Sistema de Gestión Forestal — Forest Analysis

Aplicación web **full stack** para analizar y gestionar zonas forestales sobre **mapas interactivos**: dibujar y guardar zonas y subzonas, calcular áreas, administrar un catálogo de especies, registrar la trazabilidad de los árboles y simular la extracción de madera por cable vía.

> Es el MVP de **FMS — Forest Management System**. La visión completa del producto está en [docs/VISION.md](docs/VISION.md).

## ✨ Funcionalidades

- 🗺️ **Mapa interactivo**: dibujo de polígonos (Leaflet + Geoman), cálculo de área y búsqueda de direcciones y de zonas guardadas.
- 🧩 **Zonas y subzonas forestales** con validación espacial (cada subzona debe quedar dentro de su zona).
- 🌳 **Catálogo de especies** dinámico, con especies *probables* (según la región) separadas de las *confirmadas* manualmente.
- 📦 **Trazabilidad forestal**: dashboard, estado de salud de los árboles, registro de impactos y mapa de trazabilidad.
- 🏗️ **Simulador de cable vía**: diagrama con torres independientes para planear la extracción de madera.
- 📊 **Reportes** de cobertura vegetal por zona.
- 💾 Persistencia en base de datos y en el navegador (`localStorage`).

## 🛠️ Tecnologías

| Capa | Tecnologías |
|---|---|
| Frontend | React 18 · React Router · React-Leaflet · Leaflet · Geoman · Axios · Capacitor |
| Backend | Node.js · Express · API REST · validación y *rate limiting* |
| Base de datos | PostgreSQL (PostGIS opcional) · SQLite para la demo local |
| Despliegue | GitHub Actions → GitHub Pages (frontend) · Render (API) |

## 🚀 Ejecución rápida (SQLite, sin instalar base de datos)

```bash
git clone https://github.com/juan2052H/sistema-forestal.git
cd sistema-forestal/forest-analysis-app

# Backend
cd backend
npm install
cp .env.example .env          # en Windows: copy .env.example .env
DB_CLIENT=sqlite npm run migrate   # PowerShell: $env:DB_CLIENT="sqlite"; npm run migrate
DB_CLIENT=sqlite npm run seed
DB_CLIENT=sqlite npm start
```

En otra terminal:

```bash
cd sistema-forestal/forest-analysis-app/frontend
npm install
npm start
```

En Windows también puedes usar `forest-analysis-app/start.bat`.

## 📚 Documentación

| Documento | Contenido |
|---|---|
| [forest-analysis-app/README.md](forest-analysis-app/README.md) | Detalle técnico de la aplicación |
| [forest-analysis-app/API.md](forest-analysis-app/API.md) | Endpoints de la API |
| [forest-analysis-app/SETUP.md](forest-analysis-app/SETUP.md) | Instalación con PostgreSQL |
| [forest-analysis-app/USER_GUIDE.md](forest-analysis-app/USER_GUIDE.md) | Guía de uso |
| [forest-analysis-app/CHANGELOG.md](forest-analysis-app/CHANGELOG.md) | Historial de versiones |
| [docs/VISION.md](docs/VISION.md) | Visión del producto FMS |

## 🌿 Ramas

- `version1.2`: versión actual (mapa de trazabilidad, validación espacial, cable vía mejorado).
- `pruebas_1`: rama de pruebas que despliega en GitHub Pages.
- `prueva-verción-de-busqueda-de-zonas`: experimento de búsqueda de zonas.

## 👥 Autores

Proyecto desarrollado en equipo por:

- **Juan José Román Bedoya** ([@juan2052H](https://github.com/juan2052H))
- **Jose David Osorio Gallego** ([@josedavidosorio2005](https://github.com/josedavidosorio2005))
