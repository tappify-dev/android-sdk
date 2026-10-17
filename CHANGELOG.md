# Changelog

## 0.1.0 — prepared, unreleased

Four aligned binary Android artifacts: core runtime, in-window UI, dependency-only
default aggregate, and optional Compose helpers. Android 24+, compile/target 36,
JVM 17; Compose BOM 2026.06.01. Sources JARs are README-only; docs are generated
public API reference. Maven metadata, PGP signatures, checksums and repository-only
R8 consumer verification are part of the release process.

No public release has been created. API24/API36 instrumentation and live/manual
flows remain mandatory blockers; see [release gates](RELEASE-GATES.md).

Release verification hardening: bounded recursive archive scanning, lossless binary
API checks, exact bundle membership, candidate-byte verification, authenticated
device/live/manual approval and signed candidate attestations. Public artifacts
and platform requirements are unchanged; no release has been published.
