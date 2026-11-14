School App - Staff Cloud Sync Patch

Changes in this package:
- Added Staff account records to the school's Firestore appData sync load.
- Added Staff and Parent account records to saveAll cloud uploads.
- Existing modulePermissions data is carried with the staff account records.

Important:
- This patch fixes the missing Staff/Parent records in the Principal's cloud sync.
- It does NOT convert Staff login to Firebase Authentication. The current Staff portal still checks the locally stored ID/password.
- For a second device, the Principal account must sign in on that device and sync the school data before the locally stored Staff login can find the account. This is not a fully independent or ideal secure staff-login architecture.
- Do not loosen Firestore rules to allow public read/write. The supplied firestore.rules is left unchanged.
- No Firebase Blaze upgrade is required for this code change.
- The ZIP has not been built or tested on GitHub in this environment.

Install:
1. Keep a backup of your current GitHub repository.
2. Replace the repository files with the contents of this ZIP (preserve your existing Firebase config).
3. Check Firebase Console > Firestore Rules: keep the existing owner/approved-school restrictions.
4. Build and test with two devices before using real school data.
