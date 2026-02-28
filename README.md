# Miri Language Support for VS Code

This is the official Visual Studio Code extension for the [Miri programming language](https://github.com/miri-lang/miri). It provides syntax highlighting and basic support for Miri source files (`.mi`).

## Features

- **Syntax Highlighting**: Comprehensive coloring for Miri keywords, types, strings, comments, and numbers.
- **Language Configuration**: Basic auto-closing pairs and indentation rules.

## Installation

You can install this extension directly from the VS Code Marketplace (search for "Miri Language") or build it from source.

### Example Code

```miri
use system.io

fn main()
    let x int = 10
    let message = f"Value is {x}"
    println(message)
```

## Contributing

To contribute to this extension or the Miri language compiler itself, please visit the [Extension GitHub Repository](https://github.com/miri-lang/vsc-extension).

### Local Development

1. Clone the repository: `git clone https://github.com/miri-lang/vsc-extension.git`
2. Navigate to the extension folder: `cd vsc-extension`
3. Install dependencies: `npm install`
4. Open the folder in VS Code and press `F5` to start debugging.

## License

[Apache-2.0](LICENSE)
