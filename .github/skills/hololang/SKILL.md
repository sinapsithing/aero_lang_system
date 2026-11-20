# Work Safely on HoloLang

## Apply when

Use this skill for HoloLang syntax, lowering, SafeTensor, graph declarations, device descriptors, or spatial canvases.

## Workflow

1. Define the data shape and bounds before writing lowering logic.
2. Keep HoloLang parsing separate from AERO lowering.
3. Test lowering using simulated devices and mock sensors.
4. Ensure shape mismatches and unsafe numeric bounds fail before execution.
5. Represent device limits in typed constraints.
6. Add physical safety tests without assuming real hardware behavior.

## Validation

```bash
cargo test --workspace
cargo fmt --all -- --check
```

## Constraints

- never issue real laser or mirror commands from compiler tests;
- never infer missing safety limits;
- never call HoloLang a working runtime feature until executable tests prove it;
- no network or hardware dependency in unit tests.
