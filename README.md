# R-Sessions releases

R-Sessions is a remote session manager for administrators and IT teams: SSH, SFTP, serial, Telnet and VNC in one window, with an encrypted vault for your hosts, identities and keys. It runs on Windows and Linux and does not send any data about you anywhere.

This repository only hosts the installers. The source code is not here.

## Which file to download

Open the [latest release](../../releases/latest) and pick the file for your system (`X.Y.Z` is the version):

| System | File |
|---|---|
| Windows 10 / 11 | `R-Sessions_X.Y.Z_x64-setup.exe` |
| Windows, company deployment (GPO, Intune, SCCM) | `R-Sessions_X.Y.Z_x64_en-US.msi` |
| Ubuntu, Debian, Linux Mint | `R-Sessions_X.Y.Z_amd64.deb` |
| Fedora, RHEL, Rocky Linux, AlmaLinux | `R-Sessions-X.Y.Z-1.x86_64.rpm` |
| Other Linux distributions | `R-Sessions_X.Y.Z_amd64.AppImage` (make it executable: `chmod +x`) |

Installed copies check for updates once a day and can install them from Settings > About. The `.sig` files and `latest.json` are used by that update check; you do not need to download them.

## User guide

The full user guide (36 pages, PDF) covers every part of the app, with short explanations of terms such as tunnels and jump hosts:

- [R-Sessions user guide (English)](docs/R-Sessions-user-guide-EN.pdf)
- [Instrukcja obsługi R-Sessions (polski)](docs/R-Sessions-instrukcja-PL.pdf)

## Verifying the Windows installer

The `.exe` and `.msi` files are signed by **RALKOM RAFAŁ LESIŃSKI**. To check:

- In Explorer: right-click the file, Properties, Digital Signatures. The signer must be RALKOM RAFAŁ LESIŃSKI and the signature must be OK.
- In PowerShell:
  ```powershell
  Get-AuthenticodeSignature .\R-Sessions_X.Y.Z_x64-setup.exe | Format-List Status, SignerCertificate
  ```
  `Status` must be `Valid`.

Do not run an installer whose signature is missing or invalid.

Updates installed from inside the app are additionally checked against the R-Sessions update signing key before they run, on Windows and on Linux.
