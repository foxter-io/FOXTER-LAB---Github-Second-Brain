# Mi Second Brain

Mi base de conocimiento personal en Markdown, gestionada con Claude y versionada en GitHub.

## Cómo usarlo

1. Abre la app Claude y entra en la pestaña **Code**.
2. Elige esta carpeta como proyecto.
3. Pídele que guarde información nueva o que responda preguntas sobre lo que ya hay.

Las reglas de funcionamiento están en [`CLAUDE.md`](CLAUDE.md).

## Estructura

(Se completa tras lanzar el Prompt 1.)

## Plantillas

- [`plantilla-nota.md`](plantilla-nota.md): nota general
- [`plantilla-reunion.md`](plantilla-reunion.md): notas de reunión

## Subir cambios a GitHub

1. Pídele a Claude que revise los archivos y prepare el mensaje de commit (Prompt 5).
2. En GitHub Desktop, pega el título en **Summary** y pulsa **Commit to main**.
3. Pulsa **Push origin**.

## Privacidad

- Este repositorio es **privado**. No lo cambies a público.
- No guardes contraseñas, claves ni datos sensibles de terceros.
- Lo que no deba subir a GitHub va en `_privado/`, que está en el `.gitignore`.
