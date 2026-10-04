# FAQ
<!-- position: 16 -->
<!-- description: Frequently asked questions about myKakeibo. -->

## Data

### Where is my data stored?

All your budget data is stored on your iPhone. No account is needed, and your budget data is not sent to any outside server. Scanning is also done on the device, and photos taken with the camera are not saved.
If you turn on the Premium automatic iCloud backup, backup files are saved to your own iCloud Drive.

### What should I do when I change iPhones?

Back up on your old iPhone and restore on the new one. See "When you change iPhones" in [Backup, restore and reset](backup).

### What happens to my data if I delete the app?

Deleting the app also deletes the data and backups on the device. Before deleting it, back up to iCloud or use the Files app to copy a device backup to another location.

## Recording

### Are transfers included in my balance?

No. A transfer moves money between your own accounts, so only the account balances change. → [Accounts and transfers](accounts)

### How should I record credit card spending?

When you shop, record the expense with **Credit Card** as **Paid from**. On the payment date, record a transfer from **Bank Account** to **Credit Card**. This avoids counting the expense twice.

### There is a yellow "Scheduled" record in the list

It is a scheduled record created at the start of each month from a subcategory with **Fixed monthly** turned on. Tap it, check the amount and tap **Confirm** to include it in your totals. → [Categories and subcategories](categories)

### Automatic entries are not recorded

- On iPhone, nothing can be recorded while the app is closed. Entries are recorded when you open the app after the set date and time.
- Check that both the page's and the item's **Register automatically every month** are on. Items need a default amount.
- Items already entered that month are not recorded.

→ [Bulk input pages and automatic entries](bulk-input)

## CSV import

### Some rows show as unreadable when I import a CSV

Common causes:

- The date is not in the `2026/10/25 14:30` format (no year, month/day order, month names, etc.)
- Type is something other than Income, Expense or Transfer
- The amount is negative or 0 (always write a positive amount and use Type for the direction)
- An income or expense row has no category

See [Importing records from CSV (format guide)](csv-import) for details.

### What kind of CSV should I prepare?

The same format as a CSV exported from the app is the most reliable. Put `Date,Type,Category,Subcategory,Amount,Memo,Store,Account,To account` in the first row and save as CSV UTF-8. A template is also available. → [Importing records from CSV (format guide)](csv-import)

### Importing created extra categories or accounts

If names in the CSV don't exactly match your categories and accounts, new ones are created. Check **New categories** and **New accounts** on the review screen and match the names in the file before importing.

### I imported the same CSV twice

Records with the same date & time, type, category (account pair for transfers) and amount are skipped, so the same file does not create double records. If you changed the contents and imported again, they are added as new records; restore the backup you made before importing.

## Scanning

### The scanned amount or date is wrong

Reading text from images is a best guess, so some receipt or statement layouts are not read correctly. Correct the results on the review screen before saving. If something was missed, add lines from the full-text button at the top right. → [Scanning receipts and statements](scan)

### "Could not organize with AI" appears

The reason is shown with the message. If the language is not supported, check the language in the iPhone **Settings** → **Apple Intelligence & Siri**. If there is too much text, scan the image in parts. You can still save using the regular results.

## Other

### I want to remove ads

Ads are removed with [Premium](premium).

### Amounts look wrong after changing the currency

Recorded amounts are not converted when you change the currency. Only the currency symbol and decimal places change. Switching back to the original currency restores the original display. → [Settings](settings)

### I forgot my passcode

There is no way to reset the passcode. You need to delete and reinstall the app, which also deletes the data on the device. If you have an iCloud backup, you can restore it after reinstalling.

### I don't get reminder notifications

Check that notifications are allowed in the iPhone **Settings** → **Notifications** → **myKakeibo**. → [Reminders](reminders)
