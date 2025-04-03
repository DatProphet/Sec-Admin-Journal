# 🛠️ Recommended Tools & Configs

This folder includes:
- Tools I frequently use in security and infrastructure work
- Configuration files and templates
- CLI utilities and GUI apps

## Subfolders
- `tool-configs/` – Sample config files
- `recommended-tools.md` – A running list of essential tools
- `scuba/` – [SCUBA Scan Tool](https://github.com/cisagov/ScubaGear) by CISA, added as a Git submodule

## 🔍 SCUBA Scan Tool

[SCUBA](https://github.com/cisagov/ScubaGear) (Security Configuration Benchmark Utility) is a tool developed by CISA to analyze system configurations against established security benchmarks (like CIS Benchmarks).

This project includes SCUBA as a submodule in the `scuba/` folder.

> 🔗 **To view or use the tool**, visit the original repo: [cisagov/ScubaGear](https://github.com/cisagov/ScubaGear)

To clone this repo with the SCUBA tool included:
```bash
git clone --recurse-submodules https://github.com/yourusername/Sec-Admin-Journal.git
