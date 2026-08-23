# 🐾 Veterinaria 1.0 - Sistema Integrado de Gestión Clínica

Este repositorio contiene el código fuente de **Veterinaria 1.0**, una aplicación full-stack orientada a la administración de clínicas veterinarias. El sistema permite gestionar de manera centralizada el registro de usuarios, el control médico de pacientes (mascotas), la persistencia de datos históricos y el agendamiento de turnos.

---

## 📌 Índice
1. [Características del Sistema](#-características-del-sistema)
2. [Arquitectura y Estructura del Repositorio](#-arquitectura-y-estructura-del-repositorio)
3. [Tecnologías Utilizadas](#-tecnologías-utilizadas)
4. [Instalación y Despliegue Local](#-instalación-y-despliegue-local)
5. [Estructura del Backend (API)](#-estructura-del-backend-api)
6. [Estructura del Frontend](#-estructura-del-frontend)
7. [Políticas de Contribución](#-políticas-de-contribución)

---

## ✨ Características del Sistema

*   **Autenticación Adaptativa:** Módulos independientes de registro e inicio de sesión para el personal de la clínica y clientes (`login.js`, `Registrarse.js`).
*   **Gestión de Turnos:** Controlador lógico backend (`turnosController.js`) dedicado a coordinar las citas y prevenir solapamientos horários.
*   **Fichas Médicas Digitales:** Visualización estructurada y actualización de datos biológicos de los animales en tiempo real (`FichaMascotas.js`).
*   **Persistencia Basada en Datos JSON:** Modelo ágil de almacenamiento local a través de archivos planos estructurados (`animales_guardados.json`).

---

## 📂 Arquitectura y Estructura del Repositorio

A continuación se detalla la estructura física exacta del proyecto según el árbol de directorios del repositorio:

```text
Veterinaria1.0-TP/
├── .github/                       # Configuración de workflows y CI/CD de GitHub
├── backend/                       # Capa del servidor y lógica de negocio (API)
│   ├── controller/                # Controladores lógicos (ej: turnosController.js)
│   ├── data/                      # Base de datos local (animales_guardados.json, etc.)
│   ├── database/                  # Módulos de conexión y mock data (db.js, db7.js)
│   ├── models/                    # Esquemas y abstracciones de entidades (mascota.json)
│   ├── router/                    # Definición de routers e intermediarios
│   ├── routes/                    # Endpoints expuestos de la API (index.js, userProfiles.js)
│   ├── utils/                     # Herramientas transversales (hashMaster.js)
│   ├── views/                     # Plantillas o respuestas de renderizado visual
│   ├── server.js                  # Punto de entrada de la aplicación Express
│   └── package.json               # Dependencias del entorno de servidor
├── veterinaria-frontend/          # Capa cliente e interfaz gráfica de usuario
│   ├── HTML/                      # Archivos de maquetación estructural web
│   ├── Imagenes/                  # Assets gráficos y recursos visuales locales
│   ├── src/                       # Código fuente del cliente empaquetado
│   │   ├── CSS/                   # Archivos de estilos (login.css, panel.css, etc.)
│   │   ├── JS/                    # Lógica del lado del cliente (login.js, panel.js)
│   │   ├── assets/                # Recursos estáticos adicionales
│   │   └── pages/                 # Vistas dinámicas (FichaMascotas.js, panelJS.js)
│   ├── vite.config.js             # Configuración del bundler Vite
│   └── package.json               # Dependencias del ecosistema del frontend
├── package.json                   # Gestión de dependencias globales del proyecto
└── README.md                      # Documentación general del sistema
```

---

## 🛠️ Tecnologías Utilizadas

*   **Núcleo de Servidor:** Node.js junto con el framework robusto Express.js.
*   **Almacenamiento:** Gestión de datos estructurada mediante serialización JSON nativa.
*   **Construcción Frontend:** HTML5 semántico, CSS3 avanzado y JavaScript Moderno (ES6+).
*   **Herramientas de Entorno:** Vite para compilación rápida y hot reload en desarrollo.

---

## 🚀 Instalación y Despliegue Local

Siga de manera ordenada estas instrucciones para clonar e iniciar el entorno de desarrollo en su máquina:

### ⚙️ Configuración y Arranque del Backend

1.  Ingrese a la suite del servidor:
    ```bash
    cd backend
    ```
2.  Instale los paquetes de Node requeridos:
    ```bash
    npm install
    ```
3.  Inicie el servidor Express:
    ```bash
    npm start
    ```
    > Por defecto, el servidor quedará escuchando peticiones en el puerto configurado en el archivo `server.js`.

### 💻 Configuración y Arranque del Frontend

1.  Regrese a la raíz y acceda a la suite cliente:
    ```bash
    cd ../veterinaria-frontend
    ```
2.  Descargue las dependencias administradas por Vite:
    ```bash
    npm install
    ```
3.  Ejecute el entorno local de desarrollo:
    ```bash
    npm run dev
    ```
4.  Abra su navegador web e ingrese a la dirección local provista (habitualmente `http://localhost:5173`).

---

## 🔌 Estructura del Backend (API)

El backend expone rutas estandarizadas para el consumo de datos del frontend. Algunas de las rutas clave mapeadas en los controladores son:

| Método | Endpoint | Archivo Controlador Asociado | Descripción |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/turnos` | `turnosController.js` | Devuelve la lista histórica de turnos médicos. |
| `POST` | `/api/turnos` | `turnosController.js` | Registra una nueva solicitud de cita en el sistema. |
| `POST` | `/api/auth/login` | `routes/index.js` | Autentica un usuario y redirige al panel. |
| `POST` | `/api/auth/register`| `routes/index.js` | Da de alta un nuevo perfil en la base de datos JSON. |

---

## 💻 Estructura del Frontend

El cliente está optimizado para modularidad y rendimiento:
*   **`/HTML`**: Contiene los puntos de acceso estáticos para las interfaces limpias.
*   **`/src/CSS`**: Estilos independientes y encapsulados para evitar colisiones de diseño entre el login y el panel operativo.
*   **`/src/JS`**: Scripts dedicados a la interceptación de formularios, validación del lado del cliente y comunicación asíncrona mediante `fetch`/`axios` hacia el servidor.

---

## 🤝 Políticas de Contribución

Para garantizar la estabilidad de la rama principal (`main`), el equipo aplica estrictamente el siguiente flujo de trabajo:
1.  **Aislamiento:** Está prohibido pushear código directamente a la rama `main`. Toda modificación debe realizarse en una rama auxiliar descriptiva (`feature/funcionalidad` o `bugfix/correccion`).
2.  **Mensajes Claros:** Los mensajes de commit deben describir con precisión la lógica alterada usando convenciones claras (ej: `feat: implement turnos controller validation`).
3.  **Aprobación:** Todo cambio debe integrarse mediante un Pull Request (PR) que cuente con la revisión correspondiente.
4.  

## 👥 Autores y Colaboradores

Desarrollado en el marco educativo del Trabajo Práctico por la organización **N2026-2025**.

