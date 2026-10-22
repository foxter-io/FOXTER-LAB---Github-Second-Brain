# Guía paso a paso — Bloques nuevos

Dos bloques para insertar en `2-guia-paso-a-paso.md`:

- **Bloque 2A — Que Claude te ayude a completar tu contexto** (va antes de meter contenido).
- **Bloque 3B — Tu tono de voz para escribir correos** (va justo después de traer tu fuente externa).

Los prompts están incluidos aquí para que puedas seguir el bloque sin salir de la página. Cópialos a `3-prompts.md` como **Prompt 1b** y **Prompt 3b**.

---

## Bloque 2A — Que Claude te ayude a completar tu contexto

**Tiempo estimado:** 8–10 minutos

**Para qué sirve:** tu Second Brain es tan útil como lo que Claude sabe de ti. En lugar de rellenar a mano la sección "Sobre mí" de `CLAUDE.md`, dejas que Claude haga dos cosas: proponerte lo que ya cree saber de ti (a partir de su memoria y de lo que le cuentes) y entrevistarte para rellenar los huecos.

**Importante:** lo que Claude "recuerda" es un borrador, no la verdad. Puede estar desactualizado o equivocado. Tú decides qué se guarda.

### Paso 1. Pídele a Claude un borrador de lo que sabe de ti

Hazlo en un **chat normal de Claude**, fuera de Proyectos (no en la pestaña Code, que puede no tener acceso a tu memoria).

Pega este prompt:

```text
Quiero montar mi Second Brain y necesito que me ayudes a completar mi contexto profesional.

PASO A: propuesta
Con lo que sabes de mí (memoria y esta conversación), redacta un borrador con estos apartados:
1. Rol y responsabilidades
2. Áreas, clientes o proyectos principales
3. Personas clave con las que trabajo (solo nombre de pila y rol)
4. Herramientas y fuentes donde vive mi información (correo, calendario, documentos, CRM...)
5. Cómo trabajo: idioma, ritmo, preferencias
6. Temas que consulto con frecuencia

Reglas:
- Marca cada dato como [seguro] si me lo he dicho yo claramente, o [dudoso] si lo deduces o puede estar desactualizado.
- No inventes. Si no sabes algo, escribe "SIN DATOS".
- No incluyas contraseñas, claves, números de cuenta, datos de salud, finanzas personales ni datos sensibles de terceros.
- No te alargues: máximo una o dos líneas por apartado.

PASO B: huecos
Al terminar, dime qué apartados están vacíos o dudosos y hazme como máximo 6 preguntas, numeradas, para completarlos. Las más importantes primero. No avances hasta que yo responda.
```

### Paso 2. Corrige y responde

1. Lee el borrador. Corrige lo que esté mal y borra lo que no quieras guardar.
2. Responde a las preguntas de Claude, de forma breve. Si algo no quieres contarlo, escribe "saltar".
3. Si Claude tiene muy poca información sobre ti (cuenta nueva o memoria desactivada), no pasa nada: la entrevista del Paso B rellena casi todo. Si prefieres no usar datos reales, usa `contenido-ejemplo.md`.

### Paso 3. Pídele el resultado final

En el mismo chat:

```text
Con mis correcciones y respuestas, genera la versión final como dos bloques de texto en Markdown:

BLOQUE 1: la sección "Sobre mí" para mi CLAUDE.md, con estos campos:
- Rol
- Áreas, clientes o proyectos principales
- Idioma de trabajo
- Fuentes donde vive mi información
- Cómo prefiero que me respondas

BLOQUE 2: una lista de 3 a 5 notas iniciales que valdría la pena crear en mi Second Brain (título y una frase cada una), por ejemplo una nota por cliente o proyecto principal.

No incluyas nada marcado como [dudoso] que yo no haya confirmado. Al final, lista los datos que has dejado fuera.
```

### Paso 4. Llévalo a tu Second Brain

1. Abre la pestaña **Code** con la carpeta de tu repositorio.
2. Pega este prompt, sustituyendo lo que está entre corchetes por el texto que te dio Claude:

```text
Actualiza la sección "Sobre mí" de CLAUDE.md con este texto. No toques el resto del archivo.

[PEGA AQUÍ EL BLOQUE 1]

Después, crea una nota por cada una de estas ideas usando plantilla-nota.md. Aplica el filtro de cinco preguntas de CLAUDE.md y dime qué has descartado y por qué. No hagas commit.

[PEGA AQUÍ EL BLOQUE 2]
```

3. Lee lo que Claude propone antes de aceptar cada cambio.

**Comprobación:** `CLAUDE.md` tiene la sección "Sobre mí" completa y tienes al menos 2 notas iniciales.

**Errores frecuentes:**

- Pegar el borrador sin revisarlo. Todo lo que guardes acabará en GitHub.
- Hacer el Paso 1 dentro de la pestaña Code. Hazlo en un chat normal.
- Guardar datos personales de terceros "porque Claude los sabe". Si no son necesarios para tu trabajo, fuera.

---

## Bloque 3B — Tu tono de voz para escribir correos

**Tiempo estimado:** 10–12 minutos

**Para qué sirve:** crear un archivo `tone-of-voice.md` que describe cómo escribes tú. A partir de ahora, cuando le pidas a Claude un borrador de correo, lo escribirá con tu estilo y no con el de un asistente genérico.

**Qué necesitas:** entre 8 y 15 correos que hayas **enviado tú** (no recibidos), de tipos variados: respuesta corta, seguimiento, propuesta, petición, mensaje difícil. Cuantos más tipos, mejor.

### Paso 1. Elige los correos

- Escoge correos que te representen: los que te hayan salido naturales, no los que escribiste con prisa o en un mal día.
- Evita correos con información confidencial de clientes. Si no puedes evitarlos, sustituye nombres, cifras y empresas por `[NOMBRE]`, `[CIFRA]`, `[EMPRESA]` antes de pegarlos.
- No hace falta que sean muchos: con 8 buenos correos sale un resultado útil.

### Paso 2. Pásaselos a Claude

Tienes dos formas. Usa la que te funcione:

- **Con conector (si lo tienes activo):** pídele a Claude que busque tus últimos correos enviados. Revisa la lista que te enseña y quita los que no quieras usar.
- **Pegando el texto:** copia el cuerpo de cada correo y pégalo separado por una línea con `---`.

### Paso 3. Lanza el prompt

En la pestaña **Code**, con la carpeta de tu repositorio abierta:

```text
Quiero crear mi archivo de tono de voz para redactar correos. Voy a darte correos que he enviado yo.

Tarea:
1. Analiza mi forma de escribir. Fíjate en: saludo y despedida, longitud de frases y párrafos, nivel de formalidad, cómo pido cosas, cómo digo que no, cómo hago seguimiento, uso de humor, de listas o de negritas, expresiones que repito, expresiones que evito, y cualquier diferencia según el destinatario (cliente, equipo, proveedor).
2. Rellena la plantilla tone-of-voice.md con lo que encuentres. Sustituye todos los campos entre corchetes.
3. Para cada regla, basa tu conclusión solo en lo que ves en mis correos. Si un patrón aparece en menos de 3 correos, márcalo como "tentativo". Si no hay datos para un apartado, escribe "SIN DATOS" en lugar de inventarlo.
4. En el apartado de ejemplos, incluye como máximo 3 fragmentos cortos (una o dos frases) y anonimízalos: sin nombres de personas ni empresas, sin cifras, sin datos sensibles.
5. No guardes correos completos en ningún archivo.
6. No hagas commit.

Cuando termines, dime qué patrones has marcado como tentativos y qué preguntas me haces para confirmarlos.

Estos son mis correos:

[PEGA AQUÍ LOS CORREOS, o escribe: "búscalos en mi correo con el conector"]
```

### Paso 4. Revisa y corrige

1. Abre `tone-of-voice.md` y léelo entero.
2. Marca lo que no te represente. Pídele a Claude que lo ajuste:

```text
Estas reglas no me representan: [LISTA]. Estas sí, pero faltan: [LISTA]. Actualiza tone-of-voice.md y muéstrame los cambios antes de guardar.
```

3. Responde a las preguntas sobre los patrones tentativos.

### Paso 5. Pruébalo

Pídele un correo real que tengas que escribir esta semana:

```text
Usa tone-of-voice.md para redactar un correo a [PERSONA / ROL] sobre [TEMA]. Objetivo: [QUÉ QUIERO CONSEGUIR]. Dame solo el borrador, sin explicaciones.
```

Compara el resultado con cómo lo habrías escrito tú. Si no suena a ti, dile qué falla ("demasiado formal", "demasiado largo", "yo no diría esto") y pídele que actualice el archivo con esa corrección.

### Paso 6. Haz que Claude lo use siempre

Añade esta regla a `CLAUDE.md`:

```text
Cuando te pida redactar un correo o un mensaje en mi nombre, lee primero tone-of-voice.md y sigue sus reglas. Entrega siempre un borrador, nunca envíes nada. Si falta información para redactar (destinatario, objetivo, tono), pregúntame antes de escribir.
```

**Comprobación:** existe `tone-of-voice.md` sin campos entre corchetes sin rellenar, y Claude ha redactado un borrador con él.

**Errores frecuentes:**

- Usar correos recibidos en lugar de enviados. Claude copiaría el estilo de otra persona.
- Dar solo correos de un mismo tipo. El tono cambia según el contexto.
- Dejar ejemplos con nombres o cifras reales en un archivo que acaba en GitHub.
- Esperar que salga perfecto a la primera. El archivo mejora con 2 o 3 correcciones.

**Mantenimiento:** cada cierto tiempo, cuando corrijas un borrador de Claude, pídele que actualice `tone-of-voice.md` con lo que cambiaste. Así el archivo se afina con el uso.
