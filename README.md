# Arrumo Codex Plugin

The Codex agent adapter for planning, executing, and reporting on Arrumo video jobs.

## Icon and trademarks

`icon.svg` shows OpenAI's logo so creators recognise the service this plugin connects to. Codex, OpenAI and the OpenAI logo are trademarks of OpenAI; the manifest's `iconNotice` says so wherever Arrumo shows the icon. The logo is not covered by this repository's license, and this plugin is not affiliated with or endorsed by OpenAI. The SVG is a square without rounded corners; Arrumo rounds it. If OpenAI asks, replace the logo with a generic symbol and remove `iconNotice`.

## Setup guide

[English](docs/en/setup.md) · [Español](docs/es/setup.md) · [Português](docs/pt/setup.md)

## Translate subtitles

`tools/translate-subtitles.py` implements the Auto-Dubbing local translator
interface. Select this executable with Auto-Dubbing's `--translator` option
or with its standalone subtitle translation command. It uses the local Codex
login and sends the selected cue text and target language to the provider.

The adapter runs `codex exec` in a temporary directory with a structured
output schema. It uses a read-only sandbox, disables the shell, plugins and
web search, and skips user configuration while retaining Codex authentication.
The adapter validates cue coverage before returning the translated text.
