![cfgs](https://socialify.git.ci/nndvn/cfgs/image?custom_description=My+editor+configurations%3A+EditorConfig%2C+VSCode%2C+Zed%2C+Biome%2C+...&description=1&font=JetBrains+Mono&name=1&owner=1&pattern=Floating+Cogs&theme=Dark)

# @nndvn/cfgs

![github](https://img.shields.io/github/package-json/v/nndvn/cfgs?style=flat-square&logo=github&logoColor=white&color=10069F&label=github)
![license](https://img.shields.io/github/license/nndvn/cfgs?style=flat-square&logo=opensourceinitiative&logoColor=white&color=10069F&label=license)
![biome](https://img.shields.io/npm/v/%40biomejs%2Fbiome?style=flat-square&logo=biome&logoColor=white&color=10069F&label=biome)
![bun](https://img.shields.io/github/v/release/oven-sh/bun?style=flat-square&logo=bun&logoColor=white&color=10069F&label=bun)
![zed](https://img.shields.io/github/v/release/zed-industries/zed?style=flat-square&logo=zedindustries&logoColor=white&color=10069F&label=zed)
![vscode](https://img.shields.io/github/v/release/microsoft/vscode?style=flat-square&logo=vscodium&logoColor=white&color=10069F&label=vscode)
![npm](https://img.shields.io/npm/v/@nndvn/cfgs?style=flat-square&logo=npm&logoColor=white&color=10069F&label=npm)

My editor configurations: EditorConfig, VSCode, Zed, Biome, ...

<details open>
<summary>:book: Table of Contents</summary>

* :rocket: [Installation](#rocket-installation)
* :hammer_and_wrench: [Configuration](#hammer_and_wrench-configuration)
* :gear: [Usage](#gear-usage)
    * [Command-line interface (CLI)](#command-line-interface-cli)
    * [Editor integrations (IDEs)](#editor-integrations-ides)
        * [Visual Studio Code](#visual-studio-code)
        * [Zed](#zed)
    * [Continuous integration (CI)](#continuous-integration-ci)
* :reminder_ribbon: [License](#reminder_ribbon-license)
* :raised_hands: [Acknowledgements](#raised_hands-acknowledgements)

</details>

## :rocket: Installation

> [!IMPORTANT] 
> Install configuration package directly from GitHub repository.

```bash
bun add --dev --exact git+https://github.com/nndvn/cfgs.git
```

## :hammer_and_wrench: Configuration

Add the `extends` array to your `biome.json` file:

```jsonc
// <project-root>/biome.json
{
    "$schema": "https://biomejs.dev/schemas/2.0.6/schema.json",
    "extends": ["@nndvn/cfgs"],
    // ...
}
```

Add `scripts` to your `package.json` if you haven't already:

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

## :gear: Usage

### Command-line interface (CLI)

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

### Editor integrations (IDEs)

#### Visual Studio Code

Add the following extensions to your `.vscode/extensions.json` file:

```jsonc
// <project-root>/.vscode/extensions.json
{
    "recommendations": [
        "biomejs.biome"
    ]
}
```

Add the following settings to your `.vscode/settings.json` file:

```jsonc
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

```jsonc
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

### Continuous integration (CI)

:construction: https://biomejs.dev/recipes/continuous-integration/

## :reminder_ribbon: License

This project is licensed under the [MIT](LICENSE) license.

## :raised_hands: Acknowledgements

 - [EditorConfig](https://editorconfig.org)
 - [VSCode](https://code.visualstudio.com/docs)
 - [Zed](https://zed.dev/docs)
 - [Biome](https://biomejs.dev/guides/getting-started)
