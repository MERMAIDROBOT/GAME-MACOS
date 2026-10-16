# PS2 Port Lab — macOS adapter

Optional macOS target for the open-source [PS2-to-C++ core](https://github.com/MERMAIDROBOT/GAME).
The compiler and growing knowledge bank live in GAME; this repository pins and
reuses that implementation instead of maintaining a competing copy.

**Experimental foundation:** the existing native build commands do not yet
reconstruct every feature of the private accepted first-title v56 application.
Translation is not recovery of original C++ source or proof of playability.
No retail assets, game binaries, generated game code or BIOS are included.

## Setup

Requires macOS, Python 3.11+, Git and Apple Command Line Tools.

```sh
git clone --recurse-submodules https://github.com/MERMAIDROBOT/GAME-MACOS.git
cd GAME-MACOS
python3 -m pip install -r core/requirements.txt
python3 macos_adapter.py --help
python3 macos_adapter.py doctor
```

Use `python3 macos_adapter.py --profile /absolute/local/profile.json COMMAND`
for native stages. Follow `core/NEXT-GAME.md` for intake and translation. Original
game data, generated sources, saves and diagnostics stay local and out of Git.

## Shared improvements and other devices

Shared compiler/runtime contracts belong in GAME. macOS-specific adapter work
belongs here. Future C++-to-device adapters can implement the same core API;
see [the platform contract](https://github.com/MERMAIDROBOT/GAME/blob/main/PLATFORMS.md).
The current macOS shim still calls experimental native internals in core;
extracting those internals into this repository remains future consolidation.

CI checks both the pinned core and its latest main revision. Compatibility is
rechecked every six hours. Dependabot checks the submodule daily and proposes
core updates; PRs require review/merge. Updates are not instant or auto-merged.
Core PR checks also exercise the latest macOS adapter. No cross-repository write
credential is needed. Shared changes discovered here should be contributed to
GAME first, so every platform benefits from the same reviewed fix.

## Contributing

Contribute synthetic reproducers, platform ABI/device implementations, conformance
checks and build/packaging improvements. Contribute game-independent lessons as
reviewed rules plus regression fixtures in GAME. Never submit retail-derived
code/assets, binaries, screenshots or raw traces. Both projects use GPL-3.0;
upstream dependency/model licenses remain separate. See core/CONTRIBUTING.md.
