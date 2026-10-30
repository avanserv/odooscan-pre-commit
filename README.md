# odooscan-pre-commit

The [prek](https://github.com/j178/prek) and [pre-commit](https://pre-commit.com) hook for
[odooscan](https://github.com/avanserv/odooscan), the quality and security scanner for Odoo
modules. It installs odooscan's prebuilt wheel from PyPI, so you don't need a Rust toolchain.

```yaml
repos:
  - repo: https://github.com/avanserv/odooscan-pre-commit
    rev: v0.8.0
    hooks:
      - id: odooscan
```

The hook runs `oscn check` on the whole repository whenever a Python, XML or CSV file changes,
since its rules compare modules with each other. Put the addons path, the series and a baseline in
`odooscan.toml` or `[tool.odooscan]`; see odooscan's
[README](https://github.com/avanserv/odooscan#configuration).

This repository holds no code. Each odooscan release updates the pinned version here and tags this
repository with the same version, so `prek autoupdate` picks it up.
