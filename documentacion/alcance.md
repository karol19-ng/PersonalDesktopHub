# Alcance del proyecto

## Propósito

Personal Desktop Hub es una aplicación de escritorio para Windows 11 que centraliza herramientas de productividad en una interfaz configurable. También es el proyecto base de un curso de Codex en YouTube y un portafolio que mostrará decisiones, evolución y resultados verificables.

## Qué realizará el proyecto

1. **Lanzamiento:** organizar aplicaciones, carpetas y accesos directos en un carrusel navegable.
2. **Espacio de escritorio:** mostrar una barra propia transparente del Hub, una barra lateral y widgets movibles, redimensionables y ordenables.
3. **Integración con Windows:** ofrecer personalización visual relacionada con la barra de tareas de Windows, dentro de las posibilidades compatibles del sistema.
4. **Organización personal:** administrar calendario, notas, tareas y recordatorios recurrentes.
5. **Correo:** mostrar un widget de correo y notificar mensajes entrantes de proveedores configurados.
6. **Asistencia opcional:** ofrecer un mini asistente que el usuario puede habilitar o dejar desactivado.
7. **Personalización:** guardar preferencias por perfil y por elemento, con valores predeterminados y opción de restablecimiento.
8. **Persistencia:** conservar datos personales localmente y permitir que la aplicación funcione sin conectividad.
9. **Servicios opcionales:** usar una API ASP.NET Core y PostgreSQL en Docker para aprendizaje, pruebas de integración y una posible sincronización futura.

## Barras del Hub y de Windows

Se consideran dos elementos distintos:

- **Barra transparente del Hub:** parte de la propia aplicación; contendrá lanzadores y accesos configurables.
- **Barra de tareas de Windows:** personalización o integración visual de la barra nativa, separada de la barra del Hub.

La aplicación no reemplazará Windows Explorer ni inyectará código en Explorer. La integración con la barra nativa se implementará usando mecanismos compatibles de Windows; si el sistema no permite un ajuste solicitado, la aplicación lo indicará y conservará la personalización de su propia barra.

## Correo y privacidad

- El widget mostrará información básica de las cuentas que el usuario conecte.
- Las notificaciones de correo serán configurables por cuenta y se podrán silenciar.
- La conexión se realizará mediante autorización del proveedor cuando esté disponible; no se almacenarán contraseñas de correo en texto plano.
- El usuario podrá desconectar una cuenta y desactivar por completo el módulo.

## Mini asistente

- Será opcional y estará apagado inicialmente.
- Podrá ayudar con acciones del Hub como crear una nota o una tarea, siempre mostrando claramente qué acción realizará.
- La aplicación principal seguirá operando si el asistente no está habilitado o no tiene conexión.
- Cualquier servicio externo que se integre se documentará antes de habilitarlo.

## Fuera del alcance inicial

- Reemplazar Explorer, modificar archivos críticos del sistema o alterar la barra de tareas mediante técnicas no soportadas.
- Sincronización obligatoria, cuentas de usuario propias o colaboración entre usuarios.
- Sustituir un cliente de correo completo; el widget será una vista resumida.
- Activar el asistente o conectar servicios externos sin decisión explícita del usuario.

## Criterios de éxito

- El lanzador abre accesos configurados por el usuario.
- La barra del Hub puede configurarse sin afectar los datos personales.
- Los módulos de calendario, notas, tareas y hábitos conservan sus datos al reiniciar.
- El correo puede desactivarse y sus notificaciones respetan preferencias.
- El asistente es optativo y no bloquea las funciones básicas.
- Cada fase tiene documentación, criterios de aceptación y evidencia de lo implementado.
