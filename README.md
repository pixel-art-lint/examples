# examples

Sample workspaces for [pixel-art-lint](https://pixelartlint.com). Folder layouts follow common **Kenney** asset pack conventions: promotional `Sample.png` / `Preview.png` at the pack root, optional `Tilemap/` sheet exports, per-sprite PNGs, `License.txt`, `Tilesheet.txt`, and `.url` shortcuts. Each example includes a root **`pixelartlint.ignore`** so those non-sprite images are skipped when you lint the pack.

## Example folders

- **`kenney_tiny-town/`** — Same layout as the CLI test fixture in the main repo: [`cli/test-data/kenney_tiny-town`](https://github.com/pixel-art-lint/pixel-art-lint/tree/main/cli/test-data/kenney_tiny-town). It ships `pixelartlint.toml` (palette rules), individual tiles under `Tiles/`, packed maps under `Tilemap/`, and Kenney metadata. The bundled `pixelartlint.ignore` skips `Sample.png`, `Preview.png`, everything under `Tilemap/` (sheet previews), and `Tiles/tile_0081.png` (semi-transparent pixels outside the documented palette).

## Run the CLI

Install the `pixel-art-lint` binary.

```bash
git clone https://github.com/pixel-art-lint/pixel-art-lint.git
cd pixel-art-lint
cargo install --path cli --locked
```

Lint an example from the pack directory:

```bash
git clone https://github.com/pixel-art-lint/examples.git
cd examples/kenney_tiny-town
pixel-art-lint check .
```

Default behaviour uses the glob `**/*.{png,bmp}` when you pass no extra arguments. To pass globs explicitly:

```bash
pixel-art-lint check . "**/*.{png,bmp}"
```

Use `--verbose` if you need more logging (`SPDLOG_RS_LEVEL` is also supported; see the CLI `--help` text).
