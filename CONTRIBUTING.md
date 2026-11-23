# Guía de contribución

Personal Desktop Hub se desarrolla en fases pequeñas para que cada cambio sea comprensible, revisable y útil como material de aprendizaje.

## Antes de contribuir

1. Lee el [alcance del proyecto](docs/vision.md) y la [arquitectura](docs/architecture.md).
2. Revisa la fase activa en `docs/roadmap.md`.
3. Mantén los módulos desacoplados y documenta cualquier decisión que cambie la arquitectura.
4. No marques una funcionalidad como terminada hasta que esté implementada y verificada.

## Flujo de trabajo

1. Describe un cambio pequeño con su objetivo y criterios de aceptación.
2. Implementa el cambio en el módulo correspondiente.
3. Actualiza la documentación afectada.
4. Ejecuta las verificaciones definidas para esa fase y registra el resultado.
5. Resume el cambio, las decisiones y las limitaciones conocidas.

## Convenciones

- Código, nombres de tipos y API internas en inglés; documentación de producto y curso en español.
- Sigue las convenciones estándar de C# y usa nombres descriptivos.
- Evita dependencias entre módulos de interfaz y el dominio.
- No guardes datos personales, secretos ni archivos de configuración locales en el repositorio.
- Usa commits breves que describan el cambio, por ejemplo: `docs: define initial architecture`.

## Reportar problemas

Incluye el entorno, los pasos para reproducir el problema, el resultado esperado y el resultado observado. No incluyas información privada del equipo.
