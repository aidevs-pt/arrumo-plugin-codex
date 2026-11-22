# Set up Codex in Arrumo

[Español](../es/setup.md) · [Português](../pt/setup.md)

Install and sign in to the local CLI using the [provider setup guide](https://learn.chatgpt.com/docs/codex/cli). Start Arrumo from an environment whose PATH includes the directory containing the CLI executable.

Choose Codex during workspace setup or select it as the production agent in Settings. A sign-in check confirms local authentication. It does not start an edit.

## Check the connection

From the editor CLI, pass a local database path and this plugin ID.

```sh
arrumo-workspaces ./workspaces.sqlite agent-login-status codex
```

A confirmed status means the CLI accepted the sign-in probe. If Arrumo reports unavailable, check that the executable is on the PATH visible to Arrumo. If the login is unconfirmed, sign in using the official guide and check again. A timeout or failure means the probe could not finish successfully.

## Translate subtitle cues

See [Translate subtitles](../../README.md#translate-subtitles) to use this plugin as an Auto-Dubbing translator. The translator sends the selected cue text and target language to Codex. The workflow keeps the original cue timings.

## Make images

Codex can make thumbnails and other images with its built-in image tool, on your ChatGPT plan, so you do not need an OpenAI or Gemini key for them. It appears under **Image generation** in Settings, Services and keys, first by default; move it down to prefer a keyed provider. Arrumo sends the image brief and up to eight style references. Codex stays read-only, and Arrumo collects, checks and crops the image, then removes Codex's copy.
