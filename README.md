# Stagenet token addresses

This repository records the on-chain token-metadata contract deployments on Midnight Stagenet (Midnight 2.x / ledger-v9).

The deployments implement [MIP PR #315](https://github.com/midnightntwrk/midnight-improvement-proposals/pull/315), file [`mips/mip-xxxx-on-chain-token-metadata.md`](https://github.com/midnightntwrk/midnight-improvement-proposals/blob/mip-on-chain-token-metadata/mips/mip-xxxx-on-chain-token-metadata.md): metadata travels as `Misc` contract events named `pad(32, "mip-xxxx:token-metadata[v1]")` with a 256-byte payload. The MIP is a draft and `xxxx` is a placeholder for the number it has not been assigned yet; because the event name is a literal inside the compiled circuits, **a renumbering means a redeployment and new addresses**.

The current deployment set contains 11 contracts producing 17 token records over 17 identities `(contractAddress, domainSep, kind)`. See the [Stagenet token metadata deployment record](stagenet-token-metadata-deployments.md) for addresses, colours and deployment details. It also keeps the 11 addresses of the previous, pre-MIP set in a superseded section; a conforming consumer ignores every event those contracts emitted.

The [measured token-metadata K-size comparison](token-metadata-k-sizes.md) reports equivalent Compact-v2, Compact-v3 and MinoCrab-v3 results for the byte-heavy metadata circuits, with reproducible sources, artifact hashes and differential checks. These measurements do not change the deployed contracts or addresses, and the sources under `benchmark/compact-src` stay pinned to the pre-MIP layout on purpose, so that the recorded figures remain comparable with the run they were taken from.
