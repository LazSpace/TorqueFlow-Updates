# TorqueFlow Windows updates

This repository distributes Windows x64 installers and signed update metadata for TorqueFlow Offline. The application source is maintained separately in a private repository. No workshop records, account passwords, backups, private signing keys or GitHub tokens are stored here.

## Latest preview

**[0.2.0-rc.35](https://github.com/LazSpace/TorqueFlow-Updates/releases/tag/v0.2.0-rc.35)** fixes invoice contact corrections. Open the invoice > Review updated details (or Update invoice details) > Update invoice. Review corrected customer phone/address, vehicle identifiers and workshop contact details while retaining the invoice number, totals, payments and stock. Multi-line addresses are preserved, and the audit records before/after values. Sharing after a correction generates a fresh PDF when a previously saved copy is stale; the PDF, suggested filename and WhatsApp recipient use the corrected phone. Installer and USB update ZIP are available on the release page. This includes the previous native PDF file-sharing fix.

## First updater-enabled installation

Updater support starts with **0.2.0-rc.32**. For a first installation, download the current [rc.35 Windows installer](https://github.com/LazSpace/TorqueFlow-Updates/releases/tag/v0.2.0-rc.35). Install it manually once under the same Windows account as your existing TorqueFlow installation. Back up existing workshop records first; keep the backup passphrase and owner recovery kit separately.

After installation, sign in as owner and open **Settings & backups → Application updates**. Choose **Check for updates**, or enable optional automatic checks. Automatic checks do not install or interrupt billing. Installing an available update requires owner approval and a verified encrypted backup before the local database is stopped.

The preview feed is:

`https://raw.githubusercontent.com/LazSpace/TorqueFlow-Updates/main/channels/preview/release.tfupdate`

The feed and every installer are authenticated by the publisher key pinned inside the bootstrap app. The public key is published in `publisher-key.json` for reference; the app does not accept a replacement key from a downloaded feed. Initial bootstrap trust must be established separately using the installer checksum delivered through your trusted project channel.

## Release status

These releases are explicitly identified **release candidates**. Publisher update-content signatures are separate from Windows Authenticode code signing. This bootstrap installer does not have a trusted Windows code-signing certificate, so Windows or SmartScreen may show an installation warning. Automated software checks do not constitute approval of a production PC, physical printer, statutory examples or remaining operational acceptance.

Workshop data remains local. No server, GitHub password or cloud database is needed on workshop PCs. Update checks require occasional internet access. An air-gapped PC can use the offline update ZIP: extract it, select **Import USB update**, and choose `release.tfupdate`; keep its matching `installer.exe` beside it.

There are no default app credentials. New installations create their owner account locally. Updates do not reset existing accounts. Do not overwrite or downgrade a migrated workshop database to recover an installation; retain the pre-upgrade backup and use a compatible separate restored copy.

The signed feed expires after 30 days unless refreshed by the publisher. An expired or unavailable feed prevents an update, while local workshop work remains available.
