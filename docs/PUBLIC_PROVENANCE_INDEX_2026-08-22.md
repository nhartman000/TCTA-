# Public Provenance Index — Hartman / American Milestone Pre-Existing Technical Baseline

**Index date:** 2026-08-22  
**Purpose:** Cross-reference already-public Git history and finalized repository baselines.  
**Scope:** This index introduces no new third-party, NDA, or collaborative technical disclosure. It points to existing public records and finalized repository states.

> This document is a provenance index, not a legal determination of patentability, inventorship, ownership, priority, or claim scope. Git history and the content actually disclosed in each dated commit remain the primary evidence.

## Pre-existing public chronology

The following public commits predate the August 2026 cross-architecture discussions and are retained as historical provenance points:

- **2026-03-29 — TCTA / Transform Algebra**
  - `6163f09992f624f90f18c367020ea8d073c90635` — *Create README.md with Transform Algebra axioms and description*
  - `cd211deaa9630c4980cf76022e7536f423b7f25d` — *Add Transform Algebra axioms and formal definition*
  - `275ea2e061b8fd533273bf5e511584a34418ec86` — *Create GITSON specification file*
  - `0ab42512c1fbfafcfa896ee6e97ad63929f9a72c` — *Create g8son example file for gate definition and transform trace in examples directory*
  - `21e5ee86535296e003f1d5f8ca09451141744dbc` — *Create gst_context_layer_example.gitson file with gestalt context layer example*
  - `fd08ac8c328d8c06120c18384679679e9bd69ac7` — *Create mg8_execution_trace_example.gitson file with orchestration execution trace example*

- **2026-04-22 — MG8 Engine public implementation line**
  - `d1df04ff9a448f71ba7618cbd70d64ccb45e7f5c` — *Create tote_example.mg8*
  - `83126156adbe425600b04ba1083b447a5b03fd83` — *chore: clean up for public release - minimal Nych + ADSR foundation*

- **2026-04-29 — M-Gate / NYCH / trajectory and timeline implementation line**
  - `65c8b55f044448de91672cd99b183dac27c9f27e` — *Added ADSR gating, Nych, Recursive Optimizer, Timeline, and APK export skeleton*
  - `51081b7d906a330e33bc1c358394aa6723d94ccd` — *Enhanced optimizer with better ADSR flow, Nych symbols, and rich CLI output*
  - `43770dd6e74d591d10777f26800944229fb96939` — *Added real LLM-powered editing via Gemini + timeline navigation*
  - `7e8786a59de7dc4f9f11f0a3e8e29af326914ab7` — *Added Timeline Explorer + improved APK manifests*

These commits should be evaluated according to the material actually present in the commit, not merely the commit title.

## Canonicalized core baselines finalized 2026-08-22

- `TCTA-` — `b9bfd66efcc3d0088cd9bdc27644feb833ee2810` — *Establish canonical TCTA Volume 1 baseline*
- `TCTA-` — `6fec8a2beeed149132dc96a0a8ba1019a4947290` — *Mark TCTA GITSon specification as historical auxiliary material (#2)*
- `mg8` — `1d216cbc7ae8617465e54c8af8a7b499678b797c` — *Establish canonical MG8 .mg8 unit specification*
- `mg8` — `6e35987a2f5be9e97ac1474441e4bb53dc2870d2` — *Complete MG8 file-family registry and interim ORK/MG8PK specs (#2)*
- `gst` — `49bfd8d19ba70fe86f12f3213548a8a9c8ceeaec` — *Establish canonical GST .gst state specification*
- `g8son` — `421f76e7f893908707ddd4e492f079fa93077189` — *Establish canonical G8SON .g8son specification*
- `qson-` — `fbd3fe8c5127c979b1058a486878e44702172d0d` — *Establish canonical QSON .qson trace specification*
- `mgate-keeper` — `edcd3691ec149452f364f136747e832ea68b2d74` — *Fix MGate Keeper control injection and repository hygiene*
- `mg8-engine` — `8cb5eaa3cc54c1c2527eab7a4a62ceaceded615d` — *Align mg8-engine with canonical MG8 file-family interfaces (#2)*
- `mgate-suite` — `9854bf99c6c793aac830ac46a5e8608213e6fd99` — *Separate historical mgate-suite profile from canonical MG8 standards (#1)*
- `nych` — `768743932a180afbd3c756c07a72091faa4b335a` — *Repair NYCH packaging, encoding, CI, and repository hygiene (#1)*

## Reviewed application repair baselines finalized 2026-08-22

The following repair series were reviewed through pull requests and merged without squashing so their individual commit chronology remains available:

- `kadmon` — merge `fbfc82c4e7e79a422dfc7614569203031572a432` — *Repair Kadmon provider and runtime security boundaries*
- `Medicode-Ai` — merge `5a8c22d15130b821fe0e37a6dcae6ec088e10453` — *Move MediCode AI calls behind a server boundary*
- `aether_Studio` — merge `10c405fa2895f219dd132b14f1e2e5862a360f8d` — *Repair Aether provider, workspace, and build boundaries*
- `Synthesizer` — merge `a12f528bfe00dbb67ee69341959cb27143895e39` — *Harden Synthesizer AI provider runtime*
- `Nych-Ozone-Layer` — merge `4c4e046925bb31fd88da172d01697092669b4029` — *Repair Ozone Layer credentials, runtime, history, and audit semantics*

## Boundary statement

This index concerns Hartman / American Milestone repository material and does not incorporate unpublished third-party research, private correspondence, NDA text, confidential disclosures, or later joint synthesis. Conceptual overlap by itself does not establish derivation, inventorship, ownership, or joint development.

For technical scope, use the repository's dated files and commits. For the current TCTA/HDRP pre-existing baseline and its explicit IP boundary, see `docs/PROVENANCE.md`.
