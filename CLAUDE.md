---

# Edit Text Editor - Project Context

## Project Overview
**Edit** is a terminal-based text editor written in Rust, inspired by MS-DOS Editor with modern VS Code-like input controls.

### Key Technologies
- **Language**: Rust (nightly toolchain, edition 2024)
- **Optional Dependencies**: ICU library for search/replace
- **Platform Support**: Windows, macOS, Unix/Linux
- **Build System**: Cargo with custom build configuration

### Project Structure
- `src/` - Core editor implementation
- `i18n/` - Internationalization support
- `build/` - Build scripts and configuration
- `benches/` - Performance benchmarks
- `assets/` - Images and resources
- `.cargo/` - Cargo configuration (including release.toml)

### Build Commands
- **Release Build**: `cargo build --config .cargo/release.toml --release`
- **Test**: `cargo test`
- **Test with ICU**: `cargo test -- --ignored`
- **Benchmark**: `cargo bench`

### Key Features to Consider
- Terminal UI rendering and input handling
- Text buffer management and editing operations
- Search and replace functionality (with optional ICU support)
- Multi-language support through i18n
- Cross-platform console/terminal compatibility

## Important-instruction-reminders

* Do what has been asked; nothing more, nothing less.
* NEVER create files unless they're absolutely necessary for achieving your goal.
* ALWAYS prefer editing an existing file to creating a new one.
* NEVER proactively create documentation files (*.md) or README files. Only create documentation files if explicitly requested by the User.
* NEVER create extensions on classes that need to access private properties. Instead, add the methods directly to the class for proper encapsulation.
* BEFORE WRITING ANY CODE, IF THE USER ASKS FOR SOMETHING, NEVER JUST STRAIGHT TO CODE, UNLESS THEY SAY EXPLICITLY. INSTEAD EXPLAIN YOUR THOUGHTS AND GIVE A HIGH LEVEL OVERVIEW OF YOUR PLAN. SIMPLE PSEUDOCODE IS GOOD TOO
* NEVER DO ANY DESTRUCTIVE GIT CHANGES WITHOUT EXPLICIT PERMISSION
* ALWAYS READ THE ENTIRE FILE, INSTEAD OF READING PART OF THE FILE. ALWAYS GATHER AS MUCH CODE CONTEXT AS POSSIBLE BEFORE PLANNING/CODING. DO NOT BE LAZY.
* NEVER jump straight to code edits, first call 3 shell script-architect subagents in parallel and give them all the context they need to code up a solution. Then evaluate all of their code solutions. If they all mostly agree, implement their solution. If they disagree significantly, ask me about which approach is best before proceeding.

## Rust-Specific Guidelines for This Project
* Check `Cargo.toml` dependencies before assuming any crate is available
* This project uses `opt-level = "s"` for size optimization in release builds
* The project uses `panic = "abort"` in release mode for smaller binaries
* Platform-specific code uses `cfg` attributes (e.g., `#[cfg(unix)]`, `#[cfg(windows)]`)
* The project targets Rust 1.87+ and uses nightly features when `RUSTC_BOOTSTRAP=1` is not set
