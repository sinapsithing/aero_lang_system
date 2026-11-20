# AERO Fork — Engineering and Agent Guide

This repository is a public fork of `somat3k/aero_lang_system`. The fork is intended to turn the existing AERO/HoloLang vision into a maintainable, tested, and incrementally implementable software platform.

## Scope

Prioritize work in this order:

1. A correct Rust toolchain: lexer, parser, AST, type checker, code generator, and CLI.
2. A working AVM execution path with observable instructions and tests.
3. A stable HoloLang-to-AERO lowering pipeline.
4. Capability-gated world adapters and actor runtime services.
5. Local agent integration, bounded skills, and auditable orchestration.
6. Sharding, data transformation, spatial processing, and physical-device research.

## Non-negotiable principles

- Treat existing documentation as product vision until implementation proves otherwise.
- Do not claim a feature works unless it has executable tests.
- Separate design specifications from implementation status.
- Keep capabilities explicit and session-scoped.
- Never bypass safety limits for physical devices.
- Never store credentials in source or prompts.
- Do not silently lose, duplicate, or overwrite shard data.
- Optimize only after baseline measurements exist.

## Repository map

- `aeroc/` — main compiler CLI.
- `aero-lexer/` — lexical analysis.
- `aero-parser/` — syntax and AST construction.
- `aero-ast/` — AST definitions.
- `aero-types/` — type checking and effect analysis.
- `aero-codegen/` — bytecode generation.
- `avm-runtime/` — virtual machine runtime.
- `docs/` — specifications and engineering documentation.
- `.github/skills/` — repository-specific agent instructions.

## Development loop

```bash
cargo fmt --all -- --check
cargo test --workspace
cargo clippy --workspace --all-targets -- -D warnings
cargo build --workspace
```

Run focused tests while developing a crate, then run the complete workspace suite before submitting a change.

## Definition of done

A change is complete only if it includes:

- focused implementation or documentation updates;
- relevant unit and integration tests;
- formatted Rust code;
- updated public documentation when behavior changes;
- no secrets or generated artifacts;
- a clear explanation of compatibility or migration impact.

## Architecture boundaries

- Lexer and parser must not execute code.
- Type checking must not mutate source files.
- Code generation must not depend on physical hardware.
- AVM execution must expose diagnostics and effects.
- HoloLang lowering must be tested independently of device drivers.
- Agent orchestration must be outside the deterministic compiler core.

## Safety policy

Any work involving lasers, mirrors, photonics, robot movement, or power control requires an explicit safe-state design, bounds validation, teardown behavior, and simulation tests. Hardware work must remain behind capability-gated adapter interfaces.
