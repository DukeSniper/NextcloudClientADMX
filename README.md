# NextcloudClientADMX
ADMX File for Nextcloud Desktop Client

The Windows Nextcloud Desktop Client actually supports "pre-seeding" some config values using GPO. This repo aims to (eventually) provide a usable ADMX file for that.

The following settings are currently (as of 3.11.1) supported in the Client:

```skipUpdateCheck``` -> boolean
 - when true -> disables autoUpdateCheck

```autoUpdateCheck``` -> boolean

```confirmExternalStorage``` -> boolean

```usenewBigFolderSizeLimit``` -> boolean
 - when true, disables newBigFolderSizeLimit
 - when true, disables notifyExistingFoldersOverLimit
 - when true, disables stopSyncingExistingFoldersOverLimit

```newBigFolderSizeLimit``` -> LongLong
 - value represents abount of MB

```notifyExistingFoldersOverLimit``` -> boolean

```stopSyncingExistingFoldersOverLimit``` -> boolean

```crashReporter``` -> boolean
 - huh?


All settings are first sourced from the HKCU Policies structure, then HKLM Policies, then HKLM\Software, and then the user's local config file in %APPDATA%.
First match wins. Might eventually ask the devs why on earth a user policy should overrule a machine policy
