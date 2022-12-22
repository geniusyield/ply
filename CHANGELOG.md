# 0.2.1 - Backport "Handle GHC.Num.Integer module name"

- See: https://github.com/mlabs-haskell/ply/pull/40/files

# 0.2.0 - Internal Type Cleanup

- `TypedScriptEnvelope'` is deprecated. `TypedScriptEnvelope` now implements `toJSON` and `fromJSON` directly.
- `writeEnvelope` and `readEnvelope` are updated to have more sensible types. They will read and write to and from `TypedScriptEnvelope`.
- `mkEnvelope` at `Ply.Plutarch` will convert Plutarch term into `TypedScriptEnvelope` given config and description.
- `CBORDecodeError` is removed, `AesonDecodeError` will be thrown when decoding error happen.
- Script serialization utilites are now relocated to `Ply.Core.Serialize.Script`.

# 0.1.3 - **Critical fix** for `PlyArg Extended` instance

- The constructor indices were incorrect.

  Thanks to @danielfarrelly for reporting and fixing the bug.

# 0.1.2 - **Critical fix** for `PlyArg Credential` instance

- The instance was buggy and did not produce proper UPLC. Any types containing `Credential` (e.g `Address`) may have been affected.

  Thanks to @rmgaray for reporting the bug.

# 0.1.1 - Hot fix for `PlyArg`

- Export `ToDataConstraint` and `toBuiltinArgData`.

# 0.1.0 - Initial Release

- Full Plutus V2 support with machinery for distinguishing between V1 and V2 Plutarch scripts.
- Add `getPlutusVersion` - query a `TypedScript` for its Plutus version (`ScriptV1` or `ScriptV2`).
- Plutarch 1.2 integration
- New flag for `ply-core`: `new-ledger-namespace`, turned on by default. See README.
- `writeTypedScript` and `typedWriterInfo` are now parameterized over the Plutarch compiler config.
- More documentation in general, please consider checking out the haddocks locally.
- Fix `typeName` generation: this is somewhat of an internal detail and things will _just work_. But you may consider reading the README section on type name determination in case you're having strange issues during script reading.

## Acknowledgements

Huge thanks to these folks helping me:

- @bladyjoker
- @danielfarrelly
- @MangoIV
