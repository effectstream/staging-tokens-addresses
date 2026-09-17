# Stagenet token addresses

This repository records existing Token Metadata OnChain contract deployments on Midnight Stagenet (Midnight 2.x / ledger-v9).

The deployment set contains 11 contracts producing 16 token records. See the [Stagenet token metadata deployment record](stagenet-token-metadata-deployments.md) for addresses and deployment details.

The [measured token-metadata K-size comparison](token-metadata-k-sizes.md) reports equivalent Compact-v2, Compact-v3, and MinoCrab-v3 results for the byte-heavy metadata circuits, with reproducible sources, artifact hashes, and differential checks. These measurements do not change the deployed contracts or addresses.

The [MinoCrab metadata-shape measurements](token-metadata-shapes.md) add exact costs for a fixed three-event publisher, a representative ledger-backed three-event publisher, one fully runtime typed event, and an independently supplied one/two/three-event ladder. The typed format is a benchmark variant and is not deployed.
