# AI agent configuration

## Codex

Run `cx` (or `codex --profile dotfiles`) to use the [shared profile](codex/dotfiles.config.toml).
Run `codex` for your usual defaults. Keep machine-specific settings such as
project trust and local paths in `~/.codex/config.toml`.

## OpenCode

Run `oc` to start a private server with the [shared configuration](opencode/dotfiles.config.json).
Plain `opencode` uses its usual server settings. Both use the linked
[terminal settings](opencode/cli.json).

Keep the gateway key in `~/.config/opencode/thirdparty.key`, outside Git. Restrict
access with `chmod 600 ~/.config/opencode/thirdparty.key`. The configured gateway
uses HTTP; use it only over a trusted, protected connection.
