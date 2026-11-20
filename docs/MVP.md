# AERO Delivery MVP

## Goal

Deliver one end-to-end vertical slice that a maintainer can understand, test, and extend.

The MVP is:

```text
AERO source
  -> lexer
  -> parser
  -> AST
  -> type check
  -> bytecode
  -> AVM execution
  -> observable result
```

## First accepted program

```aero
fn main() -> i64 {
    know left = 20;
    know right = 22;
    left + right
}
```

## Acceptance criteria

- `aeroc check` accepts the program and reports syntax/type errors correctly.
- `aeroc build` emits versioned, inspectable bytecode.
- `aeroc run` executes and prints or returns `42`.
- The lexer, parser, type checker, code generator, and VM all have focused tests.
- An integration test covers the complete source-to-result path.
- No hardware, network, model, or external service is required.

## Explicitly excluded from MVP

- Holographic hardware control.
- Ollama or external model calls.
- GNN routing.
- Distributed sharding.
- Linear and GitHub automation.
- GC and native LLVM backends.

## Implementation slices

1. Define and test the first language grammar subset.
2. Define and test bytecode opcodes and their encoding.
3. Implement only the arithmetic and control-flow instructions required by the sample.
4. Implement VM result reporting and diagnostic output.
5. Add a single end-to-end integration test.
6. Document implemented versus planned behavior.

## Evidence required

Record test output and a small benchmark baseline. Do not add speculative performance targets before baseline results exist.
