# @nndvn/cfgs

![version](https://img.shields.io/github/package-json/v/nndvn/cfgs?style=default&logo=git&logoColor=white&color=0080ff&label=version)
![license](https://img.shields.io/github/license/nndvn/cfgs?logo=opensourceinitiative&logoColor=white&color=0080ff&label=license)
![biome](https://img.shields.io/npm/v/%40biomejs%2Fbiome?logo=biome&logoColor=white&color=0080ff&label=biome)
![bun](https://img.shields.io/github/v/release/oven-sh/bun?logo=bun&logoColor=white&color=0080ff&label=bun)
![zed](https://img.shields.io/github/v/release/zed-industries/zed?style=default&logo=zedindustries&logoColor=white&color=0080ff&label=zed)
![vscode](https://img.shields.io/github/v/release/microsoft/vscode?style=flat-square&logo=vscodium&logoColor=white&color=0080ff&label=vscode)

My personal editor configurations: VSCode, Zed, Biome, EditorConfig,...

<details open>
<summary>:book: Table of Contents</summary>

* :hammer_and_pick: [Installation](#hammer_and_pick-installation)
    * 1. [Install package](#install-package)
    * 2. [Install package](#install-package)
* :gear: [Usage](#gear-usage)
    * 1. [Biome](#biome)
    * 2. [Zed](#zed)
    * 3. [EditorConfig](#editorconfig)
    * 4. [VSCode](#vscode)
* :shield:[License](#shield-license)
* :raised_hands: [Acknowledgements](#-acknowledgements)

</details>

## :hammer_and_pick: Installation

> [!WARNING]
> This repository is not distributed as a package

### 1. Install package

:warning: **Note:** install package from github

```bash
bun add --dev --exact git+https://github.com/nndvn/cfgs.git # @nndvn/cfgs
```

### 2. Install package

`WIP`

## :gear: Usage

### Biome

Add the `extends` array to your project's `biome.json` file:

```jsonc
// <project-root>/biome.jsonc
{
    "$schema": "https://biomejs.dev/schemas/2.0.6/schema.json",
    "extends": ["@nndvn/cfgs"],
    // ...
}
```

Add scripts to your `package.json` if you haven't already:

```jsonc
// <project-root>/package.json
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

## :shield: License

This project is licensed under the [MIT](LICENSE) license.

## :raised_hands: Acknowledgements

 - [EditorConfig](https://editorconfig.org/)
 - [VSCode](https://code.visualstudio.com/docs/configure/settings#_workspace-settings)
 - [Zed](https://zed.dev/docs/configuring-zed#settings-files)
 - [Biome](https://biomejs.dev/guides/getting-started/)
 - [Biome extension for VSCode](https://github.com/biomejs/biome-vscode) https://biomejs.dev/reference/vscode/
 - [Biome extension for Zed](https://github.com/biomejs/biome-zed) https://biomejs.dev/reference/zed/
