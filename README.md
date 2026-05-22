# fs-skills

Furkan's catalog of [Claude Code](https://code.claude.com/docs) skills for SAP development.

## Install

```shell
/plugin marketplace add sonmezfurkan/fs-skills
/plugin install fiori-design@fs-skills
```

Then run `/reload-plugins` (or restart Claude Code).

## Skills

### `fiori-design`

Aligns **freestyle SAPUI5/OpenUI5** development with the [SAP Fiori Design Guidelines](https://www.sap.com/design-system/fiori-design-web) — floorplans, layout & spacing, Horizon theming, accessibility, and UI text.

It's **model-invoked**: once installed, Claude applies it automatically when you build or review hand-written UI5. (Fiori Elements apps already enforce these conventions, so the skill stays out of the way there.)

## Develop locally

Load the plugin straight from disk, no install required:

```shell
claude --plugin-dir ./plugins/fiori-design
```

Validate before pushing:

```shell
claude plugin validate .
```

## License

MIT
