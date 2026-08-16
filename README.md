# hermes-plugin-index

Community plugin index for [Hermes Agent](https://github.com/NousResearch/hermes-agent).

`hermes plugins install <bare-name>` resolves names through this index. `hermes plugins search <term>` searches it. The list here is what `hermes_cli/plugin_index.py` reads.

## Contributing

Open a PR that adds an entry to `index.json`. Minimum fields:

- `name` — the bare name users type after `hermes plugins install`
- `repo` — `owner/repo` on GitHub
- `subdir` — optional path inside the repo, for monorepos hosting multiple plugins

Recommended fields: `description`, `author`, `homepage`, `tags`, `capabilities`.

The schema is defined by `PluginIndexEntry` in [hermes_cli/plugin_index.py](https://github.com/NousResearch/hermes-agent/blob/main/hermes_cli/plugin_index.py).

**Indexed ≠ audited.** Inclusion here is a metadata review only, not a code audit. Review a plugin before enabling it.

## Hosting

This repository is hosted under the [Revell-ai](https://github.com/Revell-ai) org as ecosystem infrastructure. Ownership can transfer to [NousResearch](https://github.com/NousResearch) whenever they'd like it under their org — see NousResearch/hermes-agent#87565 for the conversation.

## License

MIT — see [LICENSE](LICENSE).
