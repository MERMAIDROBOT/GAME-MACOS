# Superseded — use MERMAIDROBOT/GAME

The macOS target has moved into the [single PS2 Port Lab repository](https://github.com/MERMAIDROBOT/GAME), under `platforms/macos/`.

Clone GAME once. Use `python3 run.py` for PS2 → C++ or `python3 run.py --target macos` for the optional macOS workflow. Future device adapters belong in the same repository. Shared fixes and platform changes now use one PR stream and CI from the same commit; no submodule or repository synchronization is needed.

This repository is retained only for its history. Submit issues and contributions to GAME. Its old adapter, submodule and scheduled workflows have been removed from the current branch. The engine remains experimental; see GAME's README for current capabilities and limitations.
