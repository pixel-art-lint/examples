# examples

Sample workspaces for [pixel-art-lint](https://pixelartlint.com) or [itch.io](https://jilminator.itch.io/pixel-art-linter)

## Example folders

- `aseprite/Sprite-OneWrong.aseprite` Has an invalid pixel on Layer 1, Frame 2 at 1,1
- `kenney_tiny-town/` Same layout as the CLI test fixture in the main repo: [`cli/test-data/kenney_tiny-town`](https://github.com/pixel-art-lint/pixel-art-lint/tree/main/cli/test-data/kenney_tiny-town). It ships `pixelartlint.toml` (palette rules), individual tiles under `Tiles/`, packed maps under `Tilemap/`, and Kenney metadata. The bundled `pixelartlint.ignore` skips `Sample.png`, `Preview.png` and everything under `Tilemap/` (sheet previews).

## Run the CLI

[Download](https://pixelartlint.com/download) the `pixel-art-lint` binary and add it to your path.

Lint an example from the pack directory:

```bash
git clone https://github.com/pixel-art-lint/examples.git
cd examples
pixel-art-lint check .
```

Default behaviour uses the glob `**/*.{aseprite,png,bmp}` when you pass no extra arguments. To pass globs explicitly:

```bash
pixel-art-lint check . "**/*.{aseprite,png}"
```

Use `--verbose` if you need more logging (`SPDLOG_RS_LEVEL` is also supported; see the CLI `--help` text).
