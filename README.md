# hermes-plugin-index

Community plugin index for [Hermes Agent](https://github.com/NousResearch/hermes-agent).

`hermes plugins install <bare-name>` resolves names through this index. `hermes plugins search <term>` searches it. The list here is what `hermes_cli/plugin_index.py` reads.

## Pointing your client here

Bare-name resolution reads whichever index the client is configured with. To use
this one, add to `~/.hermes/config.yaml`:

```yaml
plugins:
  index_url: https://raw.githubusercontent.com/Revell-ai/hermes-plugin-index/main/index.json
```

Full identifiers need no configuration:

```console
$ hermes plugins install Revell-ai/revell-onyx
```

## Contributing

Open a PR that adds an entry to `index.json`. Minimum fields:

- `name` — the bare name users type after `hermes plugins install`
- `repo` — `owner/repo` on GitHub
- `ref` — **a full 40-character commit SHA.** Not a branch, not a tag
- `subdir` — optional path inside the repo, for monorepos hosting multiple plugins

Recommended fields: `description`, `author`, `homepage`, `tags`, `capabilities`.

`ref` is a full SHA because a branch or tag can be moved after review. A commit
cannot. What was reviewed is what installs.

### House rules

- **List a plugin you own or maintain.** Not someone else's repo.
- **One plugin per PR.**
- **Only the listing author edits their own entry.**
- Entries may be removed if the repo disappears, goes private, or is reported
  malicious.

### Reporting a plugin problem

Open it on that plugin's own repo, not here. This index carries metadata; it
does not host the code and cannot fix it.

The schema is defined by `PluginIndexEntry` in [hermes_cli/plugin_index.py](https://github.com/NousResearch/hermes-agent/blob/main/hermes_cli/plugin_index.py).

**Indexed ≠ audited.** Inclusion here is a metadata review only, not a code audit. Review a plugin before enabling it.

## Hosting

This repository is hosted under the [Revell-ai](https://github.com/Revell-ai) org as ecosystem infrastructure. Ownership can transfer to [NousResearch](https://github.com/NousResearch) whenever they'd like it under their org — see NousResearch/hermes-agent#87565 for the conversation.

## License

MIT — see [LICENSE](LICENSE).
