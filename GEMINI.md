# Magpie - Project Instructions

Magpie is a lightweight window upscaling tool for Windows 10/11, equipped with various efficient scaling algorithms and filters. It is built using WinUI and C++/WinRT, leveraging DirectX 11 for high-performance graphics processing.

## Project Overview

- **Main Technologies:** C++, HLSL, WinUI 2, C++/WinRT, DirectX 11.
- **Architecture:**
    - `src/Magpie`: Main WinUI-based user interface and application logic.
    - `src/Magpie.Core`: Core engine for window capture, processing, and scaling.
    - `src/Effects`: Collection of scaling algorithms and filters implemented as HLSL shaders.
    - `src/TouchHelper`: Utility to support touch input in upscaled windows.
    - `src/Shared`: Common utilities and shared code across the solution.
    - `src/Updater`: Component for handling application updates.
- **Target Platform:** Windows 10 v1903 (Build 18362) or newer.

## Building and Running

### Prerequisites

- **Visual Studio 2022:** Install "Desktop development with C++" and "Universal Windows Platform development" workloads.
- **Windows SDK:** Version 10.0.22621.0 or newer.
- **CMake:** Required for some dependencies.
- **Python 3.11+:** For build and release scripts.
- **Conan:** C/C++ package manager.
  ```powershell
  pip install conan
  ```

### Key Commands

- **Build Solution:** Open `Magpie.sln` in Visual Studio 2022 and perform a standard build.
- **Publish Release:** Use the provided python script for automated release builds, which handles versioning, compilation, and optional signing.
  ```powershell
  python scripts/publish.py --compiler MSVC --platform x64 --pfx-path <path> --pfx-password <password>
  ```
- **Clean:** Use Visual Studio's "Clean Solution" or manually delete `bin/` and `obj/` directories.

## Development Conventions

### Coding Style

- **Indentation:** Use **Tabs** for indentation.
- **Braces:** Use K&R style (braces on the same line for `if`, `for`, `while`, and functions).
- **Encoding:** Files must be encoded in **UTF-8 without BOM**.
- **Comments:** Prefer single-line comments (`//`) over block comments.
- **Naming Conventions:**
    - `ClassName`: PascalCase for classes.
    - `_mMemberName`: Prefix private member variables with `_m`.
    - `_PrivateMethod`: Prefix private methods with an underscore.
- **XAML Formatting:** Use [XamlStyler](https://github.com/Xavalon/XamlStyler) with the project's `Settings.XamlStyler` configuration.

### Git Conventions

- **Branching:** Merge new features and bug fixes into the `dev` branch. The `main` branch is reserved for stable releases.
- **Commit Messages:** Follow standard Git commit message styles (concise, imperative mood).

## Documentation

- **Wiki:** The project wiki is automatically generated from the `docs/` folder.
- **Localization:** Managed via [Weblate](https://hosted.weblate.org/projects/magpie).
