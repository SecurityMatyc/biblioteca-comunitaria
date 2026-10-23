# Biblioteca Comunitaria MJV

Sistema web académico para la gestión de libros, usuarios, préstamos, devoluciones y multas dentro de una biblioteca comunitaria.

Proyecto desarrollado durante **2025** para la **Evaluación 4 de Ingeniería de Software**.

El sistema incluye funcionalidades para lectores, bibliotecarios y administradores, además de una interfaz web responsive con autenticación y gestión de cuentas.

## Autores

- Matías Gajardo
- Jean Pierre Avastia
- Valentina Roldán

Proyecto realizado en equipo como parte del proceso formativo en desarrollo de software.

## Descripción del proyecto

La aplicación permite administrar los procesos principales de una biblioteca comunitaria:

- Registro y gestión de usuarios con roles.
- Catálogo de libros con control de disponibilidad.
- Registro de préstamos con validaciones de negocio.
- Registro de devoluciones y cálculo automático de multas.
- Paneles diferenciados para lector, bibliotecario y administrador.
- Inicio público con información de servicios y contacto.
- Inicio de sesión y registro de cuentas.

## Características principales

- CRUD de libros para el perfil bibliotecario.
- Control de disponibilidad para evitar préstamos duplicados.
- Cálculo automático de multas por atraso: `$1000` por día.
- Búsqueda en el catálogo y consulta de disponibilidad.
- Gestión administrativa de usuarios, roles y bibliotecarios.
- Validación de RUT chileno, teléfono y fortaleza de contraseña.
- Dashboard con métricas de libros, préstamos y multas.

## Tecnologías

- Python 3.13
- Django 5.2.8
- Django REST Framework instalado en el proyecto
- HTML, CSS y JavaScript
- Bootstrap 5
- SQLite

## Módulos del sistema

- `cuentas`: autenticación, registro, perfiles y control de roles.
- `gestion`: catálogo, préstamos, devoluciones, disponibilidad y reportes.
- `biblioteca`: configuración principal del proyecto Django.

## Puesta en marcha local

### 1. Clonar el repositorio

```powershell
git clone <url-del-repositorio>
cd <nombre-del-repositorio>
```

### 2. Crear y activar el entorno virtual

```powershell
python -m venv env
.\env\Scripts\Activate.ps1
```

### 3. Instalar dependencias

```powershell
pip install -r requirements.txt
```

### 4. Aplicar migraciones

```powershell
python manage.py migrate
```

### 5. Iniciar el servidor

```powershell
python manage.py runserver
```

## Rutas principales

| Ruta | Descripción |
|------|-------------|
| `http://127.0.0.1:8000/` | Sitio principal |
| `http://127.0.0.1:8000/admin/` | Panel de administración Django |
| `http://127.0.0.1:8000/login/` | Autenticación |

## Despliegue

Esta versión no fue desplegada en AWS. El objetivo principal fue consolidar una entrega académica funcional con reglas de negocio, validaciones, roles e interfaz web.

## Contexto académico

El proyecto se desarrolló por etapas. Durante las primeras unidades se trabajó en la planificación y los mockups; posteriormente se presentó una versión base y, en la Evaluación 4, se consolidó la versión final con mejoras de interfaz, validaciones y flujo funcional.

## Alcance

La aplicación representa una implementación académica funcional de alcance intermedio. Su principal valor técnico está en la aplicación de reglas de negocio, control de disponibilidad, cálculo de multas, validaciones de datos y gestión de permisos por rol.
