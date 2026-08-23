# Miri Language Support for VS Code

This is the official Visual Studio Code extension for the [Miri programming language](https://github.com/miri-lang/miri). It provides syntax highlighting and basic support for Miri source files (`.mi`).

## Features

- **Syntax Highlighting**: Comprehensive coloring for Miri keywords, types, strings, comments, and numbers.
- **GPU Support**: Highlighting for GPU compute — `gpu fn` kernels, `forall` / `gpu forall` parallel launches, `gpu let` / `gpu var` residency bindings, the `host` residency modifier, `frame.*` per-frame inputs, thread builtins (`global_idx`, `thread_idx`, `block_idx`, `barrier`), `Vec2`/`Vec3`/`Vec4` types, and vector/math intrinsics (`dot`, `cross`, `normalize`, `mix`, `clamp`, `smoothstep`, ...).
- **Attributes**: Highlighting for the closed attribute set — `@test`, `@ignore`, `@xfail`, `@must_use`, `@non_exhaustive`, `@deprecated`. Because the set is closed in the language, an unrecognised attribute is highlighted as an error rather than silently coloured like a working one.
- **Standard Library**: Regex literals (`re"^\d+$"i`), static class members (`public static fn`), and the modules added in 0.6.0-beta.4 — `system.text`, `system.json`, `system.fs`, `system.os`, `system.time`, `system.collections.queue` and `system.collections.stack`.
- **Language Configuration**: Basic auto-closing pairs and indentation rules.

## Installation

You can install this extension directly from the VS Code Marketplace (search for "Miri Language") or build it from source.

### Example Code

```miri
use system.io
use system.testing

fn main()
    let x int = 10
    let message = f"Value is {x}"
    println(message)

@test
fn value_is_ten()
    assert_eq(10, 10)
```

### GPU Example

```miri
gpu fn scale(out data list[f32], factor f32)
    data[global_idx] *= factor

fn main()
    var buffer = List<f32>()
    gpu forall i in 0..1024
        buffer[i] = mix(0.0, 1.0, fract(frame.time))
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
