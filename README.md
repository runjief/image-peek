[English](README.md) | [Suomi](README.fi.md)

# image-peek

A VS Code extension for personal use. Hover over a line containing Base64 image data to preview the image without saving it to a file first.

Supports the `data:image/...;base64,...` format. Works in any file type.

## Main files

| File | Purpose |
| --- | --- |
| `src/extension.ts` | Extension entry point: reads the hovered line, finds image data, and displays a hover preview. |
| `sample.txt` | Sample image data for checking previews manually. |
| `package.json` | Extension metadata, dependencies, and build commands. |
| `.vscode/launch.json`, `.vscode/tasks.json` | Local debugging and automatic builds during development. |
| `src/test/` | Extension test entry points and basic sample tests. |

## How it works

Hover over text → Read the current line → Find Base64 image data → Display an image preview.

Keep each image's data on a separate line. Multiple images on the same line may not preview correctly.

## Local use

Install Node.js, pnpm 7, and VS Code.

```sh
git clone https://github.com/runjief/image-peek.git
cd image-peek
pnpm install --frozen-lockfile
pnpm run build
```

Open the project in VS Code and press `F5` to launch the Extension Development Host. Open `sample.txt` in that window and hover over a line containing image data to see the preview.

## Checks and tests

```sh
pnpm run compile
pnpm run lint
pnpm test
```

`pnpm test` runs the first two automatically. The test command downloads and launches a VS Code test environment. The current tests are basic samples; image previews need to be checked manually.
