# Personal OpenCode instructions

- Read the relevant repository files before proposing or making changes.
- When the request implies implementation, make the changes directly and carry the task through verification.
- Preserve unrelated user changes. Do not reset, revert, or overwrite work you did not create.
- Prefer existing project patterns, frameworks, scripts, and helper APIs over new abstractions.
- Keep changes narrowly scoped. Avoid unrelated refactors, formatting churn, and speculative features.
- Use `rg` for repository searches and structured parsers or project tools for structured data.
- Before editing, identify the owning module, relevant conventions, and the narrowest useful test or check.
- After meaningful changes, run focused formatters, linters, type checks, or tests appropriate to the affected code.
- Treat credentials, local configuration, symlinks, and destructive commands as sensitive. Do not print or commit secrets.
- Do not use destructive Git commands unless explicitly requested.
- Communicate directly and concisely. Final reports should name changed files, verification performed, and any remaining uncertainty.
