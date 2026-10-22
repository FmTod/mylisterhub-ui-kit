# MyListerHub UI kit

Everything needed to prototype a screen that looks like [MyListerHub](https://mylisterhub.com),
without access to the app's code. Prototypes are single static HTML files.

| Path | What it is |
| --- | --- |
| [`DESIGN.md`](DESIGN.md) | The design system in plain language: palette, type, components, layout. Also a Google Stitch `DESIGN.md` |
| [`skills/mylisterhub-ui/`](skills/mylisterhub-ui) | An agent skill that builds prototypes from the kit, installable as a plugin (see below) |
| [`skills/mylisterhub-ui/templates/`](skills/mylisterhub-ui/templates) | List, record and settings page templates with the app frame |
| [`skills/mylisterhub-ui/assets/`](skills/mylisterhub-ui/assets) | `tokens.css` (colours, light + dark), `components.css` (`mlh-*` classes), the logo |
| [`skills/mylisterhub-ui/screens/`](skills/mylisterhub-ui/screens) | Screenshots of the real app for comparison |

## Install

| Agent | Install |
| --- | --- |
| Claude Code | `/plugin marketplace add FmTod/mylisterhub-ui-kit`, then `/plugin install mylisterhub-ui@mylisterhub` |
| Codex | `codex plugin marketplace add FmTod/mylisterhub-ui-kit`, then `codex plugin add mylisterhub-ui@mylisterhub` |
| Gemini CLI | `gemini extensions install https://github.com/FmTod/mylisterhub-ui-kit` |
| OpenCode, Cursor and [~80 others](https://github.com/vercel-labs/skills) | `npx skills add FmTod/mylisterhub-ui-kit -a opencode` (or `-a cursor`, …; add `-g` for every project) |
| Anything else | Copy `skills/mylisterhub-ui/` into your agent's skills folder |

Then ask for a screen, e.g. *"Mock up a MyListerHub page for managing return requests"*. The skill
picks a template, fills it in and checks it against the screenshots.

## Use it without an agent

Open any file in `templates/` in a browser, duplicate it and edit the HTML. The moon button toggles
dark mode. `SKILL.md` lists every class and the rules a screen has to follow.

## Use it with Google Stitch

Paste or upload [`DESIGN.md`](DESIGN.md) as the project's design system.

## Fonts

The app's headings use **Bebas Neue Pro**, a licensed font that isn't included here. The kit falls
back to the free [Bebas Neue](https://fonts.google.com/specimen/Bebas+Neue). If you have Bebas Neue
Pro installed locally, the CSS picks it up automatically.

## Keeping in sync

`assets/tokens.css` is generated from the app's theme. Don't edit it here. The app repo's
`scripts/ui-kit-sync` opens a PR in this repo whenever the theme changes.

## License

You may use the kit only to design MyListerHub features. The name, logo and screenshots are reserved.
See [LICENSE](LICENSE).
