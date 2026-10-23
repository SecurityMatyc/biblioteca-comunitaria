# Biblioteca Comunitaria MJV

Sistema web académico para gestionar libros, usuarios, préstamos, devoluciones y multas dentro de una biblioteca comunitaria.

Proyecto desarrollado durante **2025** para la **Evaluación 4 de Ingeniería de Software**.

## Estado del proyecto

Implementación académica funcional de alcance intermedio. El sistema se enfoca en reglas de negocio, control de disponibilidad, validaciones, roles de usuario y seguimiento de préstamos.

La versión disponible está orientada a ejecución local y revisión técnica. No fue desplegada en AWS; su propósito principal fue consolidar una entrega web funcional para el contexto académico.

## Contexto y objetivo

La aplicación representa una biblioteca comunitaria que necesita organizar su catálogo, controlar el préstamo de ejemplares y mantener información actualizada sobre lectores, bibliotecarios y administradores.

El objetivo fue digitalizar el ciclo básico de circulación de libros:

- Consulta del catálogo.
- Verificación de disponibilidad.
- Registro de préstamos.
- Registro de devoluciones.
- Cálculo de multas por atraso.
- Administración de usuarios y roles.

## Autores

- Matías Gajardo
- Jean Pierre Avastia
- Valentina Roldán

Proyecto realizado en equipo como parte del proceso formativo en desarrollo de software.

## Roles del sistema

### Lector

- Consulta el catálogo.
- Revisa la disponibilidad de libros.
- Gestiona su cuenta.
- Consulta información asociada a sus préstamos y devoluciones.

### Bibliotecario

- Administra libros y ejemplares.
- Registra préstamos.
- Registra devoluciones.
- Consulta disponibilidad.
- Gestiona información operativa de la biblioteca.

### Administrador

- Gestiona usuarios y roles.
- Administra bibliotecarios.
- Consulta métricas generales.
- Accede a funciones administrativas del sistema.

## Flujo de préstamo y devolución

1. El lector consulta el catálogo y selecciona un libro disponible.
2. El sistema valida la disponibilidad y las condiciones del préstamo.
3. El bibliotecario registra el préstamo.
4. El ejemplar queda marcado como no disponible.
5. Al devolver el libro, el sistema registra la fecha de devolución.
6. Si existe atraso, se calcula una multa de `$1000` por cada día.
7. La disponibilidad del libro se actualiza para futuros préstamos.

## Funcionalidades principales

- Registro e inicio de sesión de cuentas.
- Gestión de usuarios con roles.
- CRUD de libros para el perfil bibliotecario.
- Catálogo con búsqueda y consulta de disponibilidad.
- Control para evitar préstamos duplicados.
- Registro de préstamos y devoluciones.
- Cálculo automático de multas por atraso.
- Dashboard con métricas de libros, préstamos y multas.
- Inicio público con información de servicios y contacto.
- Validación de RUT chileno.
- Validación de teléfono.
- Validación de fortaleza de contraseña.
- Paneles diferenciados según el perfil del usuario.

## Reglas de negocio destacadas

- Un libro no disponible no puede entregarse en un nuevo préstamo.
- La disponibilidad se actualiza cuando se registra un préstamo o una devolución.
- Las multas se calculan a partir de los días de atraso.
- Las operaciones administrativas dependen del rol del usuario.
- Los datos de registro deben cumplir validaciones definidas por el sistema.

## Arquitectura y módulos

El proyecto está organizado en aplicaciones Django con responsabilidades separadas:

- `cuentas`: autenticación, registro, perfiles y control de roles.
- `gestion`: catálogo, préstamos, devoluciones, disponibilidad y reportes.
- `biblioteca`: configuración principal del proyecto Django.

## Tecnologías

- Python 3.13
- Django 5.2.8
- Django REST Framework instalado en el proyecto
- HTML, CSS y JavaScript
- Bootstrap 5
- SQLite

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
| `http://127.0.0.1:8000/login/` | Autenticación |
| `http://127.0.0.1:8000/admin/` | Panel de administración Django |

## Base de datos y despliegue

La aplicación utiliza **SQLite** para facilitar la ejecución local y la revisión académica.

Esta versión no fue desplegada en AWS. La configuración está orientada a un entorno local de desarrollo y demostración.

## Alcance y limitaciones

Este repositorio representa una implementación académica funcional de alcance intermedio. Antes de utilizarlo en una biblioteca real sería necesario considerar:

- Gestión de múltiples sucursales.
- Notificaciones de vencimiento.
- Reservas de libros.
- Historial detallado por ejemplar.
- Control de multas y pagos.
- Pruebas automatizadas.
- Configuración de respaldo y recuperación.
- Protección adicional de datos personales.
- Migración a una base de datos preparada para producción.

## Contexto académico

El proyecto se desarrolló por etapas. Durante las primeras unidades se trabajó en la planificación y los mockups; posteriormente se presentó una versión base y, en la Evaluación 4, se consolidó una aplicación funcional con reglas de negocio, validaciones, roles, control de disponibilidad e interfaz web.
