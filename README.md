# Personal Desktop Hub

**Un centro de productividad personal para Windows 11, construido por fases con Codex.**

Personal Desktop Hub integra un lanzador, barras y widgets configurables, calendario, notas, tareas y recordatorios. Incluye como capacidades opcionales un mini asistente y herramientas de correo. El proyecto sirve como aplicación de escritorio, portafolio profesional y base práctica para un curso de Codex en YouTube.

> **Estado:** planificación y estructura del repositorio. La aplicación todavía no está implementada.

## Alcance resumido

- Lanzador de aplicaciones, carpetas y accesos directos.
- Barra transparente propia del Hub, panel lateral y widgets.
- Integración visual y configurable con la barra de tareas de Windows.
- Calendario, notas, tareas, hábitos y notificaciones.
- Notificaciones de correo y widget para consultar el correo.
- Mini asistente opcional, desactivado hasta que el usuario lo habilite.
- Personalización individual, perfiles y persistencia local.
- API y PostgreSQL en Docker como servicios opcionales de desarrollo y posible sincronización futura.

El alcance completo, límites y exclusiones están en [documentacion/alcance.md](documentacion/alcance.md).

## Tecnologías aprobadas

- C# y .NET 10 LTS para la plataforma y la lógica.
- WPF y XAML para la interfaz nativa de Windows; patrón MVVM.
- SQLite y Entity Framework Core para datos locales.
- ASP.NET Core para una API opcional.
- Docker y Docker Compose para API y PostgreSQL en desarrollo.
- GitHub Actions para automatizar compilación y verificaciones.

La justificación y el papel de cada tecnología se detallan en [documentacion/tecnologias-y-justificacion.md](documentacion/tecnologias-y-justificacion.md).

## Documentación

- [Alcance del proyecto](documentacion/alcance.md)
- [Tecnologías y justificación](documentacion/tecnologias-y-justificacion.md)
- [Estructura de proyectos](documentacion/estructura-de-proyectos.md)
- [Plan general por fases](documentacion/fases/README.md)
- [Guía del curso de YouTube](documentacion/curso-youtube.md)
- [Guía de contribución](CONTRIBUTING.md)

Cada fase tiene su propio documento con objetivos, entregables y criterios de cierre.

## Estructura

```text
PersonalDesktopHub/
├── documentacion/            # Alcance, decisiones y especificación por fases
├── docker/                   # Dockerfile y Compose para servicios opcionales
├── src/                      # Aplicación y bibliotecas de producción
├── tests/                    # Pruebas por proyecto
└── assets/                   # Capturas y recursos visuales
```

## Inicio

Esta etapa contiene la documentación y el esqueleto de carpetas; aún no hay una aplicación ejecutable. Los pasos para compilar y ejecutar se añadirán con el primer prototipo de WPF.

## Licencia

La licencia para reutilización aún no está definida.
