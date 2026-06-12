# ActionLink CLI Releases

This repository distributes closed-source public binary releases for ActionLink CLI.

The source code is not published here. The release assets contain only the public, user-facing hardware CLI build.

## Install

Download the archive for your operating system and CPU architecture from the latest release, then verify it before running.

```bash
# macOS / Linux
shasum -a 256 -c SHA256SUMS
cosign verify-blob --key cosign.pub --signature actionlink-<version>-<target>.<ext>.sig actionlink-<version>-<target>.<ext>
```

Windows users can verify the SHA256 checksum with PowerShell:

```powershell
Get-FileHash .\\actionlink-<version>-<target>.zip -Algorithm SHA256
```

## Public Command Surface

The public binary includes: login, logout, status, profile, actionset, community, doctor, portal, ble, joycon, and config.

Internal development, moderation, mock, simulation, plugin, and virtual HID tooling is not compiled into this public build.

## Support

Use GitHub Issues in this repository for packaging, install, checksum, signature, and release problems. For account or product support, use the official ActionLink support channel.
