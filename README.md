# pilotspace/homebrew-tap

Homebrew formulae for PilotSpace tools.

## laya-codex

[laya-codex](https://github.com/pilotspace/laya-codex) gives Claude Code the code a task needs
before it starts, so Claude reads about half as much code.

```sh
brew install pilotspace/tap/laya-codex
# the ~850 MB re-ranker model (macOS; optional, laya-codex ranks by keywords without it)
curl -fsSL https://raw.githubusercontent.com/pilotspace/laya-codex/main/install.sh | sh -s -- --model-only
```

Then enable it in Claude Code, either for every repository at once:

```
/plugin marketplace add pilotspace/laya-codex
/plugin install laya-codex@laya-codex
```

or for a single repository with `laya-codex init --repo /path/to/repo`. Check the setup with
`laya-codex doctor --repo .`.

The formula installs `laya-codex` into `bin` and its Moon search server into `libexec`, so it
doesn't clash with Homebrew's unrelated `moon` formula. The formula is generated from each
release by
[`scripts/update-formula.sh`](https://github.com/pilotspace/laya-codex/blob/main/scripts/update-formula.sh).
