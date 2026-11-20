# Implement the AERO Compiler MVP

## Apply when

Use this skill for lexer, parser, AST, type-checker, code-generator, or end-to-end compiler tasks.

## Workflow

1. Find the smallest crate or test that proves the requested behavior.
2. Read its current implementation and existing tests.
3. State whether behavior is implementation or documentation-only.
4. Make the narrowest source change that closes the gap.
5. Add focused unit tests and one integration test when applicable.
6. Preserve diagnostics and source locations.
7. Run formatting, focused tests, then workspace tests.

## Validation

```bash
cargo fmt --all -- --check
cargo test -p aero-lexer
cargo test -p aero-parser
cargo test -p aero-types
cargo test -p aero-codegen
cargo test -p avm-runtime
cargo test -p aeroc
cargo test --workspace
```

## Constraints

- do not add speculative syntax;
- keep parser recovery deterministic;
- do not make code generation depend on hardware;
- do not mark placeholder behavior as complete;
- separate public syntax from proposed extensions.
