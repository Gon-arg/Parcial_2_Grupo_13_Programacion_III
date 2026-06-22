# Parcial 2 - Grupo 13 - Programación III

## Descripción del proyecto
Este proyecto consiste en el desarrollo de una API REST para la gestión de recetas y planificación de comidas utilizando **Node.js**, **Express** y **Sequelize** con PostgreSQL. La aplicación permite registrar usuarios, crear recetas, agregar ingredientes, guardar recetas favoritas y organizar menús semanales.

La idea principal del sistema es brindar una plataforma sencilla para que cada usuario pueda administrar sus propias recetas de forma segura, con autenticación mediante JWT y control de acceso por usuario.

## Integrantes y ramas

| Integrante | Rama asignada |
|-----------|---------------|
| Celina Vega | `rama_celi` |
| Gonzalo Herrera | `rama_gonza` |
| Federico Marcenac | `rama_fede` |
| Ulises Fossati | `rama_uli` |
| Ignacio Alvarado | `rama_nacho` |

Además del trabajo individual por rama, el proyecto cuenta con las ramas principales:
- `main`
- `dev`

## Tecnologías utilizadas
- Node.js
- Express
- Sequelize
- PostgreSQL
- JWT (JSON Web Token)
- bcryptjs
- dotenv
- cors
- helmet
- morgan
- Docker
- Git / GitHub

## Metodología de trabajo
El equipo trabajó con una metodología colaborativa basada en Git y GitHub. Cada integrante desarrolló funcionalidades sobre su propia rama para evitar conflictos y luego integró los cambios mediante pull requests y revisiones.

### Flujo de trabajo
```text
main
├── dev
├── rama_celi
├── rama_gonza
├── rama_fede
├── rama_uli
└── rama_nacho
```

Proceso seguido:
1. Crear rama propia desde `dev` o `main`.
2. Implementar la funcionalidad asignada.
3. Realizar commits descriptivos.
4. Subir cambios al repositorio remoto.
5. Abrir pull request para revisión.
6. Integrar cambios al proyecto principal.

## Estructura del proyecto
```text
Parcial_2_Grupo_13_Programacion_III/
├── backend/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── migrations/
│   ├── models/
│   ├── routes/
│   ├── seeders/
│   ├── tests/
│   ├── Dockerfile
│   ├── Dockerfile.dev
│   ├── package.json
│   └── server.js
└── README.md
```

## Funcionalidades principales

### Autenticación
- Registro de usuarios
- Login con validación de credenciales
- Obtención de perfil autenticado

### Recetas
- Obtener todas las recetas del usuario
- Obtener receta por ID
- Crear receta
- Actualizar receta
- Eliminar receta

### Ingredientes
- Agregar ingredientes a una receta
- Eliminar ingredientes

### Favoritos
- Ver recetas favoritas del usuario
- Agregar una receta a favoritos
- Eliminar una receta de favoritos

### Modelado adicional
- Preparación de la estructura para la gestión de menús semanales y días de menú

## Configuración del servidor
El archivo principal del servidor se encuentra en [backend/server.js](backend/server.js). Allí se configura:
- middleware de seguridad con `helmet`
- soporte para CORS
- parseo de JSON
- rutas principales de la API
- manejo de errores
- health check en `/health`

## Configuración de la base de datos
La conexión se configura en [backend/config/database.js](backend/config/database.js) y utiliza variables de entorno para definir la base de datos, usuario, contraseña y host.

## Modelos principales
Los modelos del proyecto están definidos en [backend/models](backend/models):
- `User`: usuarios y autenticación
- `Receta`: recetas del sistema
- `Ingrediente`: ingredientes asociados a recetas
- `Favorito`: recetas marcadas como favoritas
- `MenuSemanal` y `MenuDia`: estructura para la planificación semanal

## Endpoints principales
La API se organiza bajo el prefijo `/api`.

### Auth
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/auth/perfil`

### Recetas
- `GET /api/recetas`
- `GET /api/recetas/:id`
- `POST /api/recetas`
- `PUT /api/recetas/:id`
- `DELETE /api/recetas/:id`

### Ingredientes
- `POST /api/recetas/:id/ingredientes`
- `DELETE /api/ingredientes/:id`

### Favoritos
- `GET /api/favoritos`
- `POST /api/favoritos`
- `DELETE /api/favoritos/:recetaId`

## Ejecución del proyecto
1. Entrar a la carpeta del backend:
   ```bash
   cd backend
   ```
2. Instalar dependencias:
   ```bash
   npm install
   ```
3. Configurar variables de entorno en un archivo `.env`.
4. Ejecutar el servidor:
   ```bash
   npm run dev
   ```

## Docker
El proyecto incluye archivos de contenedorización para facilitar la ejecución del backend en entorno local o de desarrollo:
- [backend/Dockerfile](backend/Dockerfile)
- [backend/Dockerfile.dev](backend/Dockerfile.dev)

## Conclusión
Este trabajo permitió aplicar conceptos de desarrollo backend con Node.js, Express, autenticación JWT, bases de datos relacionales y trabajo colaborativo con Git/GitHub. La estructura del proyecto está pensada para escalar y agregar nuevas funcionalidades en futuras versiones.
