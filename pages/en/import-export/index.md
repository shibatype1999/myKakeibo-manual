# CSV Import and Export
<!-- position: 12 -->
<!-- description: How to export records to a CSV file, import records from a CSV file, and the CSV format. -->

In **Settings** → **Import & Export**, you can export records to a CSV file and import records from one. Use it to move from another budget app or to analyze your data in a spreadsheet on your computer.

> To import statements downloaded from your card company or bank (Excel or CSV), the scan button on the **Record** tab → **D Spreadsheet file** is handy. → [Scanning receipts and statements](scan)

## Export (CSV)

1. Choose the **Period**: **All**, **This year**, **This month** or **Last month**.
2. Tap **Export CSV**.
3. When the share menu opens, choose where to save it (Save to Files, Mail, AirDrop, etc.).

The exported file is also kept in the Files app under **On My iPhone** → **myKakeibo** → **exports**.
Only confirmed records are exported (scheduled records are not). The file is UTF-8 with a BOM, so it opens correctly in Excel. When the app is shown in English, the column names, types and default names are written in English.

## Import (CSV)

1. Tap **Choose file** and select a CSV file.
2. Before importing, the following is shown. Nothing has changed yet at this point.
   - The number of records to add
   - The number skipped as duplicates (records with the same date, type, category and amount already exist)
   - New categories, subcategories and accounts that will be created
   - Unreadable rows and the reason
3. Check the details and tap **Import N records**.

> **Tips**
> - Tap **Load sample data** to try the import flow with a sample CSV (nothing is imported until you tap **Import N records**).
> - Shift_JIS CSV files saved by Excel can also be read.
> - Categories, subcategories and accounts in the CSV that are not in the app are created. New accounts are created as **Cash** accounts; change them in **Settings** → **Accounts** if needed.

## CSV format

Put the column names in the first row and one record per row from the second row. Columns are matched by name, so they can be in any order. Japanese or English column names are both accepted.

| Column | Content | Example |
| --- | --- | --- |
| Date | "2026/10/25 14:30", "2026-10-25", etc. Without a time, 0:00 is used. | 2026/10/01 12:10 |
| Type | Income, Expense or Transfer | Expense |
| Category | Required for income and expenses. Blank for transfers. | Food |
| Subcategory | Can be blank | Groceries |
| Amount | "3280", "3,280", "$12.50", etc. | 55.40 |
| Memo | Can be blank | |
| Store | Can be blank | Corner Market |
| Account | Paid from / deposit to. For transfers, the account money leaves. | Wallet |
| To account | For transfers, the account money goes to. Required for transfers. | |

```
Date,Type,Category,Subcategory,Amount,Memo,Store,Account,To account
2024/10/01 00:05,Expense,Digital & Subscriptions,Video Streaming,14.90,Netflix,,Credit Card,
2024/10/02 12:10,Transfer,,,300,ATM,,Bank Account,Wallet
2024/10/02 17:45,Expense,Food,Groceries,55.40,,Corner Market,Wallet,
```
