# Quickring Share — downloads

## This is alpha software

Quickring Share is under active development. Several features shown in the
app are not finished, and some of what's in this README will go stale as
that changes — check the table below, not your memory of an earlier build.

**File sharing does not work yet.** Send and receive are the app's whole
reason to exist, and today the interface only shows sample data — nothing
is actually sent or received. If you're here for that, there's nothing to
try yet.

Don't rely on this build for anything that matters to you. Expect breaking
changes, missing features, and rough edges between releases.

## Feature status

Status vocabulary used below:

| Status | Meaning |
|---|---|
| **Works** | Verified working as described. |
| **In development** | Partially built; the core job isn't usable yet. |
| **UI only** | The screen exists; nothing behind it is wired up. |
| **Not implemented** | No code path for this exists yet. |
| **Broken** | It's supposed to work and currently doesn't. |

### App features

| Feature | Status | Notes |
|---|---|---|
| Device pairing | Works | Verified across platforms. |
| Home Assistant control | Works | Lights, switches, and climate verified end to end. It's currently the only integration that works end to end. |
| File sharing (send / receive) | Not implemented | The screen shows sample data. Nothing is actually sent or received. |
| Household services store | In development | Browsing and viewing service details work. Installing does not complete — there's no way yet to run the service, so install stops at the credentials step. |
| End-to-end encryption | Not implemented | Connections use TLS in transit. Messages pass through infrastructure that can read their contents and keeps them for 7 days to support offline delivery. |
| Per-device permissions | Not implemented | Access is household-wide: anyone signed in to the household can use a connected service from their own device. |
| Device revocation | Not implemented | Removing a device does not immediately end that device's active session. |
| Storage tiers / account screens | UI only | Not connected to a backend. |

### Desktop builds

| Platform | Status | Notes |
|---|---|---|
| macOS | Works | Unsigned. Gatekeeper will warn before you can open it. |
| Linux | Works | Unsigned. |
| Windows | Broken | The Windows build is currently unavailable; recent releases don't include a Windows binary. The last release that shipped one is `v0.1.29`. |
| Code signing / notarization | Not implemented | Not done on any platform yet. |

## What this repo is

This repo hosts the built desktop binaries for Quickring Share as GitHub
Releases. It's the target of `quickring.me/download`. The app's source
lives in a private repository — this repo exists only to publish and serve
built artifacts.

There's no source code to review here, and no issue history for the app
itself — just releases and their assets.

## Verifying a download

Every release includes a `SHA256SUMS` file alongside the binaries. After
downloading, check your file's hash against it, for example:

```sh
sha256sum -c SHA256SUMS --ignore-missing
```

on Linux, or on macOS:

```sh
shasum -a 256 -c SHA256SUMS --ignore-missing
```

**GitHub's "Latest" label can point to an older release than what's actually
newest.** GitHub excludes prereleases from the release marked "Latest," so
a newer prerelease build can exist without showing up there. As an example
of this in practice: the release currently marked "Latest" is `v0.1.29`,
while `v0.1.32` is available as a newer prerelease. If you want the most
recent build rather than the most recent stable-labeled one, check the full
[releases page](https://github.com/quickring/downloads/releases) rather than
following "Latest" alone.

## Reporting a problem

Open an issue in this repository:
[github.com/quickring/downloads/issues](https://github.com/quickring/downloads/issues).

This repo only hosts binaries, so an issue filed here is a reasonable place
to report a download or release problem (a missing platform build, a hash
mismatch, a broken link). For a problem with the app itself, say which
release and platform you're on.
