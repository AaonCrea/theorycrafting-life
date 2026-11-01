# NFC contact-card runbook

This is a pre-write checklist for the Theorycrafting.life contact cards. It does not replace testing on the actual tag and devices.

## Record layout

Use one NDEF message with two records, in this order:

1. MIME record: `text/vcard`, containing the person’s vCard 3.0 data.
2. URI record: the person-specific HTTPS card URL.

URLs:

- James Thompson: `https://theorycrafting.life/contact/`
- Marissa Sears: `https://theorycrafting.life/contact/marissa-sears/`

Android commonly dispatches from the first NDEF record, while iPhone background reading looks for a URI record. This ordering is a compatibility strategy and must be tested on the target Android and iPhone devices. See the [Android NFC dispatch documentation](https://developer.android.com/reference/android/nfc/NfcAdapter) and [Apple background tag-reading documentation](https://developer.apple.com/documentation/CoreNFC/adding-support-for-background-tag-reading).

## Before overwriting a tag

1. Read and export the complete existing NDEF message.
2. Save the export with the tag/person identifier and date.
3. Record the tag type, usable capacity, and current record order.
4. Confirm that the new vCard plus URL fits within the available capacity.
5. Test the proposed message without overwriting the original tag when the hardware/app supports a preview.
6. Write only after Android contact import and iPhone HTTPS notification/browser behavior are both confirmed.

Never reuse one person’s URL or vCard data on another person’s physical tag.
