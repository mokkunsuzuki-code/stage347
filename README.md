# REMEDA Stage346

## Multi-Artifact Verification Layer

Stage346 extends Stage345 by verifying multiple public verification artifacts as one connected evidence set.

## Purpose

Stage345 verified one downloaded GitHub Actions artifact:

```text
GitHub Run
↓
Artifact Download
↓
Artifact SHA256
↓
Session Manifest SHA256
↓
accept

Stage346 verifies the connected evidence set:

session_manifest.json
↓
signed_session_manifest.json
↓
external_anchor_receipt.json
↓
independent_verification_report.json
↓
github_artifact_verification_report.json
↓
artifact_download_verification_report.json
↓
multi_artifact_verification_report.json
What Stage346 Adds
Multi-artifact existence verification
Session manifest SHA256 verification
Signed session manifest SHA256 verification
Stage343 independent verification connection
Stage344 GitHub artifact verification connection
Stage345 artifact download verification connection
accept / reject multi-artifact decision
multi_artifact_verification_report.json
multi_artifact_verification_summary.txt
Public Files
docs/artifacts/multi_artifact_verification_report.json
docs/artifacts/multi_artifact_verification_summary.txt
docs/artifacts/artifact_download_verification_report.json
docs/artifacts/github_artifact_verification_report.json
docs/verification/independent_verification_report.json
docs/anchors/external_anchor_receipt.json
docs/session/session_manifest.json
docs/session/signed_session_manifest.json
Private / Ignored Files

The downloaded artifact directory remains intentionally excluded from GitHub:

downloaded_stage345_artifact/
downloaded_stage346_artifacts/
Safety Boundary

Stage346 does not publish:

private keys
attack code
dangerous prompts
exploit payloads
bypass procedures
automated attack logic
Meaning

Stage346 moves REMEDA/QSP from:

single artifact verification

to:

multi-artifact evidence set verification

This strengthens the evidence chain by verifying that multiple public artifacts agree with each other.

License

MIT License

Copyright (c) 2025 Motohiro Suzuki

---

## Stage347: Quantum-Safe Behavior Template Layer

Stage347 adds a quantum-safe behavior template layer on top of Stage346.

Stage346 verifies multiple public artifacts as one connected evidence set.
Stage347 extends that evidence set to PQC and QKD behavior metadata.

This stage is designed to connect older PQC/QKD implementation stages, such as QKD session logs, PQC handshake metadata, and failover metadata, into the current audit and verification rail.

### What Stage347 Adds

- PQC behavior templates
- QKD behavior templates
- ML-KEM metadata confirmation
- ML-DSA metadata confirmation
- SLH-DSA metadata confirmation
- QKD key-session metadata confirmation
- QKD failover metadata confirmation
- pass / fail / unknown decision output

### Public Artifacts

- `docs/quantum/quantum_safe_behavior_templates.json`
- `docs/quantum/quantum_safe_behavior_input.json`
- `docs/quantum/quantum_safe_behavior_decision.json`

### Safety Boundary

Stage347 publishes safe metadata only.

It does not publish:

- private keys
- raw QKD key material
- real cryptographic backend code
- exploit code
- attack procedures
- production QKD device configuration

### Decision Meaning

- `pass`: PQC/QKD behavior metadata satisfies the template
- `fail`: unsafe publication or misleading claim is detected
- `unknown`: evidence is insufficient

### Position

Stage347 connects:

Stage87-198 PQC/QKD implementation metadata

to

Stage346 multi-artifact verification.

This makes Stage347 the bridge between quantum-safe implementation history and the current QSP evidence verification system.
