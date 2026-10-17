# Release acceptance

`0.1.0` remains unreleased. A maintainer must record evidence for the exact commit:
signed four-artifact/API/archive/checksum verification; independent repository-only
Views and Compose R8 full-mode consumers; all instrumentation on API24 and API36;
a fresh-token live contract suite; manual create/read/reply/resolve, offline queue
and replay, revocation, Views host and Compose host flows. Builds without a
device do not satisfy instrumentation. JVM tests do not satisfy live/manual flows.

Only after these checks may a maintainer create tag `0.1.0`, approve the protected
release environment, upload the source-free binary bundle to Central Portal,
inspect/release the validated deployment, and create a public GitHub release.
Namespace ownership, release signing fingerprint, license, remote visibility and
Maven Central availability must be verified externally. Local initialization of
this documentation repository does not establish public visibility or publication.
