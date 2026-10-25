# TorqueFlow Windows updates

This repository distributes Windows x64 installers and signed update metadata for TorqueFlow Offline. The application source is maintained separately in a private repository. No workshop records, account passwords, backups, private signing keys or GitHub tokens are stored here.

## Latest preview

**[0.2.0-rc.36](https://github.com/LazSpace/TorqueFlow-Updates/releases/tag/v0.2.0-rc.36)** simplifies updates. Enable automatic checks and verified downloads once under Settings & backups > Application updates > Automatic update settings. Choose Install update when current work is finished: TorqueFlow saves drafts, creates and verifies an encrypted safety backup, then stops PostgreSQL and opens the Windows installer. Repeated backup/password forms are optional under Use a portable backup instead. The installer and USB update ZIP are on the release page. Existing installations need this update once to get the new UI.

Automatic backup keys are protected by the current Windows account. After reopening, choose Save safety backup recovery key; keep it separate from the archive and copy both off the PC for recovery elsewhere. Continue regular portable backups for loss of the PC or Windows account. This version includes the previous billing, PDF sharing and invoice contact correction fixes.

## First updater-enabled installation

Updater support starts with **0.2.0-rc.32**. For a first installation, download the current [rc.36 Windows installer](https://github.com/LazSpace/TorqueFlow-Updates/releases/tag/v0.2.0-rc.36). Install it manually once under the same Windows account as your existing TorqueFlow installation. Back up existing workshop records first; keep the backup passphrase and owner recovery kit separately.

After installation, sign in as owner and open **Settings & backups → Application updates**. Choose **Check for updates**, or enable optional automatic checks and downloads. Downloads do not install or interrupt billing. Choose **Install update** after finishing work; the default path creates a verified encrypted safety backup automatically. The normal Windows installer and any Windows confirmation still apply; this is not unattended installation or an automatic restart promise.

The preview feed is:

`https://raw.githubusercontent.com/LazSpace/TorqueFlow-Updates/main/channels/preview/release.tfupdate`

The feed and every installer are authenticated by the publisher key pinned inside the bootstrap app. The public key is published in `publisher-key.json` for reference; the app does not accept a replacement key from a downloaded feed. Initial bootstrap trust must be established separately using the installer checksum delivered through your trusted project channel.

## Release status

These releases are explicitly identified **release candidates**. Publisher update-content signatures are separate from Windows Authenticode code signing. This bootstrap installer does not have a trusted Windows code-signing certificate, so Windows or SmartScreen may show an installation warning. Automated software checks do not constitute approval of a production PC, physical printer, statutory examples or remaining operational acceptance.

Workshop data remains local. No server, GitHub password or cloud database is needed on workshop PCs. Update checks require occasional internet access. An air-gapped PC can use the offline update ZIP: extract it, select **Import USB update**, and choose `release.tfupdate`; keep its matching `installer.exe` beside it.

There are no default app credentials. New installations create their owner account locally. Updates do not reset existing accounts. Do not overwrite or downgrade a migrated workshop database to recover an installation; retain the pre-upgrade backup and use a compatible separate restored copy.

The signed feed expires after 30 days unless refreshed by the publisher. An expired or unavailable feed prevents an update, while local workshop work remains available.
