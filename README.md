# AI agent configuration

Shared configuration for AI agents, organized into one directory per agent.
Install each agent separately; this repository contains configuration only.

## Agents

| Agent | Configuration | Setup |
| --- | --- | --- |
| Codex | `codex/dotfiles.config.toml` | [Codex setup](#codex-setup) |

Keep each agent’s shared configuration in its own directory.
Machine-specific settings, credentials, and sessions stay in the agent’s local
configuration directory.

## Dotfiles integration

The [dotfiles repository](https://github.com/TenofHearts/dotfiles) includes this
repository as the `config/ai` submodule. Run `./install.sh --only codex` from
that repository to link `codex/dotfiles.config.toml` into
`~/.codex/dotfiles.config.toml`. Use `--force` to replace an existing link after
a layout change, or `--dry-run` to preview the operation.

## Codex setup

Install Git and Codex CLI separately. The shared profile works on Windows,
macOS, and Linux. It enables automatic approval review, Vim input mode, and a
status line with model, reasoning, directory, Git branch, context, and usage limits.

Clone this repository and copy the profile into your Codex configuration directory.
These commands respect `CODEX_HOME` when set and otherwise use `~/.codex`.
They copy only the shared profile; your local `config.toml` stays separate.

### macOS and Linux

```sh
git clone https://github.com/TenofHearts/ai-config.git "$HOME/ai-config"
codex_config_dir="${CODEX_HOME:-$HOME/.codex}"
mkdir -p "$codex_config_dir"
cp "$HOME/ai-config/codex/dotfiles.config.toml" "$codex_config_dir/dotfiles.config.toml"
```

### Windows (PowerShell)

```powershell
git clone https://github.com/TenofHearts/ai-config.git "$HOME/ai-config"
$codexConfigDir = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $HOME ".codex" }
New-Item -ItemType Directory -Force -Path $codexConfigDir | Out-Null
Copy-Item "$HOME/ai-config/codex/dotfiles.config.toml" (Join-Path $codexConfigDir "dotfiles.config.toml")
```

### Usage

Start Codex with the shared profile:

```sh
codex --profile dotfiles
```

The profile overrides matching values in your local `config.toml`. Keep
machine-specific settings such as project trust, providers, and local paths in
that file. Run `codex` without the profile flag to use your usual defaults.

### Updates

Run `git pull` inside the clone, then repeat your platform’s copy command to
refresh the installed profile. Restart Codex to load the updated settings.
To share changes, edit `codex/dotfiles.config.toml` in the clone, commit, and push.
