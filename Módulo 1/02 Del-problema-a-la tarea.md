# 02 — Del problema a la tarea

## El problema, como lo pediría un jefe o un cliente

> Hay instituciones públicas de educación superior que reciben subsidio estatal y federal, pero sin embargo, presentan problemas financieros que llegan a ser graves y a los que no se les vislumbra una solución breve ni a corto plazo, que sea suficiente y sostenible en el tiempo para evitar su quiebra.

## Pregunta de datos

¿Qué contribuye a que haya instituciones de educación superior en crisis financiera, y cómo podría aminorarse la problemática?

En las instituciones de educación superior no se conoce cómo se distribuye su personal entre funciones docentes y administrativas, por entidad y sostenimiento, lo que dificulta planear la planta de personal y los gastos presupuestales de la institución.

## Decisión que apoya

Tener conocimiento de los factores que contribuyen a la crisis de una institución beneficia en conocer la implementación o ajuste a la normativa interna que contribuya a la sostenibilidad de la institución.

## ¿Qué datos necesitaría?

- Cantidades del personal de cada institución por función (docente, docente-investigador, investigador, administrativo, directivo, otros) y por sexo, con su entidad y sostenimiento.
- Alumnado por nivel, como contexto para comparar el tamaño de cada institución.
- Una referencia de tiempo (el ciclo escolar) para ubicar el diagnóstico.

### ¿Cuáles tengo?

- La base `INSTITUCIÓN.xlsx` (Formato 911, cuestionario 911.10, SEP): 5,270 instituciones, ciclo 2025-2026, con el personal por función y sexo (docente, administrativo en escuelas y en áreas centrales), entidad, municipio, control y subcontrol.
- El diccionario de variables, el cuestionario en blanco `INSTITUCI_N.pdf` (911.10, ciclo 2025-2026).
- La misma base trae también las finanzas por institución (sección IV del cuestionario: ingresos y gasto por función), que se podría cruzar después en una segunda fase.

### ¿Cuáles me faltan?

- La serie de varios ciclos: solo tengo el ciclo 2025-2026, así que puedo describir el momento actual pero no la tendencia en el tiempo.
- Datos por persona: la base trae números agregados por institución, no registros individuales, así que no puedo cruzar el sexo con edad, antigüedad o nivel de estudios del personal.
- Variables que expliquen el porqué: la base dice dónde está la brecha, no por qué existe (eso pediría otras fuentes, como encuestas o registros de contratación).

### ¿Qué habría que transformar?

- Elegir solo las columnas que usa el problema (unas 20 de las 862 que trae el archivo) y renombrar los códigos V con su significado del cuestionario.
- Crear las proporciones que responden la pregunta: mujeres entre el total de cada función, y docentes por cada administrativo en cada institución.
- Atender a las instituciones sin personal en alguna función (745 no reportan docentes; 1,053 no reportan administrativo en escuelas) para que no distorsionen los promedios.
- Agregar por entidad y sostenimiento para comparar.
- Verificar las sumas de control del cuestionario (ya hecho: cuadran al 100% en las 5,270 filas).

## ¿Qué tipo de tarea es?

**Descriptiva**, ya que es necesario describir cómo se distribuye el personal y cómo cambian las proporciones por entidad, institución y sostenimiento.