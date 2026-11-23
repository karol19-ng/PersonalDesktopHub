# Arquitectura inicial

## Estado

Propuesta inicial para la fase de arquitectura. Se revisará al implementar el prototipo y se registrarán los cambios importantes como ADR en `docs/adr/`.

## Tecnologías propuestas

- **C# / .NET 8 LTS:** plataforma de desarrollo y distribución para Windows.
- **WPF:** interfaz inicial, apropiada para una aplicación de escritorio Windows con ventanas, estilos y controles propios.
- **SQLite:** base de datos local para notas, tareas, eventos, hábitos y preferencias.
- **MVVM:** separación de presentación, estado y acciones de la interfaz.

La elección de WPF prioriza un prototipo Windows nativo y didáctico. La implementación medirá consumo, compatibilidad DPI, múltiples monitores y soporte de transparencia antes de cerrar la decisión.

## Proyectos y responsabilidades

### `PersonalDesktopHub.App`

Punto de entrada, ventanas, vistas, controles visuales, ViewModels, recursos y composición de dependencias. No debe contener reglas de negocio complejas ni acceso directo a SQLite.

### `PersonalDesktopHub.Core`

Modelos del dominio, enumeraciones, reglas, contratos de repositorios y servicios. No depende de WPF ni de SQLite.

### `PersonalDesktopHub.Infrastructure`

Implementaciones de persistencia SQLite, notificaciones de Windows e integración con funciones del sistema operativo. Depende de los contratos definidos en Core.

### `tests/`

Pruebas de reglas y casos de uso, organizadas por proyecto. Las verificaciones se incorporarán con las fases funcionales.

## Dirección de dependencias

```text
App ───────────────► Core
Infrastructure ───► Core
App ───────────────► Infrastructure (composición al iniciar)
Tests ─────────────► proyectos bajo prueba
```

Core no conoce la interfaz ni la infraestructura concreta. La aplicación conecta las implementaciones mediante inyección de dependencias.

## Módulos funcionales

- **ApplicationLauncher / Carousel:** accesos, categorías, navegación y atajos.
- **WidgetManager / Sidebar:** ciclo de vida y disposición de widgets.
- **Calendar:** eventos y consultas por intervalo de fechas.
- **TaskManager:** tareas, prioridades y recurrencias.
- **Notes:** contenido, etiquetas, búsqueda y asociación con fechas.
- **HabitReminders:** programación e historial de cumplimiento.
- **NotificationManager:** notificaciones del sistema y horas de silencio.
- **Settings:** perfiles, preferencias generales y anulaciones individuales.
- **DataStorage:** contexto de SQLite, repositorios y migraciones.

## Personalización y persistencia

Las preferencias generales viven en un perfil. Un elemento puede definir ajustes propios que prevalecen sobre el perfil; la ausencia de una preferencia individual significa que hereda el valor del perfil. Se debe poder restablecer un elemento sin borrar los demás ajustes.

La persistencia separará los datos de usuario de las preferencias de presentación cuando el diseño del esquema lo permita. Cambios del esquema se gestionarán mediante migraciones. Fechas y recurrencias se modelarán con una zona horaria explícita para evitar ambigüedades al cambiar horario o viajar.

## Decisiones pendientes de prototipo

- Mecanismo de ventanas flotantes y comportamiento frente a pantalla completa.
- Estrategia de desenfoque y transparencia compatible con Windows 11.
- API y límites de las notificaciones nativas.
- Esquema inicial de SQLite y política de respaldo/exportación.
- Comportamiento multi-monitor y restauración de posiciones fuera de pantalla.
