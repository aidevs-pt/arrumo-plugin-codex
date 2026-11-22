# Arrumo Codex Plugin

The Codex agent adapter for planning, executing, and reporting on Arrumo video jobs.

## Icon and trademarks

`icon.svg` uses the official Codex mark, only to identify the service this
plugin connects to. Codex, OpenAI and the OpenAI logo are trademarks of OpenAI. This plugin is not affiliated with or endorsed by
OpenAI, and the mark is not covered by this repository's license.

Copyright © 2026 DEVS AI Unipessoal LDA. Licensed under the [GNU Affero General Public License v3.0](LICENSE).

For custom AI solutions for your company, visit [DEVS AI](https://aidevs.pt).

The manifest declares the provider label, setup guide, and local authentication status command through the Arrumo Plugin SDK. The plugin ID is `codex`.

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
