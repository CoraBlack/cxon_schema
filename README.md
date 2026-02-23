# cxon_schema

JSON Schema for cxon build configuration files.

## Usage

Validate a cxon configuration file:

```bash
npx ajv validate -s schema/cxon.schema.json -d schema/cxon.json
```

## Schema Properties

| Property | Type | Description |
|----------|------|-------------|
| `project`     | string | Project name |
| `target_name` | string | Target executable name |
| `target_type` | string | executable, static_lib, shared_lib or object_lib |
| `build_dir`   | string | Build output directory |
| `output_dir`  | string | Output directory |
| `toolchain`   | string | gnu, llvm, or msvc |
| `cc`          | string | Custom C compiler |
| `cxx`         | string | Custom C++ compiler |
| `threads`     | integer | Number of build threads |
| `flags`       | array | Common compiler flags |
| `cflags`      | array | C compiler flags |
| `cxxflags`    | array | C++ compiler flags |
| `include`     | array | Include directories |
| `defines`     | array | Preprocessor defines |
| `sources`     | array | Source files |
| `link`        | array | Directories of libraries to link |
| `libs`        | array | Libraries to link |

## Schema URL

The schema is deployed to GitHub Pages. You can reference it directly in your configuration file or IDE:

```
https://corablack.github.io/cxon_schema/cxon.schema.json
```

For example, in your `cxon.json` file:

```json
{
    "$schema": "https://corablack.github.io/cxon_schema/cxon.schema.json",
    "project": "my_project",
    "target_name": "my_app"
}
```

## Deploy

Push to `main` branch to trigger automatic deployment to GitHub Pages.
