# Estructura de proyectos

La estructura divide responsabilidades para que el producto pueda crecer por módulos y cada fase del curso tenga límites claros.

```text
PersonalDesktopHub/
├── .github/
│   └── workflows/                         # Automatización CI
├── assets/
│   └── screenshots/                       # Capturas del portafolio
├── docker/
│   ├── api/                                # Dockerfile de ASP.NET Core
│   └── compose.yaml                        # API + PostgreSQL opcional
├── documentacion/
│   ├── fases/                              # Un documento por fase
│   └── adr/                                # Decisiones de arquitectura
├── src/
│   ├── PersonalDesktopHub.App/             # WPF, XAML, ventanas y ViewModels
│   │   ├── Views/
│   │   ├── ViewModels/
│   │   ├── Controls/
│   │   ├── Widgets/
│   │   ├── Themes/
│   │   └── Resources/
│   ├── PersonalDesktopHub.Application/     # Casos de uso y coordinación
│   │   ├── Launcher/
│   │   ├── Calendar/
│   │   ├── Notes/
│   │   ├── Tasks/
│   │   ├── Email/
│   │   └── Assistant/
│   ├── PersonalDesktopHub.Core/            # Dominio y contratos
│   │   ├── Models/
│   │   ├── Enums/
│   │   └── Interfaces/
│   ├── PersonalDesktopHub.Infrastructure/  # SQLite y APIs de Windows/proveedores
│   │   ├── Persistence/
│   │   ├── Notifications/
│   │   ├── Email/
│   │   ├── Assistant/
│   │   └── Windows/
│   └── PersonalDesktopHub.Api/             # API opcional para fase posterior
├── tests/
│   ├── PersonalDesktopHub.Core.Tests/
│   ├── PersonalDesktopHub.Application.Tests/
│   ├── PersonalDesktopHub.Infrastructure.Tests/
│   └── PersonalDesktopHub.Api.Tests/
└── PersonalDesktopHub.sln
```

## Responsabilidades

- **App:** presenta la interfaz y enlaza las acciones del usuario con casos de uso; aloja la barra del Hub y widgets.
- **Application:** coordina flujos, por ejemplo crear una tarea, consultar el correo o invocar el asistente.
- **Core:** contiene modelos y reglas sin dependencia de WPF, SQLite, Docker o proveedores externos.
- **Infrastructure:** implementa persistencia, notificaciones nativas, correo y adaptadores de Windows.
- **Api:** ofrece endpoints solo cuando se necesite un servicio remoto/local; no es requisito para ejecutar la app.
- **Docker:** define el entorno de API y PostgreSQL; no guarda la base de datos local del usuario.

## Dirección de dependencias

```text
App ─────────────► Application ─────────────► Core
Infrastructure ─► Application / Core
Api ─────────────► Application / Infrastructure
Tests ───────────► proyecto bajo prueba
```

La integración de la barra de tareas de Windows se encapsulará en Infrastructure. La barra transparente del Hub será una ventana/control de App. Esto evita mezclar la interfaz propia con cambios globales del sistema.
