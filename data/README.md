# Published launcher data

This directory is maintained automatically by the publishing task on the
server. It contains:

```text
launcher-manifest.json
launcher-manifest.json.sig
```

The manifest holds the server list, the mod catalogue, the metadata of the
Windows 11 BattlEye fix, the latest released launcher version and the project
links. The launcher reads nothing else from this repository.

Do not edit these files manually. The signature is created from the exact JSON
bytes; reformatting, re-encoding or changing a single character invalidates it,
and every installed launcher will then reject the file.
