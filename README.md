# Community Mod Launcher

A lightweight launcher for finding and joining community servers for
**Arma 2: Operation Arrowhead** on Windows 10 and Windows 11.

This public repository contains only:

- official launcher releases;
- the signed launcher manifest;
- public documentation and possible external download sources.

The launcher source code is maintained in a separate private repository.

Repository content and launcher binaries are provided under the
[Community Mod Launcher Release Licence](LICENSE). Mandatory legal rights and
third-party ownership remain unaffected.

## Downloads

Launcher builds are published on the
[Releases](https://github.com/DeandlDernai/Epoch-Mod-Launcher-Releases/releases)
page. The launcher is portable and does not require installation.

Every release lists the SHA-256 checksum of its executable. Verify it before
running the file:

```powershell
(Get-FileHash -Algorithm SHA256 .\Community-Mod-Launcher-v1.0.0.exe).Hash
```

Only download builds from this repository. Executable files copied to other
websites or file hosts cannot be verified by us.

## Launcher data

The launcher receives all of its public data from a single signed manifest:

```text
data/launcher-manifest.json
data/launcher-manifest.json.sig
```

The manifest holds the server list, the mod catalogue with its external
download pages, the metadata of the Windows 11 BattlEye fix, the latest
released launcher version and the project links.

`launcher-manifest.json.sig` is a detached Ed25519 signature for the exact
bytes of the JSON file. It allows the launcher to reject modified or forged
data. It is not an encrypted file and contains no secret key.

The server list is generated from Steam server discovery data. Live
information such as availability, player count, ping, map and reported mod
hints is queried directly from the selected game server and is never treated as
an approval of anything.

## Why we do not host every mod

Most Arma 2 community mods were created by independent authors and teams. The
fact that a mod can be downloaded or is used by a game server does not
automatically grant us permission to copy and redistribute it from our own
infrastructure.

We therefore do not mirror third-party mod packages unless at least one of the
following can be verified:

- the published licence explicitly permits redistribution;
- the rights holder has given us permission;
- the package is distributed through an official source that permits this use.

When redistribution rights are unclear, the launcher may provide a possible
external project page or download source instead. Users may also need to
contact the operator of the server they want to join.

This approach protects mod authors, users and the project from unapproved or
modified packages. External links are informational references only. We do not
host or control their content and do not guarantee their availability,
authenticity, safety, licence status or continued ownership. A link is not an
endorsement of the external website or its files, and users leave the launcher
project when opening it. Users must assess the source and downloaded files
themselves.

## For mod authors

If you own or maintain a mod and want it listed through the launcher, or if you
want an existing link removed, please contact the project team on
[Discord](https://discord.gg/kjGXC7X93S). A takedown request is acted on first
and discussed afterwards.

For listing a mod we will need a verifiable connection to the official project,
for example:

- a message or change published through the official repository or website;
- confirmation from an established official community account;
- licence information that clearly identifies the package and redistribution
  terms.

Permission must cover the exact mod, versions and type of distribution. A
server operator possessing a copy of a mod is not automatically its rights
holder.

## Security

- The launcher never contains the Steam Web API key or signing private key.
- Published data is signed and verified before it is trusted. The signature is
  checked against the raw bytes before the file is parsed.
- **The launcher does not download mods.** It checks whether the mods a server
  requires are present locally and unmodified, and points to external sources.
- The Windows 11 BattlEye fix is not downloaded either. Users fetch the file
  themselves; the launcher only verifies it against the checksum from the
  signed manifest before installing it.
- Server-reported mod names are only hints and never authorize anything.
- External links are opened only on an explicit user action, always after a
  warning, and always over HTTPS.

Please report suspected manipulated files or unsafe download links privately
according to the [Security Policy](SECURITY.md) instead of publishing sensitive
security details.

## Disclaimer

This is an independent, voluntary community project provided without warranty.
It is not affiliated with or endorsed by Bohemia Interactive a.s., Valve
Corporation, BattlEye Innovations e.K. or the authors of third-party mods.

Arma, DayZ and related names and trademarks belong to their respective owners.
Operating the infrastructure used to provide launcher and server data incurs
ongoing costs. Any support is voluntary and does not purchase features,
services or preferential treatment.
