# Tappify Android SDK

Binary distribution documentation for the prepared `0.1.0` Android SDK. The
artifacts have not yet been published to Maven Central and no release tag exists.
This repository contains documentation only; implementation source is proprietary.
Public remote visibility is a separate hosting setting not established locally.

After publication, add `mavenCentral()` and select one dependency:

```kotlin
implementation("ai.tappify:tappify:0.1.0") // default: core + in-window UI
// Compose hosts instead use:
implementation("ai.tappify:tappify-compose:0.1.0") // default SDK + route helpers
```

Advanced hosts may choose `ai.tappify:tappify-core:0.1.0` for headless operation
or add `ai.tappify:tappify-ui:0.1.0` for explicit overlay installation. All four
artifacts use the same version. The aggregate has no implementation classes or
resources. Minimum Android API 24; compile/target API 36; JVM 17. Compose hosts
use BOM `2026.06.01`; ordinary Views hosts need no Compose APIs in host source.

Call `Tappify.start(application, "tpf_pk_<12 hex digits>", TappifyOptions(...))`
in `Application.onCreate`, using your approved API/dashboard URLs and build type.
The default SDK installs UI automatically through a private initializer. Direct
UI users call idempotent `TappifyUi.install()`, which can precede startup. Set
`manifestPlaceholders["tappifyActivationScheme"] = "tappify-<12 hex digits>"` to
match the app key. `Tappify.tagScreen("Checkout")` tags a logical screen;
Compose uses `TappifyScreen("Checkout")` and `BindTappify(navController) { ... }`.
Never put personal data or entity identifiers into screen names.

Every sources JAR intentionally contains only a README. Matching javadoc JARs
contain generated public JVM API reference, including compiler lowered Compose
signatures. No Kotlin/Java implementation or test fixtures are distributed.
Samples in the maintained SDK checkout (`sample-views`, `sample-compose`) use
placeholder keys and `.invalid` endpoints; request approved sample/live access
through support@tappify.ai. See [Android documentation](https://docs.tappify.ai)
for product documentation; runtime credentials are never public examples.

Releases include a Maven-layout binary ZIP with detached PGP signatures and
SHA-256/SHA-512 checksums (plus SHA-1/MD5 for repository compatibility). Obtain
the release key's full fingerprint through an independent trusted support
channel, then run `gpg --verify ARTIFACT.asc ARTIFACT` and compare
`shasum -a 256 ARTIFACT` with `ARTIFACT.sha256`. A test/local signing identity
must never be accepted as the release identity.

The overlay stays inside the host window and requests no SYSTEM_ALERT_WINDOW
or broad package visibility. A scoped credential provider and activation Activity
are the only intentional external SDK endpoints; the aggregate initializer is
private. Credentials/outbox are encrypted, startup is crash-shielded, and internal
auth/storage/kernel APIs are unsupported host interfaces. Keep tokens and signing
keys out of logs, repositories and screenshots. Review [release gates](RELEASE-GATES.md)
before accepting any claimed release. [Changelog](CHANGELOG.md).
