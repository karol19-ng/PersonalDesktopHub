# Fase 7: Docker y API opcional

## Objetivo

Aprender Docker con servicios separados, sin hacer que el Hub dependa de ellos para su uso básico.

## Trabajo

- Añadir API ASP.NET Core con endpoints explícitos.
- Definir `docker/api/Dockerfile` y `docker/compose.yaml`.
- Ejecutar PostgreSQL en un contenedor con volumen de desarrollo.
- Añadir verificaciones de disponibilidad y configuración local segura.
- Evaluar sincronización solo como una capacidad opcional futura.

## Criterio de cierre

API y PostgreSQL arrancan con Compose y pueden apagarse sin afectar las funciones locales de WPF/SQLite. No se suben secretos al repositorio.
