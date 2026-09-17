# Token Metadata OnChain — Stagenet deployment record

Last updated: 2026-09-17T20:26:14Z

This file records the existing reference deployments from the pinned repository manifest. No new deployment transactions were submitted while preparing this record. All 11 deployment addresses, transaction hashes, block heights, and successful transaction results were independently checked against the public Stagenet indexer.

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
| Pinned source revision | `71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6` |
| Compiler / runtime | Compact 0.34.0 / compact-runtime 0.19.0 |
| Ledger dependency | `@midnightntwrk/ledger-v9@1.0.0-rc.3` |
| Recorded deployment date | 2026-09-17 UTC |
| Deployment verification | 11/11 `ContractDeploy`, transaction result `SUCCESS`; checked 2026-09-17T20:26:14Z |
| Token fixture recorded at | 2026-09-17T06:20:14.133Z |
| Deployment manifest SHA-256 | `dad2f75a9839df4bf98b051bf4589ef330c0741b85252423828c4859c1f16503` |

Source links: [deployment manifest](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/deployments/stagenet-deployment.json), [reference set](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/deployments/reference-set.json), [recorded token fixture](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/fixtures/stagenet/expected-tokens.json), [metadata standard](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/TOKEN-METADATA.md), [toolchain and deployment instructions](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/README.md), [UmbraDB token indexer PR #19](https://github.com/acedward/UmbraDB/pull/19).

The [Compact/MinoCrab K-size comparison](token-metadata-k-sizes.md) measures equivalent metadata routines. It is an off-chain compiler experiment and does not replace these deployed artifacts, verifiers, addresses, or transaction facts.

## Contract address directory

11 contract addresses correspond to 16 token records: DAUR contributes two kinds and CNST contributes five pieces. Names below are reference labels; published values and exceptions are documented later.

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

## Recorded token metadata

Metadata, native mint counts, and amounts are the pinned fixture snapshot, not a fresh scan of later activity. The status column is the expected UmbraDB classification from that fixture. Amounts are base units; native mint totals are not circulating supply and do not describe ledger-token balances.

| Token record | Published name | Published symbol | Decimals | Storage / kind | Expected status | Native mints | Native amount |
|---|---|---|---|---|---|---|---|
| LSUN | Ledger Sun | LSUN | 6 | ledger / unshielded | declared | 0 | 0 |
| LMOON | Ledger Moon (renamed) | LMOON | 8 | ledger / unshielded | declared | 0 | 0 |
| SSTAR | Shielded Star | SSTAR | 6 | native / shielded | described | 1 | 5000000 |
| SNEB | Shielded Nebula | SNEB | 0 | native / shielded | described | 2 | 3 |
| SGHOST | not published | not published | not published | native / shielded | observed | 1 | 13 |
| UCOM | Unshielded Comet | UCOM | 6 | native / unshielded | described | 1 | 2500000 |
| UMET | Unshielded Meteor | UMET | 2 | native / unshielded | described | 3 | 600 |
| UPROM | Unshielded Promise | UPROM | 6 | native / unshielded | declared | 0 | 0 |
| DAUR / unshielded | Dual Aurora | DAUR | 6 | native / unshielded | described | 1 | 2000 |
| DAUR / shielded | Dual Aurora | DAUR | 6 | native / shielded | described | 1 | 1000 |
| CNST / orion | Constellations · Orion | CNST | 0 | native / shielded | described | 1 | 1 |
| CNST / lyra | Constellations · Lyra | CNST | 0 | native / shielded | described | 1 | 1 |
| CNST / cygnus | Constellations · Cygnus | CNST | 0 | native / shielded | described | 1 | 1 |
| CNST / vega | Constellations · Vega | CNST | 0 | native / shielded | described | 1 | 1 |
| CNST / altair | Constellations · Altair | CNST | 0 | native / shielded | described | 1 | 1 |
| LLIAR | Ledger Liar | LLIAR | 6 | native / unshielded | inconsistent | 1 | 7 |

## Token domains and native colors

Every domain text below is UTF-8 padded with trailing zero bytes to exactly 32 bytes. Ledger tokens LSUN and LMOON have no native color: the derivations stored as tokenColor for those rows in the deployment manifest must not be used as token identifiers. LLIAR uses its recorded native color despite its conflicting metadata declaration.

| Token record | Domain text | Native color (hex) |
|---|---|---|
| LSUN | `umbra:lsun` | none — ledger token |
| LMOON | `umbra:lmoon` | none — ledger token |
| SSTAR | `umbra:sstar` | `a988a5eccbc9ba6faa93c72aa344db0776dae4962a6c67dbe1b1633a883df997` |
| SNEB | `umbra:sneb` | `b147dc1b324117e5c5f8d06cf8b2277b4067b1feeb285f00b76e692e1f760566` |
| SGHOST | `umbra:sghost` | `14422c1082c4af5037779011e96926fd13f59786fa36e6df61a45c41d75e7f11` |
| UCOM | `umbra:ucom` | `b92eb7e767009c202a9419a7f8952002959d42c2a1672efc7171a8af1e0c7fa4` |
| UMET | `umbra:umet` | `1677a42ad8a035718b84662852e9be4961870b1d601c2b35a709be68ebee0438` |
| UPROM | `umbra:uprom` | `19e18ca3ee12f6e93e24ec53ca5dfe3f3904509767e3ffd8e5fd02498b471cf9` |
| DAUR / unshielded | `umbra:daur` | `0cc414ba41fbfcc579fcc23abc40d15686ba0256e366e53e8145683a97fef136` |
| DAUR / shielded | `umbra:daur` | `0cc414ba41fbfcc579fcc23abc40d15686ba0256e366e53e8145683a97fef136` |
| CNST / orion | `cnst:orion` | `00a3eb500a600b975ff35b9ac624513e0c1c4277f794a3df4d5dfd3e0b487b93` |
| CNST / lyra | `cnst:lyra` | `cd99dea3f3a4e691f045d76e4b98747b68e3fa4f90b9c8414337a5b3e6758081` |
| CNST / cygnus | `cnst:cygnus` | `4d04dab56afbb37ce2b135937f6efeac132b7a7e79139daec9854fc908da2868` |
| CNST / vega | `cnst:vega` | `3d9180f0b7b00dd52c8a35c0ee1558d901e11619bcea9e2e4aaef1a0722bf64f` |
| CNST / altair | `cnst:altair` | `9e7032f27cb031d4a3518d970391c0d775485b8f15f41cbf18d4142c7e1f15b1` |
| LLIAR | `umbra:lliar` | `322445b1187ef7c276c68740958ed158f32b7582b2ad8b4d67ef05c9b5de988d` |

## Deployment and call details

Deployment block times below come from the live indexer query. The script recorded-at time comes from the pinned manifest and is later than the block timestamp. Post-deployment calls are transcribed from the manifest, where every listed call has status SucceedEntirely; those individual calls were not independently re-queried for this record.

### LSUN — Ledger Sun

- Source: [LSUN.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/LSUN.compact); reference template: `LedgerToken`.
- Contract address: `76c2fd63ad1a637dc5900e2bbfac47c2a30405eb3b8b2c0c32d675846c100058`.
- Deployment transaction hash: `1439d7af123095c763fee76ebca7481401637a7d3d3a0d4d71d7d0daae632262`.
- Deployment transaction identifier: `00e1015fb005a27bef3a51cc3a671f0cd8c090a2d2807f645c3aeab2419b6d8acc`.
- Deployment block: **497370**; block hash: `0dc542c695e3cbe5fe9065c31127efc5991f0fcaef9f8ce3687033d2de3be1a4`.
- Block timestamp: **2026-09-17T06:00:48Z**; script recorded at: `2026-09-17T06:01:01.893Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `6e0c3e6fdfd16b0340c0d4096e88a126d118e8b5e1136ee3f1846f85933b0523`.

Ledger balances: the reference sequence credits 1,000,000 base units and transfers 250,000. These are contract-state operations, not native mint effects; the token has no native color.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 497373 | `cd51d104924895a1f8601568e88420d3bb0dc671188f9b3715b7ea15e24a5be8` | 2026-09-17T06:01:20.291Z |
| 1 | `ledgerMint` | 497376 | `2643633e666d18a989919d2875272e3c411c3ec2f6e1ea3a6908000f1e0b2a9d` | 2026-09-17T06:01:38.993Z |
| 2 | `transfer` | 497379 | `34e0052c4ffb7387a06c19a0d98aebb089cb9c563ffccae6798f9adcad760f44` | 2026-09-17T06:01:56.360Z |

### LMOON — Ledger Moon

- Source: [LMOON.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/LMOON.compact); reference template: `LedgerToken`.
- Contract address: `9fe4724d67cb395791ad69ba040f8c7dae872b9e961bd766a390db3954694932`.
- Deployment transaction hash: `98617142cff03d0ebef93a4f329b8f37515f14d34a415227b65fa759e8f4a898`.
- Deployment transaction identifier: `00e5eab7c7fa2f05de56d12789699ffcdc586cd7317b3e7ea9e1a49341409d2c03`.
- Deployment block: **497524**; block hash: `dafdb36d892ae3bab8308b395734cbe6052aad6fae9633fb12fb9afa067c1c4c`.
- Block timestamp: **2026-09-17T06:16:12Z**; script recorded at: `2026-09-17T06:16:27.233Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `c6cd3d0e773f9285575ee39945b68575e31064f6f2536fdebd83cb1548706258`.

Published initially as Ledger Moon, then changed to Ledger Moon (renamed). The reference sequence credits 5,000,000 base units in contract state. The token has no native color.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 497528 | `8f8bbd0e98101dc90bc0363efe6ed8e8e05ec42f76c07e3e097eb15c790817db` | 2026-09-17T06:16:51.056Z |
| 1 | `ledgerMint` | 497532 | `6d93e088948f48eb2b6104aa445eb82020087125d0aa6de50d535c5ad6952cf6` | 2026-09-17T06:17:15.075Z |
| 2 | `publishRename` | 497535 | `bd5fc946efc966cc9f70afd3a50db8049c63e9de8c5a6aac3747b27364f08956` | 2026-09-17T06:17:32.224Z |

### SSTAR — Shielded Star

- Source: [SSTAR.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/SSTAR.compact); reference template: `NativeShieldedToken`.
- Contract address: `7d0bbc9546e0976f27a069e43490deb670ec0d51514c2da634b062e65b2938c7`.
- Deployment transaction hash: `e95797175c485df7d0c5a809e0e3178909c18f43fc63f9fae96a0b242390f34d`.
- Deployment transaction identifier: `008cbb9c0c79455bc47bc43a7fb69b3ba92d007e5476edc87cc69c36e08627edae`.
- Deployment block: **497302**; block hash: `ce8bca97a9055a0599edcbd47374da69d30d3ceafb73bf27aff7907b290f873a`.
- Block timestamp: **2026-09-17T05:54:00Z**; script recorded at: `2026-09-17T05:54:14.976Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `34eec417c635cf3bb5d821a58f5abc3d4bf10f45aa7a9156de10383d3c4681e6`.

Publishes metadata, then mints 5,000,000 native shielded base units.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 497306 | `ca7aa26e6ac435dac92678d4c4ada1226d5fbc435f52ee0b043fe9af55666e56` | 2026-09-17T05:54:38.466Z |
| 1 | `mint` | 497355 | `403336bc75c82f3690647c783282d891beecf8ae897427e7dc06dc0781473784` | 2026-09-17T05:59:32.378Z |

### SNEB — Shielded Nebula

- Source: [SNEB.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/SNEB.compact); reference template: `NativeShieldedToken`.
- Contract address: `e7597c0205132b33c76d1df7f062ed022616807bd868d0fc101a65a89fee6fce`.
- Deployment transaction hash: `06dda4c041b31830de6bc816f5a45269cc5b6c07ea5cee0412c0dcb3bf1626f7`.
- Deployment transaction identifier: `003a4d77990c25a03c5dd8835ee901c6f36a68eb66bf3c1ce255f534aa682e0633`.
- Deployment block: **497479**; block hash: `b98cf0be58f7d3b95f78f9ad201d8c35ea83f6179d3d702d00e2e5e59ec4ab23`.
- Block timestamp: **2026-09-17T06:11:42Z**; script recorded at: `2026-09-17T06:11:56.157Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `057e23444423e4a4d6784705f8af8d058f7489d6e670c8e2f9978aa32fd7b6ee`.

Publishes metadata and multipart JSON in metadata/0 through metadata/5, then mints 1 and 2 native shielded units.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 497482 | `d8cd47f423f1b4b9dda0ac6b9247f4d319319dd87882276effca5045981767c1` | 2026-09-17T06:12:14.473Z |
| 1 | `mint` | 497486 | `16f89052b957025fef69be9f16f1f3eba19acd59812739a4436942df94a0297b` | 2026-09-17T06:12:38.753Z |
| 2 | `mint` | 497490 | `deac4287d5aa3efcea81df8fb581a3dbd3b1833ab9112bca0be77b9f5338c058` | 2026-09-17T06:13:02.741Z |

### SGHOST — Shielded Ghost

- Source: [SGHOST.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/SGHOST.compact); reference template: `NativeShieldedToken`.
- Contract address: `520b8ecf3517a9fa797352bb97f438ccab0aa8f3cc452d3b3ef57df519a77298`.
- Deployment transaction hash: `fd1de354173b232bc19f2ecdf75be32a2c5c47e5e5ceee8219fa020d5bb597b0`.
- Deployment transaction identifier: `003eddec1fe594610f6c419894477bc9b0c833bfae51ca3a2320866b17d6d07df0`.
- Deployment block: **497493**; block hash: `8ca6418945ebaed23fc7da62afc73efbb8c97671e276834fb77e194e68ca159e`.
- Block timestamp: **2026-09-17T06:13:06Z**; script recorded at: `2026-09-17T06:13:20.477Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `ccaa94d5265e30cabd6085866422251b641a04c5551b3b6968aa5e623d08e395`.

Shielded Ghost / SGHOST is a reference label only. No name, symbol, or decimals were published; the recorded token metadata is null for all three fields. The mint creates 13 native shielded base units.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `mint` | 497497 | `fcc68933c203738b7fa93b806e2231b86e5f1b3fe590ac6f2729dd1f10cfdd77` | 2026-09-17T06:13:44.161Z |

### UCOM — Unshielded Comet

- Source: [UCOM.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/UCOM.compact); reference template: `NativeUnshieldedToken`.
- Contract address: `40918a6666a2390010f189cdb535b5b17cdd9479f502241e02ec4a76a69eebf2`.
- Deployment transaction hash: `a0a9b5b6abcfae62b6b80bd2fa791843127856bf0da1c8be128eb23171bf014e`.
- Deployment transaction identifier: `00f54fb6a24241dca4f7cc994e08b0764626d27c5ec834f07b1d384543f895c22e`.
- Deployment block: **497358**; block hash: `32aae1b105d0b4a1ebcd6d56794df9e6eb9e669ecf0ff23eecde8cc1c161bf37`.
- Block timestamp: **2026-09-17T05:59:36Z**; script recorded at: `2026-09-17T05:59:51.211Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `7158abf8c9b2ab8fba211807dbdf46985205b89a764ab3789f3d265224c6537c`.

Publishes metadata, then mints 2,500,000 native unshielded base units.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 497363 | `3284003ada9f8812dbe1a94132a9e02de409be4900eb9d2b4b5eb87bd7649635` | 2026-09-17T06:00:20.250Z |
| 1 | `mint` | 497367 | `6247a89afa6aba2b81e09447da75cbd4b5d7b307f2859b547ccc2f3d725eb0d5` | 2026-09-17T06:00:44.337Z |

### UMET — Unshielded Meteor

- Source: [UMET.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/UMET.compact); reference template: `NativeUnshieldedToken`.
- Contract address: `f184f92ffe9f015d1a2cdb76d7b5621fe50714175360310b046c9a7fe8fee43e`.
- Deployment transaction hash: `6d41f42213c3dacce511bed657a035d0233709dc3919ad9540b921fb45805448`.
- Deployment transaction identifier: `00086c26fc45bf03ec1a6b9443716022257cc9a2d892e5c880d4fd66419691fdd2`.
- Deployment block: **497500**; block hash: `4fce0d107c84c60f5527f2a1f04538988f263c821b7539aca6515a05a2397703`.
- Block timestamp: **2026-09-17T06:13:48Z**; script recorded at: `2026-09-17T06:14:02.849Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `3f4442b5d2bd8af96a66c2861fd65099b6de2f162fc870558596e737a27262a5`.

Mints 100, 200, and 300 native unshielded base units before publishing metadata; exercises the observed-to-described transition.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `mint` | 497504 | `3e27a0879bcfc38dc65eaf7db342c170399783380c139fe6658311e85869f457` | 2026-09-17T06:14:26.598Z |
| 1 | `mint` | 497508 | `a3d90cfe4c0d374e9d384a50d6cf60dae048f27ab8bedf9b30025008028f71e6` | 2026-09-17T06:14:50.744Z |
| 2 | `mint` | 497512 | `5916ccb98dbfa8172995670df6f391afadf649bb2b182e0fb71844a45ded61a3` | 2026-09-17T06:15:14.660Z |
| 3 | `publishMetadata` | 497515 | `7c2644c1249c1082a7e49b62ad79236f93e35cbd6fb98d73e3dc9b28fa185a98` | 2026-09-17T06:15:32.095Z |

### UPROM — Unshielded Promise

- Source: [UPROM.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/UPROM.compact); reference template: `NativeUnshieldedToken`.
- Contract address: `64f7b33d55c2647b6ce11a8a6c631f9558da6a6354f0ffa9a852cccc4c547da2`.
- Deployment transaction hash: `6b49da50bc65fde667244d6f622f8995affb72974f45a2eca973a261fdb9322f`.
- Deployment transaction identifier: `00053e07132960b94be8f03d52c864305743d134f1ea3588f1171145981bf35368`.
- Deployment block: **497518**; block hash: `aa0313727ba67fd8127353683d8d87c04252805ced0e3df9b9832a012790bc18`.
- Block timestamp: **2026-09-17T06:15:36Z**; script recorded at: `2026-09-17T06:15:50.978Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `b1e0c0d2a15636aaea05106f880fc31ab4592c7af95ce7b95a48bb812d400d6a`.

Publishes metadata without minting. Its native color is derivable, but the recorded native mint count is zero.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 497521 | `725569eea2b4f3a7be502d4d461cdc6301e00bc1fda290009429485e30395d75` | 2026-09-17T06:16:08.046Z |

### DAUR — Dual Aurora

- Source: [DAUR.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/DAUR.compact); reference template: `NativeDualToken`.
- Contract address: `57244319c3660e539b6f7f66248e46642c0d31d862986bedb2c1d4186061d685`.
- Deployment transaction hash: `3a892dc137614d410b2faff51dbad7fad2a99969b26d0513bd966e91135ed8ed`.
- Deployment transaction identifier: `00652d5972dbeb57be4dff3186eb9fb2bdb50d0af32337282e1177f3c526406e6a`.
- Deployment block: **497382**; block hash: `f228f234d2d06904b0972fc65a68f05c76a94c5477ce0c30f34420aab04d4099`.
- Block timestamp: **2026-09-17T06:02:00Z**; script recorded at: `2026-09-17T06:02:14.256Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `5ffe2786e1a57a696e92423e86ce6947da6b7dcfdb9d7c77e5bb112fa8c48d2d`.

One contract and domain separator produce two token records: shielded and unshielded. Both share the same 32-byte color; the reference mints 1,000 shielded and 2,000 unshielded base units.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishUnshielded` | 497385 | `3ca0b8329d36bdd02c6bb336ce37fa8daa9a76fd34e697795e9257b40ce128b4` | 2026-09-17T06:02:32.398Z |
| 1 | `publishShielded` | 497388 | `08c0889ccca19a30808043f3a52de497662cfc46a57f36069d0ba76c9bd1e5e4` | 2026-09-17T06:02:49.831Z |
| 2 | `mintShielded` | 497392 | `1569078f5a3333aa84d0baf1ed2343cde4fd887f6034dc200c467247bae7b92c` | 2026-09-17T06:03:13.977Z |
| 3 | `mintUnshielded` | 497396 | `66e053366275aaa46201b833cc17920c761975b472ce88f7e0d0304b660d1ea3` | 2026-09-17T06:03:37.792Z |

### CNST — Constellations

- Source: [CNST.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/CNST.compact); reference template: `ShieldedCollection`.
- Contract address: `6cedc46ac5a8cda964c2493a753c2c4942d6e3ed7641bdd0c28e9b672cb1e97c`.
- Deployment transaction hash: `3c75c42298fb4355f3946f4386502c8eaded7c0a07a8e91bfa5f81923689a5a2`.
- Deployment transaction identifier: `00f7eeab9635b11771fa763c344113176091110ba225e1c617da79f53d08adfed7`.
- Deployment block: **497399**; block hash: `fa6980e9a3b0593a4149edf20e0b07724a3ae400b5eff00ae7db773f7d2db82c`.
- Block timestamp: **2026-09-17T06:03:42Z**; script recorded at: `2026-09-17T06:03:57.116Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `d3c76108bc30debc4f58d291a925ea0f79090e118f8d523f66991adee9098ccc`.

One contract holds five shielded pieces: Orion, Lyra, Cygnus, Vega, and Altair. Each has its own domain separator and color. Orion magnitude updates are 0.18 → 0.42 → 1.25. Recorded tokenUri values point to http://localhost:10020/constellations/{piece}; these are local demonstration resolver URLs, not a public hosted metadata service.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `mintPiece` | 497403 | `a80d3d0674544837d4d74702348d6e70cc80161fc40e7f9ed0118bb0cea90e2f` | 2026-09-17T06:04:20.731Z |
| 1 | `publishOrion` | 497407 | `6b30eeab3c39549f086ad3ec893e7d81f0a6a50873d53b211567ee15bda7ef51` | 2026-09-17T06:04:44.597Z |
| 2 | `updateOrion1` | 497411 | `de9e90a0bea8cd16c1c4e2be587bfda7b8cfc7d3199b9b66d1b76ccd65eeb6d6` | 2026-09-17T06:05:08.584Z |
| 3 | `updateOrion2` | 497414 | `5f953c7439a7bc408508663ee59f86407fc8cc76d6618956483f1fbf60e56f69` | 2026-09-17T06:05:25.966Z |
| 4 | `mintPiece` | 497418 | `f5dfa612d229a05e5002eeae84085863c3c19800ac8d94646c567ffa025e7825` | 2026-09-17T06:05:50.207Z |
| 5 | `publishLyra` | 497421 | `251c639ee9d91a1ea88a7b9675c6003dc45a8607601203a3163987c9b0819026` | 2026-09-17T06:06:08.692Z |
| 6 | `mintPiece` | 497425 | `0def795054303f32d4a10bb8244ce66dd27f58e4657303784ca3614dba8ebc92` | 2026-09-17T06:06:32.909Z |
| 7 | `publishCygnus` | 497428 | `4b0d51d23cb2c01b27f7c981e72290152ed631a9f9e1d159fc58ac19e9810b37` | 2026-09-17T06:06:50.019Z |
| 8 | `mintPiece` | 497432 | `edbe3db225d6faa3278eac4571175d2e864645a3e1c30329339008ca7716b950` | 2026-09-17T06:07:14.396Z |
| 9 | `publishVega` | 497435 | `d946c24a9713f6e52974b167160ca0a31b1566b5c3fddb9d1b7976d7e273e48e` | 2026-09-17T06:07:32.808Z |
| 10 | `mintPiece` | 497439 | `03089d2ff33b2d379a82f5f08824e5fa7e077bbe3225dcbc92c81ae9fdf907a8` | 2026-09-17T06:07:57.006Z |
| 11 | `publishAltair` | 497442 | `772055212d7fa0312cc46141f1dff887862f21b572b1ff0e0dd414d59e5222ea` | 2026-09-17T06:08:14.197Z |

### LLIAR — Ledger Liar

- Source: [LLIAR.compact](https://github.com/acedward/mip-erc7496-midnight-contracts/blob/71c5b0b5fc0503187df5fb7bb67687b3a5c55ef6/contracts/generated/LLIAR.compact); reference template: `NativeUnshieldedToken`.
- Contract address: `b006a6647c26829987ec1bd59de1d4107019d7f54c097d3fdc25a4dddcf1231e`.
- Deployment transaction hash: `4371af40438b44abf29cd568a2a740eeafd204b5fbfdd89ef046f65cda13da27`.
- Deployment transaction identifier: `002a9183fd830203bf34a35879254a6b18feb5ff7a1aa240750788482df6f3c0b1`.
- Deployment block: **497538**; block hash: `750d81946e352c4d7f26d0892999db2b3fb1b56b554a7ebba1b6a33578047af4`.
- Block timestamp: **2026-09-17T06:17:36Z**; script recorded at: `2026-09-17T06:17:51.154Z`.
- Live deployment verification: `ContractDeploy`, `SUCCESS`.
- Artifact SHA-256 recorded by deployment script: `4ef3204538ec1e3ee02b7b0e7740711486fd7dad200f249e7f51e34e27a0cf83`.

Intentional inconsistency fixture: metadata declares ledger kind 2, but the contract mints 7 native unshielded base units. Expected indexer status is inconsistent, with observed native storage. The pinned expected-tokens fixture has color=null for this row; this document records the native color from the deployment manifest instead and does not treat the ledger declaration as authoritative.

| Step | Circuit | Block | Transaction hash | Recorded at (UTC) |
|---|---|---|---|---|
| 0 | `publishMetadata` | 497542 | `5208e34a1b52b838fb89c8a3ffa195491e3ee100532ff0837fee1eb5e55c3633` | 2026-09-17T06:18:14.924Z |
| 1 | `mint` | 497546 | `9e1786cb028593e9fa346f772524a8d67e5ee272e56e3d84afe7b420fa889cfe` | 2026-09-17T06:18:37.597Z |

## Rechecking a deployment

Send this read-only GraphQL query to the indexer HTTP endpoint. Replace the address and deployment transaction hash to check another entry. The response should be ContractDeploy at the listed address and block, with transactionResult.status = SUCCESS.

```graphql
query VerifyRecordedDeployment {
  contractAction(address: "7d0bbc9546e0976f27a069e43490deb670ec0d51514c2da634b062e65b2938c7",
    offset: { transactionOffset: { hash: "e95797175c485df7d0c5a809e0e3178909c18f43fc63f9fae96a0b242390f34d" } }) {
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

The file contains public deployment data only. Wallet mnemonics, seeds, and private keys are not included.
