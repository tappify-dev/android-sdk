# Release acceptance

`0.1.0` remains unreleased. A maintainer must record evidence for the exact commit:
signed four-artifact/API/archive/checksum verification; independent repository-only
Views and Compose R8 full-mode consumers; actual non-skipped instrumentation in
each ordinary module (core, UI, Compose, Views sample, Compose sample) on API24 and
API36; a separate protected fresh-token live contract suite (the live-only
contract module is not an ordinary device gate); manual create/read/reply/resolve,
offline queue and replay, revocation, Views host and Compose host flows. Builds without a
device do not satisfy instrumentation. JVM tests do not satisfy live/manual flows.

Validation must come from the successful exact-commit protected workflow, including
API24/API36 job identities, a non-skipped fresh-token live suite, and an independent
allowed human's approval of every named walkthrough. Release verifies GitHub run,
workflow, artifact digest and review identities within 24 hours and signs that
authenticated record. This proves attribution and approval, not the semantic truth
of a human walkthrough; arbitrary JSON/URLs/booleans are not release evidence.

Only after these checks may a maintainer create annotated production-signed tag
`0.1.0`, which must resolve to the validated commit, approve the protected
release environment, upload the source-free binary bundle to Central Portal,
inspect/release the validated deployment, and create a public GitHub release.
Namespace ownership, release signing fingerprint, license, remote visibility and
Maven Central availability must be verified externally. Local initialization of
this documentation repository does not establish public visibility or publication.

Production performs a clean offline reconstruction and signs an attestation bound
to the exact bundle, commit/tag, coordinates, verified evidence, tools and results.
Upload independently rechecks the frozen signed candidate and attestation. These
private audit records are not public SDK artifacts. Release concurrency and a
persistent exact-version deployment fence block duplicate or ambiguous staging;
maintainers must reconcile interrupted uploads before retrying.
