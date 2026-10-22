# MyListerHub UI kit

Everything needed to prototype a screen that looks like [MyListerHub](https://mylisterhub.com),
without access to the app's code. Prototypes are single static HTML files.

| Path | What it is |
| --- | --- |
| [`skills/mylisterhub-ui/`](skills/mylisterhub-ui) | An agent skill (Claude Code and compatible tools) that builds prototypes from the kit |
| [`skills/mylisterhub-ui/DESIGN.md`](skills/mylisterhub-ui/DESIGN.md) | The design system in plain language, also usable as a Google Stitch `DESIGN.md` |
| [`skills/mylisterhub-ui/templates/`](skills/mylisterhub-ui/templates) | List, record and settings page templates with the app frame |
| [`skills/mylisterhub-ui/assets/`](skills/mylisterhub-ui/assets) | `tokens.css` (colours, light + dark), `components.css` (`mlh-*` classes), the logo |
| [`skills/mylisterhub-ui/screens/`](skills/mylisterhub-ui/screens) | Screenshots of the real app for comparison |

## Use it with Claude Code

```bash
git clone https://github.com/FmTod/mylisterhub-ui-kit.git
cp -r mylisterhub-ui-kit/skills/mylisterhub-ui ~/.claude/skills/
```

Then ask for a screen, e.g. *"Mock up a MyListerHub page for managing return requests"*. The skill
picks a template, fills it in and checks it against the screenshots.

## Use it without an agent

Open any file in `templates/` in a browser, duplicate it and edit the HTML. The moon button toggles
dark mode. `SKILL.md` lists every class and the rules a screen has to follow.

## Use it with Google Stitch

Paste or upload `skills/mylisterhub-ui/DESIGN.md` as the project's design system.

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
