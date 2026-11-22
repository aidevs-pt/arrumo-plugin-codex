# Arrumo Codex Plugin

The Codex agent adapter for planning, executing, and reporting on Arrumo video jobs.

## Icon and trademarks

`icon.svg` is a generic symbol drawn for Arrumo (a terminal prompt, for an agent that works from the command line), covered by this repository's
license. It is not the provider's logo: the provider has not published permission for its
logo to appear in another app's interface, so the plugin does not use it. The name is used
only to say which service the plugin connects to; this plugin is not affiliated with or
endorsed by the provider.

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
