# pi-inline-skills (fork)

Fork of [`@tifan/pi-inline-skills`](https://github.com/tifandotme/pi-extensions/tree/2bc1fd1/packages/pi-inline-skills) 1.0.7 (upstream commit `2bc1fd1`). MIT licensed; the original copyright notice is retained in [LICENSE](LICENSE). This fork is not affiliated with the upstream author.

Load skills from inside a pi prompt.

Type `/` and part of a skill name, pick a skill, then keep writing. On submit, the prompt stays unchanged and the matching skill content is loaded for that turn.

![Inline skill autocomplete picker](https://raw.githubusercontent.com/tifandotme/pi-extensions/refs/heads/master/packages/pi-inline-skills/assets/skills-selector-triggered-inline.webp)

## Changes from upstream

- Inline slash-skill completion triggers on Pi 1.4, which inserts typed characters through `Editor.insertCharacter`. The guarded trigger is installed on both `insertCharacter` and `handleInput`.
- Host packages are declared as `peerDependencies`.
- Standalone `tsconfig.json` and `.gitignore`; no monorepo tooling.

## Install

```bash
pi install https://github.com/111inhistory/pi-inline-skills
```

The npm package `@tifan/pi-inline-skills` is the upstream release and does not contain these fixes.

## Usage

```text
let's /tdd this and /review when done
```

This loads `tdd` and `review` behind the scenes. Slash tokens stay in the visible prompt, so rewinding and editing previous prompts is easy.

Notes:

- Already-loaded skills are not injected again on the same session branch.
- Skills with `disable-model-invocation: true` work because this extension reads skill files directly.
- A registered pi command wins at the start of a prompt. Otherwise, a starting token like `/tdd` is treated as an inline skill.

## Commands

- `/loaded-skills`: List skills loaded in the current session.

![Loaded skills command output](https://raw.githubusercontent.com/tifandotme/pi-extensions/refs/heads/master/packages/pi-inline-skills/assets/loaded-skills-output.webp)

## Release notes

See [CHANGELOG.md](https://github.com/tifandotme/pi-extensions/blob/master/packages/pi-inline-skills/CHANGELOG.md)

## License

MIT. The original copyright notice is retained in [LICENSE](LICENSE).
