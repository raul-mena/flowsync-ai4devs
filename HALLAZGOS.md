# Hallazgos

Aquí van **las tres líneas** del ejercicio, una por cada punto de abajo. Es lo único que hay que
traer hecho: un cambio de motor a medias con estas tres líneas escritas vale más que lo contrario,
porque lo que se discute en el directo es dónde te chocaste.

Escribe **una sola línea por punto**, con tus palabras y con lo que mediste, no con lo que suponías.

## 1. Las filas que cambian y la rama

mac@macbooks-MacBook-Pro flowsync-ai4devs % docker compose exec db psql -U flowsync -d flowsync -c "SELECT count(*) FROM tasks;"
 count 
-------
     0
(1 row)

0 filas cambian de valor (medido: `SELECT count(*) FROM tasks` en Postgres = N tras migrar, el cambio de motor no copia ni convierte datos, la base arranca vacia

-

## 2. Lo que la batería de pruebas no podía ver

Postgres devuelve las columnas date como objeto Date y Task.isOverdueOn compara texto ISO: sin el pg.types.setTypeParser(1082, ...) que agrego el agente en config/database.ts, ninguna tarea sale vencida y las 23 pruebas originales siguen en verde, solo lo detecta el overdue.spec.ts que añadió el agente
-

## 3. Tu duda

git diff s10/start -- backend/database/schema.ts sale vacío aunque la tarea dice que ese fichero cambia

-
