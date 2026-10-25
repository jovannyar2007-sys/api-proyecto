# API del portafolio

API REST construida con Express y MongoDB.

## Desarrollo local

Requiere Node.js 20.19 o superior y una base MongoDB accesible.

1. Instala las dependencias:

   ```powershell
   npm ci
   ```

2. Crea un archivo `.env` en la raíz de este proyecto y configura estas
   variables:

   ```text
   MONGODB_URL=<URI de conexión de MongoDB>
   ADMIN_EMAIL=<correo del administrador>
   ADMIN_PASSWORD=<contraseña segura del administrador>
   FRONTEND_URL=http://localhost:5173
   NODE_ENV=development
   PORT=3000
   ```

   Sustituye los valores entre `< >` por los tuyos. No publiques ni compartas
   `.env`; el archivo está excluido del repositorio.

3. Inicia la API:

   ```powershell
   npm run dev
   ```

La API estará disponible en <http://localhost:3000>. Comprueba el estado del
servidor y la conexión a MongoDB en <http://localhost:3000/healthz>.

## Scripts

- `npm run dev`: inicia el servidor con reinicio automático.
- `npm start`: inicia el servidor.

## Despliegue en Render

- Crea un **Web Service** conectado a este repositorio.
- Build command: `npm install`.
- Start command: `npm start`.
- Health check path: `/healthz`.
- Configura `MONGODB_URL`, `ADMIN_EMAIL`, `ADMIN_PASSWORD`,
  `FRONTEND_URL` y `NODE_ENV=production` en las variables de entorno del
  servicio. `FRONTEND_URL` debe ser el origen publicado del frontend, sin ruta.
- Render asigna `PORT` automáticamente.
