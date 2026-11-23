# Personal Desktop Hub

**Un centro de productividad personal para Windows 11, creado paso a paso con Codex.**

Personal Desktop Hub reúne en un escritorio configurable un lanzador de aplicaciones, widgets, calendario, notas, tareas y recordatorios. El proyecto está pensado como aplicación útil por sí misma y como caso práctico de portafolio para mostrar un proceso de desarrollo modular, explicado y verificable.

> **Estado:** fase inicial de planificación y estructura. La aplicación todavía no está implementada.

## Objetivos

- Crear una aplicación de escritorio nativa para Windows 11.
- Permitir personalizar cada elemento de forma individual y guardar sus preferencias.
- Mantener localmente la información del usuario.
- Desarrollar los módulos en fases pequeñas, documentando las decisiones.
- Utilizar el proyecto como hilo conductor de un curso de Codex en YouTube.

## Módulos previstos

| Módulo | Responsabilidad |
| --- | --- |
| Application Launcher | Aplicaciones, carpetas, accesos directos y categorías. |
| Carousel | Presentación y navegación por el lanzador. |
| Widget Manager / Sidebar | Widgets configurables y su disposición en pantalla. |
| Calendar | Eventos, vistas y navegación por fechas. |
| Task Manager | Tareas, prioridades, vencimientos y recurrencia. |
| Notes | Notas, búsqueda, etiquetas y asociación a fechas. |
| Habit Reminders | Recordatorios recurrentes e historial. |
| Notification Manager | Notificaciones y horas de silencio. |
| Settings | Perfiles, apariencia, atajos y preferencias por elemento. |
| Data Storage | Persistencia local y migraciones de datos. |

## Tecnologías previstas

- C# y .NET 8 LTS.
- WPF para la interfaz de escritorio inicial.
- SQLite para almacenamiento local.
- Arquitectura modular con responsabilidades separadas.
- Git y GitHub para el control de versiones y la publicación del portafolio.

Las decisiones están sujetas a validación durante la primera fase. Consulta [la arquitectura](docs/architecture.md) y los registros de decisiones en `docs/adr/`.

## Estructura del repositorio

```text
PersonalDesktopHub/
├── .github/                 # Plantillas de colaboración
├── assets/                  # Recursos visuales y capturas del proyecto
├── docs/                    # Visión, arquitectura, hoja de ruta y guía del curso
│   └── adr/                 # Decisiones de arquitectura
├── src/                     # Código de producción, separado por proyectos
│   ├── PersonalDesktopHub.App/
│   ├── PersonalDesktopHub.Core/
│   └── PersonalDesktopHub.Infrastructure/
└── tests/                   # Pruebas organizadas por proyecto
```

## Inicio

Esta entrega establece documentación y estructura; aún no hay una aplicación ejecutable. Para la siguiente fase se requiere Windows 11 y el SDK de .NET 8. La guía de instalación y ejecución se añadirá junto con el primer prototipo en `src/`.

## Documentación

- [Visión y alcance](docs/vision.md)
- [Arquitectura inicial](docs/architecture.md)
- [Hoja de ruta](docs/roadmap.md)
- [Guía del curso de YouTube](docs/course-guide.md)
- [Cómo contribuir](CONTRIBUTING.md)

## Portafolio

Este repositorio documentará el problema, las decisiones técnicas, la evolución por fases y las funcionalidades implementadas. Las capturas, demostraciones y enlaces a episodios se agregarán cuando existan resultados publicables.

## Licencia

La licencia aún no está definida. Se seleccionará antes de publicar el código para reutilización por terceros.
