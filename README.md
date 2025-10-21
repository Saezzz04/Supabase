https://supabase.com/docs/guides/local-development

# 🧩 Guía para Instalar y Desplegar Supabase Localmente

Esta guía te explica cómo instalar, configurar y ejecutar **Supabase** en tu entorno local usando la **Supabase CLI** y **Docker**.  
Ideal para desarrollo, pruebas y proyectos personales sin depender del entorno en la nube.

---

## 🚀 ¿Qué es Supabase?

Supabase es una alternativa *open-source* a Firebase que ofrece:
- 🗄️ Base de datos PostgreSQL
- 🔐 Autenticación y autorización (Auth)
- 💾 Almacenamiento de archivos (Storage)
- ⚡ API REST y Realtime automáticas
- 📊 Panel de administración (Supabase Studio)

Todo puede ejecutarse localmente con un solo comando gracias a su CLI.

---

## 🧰 Requisitos previos

Antes de comenzar, asegúrate de tener instalados:

| Requisito | Descripción |
|------------|-------------|
| **Docker** | Necesario para ejecutar los contenedores de Supabase. |
| **Node.js + npm** | Para usar la CLI. |
| **Git (opcional)** | Para versionar migraciones y configuraciones. |

Puedes verificar si están instalados:
```bash
docker -v
node -v
npm -v


# Instalación global
npm install -g supabase

# O usando npx (sin instalación global)
npx supabase --help


supabase --version


#Crea un directorio nuevo o usar este mismo 
mkdir mi-proyecto-supabase
cd mi-proyecto-supabase



npx supabase init

#Esto creará una carpeta /supabase con la configuración inicial:

supabase/
├── config.toml          # Configuración general
├── migrations/          # Migraciones SQL
├── functions/           # Edge Functions (opcional)

#Arranca todos los servicios (Postgres, Auth, API, Storage, Studio):
npx supabase start
#Esto descargará las imágenes de Docker y levantará el stack completo.
#Verás algo similar a esto:
#Started Supabase local development setup.
#API URL: http://localhost:54321
#DB URL: postgresql://postgres:postgres@localhost:54322/postgres
#Studio URL: http://localhost:54323


#Acceder al Panel de Administración (Supabase Studio)
http://localhost:54323



#Consejos útiles

Usa .env para guardar tus claves y URLs.

Mantén tus migraciones versionadas con Git.

No uses este entorno local como producción.

Si cambias el config.toml, reinicia los servicios.

Puedes usar supabase status para ver el estado de los contenedores.