# Visión y alcance

## Resumen

Personal Desktop Hub es una aplicación de escritorio para Windows 11 que ofrece un espacio de trabajo personal configurable. Agrupa herramientas cotidianas en una interfaz ligera: lanzador, widgets, calendario, notas, tareas y recordatorios.

El proyecto tiene dos propósitos: resolver una necesidad de organización personal y servir como proyecto de portafolio construido y explicado durante un curso de Codex en YouTube.

## Problema

La información personal de organización suele quedar repartida entre aplicaciones, ventanas y recordatorios desconectados. El proyecto explora una experiencia unificada que el usuario puede adaptar a su forma de trabajar.

## Usuarios previstos

- Personas que quieren acceder rápidamente a sus aplicaciones y herramientas diarias.
- Usuarios que prefieren guardar calendario, notas y tareas localmente.
- Participantes del curso que quieran seguir un ejemplo de desarrollo incremental con Codex.

## Principios de producto

1. **Personalización por elemento:** cada widget, acceso, nota, evento, tarea y recordatorio puede tener ajustes propios cuando corresponda.
2. **Persistencia local:** los datos se conservan al cerrar y volver a abrir la aplicación.
3. **Progreso verificable:** la interfaz no representa una función como completa si todavía no funciona.
4. **Modularidad:** cada capacidad tiene límites claros y dependencias explícitas.
5. **Control del usuario:** inicio automático y notificaciones son configurables; la aplicación se puede cerrar completamente.
6. **Compatibilidad con Windows:** se consideran DPI, múltiples monitores, recursos y patrones nativos de notificación.

## Alcance funcional previsto

- Carrusel de aplicaciones con categorías, accesos y atajos.
- Barra lateral en cualquiera de los lados, con widgets ordenables y redimensionables.
- Calendario mensual, semanal y diario.
- Notas con edición, búsqueda, etiquetas y fijación.
- Tareas con prioridades, fechas, estados y recurrencia.
- Recordatorios de hábitos con horarios, días activos, posponer e historial.
- Perfiles visuales y opciones individuales de apariencia.
- Bandeja del sistema, inicio automático opcional y cierre completo.

## Fuera de alcance inicial

- Reemplazar Windows Explorer o modificar archivos críticos del sistema.
- Sincronización en la nube o colaboración multiusuario.
- Aplicación móvil.
- Integraciones externas que requieran cuentas o servicios remotos.

## Criterios iniciales de éxito

- El usuario puede configurar y abrir accesos desde el lanzador.
- Puede crear, editar y eliminar eventos, notas y tareas, y los datos persisten localmente.
- Los recordatorios respetan recurrencias y horas de silencio configuradas.
- Los elementos configurables conservan sus ajustes al reiniciar la aplicación.
- La aplicación opera en Windows 11 con soporte para más de un monitor y escalado DPI.
- Cada fase del curso termina con una demostración y una explicación de lo que sí quedó implementado.
