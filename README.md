![@nndvn/cfgs](https://socialify.git.ci/nndvn/cfgs/image?description=1&font=Inter&name=1&owner=1&pattern=Floating+Cogs&theme=Dark)

# @nndvn/cfgs

![github](https://img.shields.io/github/package-json/v/nndvn/cfgs?style=flat-square&logo=github&logoColor=white&color=10069F&label=github)
![license](https://img.shields.io/github/license/nndvn/cfgs?style=flat-square&logo=opensourceinitiative&logoColor=white&color=10069F&label=license)
![biome](https://img.shields.io/npm/v/%40biomejs%2Fbiome?style=flat-square&logo=biome&logoColor=white&color=10069F&label=biome)
![bun](https://img.shields.io/github/v/release/oven-sh/bun?style=flat-square&logo=bun&logoColor=white&color=10069F&label=bun)
![zed](https://img.shields.io/github/v/release/zed-industries/zed?style=flat-square&logo=zedindustries&logoColor=white&color=10069F&label=zed)
![vscode](https://img.shields.io/github/v/release/microsoft/vscode?style=flat-square&logo=vscodium&logoColor=white&color=10069F&label=vscode)
![npm](https://img.shields.io/npm/v/@nndvn/cfgs?style=flat-square&logo=npm&logoColor=white&color=10069F&label=npm)

My editor configurations: biome, editorconfig, vscode, zed,...

<details open>
<summary>:book: Table of Contents</summary>

* 🛠️ [Installation](#-installation)
    * 1. [Install package](#install-package)
    * 2. [Install package](#install-package)
* ⚙️ [Usage](#-usage)
    * 1. [Biome](#biome)
    * 2. [Zed](#zed)
    * 3. [EditorConfig](#editorconfig)
    * 4. [VSCode](#vscode)
* 🎗[License](#-license)
* 🙌 [Acknowledgements](#-acknowledgements)

</details>

## 🛠️ Installation

### 1. Install package

> [!WARNING]
> This repository is not distributed as a package; please install it directly from the GitHub repository.
> This repository isn't available as a traditional package. To use it, you'll need to install it directly from GitHub repository.

:warning: **Note:** install package from github

```bash
bun add --dev --exact git+https://github.com/nndvn/cfgs.git
```

### 2. Install package

`WIP`

## ⚙️ Usage

### Biome

Add the following to your `<project-root>/biome.json` file:

<!-- Add the `extends` array to your project's `biome.json` file: -->

```jsonc
{
    "$schema": "https://biomejs.dev/schemas/2.0.6/schema.json",
    "extends": ["@nndvn/cfgs"],
    // ...
}
```

Add scripts to your `<project-root>/package.json` if you haven't already:

```jsonc
{
    //...
    "scripts": {
        "format": "biome format .",
        "format:fix": "biome format --write .",
        "lint": "biome lint .",
        "lint:fix": "biome lint  --write .",
        "check": "biome check .",
        "check:fix": "biome check --write ."
    },
    // ...
}
```

### Command-line interface

```bash
# Format all files
bunx biome format --write

# Format specific files
bunx biome format --write <files>

# Lint and apply safe fixes to all files
bunx biome lint --write

# Lint files and apply safe fixes to specific files
bunx biome lint --write <files>

# Format, lint, and organize imports of all files
bunx biome check --write

# Format, lint, and organize imports of specific files
bunx biome check --write <files>
```

### Editor integrations/IDEs

#### Visual Studio Code

Add the following extensions to your `.vscode/extensions.json` file:

```json
// <project-root>/.vscode/extensions.json
{
    "recommendations": [
        "biomejs.biome"
    ]
}
```

Add the following settings to your `.vscode/settings.json` file:

```json
// <project-root>/.vscode/settings.json
{
    "[javascript][typescript][json]": {
        "editor.defaultFormatter": "biomejs.biome",
        "editor.formatOnPaste": true,
        "editor.formatOnSave": true,
        "editor.codeActionsOnSave": {
            "source.fixAll.biome": "explicit",
            "source.organizeImports.biome": "explicit"
        }
    }
}
```

#### Zed

Add the following settings to your `.zed/settings.json` file:

```json
// <project-root>/.zed/settings.json
{
    "auto_install_extensions": {
        "biome": true
    },
    "file_types": {
        "Shell Script": [".editorconfig"]
    },
    "formatter": {
        "language_server": {
            "name": "biome"
        }
    },
    "code_actions_on_format": {
        "source.organizeImports.biome": true,
        "source.fixAll.biome": true
    }
}
```

### Continuous Integration 

:construction: https://biomejs.dev/recipes/continuous-integration/

```bash
biome ci .
```

## 🎗 License

This project is licensed under the [MIT](LICENSE) license.

## 🙌 Acknowledgements

 - [EditorConfig](https://editorconfig.org/)
 - [VSCode](https://code.visualstudio.com/docs/configure/settings#_workspace-settings)
 - [Zed](https://zed.dev/docs/configuring-zed#settings-files)
 - [Biome](https://biomejs.dev/guides/getting-started/)
 - [Biome extension for VSCode](https://github.com/biomejs/biome-vscode) https://biomejs.dev/reference/vscode/
 - [Biome extension for Zed](https://github.com/biomejs/biome-zed) https://biomejs.dev/reference/zed/
