# Scanning Receipts and Statements
<!-- position: 3 -->
<!-- description: How to scan receipts, bank statements, card and payment histories, and spreadsheet files, and save them as records. -->

Use the scan button (document icon) at the top right of the **Record** tab to read receipts and statements and save them together.

> **Note**
> Reading text from images is a best guess. Depending on the receipt or statement layout, dates, amounts and descriptions are often read incorrectly. Please check and correct them on the review screen before saving.

## 1. Choose what you are scanning

When "What are you scanning?" appears, choose the closest layout. The one you used last time is marked **Last used**.

![Choosing what to scan](https://raw.githubusercontent.com/shibatype1999/myKakeibo-manual/main/images/en/scan-kind.png)

| Type | What is read |
| --- | --- |
| A Receipt | Store, items with prices, total |
| B Bank statement | Date, description, in/out, balance |
| C Card / payment history | Store and amount, with a date (cards, payment apps) |
| D Spreadsheet file | CSV or Excel (date, description, amount columns) |

## 2. Choose how to scan

| Option | Description |
| --- | --- |
| Scan with camera | Take photos with the camera. Multiple pages are joined from top to bottom. Captured images are not saved. |
| Choose from Photos | Read an image from the Photos app, such as a screenshot. |
| Choose from Files | Read an image (JPEG, PNG, HEIC) from the Files app. |
| Paste text | Paste copied text. In the Photos app, long-press the receipt text → "Select All" → "Copy", then paste it. |

To choose a different type, tap **Change** at the top right.
If you chose **D Spreadsheet file**, the review screen opens as soon as you pick a file (Excel (.xlsx) and CSV are supported).

## 3. Review and save

On the **Review scan result** screen, check and correct the results, then tap **Save N records** at the bottom.
The switch at the top selects how records are saved.

| Option | How it is saved |
| --- | --- |
| Per item | Each item on the receipt becomes a separate record. |
| Total only | The receipt total becomes one record. |
| Transactions | Each line of the statement becomes a record. |

![Review scan result](https://raw.githubusercontent.com/shibatype1999/myKakeibo-manual/main/images/en/scan-confirm.png)

### Receipts (Per item / Total only)

- Check the **date & time**, **store**, **category** and **Paid from**. With **Per item**, "Category (applies to all)" changes the category of every item at once.
- With **Per item**, only checked items are saved. You can edit item names and amounts, use **Add row**, and remove rows.
- If the **Checked total** and **Receipt total** differ, the difference is shown (tax, etc.).
- If you have saved a record with the same store name before, the category you used then is selected automatically.

### Statements (Transactions)

- Choose the **Account** for the statement at the top.
- Check each line's date, description and amount, plus Expense/Income and the category. Tap the type to switch between **Expense**, **Income**, **Transfer (in)** and **Transfer (out)**.
- Top-up lines are read as transfers. For transfer lines, choose the other account.
- Lines with the same date, type and amount as an existing record are marked **Already recorded** and unchecked to avoid duplicates.
- Lines whose date could not be read show **Date?**. Tap it to choose a date.
- If a checked line has no category, you are told before saving.

### Seeing the full text

Tap the full-text button at the top right to see every line that was read. Lines read as a date, store, item, total and so on are labeled. Add unlabeled lines as items (transactions) with ⊕. Use this when something was missed.

## Organizing scans with AI (supported iPhones only)

On iPhones that support Apple Intelligence, on-device AI organizes the dates, descriptions and amounts that were read. Everything is processed on your device.

- When it finishes, "Organized with AI" appears. **Undo** shows the results without AI, and **Use AI results** switches back.
- If the AI could not organize the results, the reason is shown along with the regular results.
- To stop using AI, turn off **Settings** → **Organize scans with AI**.
- AI is not used when your currency has decimal places (such as dollars) or when importing spreadsheet files.
