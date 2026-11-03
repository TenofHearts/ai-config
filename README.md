# Codex configuration

Shared Codex CLI preferences with automatic approval review, Vim input mode,
and a status line showing model/reasoning, current directory, Git branch,
remaining context, the 5-hour limit, and the weekly limit.

The dotfiles installer sets up this configuration with:

```sh
./install.sh --only codex
```

Launch with `codex --profile dotfiles`. The profile overrides matching values
in the machine-specific `~/.codex/config.toml`, which stays local. Bash and Zsh
configurations from the dotfiles repository provide an alias to load the profile.

Keep the checkout in place: `~/.codex/dotfiles.config.toml` links to it. Commit
and push shared changes here, then update the submodule reference in dotfiles.
