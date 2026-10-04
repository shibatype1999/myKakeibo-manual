# Importing Records from CSV (Format Guide)
<!-- position: 13 -->
<!-- description: The recommended format for importing records from a CSV file, how to write each column, how to fix errors, and how to move from another budget app. -->

You can import records you kept in another budget app or a spreadsheet from a CSV file.
This page explains the **recommended format** and tips for a smooth import. For the basic steps, see [CSV import and export](import-export).

> **Back up before importing**
> There is no way to undo an import in one step. Back up first with **Settings** → **Backup & Restore** → **Back up now** so you can go back if something goes wrong. → [Backup, restore and reset](backup)

## Two ways to import

There are two ways to import a CSV file. Choose the one that fits your file.

| | Settings → **Import & Export** | Record → Scan → **D Spreadsheet file** |
| --- | --- | --- |
| Best for | CSV files in the format on this page (e.g. moving from another budget app) | Statements downloaded from your bank or card company, as they are |
| File types | CSV (.csv) | CSV, TSV, Excel (.xlsx) |
| Categories and accounts | Set in the file's columns (created automatically if missing) | Chosen line by line on the review screen |
| Transfers | Supported | Supported (switch the type on the review screen) |
| Duplicates | Skipped automatically if the same record exists | Lines with the same date and amount are marked **Already recorded** and unchecked |

Tips for statement files (**D Spreadsheet file**) are at the end of this page.

## Recommended format

The most reliable way is to use **the same format as a CSV exported from the app**. Export one with **Settings** → **Import & Export** → **Export CSV** and use it as a template.

You can also download a template: [import_template_en.csv](https://raw.githubusercontent.com/shibatype1999/myKakeibo-manual/main/templates/import_template_en.csv)

```
Date,Type,Category,Subcategory,Amount,Memo,Store,Account,To account
2026/10/01 08:30,Expense,Food,Groceries,42.80,,Corner Market,Wallet,
2026/10/01 12:10,Expense,Food,Dining Out,15.50,Lunch,,Credit Card,
2026/10/05 00:00,Income,Salary,Pay,3200,,,Bank Account,
2026/10/05 09:00,Transfer,,,200,ATM,,Bank Account,Wallet
2026/10/27 00:00,Expense,Housing,Rent,1500,October,,Bank Account,
```

### Key points

1. Put the **column names in the first row**: `Date,Type,Category,Subcategory,Amount,Memo,Store,Account,To account` (upper or lower case is fine). Japanese column names also work.
2. With column names, **columns can be in any order**, and you can leave out columns you don't use (such as Memo or Store).
3. From the second row, write **one record per row**.
4. Save the file as **CSV (comma separated), UTF-8**.

### Minimum columns

| Record type | Required columns |
| --- | --- |
| Income / Expense | Date, Type, Category, Amount |
| Transfer | Date, Type, Amount, Account, To account |

We recommend filling in **Account** too, so that account balances are calculated correctly. Records without an account are not included in any account's balance.

## Writing each column

### Date (required)

| Format | Accepted |
| --- | --- |
| `2026/10/25 14:30` | Yes (recommended) |
| `2026-10-25 14:30:00`, `2026-10-25T14:30` | Yes (seconds are ignored) |
| `2026/10/25`, `2026/1/5` | Yes (time is set to 0:00) |
| `10/25` (no year) | No |
| `10/25/2026`, `25/10/2026` | No |
| `Oct 25, 2026` | No |

Use **year (4 digits), month, day** in that order, separated by `/` or `-`. If a date cell in Excel is displayed as "10/25/2026" or "Oct 25, 2026", it is written to the CSV that way and cannot be read. Change the cell format to `yyyy/mm/dd hh:mm` before saving.

### Type (required)

Write `Income`, `Expense` or `Transfer` (Japanese `収入`, `支出`, `振替` also work). Other words such as "Debit" or "Credit" cannot be read, so replace them.

### Amount (required)

| Format | Accepted |
| --- | --- |
| `3280`, `3,280`, `$3,280`, `12.50` | Yes |
| `-3280` (negative), `0` | No |

- Always write amounts as **positive** numbers. The direction of the money is set by **Type**. If your old app exports expenses as negative numbers, remove the minus sign.
- Decimals are kept up to the number of decimal places of the currency selected in the app; extra digits are rounded.

### Category and Subcategory

- **Category is required** for income and expenses. Leave it blank for transfers (it is not used).
- Subcategory can be blank.
- If the name **exactly matches** a category in the app, the record goes into that category. If not, **a new category is created**. Differences in spacing or spelling create a separate category, so match the names in **Settings** → **Categories**.
- The default categories' English names (Food, Groceries, etc.) are matched to the built-in categories.
- Income and expense categories are separate even if they have the same name.
- You can change the icon and color of new categories later in **Settings** → **Categories**.

### Account and To account

- **Account** is the deposit account for income, the paying account for expenses, and the account money leaves for transfers.
- **To account** is the account money goes to in a transfer, and is required for transfers. Use two different accounts.
- If no account has the same name, **a new account is created as a Cash account**. For cards or bank accounts, change the type in **Settings** → **Accounts** after importing.

### Memo and Store

Free text (can be blank). If a value contains a comma or line break, wrap it in `"` (e.g. `"Lunch, for two"`). Spreadsheet apps do this automatically when saving.

## File format

| Item | Recommended | Notes |
| --- | --- | --- |
| Separator | Comma (,) | Tab-separated files cannot be read by this import. |
| Encoding | UTF-8 | Shift_JIS CSV files saved by Japanese Excel can also be read. |
| Extension | .csv | Excel .xlsx files cannot be chosen here. Save them as CSV. |

### Saving from spreadsheet apps

- **Excel**: **File** → **Save As** → file type **CSV UTF-8 (Comma delimited)**
- **Numbers** (iPhone, Mac): **Export** → **CSV** (text encoding UTF-8)
- **Google Sheets**: **File** → **Download** → **Comma Separated Values (.csv)**

Put the saved file in the Files app (iCloud Drive, etc.) and choose it with **Choose file** in the app.

## Duplicates

Rows whose **date & time (to the minute), type, category (account pair for transfers) and amount** all match a record already in the app are skipped as duplicates. Importing the same file twice does not create double records.

> **Note**
> - If the same file contains two identical rows, both are imported (e.g. you spent the same amount at the same store twice in a day).
> - If you change the date or category even slightly and import again, the rows are added as new records. To redo an import, restore the backup you made before importing, then import again.

## The review screen and fixing errors

After you choose a file, the number of records, what will be created, and **Unreadable rows** are shown before anything is imported. Unreadable rows are listed as "Line N: reason" (the column names are line 1).
Unreadable rows are not imported; the other rows are. To import everything, fix the file and choose it again.

| Reason shown | Common causes and fixes |
| --- | --- |
| Could not read the date | No year, month/day order, month names, etc. Use the `2026/10/25 14:30` format. |
| Type must be Income, Expense or Transfer | Words like "Debit" or "Payment". Replace them with one of the three. |
| Transfers need both an account and a destination account | Account or To account is blank on a transfer row. Fill in both. |
| The account and destination account are the same | The same account is used on both sides of a transfer. Use different accounts. |
| Category is empty | An income or expense row has no category. Add one. |
| Could not read the amount | Negative, 0, blank or contains text. Use a positive number. |

### When line 1 shows as unreadable

If the column names do not include both **Date** and **Amount** (or Japanese 日時 and 金額), the first row is not treated as column names and is read as data. Columns are then assumed to be in the order Date, Type, Category, Subcategory, Amount, Memo, Store, Account, To account.
Use the column names exactly. Names like "Transaction date" or "Amount (USD)" are not recognized.

### When more new categories or accounts appear than expected

If **New categories** or **New accounts** on the review screen lists names you did not expect, they are typos or spelling variations. Match the names in the file to the app before importing, or fix the records after importing and delete the categories or accounts you don't need.

## Moving from another budget app

1. Export your records from the old app as CSV (or Excel).
2. Open the file in a spreadsheet app and map the columns as follows.

| Typical column in other apps | myKakeibo column | How to fix |
| --- | --- | --- |
| Date, Transaction date | Date | Rename to "Date" and use year/month/day order |
| Income/Expense, Direction | Type | Replace values with Income, Expense or Transfer |
| Category, Group | Category | Rename to "Category" |
| Sub-category, Item | Subcategory | Rename to "Subcategory" |
| Amount (expenses negative) | Amount | Remove the minus sign and use Type for the direction |
| Separate income and expense amount columns | Amount | Combine into one column and set Type from whichever column has a value |
| Wallet, Account, Payment method | Account | Rename to "Account" and match the names to your accounts in the app |
| Description, Notes | Memo | Rename to "Memo" |
| Payee, Merchant | Store | Rename to "Store" |

3. If your old app has no transfers (e.g. ATM withdrawals were recorded as expenses), change those rows' Type to Transfer, fill in Account and To account, and clear the category.
4. Save as CSV UTF-8, try importing a few dozen rows first, check the review screen, and then import everything.

> **Tip**
> Setting up **Settings** → **Categories** and **Accounts** to match your old app first means fewer fixes after importing.

## Tips for bank and card statement files (D Spreadsheet file)

**Record** → Scan → **D Spreadsheet file** reads statements downloaded from your bank or card company **as they are**, without reformatting. Columns are detected from their names.

| What is read | Column names recognized (examples) |
| --- | --- |
| Date | Date (and Japanese names such as 日付, 利用日) |
| Description | Description, Payee, Merchant, Name, Memo |
| Money out | Debit, Withdrawal |
| Money in | Credit, Deposit |
| Amount (single column) | Amount |

- Balance and fee columns are not read.
- When there is a single amount column, if any row is negative, negative amounts are read as expenses and positive amounts as income; otherwise all rows are read as expenses. `(1,000)` is also read as negative.
- Dates such as `2026/9/7`, `26/9/7` and `9/7` are supported. Dates without a year are read as this year or last year so that they are not in the future.
- Rows whose date could not be read show **Date?** and are unchecked. Tap it to choose a date.
- For Excel (.xlsx) files, the sheet with the most transactions is used.
- If no date and amount columns are found, "Could not find date and amount columns" is shown. Rename the header row as above and choose the file again.

For the steps, see [Scanning receipts and statements](scan).
