# understand-outputs

Climb an output ladder so a result is easier to oversee: ASD-STE100 writing, then a diagram, then an HTML page, then an explainer video.

The skill follows the [Agent Skills specification](https://agentskills.io/specification). The folder name matches the `name` in `SKILL.md`.

## Install

Install it for your user, on each agent the [skills CLI](https://github.com/vercel-labs/skills) finds:

```bash
npx skills add edogbeatz/understand-outputs -g
```

Omit `-g` to install it into the current project only.

## What you get

```
skills/understand-outputs/
├── SKILL.md
├── references/ste.md
└── assets/ladder.html
```

`references/ste.md` is the working subset of ASD-STE100 rules. `assets/ladder.html` is a page you can open in a browser. It marks a sentence against that subset.

An explainer video is made on [ngram](https://www.ngram.com/). The agent shows the brief and waits for a yes before it creates the video.

## License

MIT
