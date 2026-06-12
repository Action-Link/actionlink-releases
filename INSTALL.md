## Verifying ActionLink CLI Releases

Each release contains:

- platform archives named `actionlink-<version>-<target>.<zip|tar.gz>`
- `SHA256SUMS`
- detached cosign signatures (`*.sig`)
- `cosign.pub`
- `release-manifest.json`

Always verify checksums before extracting an archive. On macOS and Windows, binaries are also platform-signed by ActionLink.

### macOS / Linux

```bash
shasum -a 256 -c SHA256SUMS
cosign verify-blob --key cosign.pub --signature actionlink-<version>-<target>.<ext>.sig actionlink-<version>-<target>.<ext>
tar -xzf actionlink-<version>-<target>.tar.gz
# or: unzip actionlink-<version>-<target>.zip
./actionlink --version
```

### Windows

```powershell
Get-FileHash .\\actionlink-<version>-<target>.zip -Algorithm SHA256
Expand-Archive .\\actionlink-<version>-<target>.zip .\\actionlink
.\\actionlink\\actionlink.exe --version
```
