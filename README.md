# cfgs

> My personal editor configurations (EditorConfig, VSCode, Zed, Biome).

## Installation

```bash
# bun/npm/pnpm/yarn
bun add --dev --exact @biomejs/biome git+https://github.com/nndvn/cfgs.git
```

## Usage

### Biome

Add the `extends` array to your project's `biome.jsonc` file:

```jsonc
// <project-root>/biome.jsonc
{
    "$schema": "https://biomejs.dev/schemas/2.0.6/schema.json",
    "extends": ["@nndvn/cfgs/biome"],
    // ...
}
```

Add scripts to your `package.json` if you haven't already:

```json
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

Add `.vscode/extensions.json` file:

```json
// <project-root>/.vscode/extensions.json
{
	"recommendations": [
		"biomejs.biome"
	]
}
```

Add `.vscode/settings.json` file:

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

Add `.zed/settings.json` file:

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

https://biomejs.dev/recipes/continuous-integration/

```bash
biome ci .
```

## Links/Acknowledgements

 - [EditorConfig](https://editorconfig.org/)
 - [VSCode](https://code.visualstudio.com/docs/configure/settings#_workspace-settings)
 - [Zed](https://zed.dev/docs/configuring-zed#settings-files)
 - [Biome](https://biomejs.dev/guides/getting-started/)
 - [Biome extension for VSCode](https://github.com/biomejs/biome-vscode) https://biomejs.dev/reference/vscode/
 - [Biome extension for Zed](https://github.com/biomejs/biome-zed) https://biomejs.dev/reference/zed/

## License

[MIT](https://choosealicense.com/licenses/mit/)
