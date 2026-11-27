# Tecnologías y justificación

Esta es la línea tecnológica aprobada para iniciar el proyecto. Las versiones exactas de paquetes se fijarán al crear la solución y se mantendrán dentro de versiones soportadas.

| Tecnología | Uso | Por qué se elige |
| --- | --- | --- |
| C# | Lenguaje principal de la aplicación, la API y los servicios. | Permite compartir modelos y conocimientos entre los proyectos de escritorio y backend, con herramientas maduras para Windows. |
| .NET 10 LTS | Plataforma de compilación y ejecución. | Tiene soporte de largo plazo y cubre la aplicación WPF y la API. Se fija como destino `net10.0-windows` para el cliente. |
| WPF | Aplicación de escritorio y ventanas del Hub. | Proporciona ventanas, controles, estilos y enlazado de datos para una aplicación nativa de Windows. |
| XAML | Diseño de vistas, recursos, estilos y animaciones. | Separa la presentación de la lógica C# y facilita enseñar la interfaz por componentes. |
| MVVM | Organización de vistas, estado y acciones. | Reduce acoplamiento entre ventanas y lógica y hace más sencillo probar casos de uso. |
| SQLite | Almacenamiento local de eventos, tareas, notas, hábitos y preferencias. | No requiere servidor y permite que el Hub siga funcionando desconectado. |
| Entity Framework Core | Acceso a SQLite y evolución del esquema mediante migraciones. | Mantiene el acceso a datos en infraestructura y ofrece una estrategia explícita para cambios de esquema. |
| ASP.NET Core | API opcional para servicios auxiliares o sincronización futura. | Reutiliza C#/.NET y separa las funciones cliente/servidor sin hacer obligatoria la nube. |
| PostgreSQL | Persistencia del servicio API cuando se incorpore. | Es una base relacional adecuada para un servicio multiusuario y se ejecutará en contenedor durante desarrollo. No sustituye la SQLite local. |
| Docker | Empaquetado reproducible de los servicios backend. | Aísla dependencias del servidor y facilita enseñar el ciclo de construir, ejecutar y depurar contenedores. |
| Docker Compose | Arranque coordinado de API y PostgreSQL. | Permite describir los servicios, red y volúmenes del entorno con una configuración común para el curso. |
| Git y GitHub | Historial, colaboración y portafolio. | Mantienen trazabilidad de cambios y hacen pública la evolución del curso. |
| GitHub Actions | Compilación y verificaciones automatizadas. | Permite verificar el proyecto en cada cambio; la app WPF se compila en un entorno Windows y los servicios se validan con Docker. |
| xUnit | Pruebas automatizadas de dominio y casos de uso. | Proporciona pruebas rápidas para reglas independientes de la interfaz. |

## Papel de Docker

Docker se utilizará para la API y PostgreSQL opcionales, no para ejecutar la interfaz WPF ni para sustituir SQLite en el equipo del usuario. La aplicación principal será Windows y local-first; los servicios de Docker se podrán apagar sin perder las funciones esenciales del Hub.

## Versión de .NET

Se elige .NET 10 LTS para iniciar el desarrollo porque es la línea LTS actual según la política de soporte consultada el 26 de noviembre de 2026. La documentación oficial marca el fin del soporte de .NET 8 el 10 de noviembre de 2026. Antes de cada fase se comprobará que los SDK y paquetes sigan dentro de soporte.

## Notas de implementación

- C# y XAML serán el lenguaje de la aplicación; YAML describirá Docker Compose y los flujos de GitHub Actions.
- SQL será el lenguaje de consultas y cambios de esquema donde se requiera.
- Las fechas de eventos se almacenarán en UTC cuando representen instantes; las recurrencias conservarán la zona horaria y hora local de la regla.
- Las integraciones de correo y del asistente tendrán interfaces separadas para poder desactivarlas o sustituir proveedores.
- Las credenciales no se guardarán en texto plano ni se incluirán en el repositorio.
