# Prompts

Aquí van **todos los prompts que lanzaste** para hacer el ejercicio, en el orden en que los
lanzaste, con el modelo y la herramienta de cada uno.

Esto no es papeleo. Lo que se revisa es **cómo pediste las cosas**, no solo lo que salió: un
resultado flojo con un prompt bueno y un resultado flojo con un prompt vago necesitan feedback
distinto, y sin este archivo no se distinguen.

## Cómo rellenarlo

- Un apartado `## Prompt N` por cada prompt.
- **Pega el prompt tal cual lo lanzaste**, dentro del bloque de código, aunque ocupe diez líneas
  y aunque tenga faltas. No lo reescribas para que quede bien: el que arreglaste mentalmente
  después no es el que lanzaste.
- Incluye también los que **no funcionaron**. Suelen ser los más útiles de leer.
- `Modelo` y `Herramienta` en todos. Si cambiaste de una a otra a mitad, se nota aquí.

Borra el ejemplo de abajo cuando escribas el primero.

---

## Prompt 1

**Modelo:** Opus 5
**Herramienta:** Claude Code

```
Migra este proyecto de SQLite a PostgreSQL en Docker. Restricciones no negociables:
- compose.yaml con servicios db y db-test, imagen pgvector/pgvector:pg17, sin clave version:
- Puertos 54410 (dev) y 54411 (test)
- db-test sin persistencia: usa tmpfs en /var/lib/postgresql/data
- Healthcheck en ambos con pg_isready por TCP (-h 127.0.0.1); el arranque espera a healthy
- .env.test apuntando a db-test, cargado solo en entorno de pruebas
- Makefile: db-up, db-down, migrate (ambas bases), test
- NO modifiques ninguna migración existente. Si alguna falla en Postgres, detente y dime cuál y por qué.
Primero muéstrame el plan sin aplicar cambios.
```

**Qué salió:** (opcional, una línea) me mostro el analisis del lo existente y el plan para hacer la migracion

## Prompt 2

**Modelo:** Opus 5
**Herramienta:** Claude Code

```
procede con el plan de migracion
```

**Qué salió:** (opcional, una línea) modifico .env, creo el contenedor en docker, instalo dependencias necesarias y actulizo la conexion

## Prompt 3

**Modelo:** Opus 5
**Herramienta:** Claude Code

```
procede con el plan de migracion
```

**Qué salió:** (opcional, una línea) modifico .env, creo el contenedor en docker, instalo dependencias necesarias y actulizo la conexion