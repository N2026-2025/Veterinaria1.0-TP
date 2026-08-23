# 🐾 Veterinaria 1.0 - Sistema Integrado de Gestión Clínica

Este proyecto es una plataforma full-stack diseñada para optimizar y automatizar los flujos de trabajo de una clínica veterinaria. Permite la administración integral de pacientes (mascotas), propietarios (clientes), asignación de turnos médicos y el seguimiento de historias clínicas en tiempo real.

---

## 📌 Índice
1. [Características Principales](#-características-principales)
2. [Tecnologías Utilizadas](#-tecnologías-utilizadas)
3. [Estructura del Repositorio](#-estructura-del-repositorio)
4. [Instalación y Configuración](#-instalación-y-configuración)
5. [Estructura de la API (Backend)](#-estructura-de-la-api-backend)
6. [Estructura del Frontend](#-estructura-del-frontend)
7. [Buenas Prácticas y Contribución](#-buenas-prácticas-y-contribución)

---

## ✨ Características Principales

*   **Gestión de Clientes:** Altas, bajas, modificaciones y perfiles de contacto de los dueños.
*   **Historias Clínicas:** Registro dinámico de consultas, diagnósticos, recetas, vacunación y peso.
*   **Control de Turnos:** Calendario interactivo para reservar, reprogramar y cancelar citas médicas.
*   **Control de Stock (Próximamente):** Inventario de medicamentos e insumos clínicos.

---

## 🛠️ Tecnologías Utilizadas

### Backend
*   **Entorno de Ejecución:** Node.js (v18+)
*   **Framework Web:** Express.js
*   **Base de Datos (Sugerida):** MongoDB (Mongoose) / PostgreSQL / MySQL
*   **Autenticación (Opcional):** JSON Web Tokens (JWT)

### Frontend
*   **Lenguajes:** HTML5, CSS3, JavaScript (ES6+) / TypeScript
*   **Estilos:** CSS Modules / Tailwind CSS / Bootstrap

---

## 📂 Estructura del Repositorio

```text
Veterinaria1.0-TP/
├── .github/               # Flujos de trabajo y configuraciones de GitHub
├── backend/               # Código del servidor y lógica de negocio
│   ├── src/
│   │   ├── controllers/   # Controladores de las rutas
│   │   ├── models/        # Esquemas de datos y modelos
│   │   ├── routes/        # Definición de endpoints API
│   │   └── app.js         # Punto de entrada del backend
│   ├── package.json
│   └── .env.example
├── veterinaria-frontend/  # Interfaz gráfica de usuario
│   ├── src/
│   │   ├── components/    # Componentes UI reutilizables
│   │   ├── views/         # Vistas o páginas principales
│   │   └── main.js        # Punto de entrada de la aplicación
│   └── package.json
├── .gitignore             # Archivos omitidos en el control de versiones
└── README.md              # Documentación del proyecto
```

---

## 🚀 Instalación y Configuración

Siga las siguientes instrucciones paso a paso para desplegar el entorno localmente:

### ⚙️ Configuración del Backend

1.  Navegue a la carpeta del servidor:
    ```bash
    cd backend
    ```
2.  Instale las dependencias de desarrollo y producción:
    ```bash
    npm install
    ```
3.  Configure sus variables de entorno creando un archivo `.env`:
    ```bash
    cp .env.example .env
    ```
    *Defina allí sus puertos de conexión y URI de base de datos.*
4.  Inicie el servidor en modo desarrollo:
    ```bash
    npm run dev
    # O use el comando por defecto si no configuró nodemon:
    npm start
    ```

### 💻 Configuración del Frontend

1.  Regrese a la raíz y diríjase al directorio cliente:
    ```bash
    cd ../veterinaria-frontend
    ```
2.  Instale las dependencias del módulo web:
    ```bash
    npm install
    ```
3.  Ejecute el servidor de desarrollo del frontend:
    ```bash
    npm start
    # O si usa herramientas modernas (Vite):
    npm run dev
    ```
4.  Abra [http://localhost:3000](http://localhost:3000) (o el puerto indicado en su terminal) en su navegador web.

---

## 🔌 Estructura de la API (Backend)

Los endpoints de la aplicación se exponen bajo el prefijo común `/api`. A continuación, se detallan las rutas principales:

| Método | Endpoint | Descripción |
| :--- | :--- | :--- |
| `GET` | `/api/pacientes` | Obtiene la lista completa de mascotas. |
| `POST` | `/api/pacientes` | Registra una nueva mascota en el sistema. |
| `GET` | `/api/turnos` | Lista todas las citas médicas programadas. |
| `POST` | `/api/turnos` | Reserva un nuevo turno médico. |
| `PUT` | `/api/turnos/:id` | Modifica el estado o fecha de un turno específico. |

---

## 🤝 Buenas Prácticas y Contribución

Para mantener la legibilidad y el orden del código dentro del repositorio, el equipo sigue estas pautas:

1.  **Ramificación (Git Flow):** No realizar commits directamente sobre la rama `main`. Utilizar ramas descriptivas como `feature/nombre-de-la-mejora` o `bugfix/nombre-del-error`.
2.  **Mensajes de Commit:** Redactar mensajes claros y concisos en tiempo presente (ej: `feat: add patient registration form` o `fix: solve database connection timeout`).
3.  **Pull Requests:** Todo PR requiere la revisión y aprobación de al menos un miembro del equipo de desarrollo antes de fusionarse.

---

## 👥 Autores y Colaboradores

Desarrollado en el marco educativo del Trabajo Práctico por la organización **N2026-2025**.

