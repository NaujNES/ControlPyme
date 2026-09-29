# ControlPyme
# ControlPyme

Aplicación web de gestión para pequeñas empresas, desarrollada y preparada para evolucionar hacia un servicio que atienda varios negocios con datos separados.

> **Estado:** en desarrollo. La versión actual implementa autenticación con sesión y permisos configurables. Todavía requiere pruebas de seguridad, operación y recuperación antes de usarse con negocios reales.

## Qué incluye

- Inicio de sesión y registro del primer negocio.
- Separación de productos, ventas, finanzas y configuración por negocio.
- Propietario, miembros, roles y permisos asignables desde la configuración.
- Inventario, ventas, finanzas, dashboard y reportes en la interfaz.
- API REST con Express y persistencia MySQL.
- Contraseñas almacenadas como hash y sesiones en cookies `HttpOnly`.

## Tecnologías

- **Interfaz:** React, TypeScript, Vite, Tailwind CSS, shadcn/ui y Recharts.
- **Servidor:** Node.js, Express y `mysql2`.
- **Base de datos:** MySQL.

## Requisitos

- Node.js y npm.
- MySQL Server activo.
- Git para clonar el repositorio una vez configurada su URL correcta. (https://github.com/NaujNES/ControlPyme)

## Preparar el entorno local

1. Descarga el código del repositorio oficial del proyecto o abre la carpeta del proyecto.
2. En la carpeta `controlpymev2_con_bd2`, instala las dependencias:

   ```bash
   npm install
   ```

3. Entra en `server` e instala las dependencias del backend:

   ```bash
   cd server
   npm install
   ```

4. Copia `server/.env.example` como `server/.env` y configura el acceso a MySQL. No publiques ese archivo ni compartas sus contraseñas.
5. Inicia el backend desde `server`:

   ```bash
   node index.js
   ```

6. En otra terminal, vuelve a `controlpymev2_con_bd2` e inicia el frontend:

   ```bash
   npm run dev
   ```

7. Abre la dirección local que muestra Vite (normalmente `http://localhost:5173`). El backend usa el puerto `3001` por defecto.

El servidor crea la base de datos y las tablas al iniciar si el usuario MySQL configurado tiene permisos para ello. Para el primer acceso, registra el negocio y su cuenta propietaria desde la pantalla de inicio.

### Datos heredados

Si se conserva una base de datos de una versión anterior, consulta `server/.env.example` para configurar `LEGACY_OWNER_EMAIL` y `LEGACY_OWNER_PASSWORD` antes de iniciar el servidor. Esas credenciales permiten acceder al negocio creado para los datos anteriores. No reutilices contraseñas reales ni subas `.env` a GitHub.

## Estructura

```text
controlpymev2_con_bd2/
├── server/                 # API Express, configuración MySQL y .env.example
├── src/
│   ├── app/                 # Pantallas y componentes de la aplicación
│   └── context/             # Estado y acceso a la API
├── public/
├── package.json
└── README.md
```



## Trabajo pendiente 

- Pruebas automatizadas de aislamiento entre negocios, roles, sesiones, ventas simultáneas y persistencia.
- Verificación de correo, recuperación de contraseña, invitaciones y límites frente a intentos automatizados.
- Historial auditable de cambios de inventario, ventas y movimientos financieros; definir anulaciones y devoluciones.
- Clientes, proveedores y compras con actualización transaccional de existencias.
- Terminar y reconciliar dashboard y reportes, con filtros y exportación a PDF y Excel.
- Copias de seguridad automáticas y pruebas de restauración.
- Despliegue HTTPS, monitoreo, manejo de errores, paginación, índices y plan de respuesta ante incidentes.
- Documentación de privacidad, retención de datos, soporte y costos de operación.


## Repositorio
(https://github.com/NaujNES/ControlPyme)

