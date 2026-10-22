# Prompts del workshop

Cinco prompts principales y dos variantes (1b y 3b). Cópialos tal cual y sustituye lo que está entre `[CORCHETES]`. Revisa siempre lo que Claude propone antes de aceptar cambios.

**Dónde se lanza cada uno**

| Prompt | Para qué | Dónde |
|---|---|---|
| 1 | Crear la estructura | Pestaña Code |
| 1b | Completar tu contexto | Paso A y B en chat normal; Paso C en Code |
| 2 | Guardar contenido con filtro | Pestaña Code |
| 3 | Traer una fuente externa | Pestaña Code |
| 3b | Crear tu tono de voz | Pestaña Code |
| 4 | Consultar | Pestaña Code |
| 5 | Preparar el commit | Pestaña Code |

---

## Prompt 1 — Crear la estructura

```text
Lee CLAUDE.md. Voy a usar este repositorio como mi Second Brain.

Mi rol: [TU ROL]
Mis áreas, clientes o proyectos principales: [LISTA]

Tarea:
1. Propón una estructura de carpetas sencilla (máximo 6 carpetas de primer nivel) adaptada a mi trabajo. Explícame en una línea para qué sirve cada una.
2. Espera mi confirmación antes de crear nada.
3. Tras confirmar: crea las carpetas, actualiza la sección "Estructura" de CLAUDE.md y de README.md, y crea un archivo .gitignore que excluya la carpeta _privado/ y los archivos del sistema (.DS_Store, Thumbs.db).
4. No hagas commit.
```

## Prompt 1b — Completar tu contexto

**Paso A. En un chat normal de Claude (fuera de Proyectos):**

```text
Quiero montar mi Second Brain y necesito que me ayudes a completar mi contexto profesional.

PASO A: propuesta
Con lo que sabes de mí (memoria y esta conversación), redacta un borrador con estos apartados:
1. Rol y responsabilidades
2. Áreas, clientes o proyectos principales
3. Personas clave con las que trabajo (solo nombre de pila y rol)
4. Herramientas y fuentes donde vive mi información
5. Cómo trabajo: idioma, ritmo, preferencias
6. Temas que consulto con frecuencia

Reglas:
- Marca cada dato como [seguro] si me lo he dicho yo claramente, o [dudoso] si lo deduces o puede estar desactualizado.
- No inventes. Si no sabes algo, escribe "SIN DATOS".
- No incluyas contraseñas, claves, números de cuenta, datos de salud, finanzas personales ni datos sensibles de terceros.
- Máximo una o dos líneas por apartado.

PASO B: huecos
Al terminar, dime qué apartados están vacíos o dudosos y hazme como máximo 6 preguntas numeradas para completarlos, las más importantes primero. No avances hasta que yo responda.
```

**Paso B. Corrige y responde.** Borra lo que no quieras guardar y responde brevemente (o escribe "saltar"). Después:

```text
Con mis correcciones y respuestas, genera la versión final en dos bloques de Markdown:

BLOQUE 1: la sección "Sobre mí" para mi CLAUDE.md, con: Rol, Áreas/clientes/proyectos, Idioma de trabajo, Fuentes donde vive mi información, Cómo prefiero que me respondas.

BLOQUE 2: de 3 a 5 notas iniciales que valdría la pena crear (título y una frase cada una).

No incluyas nada marcado como [dudoso] que yo no haya confirmado. Al final, lista lo que has dejado fuera.
```

**Paso C. En la pestaña Code:**

```text
Actualiza la sección "Sobre mí" de CLAUDE.md con este texto. No toques el resto del archivo.

[PEGA EL BLOQUE 1]

Después, crea una nota por cada una de estas ideas usando plantilla-nota.md. Aplica el filtro de cinco preguntas de CLAUDE.md y dime qué has descartado y por qué. No hagas commit.

[PEGA EL BLOQUE 2]
```

## Prompt 2 — Guardar contenido con filtro

```text
Voy a pegarte contenido de mi trabajo. Guárdalo en mi Second Brain.

Tipo de contenido: [correo / reunión / idea / documento]
Cliente o proyecto: [NOMBRE]

Antes de guardar, aplica el filtro de cinco preguntas a cada dato:
1. ¿Es esencial? (¿cambiaría una decisión o respuesta futura?)
2. ¿Es una sola idea?
3. ¿Me servirá dentro de un mes?
4. ¿Es fiable? (si es dudoso, márcalo como "pendiente de confirmar")
5. ¿Es seguro guardarlo? (sin contraseñas, claves ni datos sensibles)

Tarea:
- Crea una o varias notas con plantilla-nota.md (o plantilla-reunion.md si es una reunión), en la carpeta que corresponda.
- No guardes transcripciones ni correos completos: guarda solo lo esencial.
- Enlaza con notas relacionadas si existen.
- Al terminar, dime qué notas has creado y qué has descartado y por qué.
- No hagas commit.

Contenido:
[PEGA AQUÍ]
```

## Prompt 3 — Traer una fuente externa

```text
Quiero traer información de [mi calendario / mi correo] a mi Second Brain.

Qué busco: [por ejemplo: las reuniones de esta semana / los correos con el cliente X de los últimos 30 días]

Tarea:
1. Búscalo con el conector. Si no puedes acceder, dímelo y espera a que yo pegue el contenido.
2. ANTES de guardar nada, enséñame una lista de lo que has encontrado (fecha, asunto, personas) y espera mi confirmación.
3. Tras confirmar, guarda un resumen por elemento con las plantillas, aplicando el filtro de cinco preguntas. Guarda resúmenes, nunca correos completos.
4. Avísame si hay datos sensibles y no los guardes.
5. No hagas commit.

Plan B, si no hay conector: contenido pegado o exportado:
[PEGA AQUÍ]
```

## Prompt 3b — Crear tu tono de voz

```text
Quiero crear mi archivo de tono de voz para redactar correos. Voy a darte correos que he enviado yo.

Tarea:
1. Analiza mi forma de escribir: saludo y despedida, longitud de frases y párrafos, formalidad, cómo pido cosas, cómo digo que no, cómo hago seguimiento, humor, uso de listas o negritas, expresiones que repito o evito, y diferencias según destinatario.
2. Rellena la plantilla tone-of-voice.md. Sustituye todos los campos entre corchetes.
3. Basa cada regla solo en mis correos. Si un patrón aparece en menos de 3 correos, márcalo como "tentativo". Si no hay datos, escribe "SIN DATOS".
4. Incluye como máximo 3 ejemplos cortos y anonimizados: sin nombres, empresas ni cifras.
5. No guardes correos completos. No hagas commit.

Al terminar, dime qué patrones son tentativos y qué preguntas me haces para confirmarlos.

Mis correos:
[PEGA AQUÍ, separados por ---, o escribe: "búscalos en mi correo con el conector"]
```

## Prompt 4 — Consultar

```text
Responde usando solo lo que hay en este repositorio. Cita el archivo de cada dato. Si no hay información suficiente, dilo claramente.

Mi pregunta: [PREGUNTA]
```

**Preguntas de ejemplo**

- ¿Qué decidimos en la última reunión con [CLIENTE]?
- ¿Qué tengo pendiente esta semana?
- Resume en 5 líneas el estado de [PROYECTO].
- ¿Qué sé de [PERSONA]?
- **Pregunta trampa (obligatoria):** una cuya respuesta sepas que NO está en el repositorio. Claude debe decir que no lo sabe.

## Prompt 5 — Preparar el commit

```text
Revisa los cambios del repositorio y prepárame el commit. No lo ejecutes.

1. Lista los archivos nuevos y modificados.
2. Avísame si algún archivo contiene contraseñas, claves, números de cuenta o datos sensibles.
3. Propón un título de commit (máximo 70 caracteres, en español) y una descripción de 2–4 líneas.
```

Después, en GitHub Desktop: pega el título en **Summary**, pulsa **Commit to main** y luego **Push origin**.

---

## Uso diario: redactar correos con tu tono

```text
Usa tone-of-voice.md para redactar un correo a [PERSONA / ROL] sobre [TEMA]. Objetivo: [QUÉ QUIERO CONSEGUIR]. Dame solo el borrador.
```
