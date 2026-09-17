# Reproducing the token-metadata benchmarks

This focused crate contains two suites:

- the exact ports of `MetadataProbe.publishRaw`, `publishStandard`, `publishFixture`, `calls`, and generated `SSTAR.publishMetadata` used by the original K-size comparison;
- five user-requested typed-format shapes: `literal3`, `ledger3`, `runtime1`, `runtime2`, and `runtime3`.

The original Compact files at revision `71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6` are copied under `compact-src/`. `compact-src/shapes/MetadataShapes.compact` is a clearly isolated comparable fixture for the benchmark-local typed format. MinoCrab and every Rust dependency are pinned by `Cargo.toml` and `Cargo.lock`.

Run the complete Docker workflow from the repository root:

```bash
./benchmark/scripts/reproduce.sh
```

By default, the script builds its Compact container from the [official Compact 0.34.0 release](https://github.com/LFDT-Minokawa/compact/releases/tag/compactc-v0.34.0). It pins the Linux aarch64 asset to SHA-256 `d3e292c4f48e257dcd6b3d3e3e4743d7d8ea0729f48953eab91a366d44cd026d`, the same asset used by the measured image. On another Docker architecture, set `COMPACT_IMAGE` to a compatible image that contains this toolchain at `/opt/compactc`; the script checks that the image exists before starting. The script fetches locked Cargo dependencies during the test build, then uses `--network none` for artifact emission and every cost measurement. It generates no proving or verifier keys.

Set `KEEP_COMPACT_IMAGE=1` to retain the image built from the official asset or `KEEP_DOCKER_VOLUMES=1` to retain the two temporary Cargo volumes. Both are removed by default.

For a focused rerun after dependencies are cached, the relevant commands inside the pinned Rust container are:

```bash
cargo test --locked --offline --test equivalence
cargo test --locked --offline --test shapes_equivalence
cargo run --locked --offline --bin emit_zkir -- generated/minocrab-v3
cargo run --locked --offline --bin model_cost
```

`COMPACT_V3_DIR` must point to the fresh Compact-v3 output when running either equivalence target directly. The script compiles all Compact fixtures without proof or verifier keys. Generated artifacts, build targets, Cargo caches, BZKIR, keys, and its generated Dockerfile are ignored.

See the [original K-size comparison](../token-metadata-k-sizes.md), [metadata-shape report](../token-metadata-shapes.md), [historical measurements](results/measurements.json), and [typed-shape measurements](results/metadata-shapes.json).
