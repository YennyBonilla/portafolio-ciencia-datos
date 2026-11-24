 # 03 — Ficha de proyecto

## Título

¿Cómo se distribuye el personal de las instituciones de educación superior por función y sexo?

## Pregunta de análisis

¿Cómo varía la proporción entre personal docente y administrativo, en cada función, por entidad, institución y sostenimiento en las instituciones de educación superior en el ciclo 2025-2026?

¿Cómo se distribuye el personal de las instituciones de educación superior entre funciones docentes y administrativas, y cómo varía la presencia de mujeres y hombres en cada función por entidad e institución?

## Tipo de pregunta

**Descriptiva.** El objetivo es describir cómo se distribuye el personal entre funciones (docente, administrativo, directivo e investigación) y entre mujeres y hombres, y cómo cambia esa distribución por entidad y sostenimiento. No se busca predecir un caso nuevo ni probar una causa.

## Fuente de datos

- **Fuente:** SEP, Formato 911, cuestionario 911.10 «Institución».
- **Base utilizada:** archivo propio, `INSTITUCIÓN.xlsx`, hoja «F911 10 Instituciones Ciclo 2025-2026».
- **Diccionario de variables:** cuestionario en blanco `INSTITUCI_N.pdf` (911.10, ciclo escolar 2025-2026), que describe el significado de las columnas.
- **Alternativa pública:** conjunto «Registro del alumnado y personal docente de educación básica, media y superior (formato 911)» en [datos.gob.mx](https://datos.gob.mx/es/dataset/registro_alumnado_personal_docente_educacion_basica_media_superior_formato_911). Incluye datos de alumnado y docentes, pero no de personal administrativo.

La base corresponde al levantamiento oficial de la SEP. El cuestionario 911 es el instrumento con el que cada institución reporta su personal, alumnado, finanzas e investigación en cada ciclo escolar.

## Dónde buscar datos

- Kaggle: repositorio de datasets, generalmente en CSV.
- INEGI: estadística oficial de México.
- datos.gob.mx: datos abiertos del gobierno.
- Banco Mundial: indicadores por país y año.
- Google Dataset Search: buscador de datasets.

## Verificación de requisitos

Verificado el 18 de noviembre de 2026 sobre el archivo real:

| Requisito | Verificación |
|---|---|
| Una sola tabla en CSV o Excel | Un archivo Excel con una hoja: «F911 10 Instituciones Ciclo 2025-2026». |
| Menos de 25 MB | 15.2 MB. |
| De 1,000 a 100,000 filas | 5,270 instituciones. |
| Dos o más columnas categóricas | Entidad federativa, municipio, control (público/privado), subcontrol (estatal, federal, autónomo, entre otros), turno y modalidad. |
| Dos o más columnas numéricas | Personal por función y sexo, y alumnado por nivel. |
| Una fecha (deseable) | Columna `PERIODO` = 2025; ciclo escolar 2025-2026. |
| Datos reales y descripción de columnas | Estadística oficial de la SEP; el cuestionario 911.10 en blanco describe las columnas. |
| Sin datos personales identificables | Datos agregados por institución, sin nombres de docentes ni de personal administrativo. |

**Comprobación adicional:** las sumas del cuestionario cuadran al 100 % en las 5,270 filas: el total de personal de áreas centrales es directivo + administrativo + otros; el total de personal de escuelas es la suma de las siete funciones; el total de la institución es áreas centrales + escuelas; y el total de alumnado es técnico superior + licenciatura + posgrado.

## Variables principales

Del cuestionario 911.10, secciones I, II y III:

- **Categóricas:** entidad federativa, municipio, control (público/privado), subcontrol, turno y modalidad (escolarizada/no escolarizada).
- **Numéricas — personal de escuelas (sección III):**
	- Docente: V44 hombres, V45 mujeres, V46 total.
	- Docente-investigador: V49 hombres, V50 mujeres, V51 total.
	- Investigador: V54 hombres, V55 mujeres, V56 total.
	- Personal administrativo y demás funciones: considerar los campos correspondientes del cuestionario 911.10.
- **Otras numéricas:** alumnado por nivel y totales de personal y alumnado.
- **Temporal:** `PERIODO` (2025), correspondiente al ciclo escolar 2025-2026.

## Alcance y limitaciones

El análisis es descriptivo y se basa en conteos agregados reportados por institución. 
**Relevancia:** Es importante determinar las caracteristicas del personal que conforma cada institución para identificar áreas de oportunidad que determinan el tipo de politicas públicas enecesarias para apoyar a las instituciones.
**Liminaciones:** La alternativa pública de datos.gob.mx no contiene personal administrativo; para comparar todas las funciones se utilizará la base propia de la SEP y su cuestionario como diccionario.
