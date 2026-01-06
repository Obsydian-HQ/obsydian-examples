# Obsidian Examples

Official example applications demonstrating the Obsidian Framework capabilities.

## Overview

This repository contains example applications that showcase various features of the Obsidian Framework. Each example is a standalone application that demonstrates specific functionality.

## Examples

| Example | Description |
|---------|-------------|
| `hello_world` | Minimal app demonstrating basic Obsidian usage |
| `ui_showcase` | Comprehensive UI components demonstration |
| `layout_showcase` | Layout system and constraints examples |
| `router_basic` | Basic file-based routing |
| `router_dynamic` | Dynamic routes with parameters |
| `router_nested` | Nested layouts and routes |
| `router_complete` | Complete routing features |
| `router_patterns` | Advanced routing patterns |
| `sidebar_showcase` | Sidebar navigation component |
| `sidebar_with_router` | Sidebar integrated with router |
| `splitview_showcase` | Split view layouts |
| `textview_showcase` | Text view and editing |
| `zstack_showcase` | Z-axis stacking layouts |
| `system_showcase` | System APIs (processes, etc.) |

## Prerequisites

- Bazel 8.1.0 or later
- Xcode 15+ (for macOS/iOS examples)
- Obsidian Framework (see setup below)

## Setup

### Using Local Obsidian Framework (Development)

The `MODULE.bazel` is configured to use the local Obsidian framework by default:

```bazel
local_path_override(
    module_name = "obsidian",
    path = "../obsydian",
)
```

Ensure the `obsydian` repository is located at `../obsydian` relative to this repository.

### Using Released Obsidian Framework

To use a released version, comment out the `local_path_override` in `MODULE.bazel` and ensure the Obsidian module is available in your Bazel registry.

## Building Examples

### Build All Examples

```bash
bazel build //examples/...
```

### Build Specific Example

```bash
bazel build //examples/hello_world:hello_world_app
```

### Run Example (macOS)

```bash
bazel run //examples/hello_world:hello_world_app
```

Or open the built `.app` bundle:

```bash
bazel build //examples/hello_world:hello_world_app
open bazel-bin/examples/hello_world/hello_world_app.app
```

## Directory Structure

```
obsydian-examples/
├── MODULE.bazel          # Bazel module configuration
├── BUILD                 # Root BUILD file
├── README.md             # This file
├── .bazelversion         # Bazel version pin
└── examples/
    ├── BUILD             # Examples package BUILD
    ├── hello_world/      # Basic example
    ├── ui_showcase/      # UI components
    ├── router_*/         # Routing examples
    └── ...               # Other examples
```

## Contributing

See the main [Obsidian Framework](https://github.com/Obsydian-HQ/obsydian) repository for contribution guidelines.

## License

See LICENSE file for details.
