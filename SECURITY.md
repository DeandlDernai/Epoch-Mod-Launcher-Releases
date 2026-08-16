# Security Policy

## Supported releases

Security fixes are provided only for the latest launcher release. Older
versions may remain available for reference but should not be considered
supported.

## Reporting a vulnerability

Please do not disclose suspected vulnerabilities, signing-key issues,
manipulated release files or unsafe download links in a public issue.

Use GitHub's private vulnerability reporting for this repository:

https://github.com/DeandlDernai/Epoch-Mod-Launcher-Releases/security/advisories/new

Include:

- the affected launcher version;
- a clear description of the issue and its impact;
- reproducible steps that do not contain personal data or secrets;
- relevant logs with tokens, passwords and private addresses removed.

Do not submit private keys, API keys, passwords, access tokens, personal data
or weaponized public demonstrations.

Receipt and next steps will be confirmed when the report has been reviewed.
There is currently no guaranteed response time or bug-bounty programme.

## Release verification

Download launcher builds only from this repository's Releases page and compare
the SHA-256 checksum published with the release.

The file `data/launcher-manifest.json.sig` is a detached Ed25519 signature for
the exact bytes of `data/launcher-manifest.json`. It is not a checksum,
encrypted content or a private key. The public key needed to verify it is built
into the launcher.
