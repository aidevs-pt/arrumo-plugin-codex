<p align="center">
  <img src="icon.svg" width="88" height="88" alt="">
</p>

<h1 align="center">Codex for Arrumo AI Video Editor</h1>

<p align="center">Use Codex as the agent that writes, designs and cuts your videos in Arrumo, and make thumbnails with its image tool, on your ChatGPT plan.</p>

<p align="center">
  <a href="LICENSE"><img alt="License: AGPL-3.0" src="https://img.shields.io/badge/license-AGPL--3.0-2337B4"></a>
  <img alt="Bundled with Arrumo" src="https://img.shields.io/badge/bundled%20with-Arrumo-2337B4">
  <a href="https://www.aidevs.pt/tools/arrumo/docs/plugins/codex/setup"><img alt="Docs in English, Spanish and Portuguese" src="https://img.shields.io/badge/docs-EN%20%C2%B7%20ES%20%C2%B7%20PT-111"></a>
</p>

This plugin ships with [Arrumo AI Video Editor](https://github.com/aidevs-pt/arrumo-video-editor), the free, open-source desktop app where an AI agent writes, designs, voices and cuts your videos and you approve every step. It comes installed with Arrumo; turn it on or off in **Settings › Plugins**.

## Guides

- **Set up Codex**: [English](https://www.aidevs.pt/tools/arrumo/docs/plugins/codex/setup) · [Español](https://www.aidevs.pt/es/tools/arrumo/docs/plugins/codex/setup) · [Português](https://www.aidevs.pt/pt/tools/arrumo/docs/plugins/codex/setup)

## Translate subtitles

`tools/translate-subtitles.py` implements the Auto-Dubbing local translator
interface. Select this executable with Auto-Dubbing's `--translator` option
or with its standalone subtitle translation command. It uses the local Codex
login and sends the selected cue text and target language to the provider.

The adapter runs `codex exec` in a temporary directory with a structured
output schema. It uses a read-only sandbox, disables the shell, plugins and
web search, and skips user configuration while retaining Codex authentication.
The adapter validates cue coverage before returning the translated text.

## Plan usage

The manifest's `usageRun` (schema 11) starts `codex app-server` and asks
`account/rateLimits/read`, which reports how much of each ChatGPT plan window is
used without spending it. Arrumo shows the most used window, such as the weekly
limit, in Settings › Services and keys and warns at 20% and 10% left.

## Icon and trademarks

`icon.svg` shows OpenAI's logo so creators recognise the service this plugin connects to. Codex, OpenAI and the OpenAI logo are trademarks of OpenAI; the manifest's `iconNotice` says so wherever Arrumo shows the icon. The logo is not covered by this repository's license, and this plugin is not affiliated with or endorsed by OpenAI. The SVG is a square without rounded corners; Arrumo rounds it. If OpenAI asks, replace the logo with a generic symbol and remove `iconNotice`.

## Contributing

Contributions are welcome: read [CONTRIBUTING.md](CONTRIBUTING.md) and our [Code of Conduct](CODE_OF_CONDUCT.md). Report security problems privately as described in [SECURITY.md](SECURITY.md).

## License

Copyright © 2026 DEVS AI Unipessoal LDA. Licensed under the [GNU Affero General Public License v3.0](LICENSE). Built by [DEVS AI](https://aidevs.pt), who make custom AI solutions for companies.
