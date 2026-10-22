# Consultar tu Second Brain desde el móvil

Esta guía crea un **Proyecto de Claude** con una copia de tu repositorio, para que puedas preguntarle a tu Second Brain desde la app del móvil.

> **Qué es y qué no es:** es una **copia** de tu repositorio, no una conexión en vivo. Cada vez que hagas push con novedades, hay que **sincronizar** el Proyecto. Sirve para consultar, no para guardar notas.

> **Comprueba antes:** que la opción de añadir contenido desde GitHub aparece en tu plan y funciona con repositorios privados. Si no aparece, usa el plan B de abajo.

## Requisitos

- Has hecho commit y push (Bloque 5). Si no, el Proyecto estará vacío.
- Tienes la app de Claude en el móvil con la misma cuenta.

## Pasos

### 1. Crea el Proyecto (en claude.ai, desde el navegador del ordenador)

1. Entra en [claude.ai](https://claude.ai) → **Projects** → **New project**.
2. Nombre: `Mi Second Brain`.

### 2. Añade tu repositorio

1. En el Proyecto, en el área de conocimiento, pulsa **+** y elige **GitHub**.
2. Autoriza el acceso **solo al repositorio `mi-second-brain`**, no a todos.
3. Selecciona los archivos o carpetas a incluir. Excluye `_privado/` si existe.

### 3. Pega las instrucciones del Proyecto

En **Instructions** pega:

```text
Eres mi asistente para consultar mi Second Brain, formado por los archivos Markdown de este Proyecto.

Reglas:
1. Responde solo con lo que haya en estos archivos. Si no hay información suficiente, dilo claramente. No inventes.
2. Cita siempre el archivo (ruta) de donde sale cada dato.
3. Responde en español y de forma breve, salvo que pida más detalle.
4. Si redactas correos, lee primero tone-of-voice.md y sigue sus reglas. Entrega solo borradores.
5. Si algo parece desactualizado, recuérdame que debo sincronizar el Proyecto.
```

### 4. Pregunta desde el móvil

1. Abre la app de Claude → **Projects** → `Mi Second Brain`.
2. Haz una pregunta real, por ejemplo: "¿Qué tengo pendiente con [CLIENTE]?".
3. Haz también la **pregunta trampa** (algo que no está en tus notas).

## Mantenerlo al día

Cada vez que hagas push: en el Proyecto, en la sección del repositorio, pulsa **Sync now**.

## Si algo falla

| Problema | Solución |
|---|---|
| No aparece la opción de GitHub | Tu plan puede no incluirla. Plan B: sube manualmente los archivos `.md` más importantes al Proyecto |
| No ves tu repositorio privado | Revisa la autorización de la app de GitHub y concede acceso a ese repositorio |
| El Proyecto no aparece en el móvil | Cierra y abre la app, y comprueba que usas la misma cuenta |
| Está vacío | Falta hacer el push del Bloque 5 |

## Privacidad

El Proyecto contiene una copia de tus notas. Comprueba qué incluyes y no añadas nada que no deba salir de tu repositorio privado.
