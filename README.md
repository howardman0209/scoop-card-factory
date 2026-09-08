# Card Factory Scoop bucket

Scoop bucket for the Card Factory EMV test-card CLI. This repository holds
package metadata only; the binaries live in the project's public release
repository.

**Staging distribution.** This bucket tracks staged Card Factory CLI releases
for the project's own testers. Treat installations from it as disposable and
reinstall rather than upgrade if the project's release repository moves to a
different account. The manifest is published together with each staged CLI
release.

## Install

```powershell
scoop bucket add howardman0209 https://github.com/howardman0209/scoop-card-factory
scoop install howardman0209/card-factory
card-factory --version
card-factory doctor --scheme mastercard
```

## Supported target

| Platform | Architecture |
| --- | --- |
| Windows | x64 |

ARM64 Windows is not published.

## Upgrade and removal

```powershell
scoop update
scoop update card-factory
scoop uninstall card-factory
```

Uninstalling removes only the package-manager copy. The downloaded CAP cache
and the current selection under `%LOCALAPPDATA%\CardFactory` survive upgrade,
uninstall, and reinstall.

## Prerequisites

The package carries a complete self-contained tree, including a Java runtime,
GlobalPlatformPro, and verified CAPs, so no separate Java, Gradle, Java Card
SDK, or `gp` installation is needed. A PC/SC reader and its operating-system
driver remain separate prerequisites, installed from their own vendor
instructions.
