# Token Metadata OnChain — Stagenet deployment record

Last updated: 2026-09-18T00:50:20Z

This file records the reference deployments of the on-chain token-metadata standard on Midnight Stagenet, redeployed on 2026-09-18 under the layout of **MIP PR #315** (`mip-xxxx:token-metadata[v1]`). All 11 deployment addresses, transaction hashes, block heights and transaction results were checked against the public Stagenet indexer while this record was written (11/11 `ContractDeploy`, `SUCCESS`). The previous set, which used the earlier repository-local layout, is kept in [Superseded deployments](#superseded-deployments-pre-mip-layout-source-71c5b0b) and a consumer of the standard **ignores** it.

## Standard

These contracts implement [MIP PR #315](https://github.com/midnightntwrk/midnight-improvement-proposals/pull/315), file [`mips/mip-xxxx-on-chain-token-metadata.md`](https://github.com/midnightntwrk/midnight-improvement-proposals/blob/mip-on-chain-token-metadata/mips/mip-xxxx-on-chain-token-metadata.md). The MIP is transport-only: metadata travels as `Misc` contract events whose 32-byte name is `pad(32, "mip-xxxx:token-metadata[v1]")` —

    6d69702d787878783a746f6b656e2d6d657461646174615b76315d0000000000

— and whose payload is exactly 256 bytes laid out as `domainSep` at offset 0 (32 bytes), `kind` at 32 (1 byte), `key` at 33 (32 bytes), **`val-type` at 65 (1 byte)**, `val-len` at 66 (1 byte) and `value` at 67 (189 bytes). A `Misc` event under any other name is ignored, not rejected. The token identity is the triple `(contractAddress, domainSep, kind)` with the **full** kind byte, so one contract and one domain separator can hold up to four distinct token records; `privacy` and `storage` derive from that byte, and only the native kinds 0 and 1 have a colour.

**The `xxxx` in the event name is a placeholder.** The MIP is a draft and has not been assigned its number yet. When it is, the event name string changes, and because the name is a literal inside the compiled circuits, **these contracts must be redeployed and the addresses in this file replaced**. The addresses below are therefore valid for the draft layout only.

## Network and source

| Field | Value |
|---|---|
| Network / network ID | Midnight Stagenet / `stagenet` |
| Compatibility target | Midnight 2.x / ledger-v9 |
| Node WebSocket | `wss://rpc.stagenet.shielded.tools` |
| Node HTTP (recorded deployment endpoint) | `https://rpc.stagenet.shielded.tools` |
| Indexer HTTP | [Stagenet GraphQL API](https://indexer.stagenet.shielded.tools/api/v4/graphql) |
| Indexer WebSocket | `wss://indexer.stagenet.shielded.tools/api/v4/graphql/ws` |
| Faucet | [Stagenet faucet API](https://faucet.stagenet.shielded.tools/api/drips) |
| Standard | MIP PR #315 `mip-xxxx:token-metadata[v1]` (draft; the number is a placeholder) |
| Pinned source revision | `17216362077b3c48da05f06d3a7b0be1b248e1ff` |
| Compiler / runtime | Compact 0.34.0 / compact-runtime 0.19.0 |
| Ledger dependency | `@midnightntwrk/ledger-v9@1.0.0-rc.3` |
| Recorded deployment date | 2026-09-18 UTC |
| Deployment verification | 11/11 `ContractDeploy`, transaction result `SUCCESS`; checked 2026-09-18T00:50:20Z |
| Token fixture recorded at | 2026-09-18T00:45:29.268Z |
| Deployment manifest SHA-256 | `1b611c71895a7c7c858b87f8a1df5d265a3ca52066cd4976fce5c5adcb802bc5` |

Source links: [deployment manifest](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/deployments/stagenet-deployment.json), [reference set](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/deployments/reference-set.json), [recorded token fixture](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/fixtures/stagenet/expected-tokens.json), [implementation notes](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/TOKEN-METADATA.md), [toolchain and deployment instructions](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/README.md), [contracts PR #2](https://github.com/acedward/mip-erc7496-midnight-contracts/pull/2), [UmbraDB token indexer PR #19](https://github.com/acedward/UmbraDB/pull/19).

The [Compact/MinoCrab K-size comparison](token-metadata-k-sizes.md) measures equivalent metadata routines. It is an off-chain compiler experiment and does not replace these deployed artifacts, verifiers, addresses or transaction facts. Its sources under `benchmark/compact-src` are **pinned to the pre-MIP layout on purpose** — the measurement compares compilers, not standards, and repinning them would invalidate the recorded figures against which they were taken.

## Contract address directory

11 contract addresses carry 17 token records over 17 identities `(contractAddress, domainSep, kind)` and 15 `(contractAddress, domainSep)` pairs: DAUR contributes two kinds under one domain separator, CNST contributes five pieces, and LLIAR contributes two kinds — one observed, one declared. Names below are reference labels; published values and exceptions are documented later.

| ID | Reference name | Contract address (hex) | Deployment block |
|---|---|---|---|
| LSUN | Ledger Sun | `152827bc1d9ea7ecec0d13879e87a21ecf8f283804dfef16c9b805612acfea90` | 508432 |
| LMOON | Ledger Moon | `fef951c605d33514bd9c54b56772e23e9abaad07982457fd918dc68984cc433a` | 508451 |
| SSTAR | Shielded Star | `171ac372bb73fb9fee495cf578fe8e99ddc622f2ee18fd327e1a90d01cb3cc95` | 508464 |
| SNEB | Shielded Nebula | `19036e0277d378ff8356b32e74bbd6aa03d4531bc9094031e785fb48c151b538` | 508474 |
| SGHOST | Shielded Ghost | `165e623bc4e5e0fc99607011fcb8cbe436e001071f52130435b2ae11bbfdcf34` | 508489 |
| UCOM | Unshielded Comet | `de76f303d319aa7427cfac5eb671c1d693259e9ba59086c251c495708fc88acb` | 508496 |
| UMET | Unshielded Meteor | `e17be6733ec82a884927041bdcf2e954265a0cd07864df8922064bc218e8198a` | 508507 |
| UPROM | Unshielded Promise | `2af4685bc8328a1a18ae86e428a9ecacc7c2f3bf12c293e18b2fd9cf4092bdf3` | 508524 |
| DAUR | Dual Aurora | `3ad541b2dbbaeb69b2381bec19b0d9211925726f8784b8bff1b87b92d6a09256` | 508530 |
| CNST | Constellations | `9f0d030eb2716e593a3872d569664d6ff680cdfd81ed40e86d60de39557511d7` | 508547 |
| LLIAR | Ledger Liar | `af0330b143e2ea01071a1435495f8be82cd689e8c5af8a05c5dd0df652f20a95` | 508592 |

## Recorded token metadata

Metadata, native mint counts and amounts are the pinned fixture snapshot, not a fresh scan of later activity. The status column is the expected consumer classification from that fixture: MIP section 7.2 defines exactly three — `observed` (minted, nothing said), `declared` (described, never minted) and `described` (both). Amounts are base units; native mint totals are not circulating supply and do not describe ledger-token balances. `Kind` is the MIP identity byte.

| Token record | Published name | Published symbol | Decimals | Kind | Expected status | Native mints | Native amount |
|---|---|---|---|---|---|---|---|
| LSUN | Ledger Sun | LSUN | 6 | 2 — unshielded ledger | declared | 0 | 0 |
| LMOON | Ledger Moon (renamed) | LMOON | 8 | 2 — unshielded ledger | declared | 0 | 0 |
| SSTAR | Shielded Star | SSTAR | 6 | 1 — shielded native | described | 1 | 5000000 |
| SNEB | Shielded Nebula | SNEB | 0 | 1 — shielded native | described | 2 | 3 |
| SGHOST | not published | not published | not published | 1 — shielded native | observed | 1 | 13 |
| UCOM | Unshielded Comet | UCOM | 6 | 0 — unshielded native | described | 1 | 2500000 |
| UMET | Unshielded Meteor | UMET | 2 | 0 — unshielded native | described | 3 | 600 |
| UPROM | Unshielded Promise | UPROM | 6 | 0 — unshielded native | declared | 0 | 0 |
| DAUR / kind 0 | Dual Aurora | DAUR | 6 | 0 — unshielded native | described | 1 | 2000 |
| DAUR / kind 1 | Dual Aurora | DAUR | 6 | 1 — shielded native | described | 1 | 1000 |
| CNST / orion | Constellations · Orion | CNST | 0 | 1 — shielded native | described | 1 | 1 |
| CNST / lyra | Constellations · Lyra | CNST | 0 | 1 — shielded native | described | 1 | 1 |
| CNST / cygnus | Constellations · Cygnus | CNST | 0 | 1 — shielded native | described | 1 | 1 |
| CNST / vega | Constellations · Vega | CNST | 0 | 1 — shielded native | described | 1 | 1 |
| CNST / altair | Constellations · Altair | CNST | 0 | 1 — shielded native | described | 1 | 1 |
| LLIAR / kind 0 | not published | not published | not published | 0 — unshielded native | observed | 1 | 7 |
| LLIAR / kind 2 | Ledger Liar | LLIAR | 6 | 2 — unshielded ledger | declared | 0 | 0 |

## Token domains and native colors

Every domain text below is UTF-8 padded with trailing zero bytes to exactly 32 bytes. A kind-2 or kind-3 record has no colour at all (MIP section 3), so the ledger rows below carry none; LLIAR appears twice because its two kinds are two records, and only its kind-0 row — the one the chain actually minted — has a colour.

| Token record | Domain text | Kind | Native color (hex) |
|---|---|---|---|
| LSUN | `umbra:lsun` | 2 | none — not a native kind |
| LMOON | `umbra:lmoon` | 2 | none — not a native kind |
| SSTAR | `umbra:sstar` | 1 | `3248c456d02ce8a8c2b42541488add504152f745e168d139934c637339c55553` |
| SNEB | `umbra:sneb` | 1 | `e51a1df69e7bdac483b1ef3a418ab993145e075c946aa90b57a5200328a60e01` |
| SGHOST | `umbra:sghost` | 1 | `1be172b1e46d0ceacc3200aded4f681eafabe42611ee2b962200802573675bb3` |
| UCOM | `umbra:ucom` | 0 | `10dbdaf2b0b0aee765b3a83517f63a0371088565aa1d4cf89ccdc1c70b298269` |
| UMET | `umbra:umet` | 0 | `ab2fed68e75cd202f09dc7dc224fdb9c7a77c078a073596d39f574598f19d6ee` |
| UPROM | `umbra:uprom` | 0 | `a166e633b53e590c2d8fd9c7d6bcd655867b4c03b3f0cdd53be11adb99d80ac3` |
| DAUR / kind 0 | `umbra:daur` | 0 | `00b357a6d3d7a08be132a3ff81c48a54c9a566b4e73eedc285a34c6d2c51d325` |
| DAUR / kind 1 | `umbra:daur` | 1 | `00b357a6d3d7a08be132a3ff81c48a54c9a566b4e73eedc285a34c6d2c51d325` |
| CNST / orion | `cnst:orion` | 1 | `e53dea555436716ce8a774fcfe0a71a3076725f6723930d82a0134e02730ccdc` |
| CNST / lyra | `cnst:lyra` | 1 | `ffe655921c01f3a091fc2f935c71e72ac41669609bfd0c97ac9a84b4546097dd` |
| CNST / cygnus | `cnst:cygnus` | 1 | `d33a7c573e3272dfc2a52620327e682d178fb9df5d391cb9b5da966587ec5934` |
| CNST / vega | `cnst:vega` | 1 | `6f6d0047200c30d3bf0b6bdd9c6beaf4946255e7eadc1ceb15192f8c6d71a5cf` |
| CNST / altair | `cnst:altair` | 1 | `43a69ea323b809fa5ece303c1b7d8bb6c9f7835e67ca5b8a205074e2840e1032` |
| LLIAR / kind 0 | `umbra:lliar` | 0 | `3b420f37be1c6c175a2f3766e74ab4308aba79a33c7037acdc9a1c7118fd4dc1` |
| LLIAR / kind 2 | `umbra:lliar` | 2 | none — not a native kind |

## Deployment and call details

Deployment block times below come from the live indexer query. The script recorded-at time comes from the pinned manifest and is later than the block timestamp. Post-deployment calls are transcribed from the manifest, where every listed call has status SucceedEntirely; those individual calls were not independently re-queried for this record.

### LSUN — Ledger Sun

- Source: [LSUN.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/LSUN.compact); reference template: `LedgerToken`.
- Contract address: `152827bc1d9ea7ecec0d13879e87a21ecf8f283804dfef16c9b805612acfea90`.
- Deployment transaction hash: `9a131d060981b73d8574bd2307f62d9e9fd90611704b9168aafe2ef1ad7287b6`.
- Deployment transaction identifier: `001e34832416c9015ea681142603eb2d13f50e17b4d6a1cbe827491f1af53c0944`.
- Deployment block: **508432**; block hash: `f8b97c27baa12473c0eecdbc7d73f4a02a5c945306e1dcd0b0dfce21ecd05fed`.
- Block timestamp: **2026-09-18T00:27:00Z**; script recorded at: `2026-09-18T00:27:15.037Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `2ae4c2fe41d44e65472c934a4400d4a7f585b8c17c4499360497c7bd24e04ba5`.

Ledger balances: the reference sequence credits 1,000,000 base units and transfers 250,000. These are contract-state operations, not native mint effects; a kind-2 token has no colour (MIP section 3).

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 508442 | `fba09720978780bbf8ee675467691dd3286436d675a8ca17a26e8f4a1846079c` | 2026-09-18T00:28:14.756Z |
| 1 | `ledgerMint` | 508445 | `973ee90713850d35edd53fe794dd5fb1bc42e3f7507e368c9638aa4c626da3b9` | 2026-09-18T00:28:31.850Z |
| 2 | `transfer` | 508448 | `19d940276b6037515484a523c31130083325c5dbe79027db1a8a9b20ba380232` | 2026-09-18T00:28:50.586Z |

### LMOON — Ledger Moon

- Source: [LMOON.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/LMOON.compact); reference template: `LedgerToken`.
- Contract address: `fef951c605d33514bd9c54b56772e23e9abaad07982457fd918dc68984cc433a`.
- Deployment transaction hash: `b51f62231cb15984bb4f7b727ae931b25ab65f510eb5848c56d338dd408621e8`.
- Deployment transaction identifier: `00a8e6788d6a6f147ff517d265f02af2d10262fa6719407467109c1e7863d8c550`.
- Deployment block: **508451**; block hash: `d16c68035b7332ec16097bb750c9852b18f15ae719794442813b9e3b0697e228`.
- Block timestamp: **2026-09-18T00:28:54Z**; script recorded at: `2026-09-18T00:29:08.467Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `218656a63c52d70458c6aa7a830099ad014a8bc8128588870d9c7e4603a84c06`.

Published initially as Ledger Moon, then changed to Ledger Moon (renamed). The reference sequence credits 5,000,000 base units in contract state. A kind-2 token has no colour.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 508454 | `d21119de590a698a01a8185cf70c68a4ef8947f0220e0196d47c94977f51cc57` | 2026-09-18T00:29:26.624Z |
| 1 | `ledgerMint` | 508457 | `9de39cc155bc8b13596230143db1ce0e8d4fdbaa945838afd47d737752319e57` | 2026-09-18T00:29:43.951Z |
| 2 | `publishRename` | 508461 | `d2e96632e7d368a3fcd2379fb4978d55a3ea09d491e8828245da5faabddc742d` | 2026-09-18T00:30:07.966Z |

### SSTAR — Shielded Star

- Source: [SSTAR.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/SSTAR.compact); reference template: `NativeShieldedToken`.
- Contract address: `171ac372bb73fb9fee495cf578fe8e99ddc622f2ee18fd327e1a90d01cb3cc95`.
- Deployment transaction hash: `ddd4afb291674087db777871d602475a3e605e1f7819421f39387d2947bb3e4d`.
- Deployment transaction identifier: `0031ddab3ee80ad2b2a3a58cea6b30fec7081e509a775302e7e4339a0577cd3dec`.
- Deployment block: **508464**; block hash: `585dca21ed7d2d90d2ab1f0533b813bf00bd53d88a96fec407dfc8b127e127ea`.
- Block timestamp: **2026-09-18T00:30:12Z**; script recorded at: `2026-09-18T00:30:27.018Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `055a65a7128a6a6a2f04a4c48c05b8b31a4743632668ed9df91e2a87efb87069`.

Publishes name, symbol and decimals, then mints 5,000,000 native shielded base units. `decimals` is carried as `val-type` 2 (a big-endian unsigned integer of one byte), which is what MIP Appendix A requires.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 508467 | `4f9c48dd7c9c71d35bb9c55f9d6cc6dfb704267a720d46b66a61954a402ba564` | 2026-09-18T00:30:44.038Z |
| 1 | `mint` | 508471 | `a25d848fd9d8bf38a9ca782adb40611d4be9158760c8e5b088e01336cccda147` | 2026-09-18T00:31:08.270Z |

### SNEB — Shielded Nebula

- Source: [SNEB.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/SNEB.compact); reference template: `NativeShieldedToken`.
- Contract address: `19036e0277d378ff8356b32e74bbd6aa03d4531bc9094031e785fb48c151b538`.
- Deployment transaction hash: `5a8970eb2b0baf755a14a9b217e5d7019f4c2bd8895adb876c01b1f02670180b`.
- Deployment transaction identifier: `0097aa6a5b2aec7711cc65e14ca1ac40464eb5278ff91014d983223bb61f9af11a`.
- Deployment block: **508474**; block hash: `db5a922d26e5565f54a0503fcca32b784d3e5fbda5a3bb2405123f3cee26429f`.
- Block timestamp: **2026-09-18T00:31:12Z**; script recorded at: `2026-09-18T00:31:27.148Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `7e22ec0cb67f8a77ff357823476773cf0ffe5420d1028fa5245d884e25759bf4`.

Publishes metadata and a multipart JSON document in `metadata/0` through `metadata/5`, each part `val-type` 3, then mints 1 and 2 native shielded units. The split exists because one event carries at most 189 bytes of value.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 508478 | `c5605da20d98b27b9393998762dd401aaa916b76829786f9bb31f43412815144` | 2026-09-18T00:31:50.757Z |
| 1 | `mint` | 508482 | `dfb58222e42486ce648b58af707f8601758392d8f5e767e157b1b4222fc01ade` | 2026-09-18T00:32:14.998Z |
| 2 | `mint` | 508486 | `6196df7d85f97273b1ce5cf1438765d5a4f6abadb1eeaa39d1d89026c021775c` | 2026-09-18T00:32:39.117Z |

### SGHOST — Shielded Ghost

- Source: [SGHOST.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/SGHOST.compact); reference template: `NativeShieldedToken`.
- Contract address: `165e623bc4e5e0fc99607011fcb8cbe436e001071f52130435b2ae11bbfdcf34`.
- Deployment transaction hash: `f279fb502650ce0a243a7a1721794a8bd23637a71327fb21427eb426dff09fc1`.
- Deployment transaction identifier: `006e87fcaa876cc627b4e9120190ab77433f8d15d0ba205e0b6dc09c945b0b55c3`.
- Deployment block: **508489**; block hash: `014ac713bccd992a61d67ead2a4894858e8198750ce1b029a1dee9427360d5fb`.
- Block timestamp: **2026-09-18T00:32:42Z**; script recorded at: `2026-09-18T00:32:56.502Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `adfe46e83da1d995b955cb1dd16ee6c9130b7f81016eca6469ab48b9a26e7f14`.

Shielded Ghost / SGHOST is a reference label only. No name, symbol or decimals were published, so the row stays `observed`: the chain shows a token that exists and says nothing about itself. The mint creates 13 native shielded base units.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `mint` | 508493 | `2e62bdab138c3228ddeddcf37fc47d6f6f9296ff1805eb0be0bfb8523fb50897` | 2026-09-18T00:33:20.372Z |

### UCOM — Unshielded Comet

- Source: [UCOM.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/UCOM.compact); reference template: `NativeUnshieldedToken`.
- Contract address: `de76f303d319aa7427cfac5eb671c1d693259e9ba59086c251c495708fc88acb`.
- Deployment transaction hash: `76405e2e994fd11c0e698f6f4133e65d5be4ba96337991741652bc2b18e7f2ba`.
- Deployment transaction identifier: `0004b869f51b4ab62ab5086f3f0ae32c3c5a40c682a417eff4469293e2d9ee4d2c`.
- Deployment block: **508496**; block hash: `b724db5a581f78f574c706b6544824a11732c15fb539d65eb405f7d07d84c92b`.
- Block timestamp: **2026-09-18T00:33:24Z**; script recorded at: `2026-09-18T00:33:39.354Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `bb3352d88b2c3251fc901eaa1aeb3ccfd0dfc23a716a59d318ea589119141937`.

Publishes metadata, then mints 2,500,000 native unshielded base units.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 508500 | `44b534f86a9af1dccc4de2d7f3589c16e91d9450e2f2b671d637b4662d7480c2` | 2026-09-18T00:34:02.879Z |
| 1 | `mint` | 508504 | `d9776f172ea74c059f83b04999ef9ed941c0b815d72c418bddbfcad168d83f07` | 2026-09-18T00:34:25.618Z |

### UMET — Unshielded Meteor

- Source: [UMET.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/UMET.compact); reference template: `NativeUnshieldedToken`.
- Contract address: `e17be6733ec82a884927041bdcf2e954265a0cd07864df8922064bc218e8198a`.
- Deployment transaction hash: `88fcfd807e6a7e9a26ecb456fa256b1be72fbfc49b6233cbe35f6c944be0ee19`.
- Deployment transaction identifier: `008f97e75ff9305159ea837c4c3b86b505003c527ea45ff68b443bd6c63251e105`.
- Deployment block: **508507**; block hash: `e836dc13557c5b8e8e0a77b0fd2594ce7d38965154f6a5837530be17642f32e1`.
- Block timestamp: **2026-09-18T00:34:30Z**; script recorded at: `2026-09-18T00:34:44.544Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `0c1ddee94faa3b6ac14f90aa215702c9d405e276e28579dc708dc2105f8dbfe1`.

Mints 100, 200 and 300 native unshielded base units before publishing metadata; exercises the observed-to-described transition.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `mint` | 508511 | `ce3f21f21cf4ea0bee8ea4105ea50cc624db44ec8c4a60de60030779042119da` | 2026-09-18T00:35:08.270Z |
| 1 | `mint` | 508514 | `88f37a81eedba36b3477008492af9a60a28a37699685fc7d19e9d1598bada3fe` | 2026-09-18T00:35:25.622Z |
| 2 | `mint` | 508518 | `088037cb9ce3e17ff2399f3d0847e47d06648b996d3ac250b550a8cd6ceda4d5` | 2026-09-18T00:35:49.627Z |
| 3 | `publishMetadata` | 508521 | `f1243033cf60fce52465d479f032b6fdf74b4b1857c18c9b5d38ec77d4244b51` | 2026-09-18T00:36:08.387Z |

### UPROM — Unshielded Promise

- Source: [UPROM.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/UPROM.compact); reference template: `NativeUnshieldedToken`.
- Contract address: `2af4685bc8328a1a18ae86e428a9ecacc7c2f3bf12c293e18b2fd9cf4092bdf3`.
- Deployment transaction hash: `e4a9bd3eed9fb034bc1cab9bfc1d08a6a90ac32e1f4b8d27bc51afbb2d18dc48`.
- Deployment transaction identifier: `0066aa1080cad1604991eb8577451b1fcef6a5c1f65f6d6d9987ea404d1b667a92`.
- Deployment block: **508524**; block hash: `c936ec2147a5d4823a1344e0b6e67fd5f259aefc8f9335e4ec1e72025a2b3e94`.
- Block timestamp: **2026-09-18T00:36:12Z**; script recorded at: `2026-09-18T00:36:25.974Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `d52e20d3784d069f9b2c59d9047effaaa07313300a80b4b2bc57af60479bddab`.

Publishes metadata without minting: `declared`, with a derivable colour and no mint effect behind it.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 508527 | `0cf6cdf80fb2534a59e29aac9bf5307726574d194b8ea417c26c9398dd284bb8` | 2026-09-18T00:36:44.414Z |

### DAUR — Dual Aurora

- Source: [DAUR.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/DAUR.compact); reference template: `NativeDualToken`.
- Contract address: `3ad541b2dbbaeb69b2381bec19b0d9211925726f8784b8bff1b87b92d6a09256`.
- Deployment transaction hash: `31d308627efd2dffe6c369b0205e160a6d0c02075de2836b420ae5632b86beca`.
- Deployment transaction identifier: `0042eefc5423d50bd79669102227fcfb586495f0e60200a8d76947dca7d91250c8`.
- Deployment block: **508530**; block hash: `e1f3528fa9cc1b66df1255dd659ecf7e15e9d7d4a591c03958131793a06bd522`.
- Block timestamp: **2026-09-18T00:36:48Z**; script recorded at: `2026-09-18T00:37:02.210Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `eab07f637c50155e363b650542d1700458d912c0cd7ffc7803fda633913db0c6`.

One contract and one domain separator produce two token records, kind 0 and kind 1. Both share the same 32-byte colour; the reference mints 1,000 shielded and 2,000 unshielded base units. Under MIP section 4 these are two identities, not one row with two storages.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishUnshielded` | 508533 | `a78694fe4a01b8ff207f5c0b937b75b56175825c17b1b54a6e0959d21096cbbc` | 2026-09-18T00:37:20.431Z |
| 1 | `publishShielded` | 508536 | `07b668ee87dc7f4f85fec2ea3c8c2370fe36ae8a1206a78a64f4807f6ffb4b90` | 2026-09-18T00:37:37.768Z |
| 2 | `mintShielded` | 508540 | `905cce98a63a69d167cbd1e623cc86f9d788f3ef204e6098f34cfcdd55d32428` | 2026-09-18T00:38:01.986Z |
| 3 | `mintUnshielded` | 508544 | `bcc9c1226b0217cf1a4caa1b8acee9dbc6b3fc45f03189e289ff837236c64d85` | 2026-09-18T00:38:25.759Z |

### CNST — Constellations

- Source: [CNST.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/CNST.compact); reference template: `ShieldedCollection`.
- Contract address: `9f0d030eb2716e593a3872d569664d6ff680cdfd81ed40e86d60de39557511d7`.
- Deployment transaction hash: `49dfe957eaf737dcbadb3345e052a54ff0311b296c1b160eec2d52d595c8866c`.
- Deployment transaction identifier: `0041f402b5a08c0e4ee9dbf024249939e1817801c90388d122df673069dc3f91e1`.
- Deployment block: **508547**; block hash: `93d86d4c38729944d48efddf384dc5204c2df66074b74622d37732d530891577`.
- Block timestamp: **2026-09-18T00:38:30Z**; script recorded at: `2026-09-18T00:38:45.085Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `22f1428951ea960a1025e9bc8e6cab1ca93e2e458875c6f32a12f582d9b4b0ec`.

One contract holds five shielded pieces: Orion, Lyra, Cygnus, Vega and Altair. Each has its own domain separator and colour. Orion magnitude updates are 0.18 → 0.42 → 1.25, carried as `val-type` 1 text (MIP Appendix A has no fractional integer type). Recorded `tokenUri` values are `val-type` 4 and point at `http://localhost:10020/constellations/{piece}`; these are local demonstration resolver URLs, not a public hosted metadata service.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `mintPiece` | 508551 | `6b460586b758a441d706cca8fcc390937929c1ddf785bd42db007d21190095d0` | 2026-09-18T00:39:08.792Z |
| 1 | `publishOrion` | 508554 | `3ad443ffb246854763f4e215b1a4bcf40c95601590dfcdae86d58a79290dad7e` | 2026-09-18T00:39:25.856Z |
| 2 | `updateOrion1` | 508557 | `e9f679d8c741602e24a773db9b61f0f7f2078c6e4f3e9cb1c6c2f87cb40af8cb` | 2026-09-18T00:39:44.574Z |
| 3 | `updateOrion2` | 508560 | `b482d285b284ed9c8f555a7e36d3d8155568692be9c7c7508c4aea00d5091f40` | 2026-09-18T00:40:01.931Z |
| 4 | `mintPiece` | 508564 | `8eec45631ee6812f1486fa47b4c8b9511958a02740f1401fa1156149383c6012` | 2026-09-18T00:40:26.145Z |
| 5 | `publishLyra` | 508567 | `d1f43fb4e30137671300c52502171684d44ee0e3cab309d546002fd13bdb9d82` | 2026-09-18T00:40:44.612Z |
| 6 | `mintPiece` | 508571 | `cf9008d7fea43041be2837e14daf74c648477234d2b69535204ba078d4a2c42f` | 2026-09-18T00:41:08.833Z |
| 7 | `publishCygnus` | 508575 | `6542360a07686bf8fddb6cb8554ee8e481d5624b0a9284f1495c4516ae67344c` | 2026-09-18T00:41:32.670Z |
| 8 | `mintPiece` | 508579 | `c0febe7ceaea028a12be555301471e7d17306f683c3aa8fa904896a20bf35803` | 2026-09-18T00:41:56.988Z |
| 9 | `publishVega` | 508582 | `b9c633bdc5f8c6c6190bad7f22e51336429e3f2ee3ecb26ecd633dfee07a84cf` | 2026-09-18T00:42:14.038Z |
| 10 | `mintPiece` | 508586 | `26c517051b1ca33c0d807c58eef0de1ffb6a8fc1dbe2fad2c3efa1a12f74d8dd` | 2026-09-18T00:42:38.306Z |
| 11 | `publishAltair` | 508589 | `cb92579d7fe432f6ce1965f20e64bc7260cabafd6c0944f649012212253c1b81` | 2026-09-18T00:42:56.762Z |

### LLIAR — Ledger Liar

- Source: [LLIAR.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/17216362077b3c48da05f06d3a7b0be1b248e1ff/contracts/generated/LLIAR.compact); reference template: `NativeUnshieldedToken`.
- Contract address: `af0330b143e2ea01071a1435495f8be82cd689e8c5af8a05c5dd0df652f20a95`.
- Deployment transaction hash: `ea3acc74df49db1c1e99f872e9a4b041bb8413b6a49aa1aa0386069fda09a143`.
- Deployment transaction identifier: `00506a914ce46af617cecf7ff5a14f9bec7746d623c909493c5745ff53dc54599b`.
- Deployment block: **508592**; block hash: `6699865c2adf79357362eb4f29d2452a14babd0aedce333ed0a6ad306bb13bf2`.
- Block timestamp: **2026-09-18T00:43:00Z**; script recorded at: `2026-09-18T00:43:14.462Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `79f9e8eb2e21b11b475aad7ab7587b996cc091041a48d8dc39f0489d243ba8bb`.

The reference contradiction fixture, and the row that shows what MIP section 4 changed. Its metadata declares kind **2** (unshielded ledger) while the contract mints **7** native unshielded base units, which is kind **0**. Because the identity is `(contractAddress, domainSep, kind)` with the full kind byte, this is not a conflict inside one row: it is **two rows** — an `observed` kind-0 row carrying the mint and the colour and no name, and a `declared` kind-2 row carrying the name and no mint and no colour. Neither can hide or relabel the other (MIP sections 6.3 and 7.2), and there is no `inconsistent` state anywhere.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 508595 | `87145bb180fba12fd471d4e1fb3fde77b3b2278bd0920d53e74c4def709e79c9` | 2026-09-18T00:43:33.127Z |
| 1 | `mint` | 508599 | `7938eeebab0367aeeebe437a2cf22ea0673492222e1487e30daca74d070881ae` | 2026-09-18T00:43:56.821Z |

## Superseded deployments (pre-MIP layout, source `71c5b0b`)

The set below was deployed on 2026-09-17 under the earlier repository-local layout: event name `TokenMetadata`, no `val-type` byte, a 190-byte value, and a token table keyed on bit 0 of the kind byte (which is why its record carried a sixteenth row and an `inconsistent` status that the MIP does not define). **A MIP consumer ignores every event these contracts emitted** (MIP section 1). They are still deployed and still queryable; nothing was revoked or destroyed. They are kept here so that anyone holding the old addresses can see what became of them.

Pinned source revision: `71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6`. Deployment manifest SHA-256: `dad2f75a9839df4bf98b051bf4589ef330c0741b85252423828c4859c1f16503`. Recorded 2026-09-17; 11 contracts, 16 token records.

| ID | Reference name | Contract address (hex) | Deployment block |
|---|---|---|---|
| LSUN | Ledger Sun | `76c2fd63ad1a637dc5900e2bbfac47c2a30405eb3b8b2c0c32d675846c100058` | 497370 |
| LMOON | Ledger Moon | `9fe4724d67cb395791ad69ba040f8c7dae872b9e961bd766a390db3954694932` | 497524 |
| SSTAR | Shielded Star | `7d0bbc9546e0976f27a069e43490deb670ec0d51514c2da634b062e65b2938c7` | 497302 |
| SNEB | Shielded Nebula | `e7597c0205132b33c76d1df7f062ed022616807bd868d0fc101a65a89fee6fce` | 497479 |
| SGHOST | Shielded Ghost | `520b8ecf3517a9fa797352bb97f438ccab0aa8f3cc452d3b3ef57df519a77298` | 497493 |
| UCOM | Unshielded Comet | `40918a6666a2390010f189cdb535b5b17cdd9479f502241e02ec4a76a69eebf2` | 497358 |
| UMET | Unshielded Meteor | `f184f92ffe9f015d1a2cdb76d7b5621fe50714175360310b046c9a7fe8fee43e` | 497500 |
| UPROM | Unshielded Promise | `64f7b33d55c2647b6ce11a8a6c631f9558da6a6354f0ffa9a852cccc4c547da2` | 497518 |
| DAUR | Dual Aurora | `57244319c3660e539b6f7f66248e46642c0d31d862986bedb2c1d4186061d685` | 497382 |
| CNST | Constellations | `6cedc46ac5a8cda964c2493a753c2c4942d6e3ed7641bdd0c28e9b672cb1e97c` | 497399 |
| LLIAR | Ledger Liar | `b006a6647c26829987ec1bd59de1d4107019d7f54c097d3fdc25a4dddcf1231e` | 497538 |

The full pre-MIP record — per-row transaction tables, colours and domains — is the previous revision of this file, `git show fc1f4f4:stagenet-token-metadata-deployments.md`.

## Rechecking a deployment

Send this read-only GraphQL query to the indexer HTTP endpoint. Replace the address and deployment transaction hash to check another entry. The response should be ContractDeploy at the listed address and block, with transactionResult.status = SUCCESS.

```graphql
query VerifyRecordedDeployment {
  contractAction(address: "152827bc1d9ea7ecec0d13879e87a21ecf8f283804dfef16c9b805612acfea90",
    offset: { transactionOffset: { hash: "9a131d060981b73d8574bd2307f62d9e9fd90611704b9168aafe2ef1ad7287b6" } }) {
    __typename
    address
    transaction {
      hash
      block { height hash timestamp }
      ... on RegularTransaction { transactionResult { status } }
    }
  }
}
```

To see the metadata itself, ask the same indexer for the events of one publish transaction: `contractEvents(filter: { contractAddress: "…", transactionHash: "…", types: [MISC] })` returns `MiscContractEvent`s whose `name` is the 32 bytes above and whose `payload` is 256 bytes with the `val-type` byte at offset 65.

The file contains public deployment data only. Wallet mnemonics, seeds and private keys are not included.
