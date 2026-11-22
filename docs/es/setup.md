# Configura Codex en Arrumo

[English](../en/setup.md) · [Português](../pt/setup.md)

Instala la CLI local e inicia sesión siguiendo la [guía del proveedor](https://learn.chatgpt.com/docs/codex/cli). Inicia Arrumo desde un entorno cuyo PATH incluya el directorio del ejecutable.

Elige Codex al configurar el espacio de trabajo o selecciónalo como agente de producción en Ajustes. La comprobación confirma la sesión local y no inicia ningún montaje.

## Comprueba la conexión

Desde la CLI del editor, indica la ruta de una base de datos local y el identificador de este plugin.

```sh
arrumo-workspaces ./workspaces.sqlite agent-login-status codex
```

El estado confirmed indica que la CLI aceptó la comprobación. Si Arrumo devuelve unavailable, comprueba que el ejecutable esté en el PATH que ve Arrumo. Si devuelve unconfirmed, inicia sesión según la guía oficial y vuelve a comprobarlo. Un tiempo de espera agotado o un error indica que la comprobación no pudo completarse.

## Traduce los subtítulos

Consulta [la traducción de subtítulos](../../README.md#translate-subtitles) para usar este plugin como traductor de Auto-Dubbing. El traductor envía a Codex el texto de los subtítulos seleccionados y el idioma de destino. El proceso conserva las marcas de tiempo originales.

## Crea imágenes

Codex puede crear miniaturas y otras imágenes con su herramienta de imágenes integrada, con tu plan de ChatGPT, así que no necesitas una clave de OpenAI o Gemini para ellas. Aparece en **Generación de imágenes**, en Ajustes, Servicios y claves, en primer lugar de forma predeterminada; bájalo para preferir un proveedor con clave. Arrumo envía la descripción de la imagen y hasta ocho referencias de estilo. Codex trabaja en solo lectura, y Arrumo recoge, comprueba y recorta la imagen, y después borra la copia de Codex.

## Preguntas de seguimiento

Cuando Codex pide a Arrumo material del espacio de trabajo, como el guion de un vídeo anterior, Arrumo responde en la misma sesión de Codex solo con ese material, así el encargo no se envía ni se paga dos veces. Estas sesiones quedan en el historial de Codex (`codex resume`); las ejecuciones puntuales no guardan ninguna.
