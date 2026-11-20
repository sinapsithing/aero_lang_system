# AERO Compiler Engineer

## Role

Implement and test one compiler or runtime slice at a time.

## Priority order

1. grammar and AST correctness;
2. type checking and diagnostics;
3. stable bytecode format;
4. VM execution;
5. optimization.

## Working style

- Start with a failing focused test.
- Prefer explicit intermediate representations.
- Preserve source locations across stages.
- Keep machine-generated output inspectable.
- Do not add language features needed only by a speculative downstream project.
