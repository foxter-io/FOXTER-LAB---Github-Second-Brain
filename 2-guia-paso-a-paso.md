# Guía paso a paso

Sigue esta guía durante las 2 horas, con [`3-prompts.md`](3-prompts.md) abierto al lado. Cada bloque termina con una **comprobación**: no pases al siguiente hasta cumplirla, o levanta la mano.

| Bloque | Franja | Qué haces |
|---|---|---|
| 0 | 0:00–0:15 | Contexto y reglas de privacidad |
| 1 | 0:15–0:35 | Repositorio y estructura |
| 2 | 0:35–0:55 | Tu contexto y tu primer contenido |
| 3 | 0:55–1:15 | Fuente externa y tono de voz |
| 4 | 1:15–1:35 | Consultas |
| 5 | 1:35–1:45 | Commit y push |
| 6 | 1:45–1:55 | Consultar desde el móvil |
| 7 | 1:55–2:00 | Cierre |

Los tiempos son orientativos.

---

## Bloque 0 — Contexto (15 min)

Escucha y ten abiertas la app **Claude (pestaña Code)** y **GitHub Desktop**. Tres ideas:

1. **Second Brain:** un único lugar donde vive tu conocimiento y que una IA puede leer.
2. **Markdown + GitHub:** texto plano, tuyo, con historial y sin depender de ninguna app.
3. **Claude Code:** lee y escribe en tu carpeta, así que él hace el trabajo de organizar.

**Reglas de privacidad:** repositorio privado, sin contraseñas ni claves, sin datos sensibles de terceros, y respeta la política de tu empresa.

**Comprobación:** tienes abiertas la app Claude (Code) y GitHub Desktop con sesión iniciada.

---

## Bloque 1 — Repositorio y estructura (20 min)

1. En GitHub Desktop: **File → New repository**. Nombre: `mi-second-brain`. Elige dónde guardarlo y crea el repositorio.
2. Pulsa **Publish repository** y **deja marcado "Keep this code private"**.
3. Copia a la carpeta del repositorio estos archivos de `plantillas-repo/`: `CLAUDE.md`, `README.md`, `plantilla-nota.md`, `plantilla-reunion.md` y `tone-of-voice.md`.
4. En la app Claude, pestaña **Code**, elige **esa misma carpeta**.
5. Lanza el **Prompt 1**. Claude te propondrá una estructura: léela, ajusta lo que no te encaje y confirma.

Claude pide permiso antes de crear o modificar archivos. Lee antes de aceptar.

**Comprobación:** hay carpetas nuevas, `CLAUDE.md` tiene la sección "Estructura" y en github.com tu repositorio muestra la etiqueta **Private**.

**Errores frecuentes:** publicar sin marcar "private" · elegir en Claude una carpeta distinta a la del repositorio · no tener sesión en GitHub Desktop · olvidar copiar `CLAUDE.md`.

---

## Bloque 2 — Tu contexto y tu primer contenido (20 min)

### 2A. Que Claude te ayude a completar tu contexto (8–10 min)

Claude es tan útil como lo que sabe de ti. Lanza el **Prompt 1b**:

1. **Paso A, en un chat normal** de Claude (fuera de Proyectos): Claude te enseña lo que cree saber de ti, marcando cada dato como [seguro] o [dudoso], y te hace hasta 6 preguntas.
2. **Revisa y responde.** Lo que Claude "recuerda" es un borrador, no la verdad. Borra lo que no quieras guardar. Si tu memoria está vacía, la entrevista rellena casi todo (o usa `contenido-ejemplo.md`).
3. **Paso B:** pídele la versión final (sección "Sobre mí" y 3–5 notas iniciales).
4. **Paso C, en la pestaña Code:** pega el resultado. Claude actualiza `CLAUDE.md` y crea las notas.

### 2B. Guarda tus 2 primeras piezas (10 min)

Lanza el **Prompt 2** con dos contenidos (por ejemplo, un correo importante y las notas de una reunión).

Claude aplica el **filtro de cinco preguntas** antes de guardar: ¿es esencial?, ¿es una sola idea?, ¿me servirá dentro de un mes?, ¿es fiable?, ¿es seguro guardarlo? De una reunión de 2 horas no se guarda la transcripción: se guardan 5–6 cosas. Eso hace que las respuestas del Bloque 4 sean buenas.

**Comprobación:** tienes al menos **3 notas** en tu repositorio y `CLAUDE.md` tiene la sección "Sobre mí".

**Errores frecuentes:** pegar el borrador de memoria sin revisarlo (todo acaba en GitHub) · hacer el Paso A dentro de Code · guardar datos de terceros que no necesitas · pegar algo sensible. Si Claude te avisa de que algo lo es, no lo guardes.

---

## Bloque 3 — Fuente externa y tono de voz (20 min)

### 3A. Trae una fuente externa (10 min)

Lanza el **Prompt 3** para traer, por ejemplo, las reuniones de tu semana o los correos de un cliente.

- Claude te **enseña primero** lo que ha encontrado. Tú confirmas antes de guardar.
- Guarda **resúmenes**, no correos completos.
- **Plan B** si tu conector no funciona o está bloqueado: pega o exporta el contenido y usa el mismo prompt.

### 3B. Crea tu tono de voz para los correos (10–12 min)

Un archivo `tone-of-voice.md` describe cómo escribes tú, para que Claude redacte borradores que suenen a ti.

1. **Elige 8–15 correos que hayas enviado tú** (no recibidos), de tipos variados: respuesta corta, seguimiento, petición, mensaje difícil. Evita los que tengan información confidencial o sustituye nombres y cifras por `[NOMBRE]`, `[CIFRA]`.
2. **Lanza el Prompt 3b**, pegando los correos o pidiendo a Claude que los busque con el conector (revisa la lista antes de aceptar).
3. **Revisa `tone-of-voice.md` entero.** Corrige lo que no te represente y responde a las preguntas sobre los patrones "tentativos".
4. **Pruébalo** con un correo real de esta semana (prompt de uso diario al final de `3-prompts.md`). Si no suena a ti, dile qué falla y pídele que actualice el archivo.
5. **Añade esta regla a `CLAUDE.md`:**

```text
Cuando te pida redactar un correo o un mensaje en mi nombre, lee primero tone-of-voice.md y sigue sus reglas. Entrega siempre un borrador, nunca envíes nada. Si falta información (destinatario, objetivo, tono), pregúntame antes de escribir.
```

**Comprobación:** has traído al menos una fuente (o pegado contenido) y existe `tone-of-voice.md` sin campos entre corchetes sin rellenar, con un borrador de prueba hecho.

**Errores frecuentes:** usar correos recibidos (Claude copiaría el estilo de otro) · dar solo un tipo de correo · dejar nombres o cifras reales en los ejemplos · esperar que salga perfecto a la primera: mejora con 2–3 correcciones.

---

## Bloque 4 — Consultas (20 min)

1. Haz 4–5 preguntas con el **Prompt 4** (hay ejemplos en `3-prompts.md`).
2. Haz la **pregunta trampa**: una cuya respuesta NO está en tu repositorio. Claude debe decir que no lo sabe.
3. **Por parejas:** intercambiad una pregunta y comparad resultados.

Las respuestas son tan buenas como el contenido guardado. Si Claude responde mal, casi siempre falta información o se guardó demasiado ruido.

**Comprobación:** Claude ha citado archivos en sus respuestas y ha reconocido que no sabía la respuesta a la pregunta trampa.

---

## Bloque 5 — Commit y push (10 min)

1. Lanza el **Prompt 5**. Claude revisa los archivos, te avisa si ve algo sensible y propone el mensaje del commit.
2. En GitHub Desktop pega el título en **Summary**, pulsa **Commit to main** y después **Push origin**.
3. Abre tu repositorio en github.com y comprueba archivos, historial y la etiqueta **Private**.

El historial te permite recuperar cualquier versión anterior de una nota.

**Comprobación:** tus notas aparecen en github.com y el repositorio sigue siendo privado.

---

## Bloque 6 — Consultar desde el móvil (10 min)

Sigue [`5-consultar-desde-movil.md`](5-consultar-desde-movil.md): creas un Proyecto en claude.ai con tu repositorio, pegas las instrucciones y haces una pregunta desde la app del móvil.

Es una **copia** de tu repositorio, no una conexión en vivo: tras cada push hay que sincronizar. Y es solo para consultar.

**Comprobación:** has recibido en el móvil una respuesta con archivo citado. Si tu plan no muestra la opción de GitHub, míralo en casa con la guía.

---

## Bloque 7 — Cierre (5 min)

Completa en voz alta: "Esta semana voy a meter en mi Second Brain…". Te llevas [`4-despues-del-workshop.md`](4-despues-del-workshop.md).

> El valor está en el hábito, no en la herramienta.

---

## Si te atascas

| Problema | Qué hacer |
|---|---|
| No puedes usar Claude Code | Trabaja en pareja con otro asistente y retoma en casa |
| Conector de correo/calendario bloqueado | Plan B: pega o exporta el contenido |
| GitHub Desktop no hace push | Pide ayuda a un facilitador |
| No quieres usar datos reales | Usa `contenido-ejemplo.md` |
| Publicaste el repositorio como público | En github.com: Settings → Danger Zone → Change visibility → Private |
| Tu memoria de Claude está vacía | Salta lo que no aplique del Bloque 2A y usa la entrevista |
