# Smart Credit 3-B Standalone HTML Reports

This repository provides standalone, semantic HTML5 replicas of Smart Credit 3-Bureau credit reports. Each file contains embedded CSS, making it completely self-contained without external stylesheet dependencies or build steps.

## Live Demo
- Demo Portal: https://your-project-name.vercel.app

## File Structure
- index.html: Demo portal page for navigation between sample reports.
- report-1-johnathan-doe.html: Standalone report for a prime borrower profile.
- report-2-sarah-connor.html: Standalone report for a subprime borrower profile.
- README.md: Technical documentation and editing guide.

## How to Modify Content

All data is structured using semantic HTML tables and organized with commented section headers for fast editing.

### 1. Personal & Meta Information
Open the target HTML file in any code or text editor and locate:
- Borrower Header: Edit text inside the top `.meta-table` block.
- Section 1 (Personal Info): Search for `<!-- SECTION 1: PERSONAL INFORMATION -->` to update names, addresses, and employer data for each bureau column.

### 2. Credit Scores
Search for `<!-- SECTION 2: CREDIT SCORES -->` to modify score numbers, models, or lender ratings inside the table cells:
- TransUnion column
- Experian column
- Equifax column

### 3. Account Summary & Trade Lines
Search for:
- `<!-- SECTION 3: ACCOUNT SUMMARY -->` to update total balances, account counts, and monthly payments.
- `<!-- SECTION 4: TRADE LINES -->` to add, remove, or modify credit card/loan accounts.
  - Account Details: Edit status, limits, and balances in the primary account table.
  - 24-Month History: Modify payment status codes (`OK`, `30`, `60`, `90`, `CO`) directly inside the `.pay-grid` table cells.

### 4. Hard Inquiries & Public Records
Search for:
- `<!-- SECTION 5: HARD INQUIRIES -->` to update creditor inquiry entries.
- `<!-- SECTION 6: PUBLIC RECORDS -->` to update or clear public record listings.
- `<!-- SECTION 7: CREDITOR CONTACT DIRECTORY -->` to update creditor addresses and phone numbers.

## Styling & Layout Adjustments

All styling is located inside the `<style>` block in the `<head>` section of each report file:
- Page Width: Adjust `max-width: 900px;` under `body` to change overall page container width.
- Fonts: Change `font-family: Arial, Helvetica, sans-serif;` under `body` to modify typography.
- Table Borders: Modify `border: 1px solid #666;` under `table.data-table th, table.data-table td` to change table line thickness or color.

## Printing and PDF Export

1. Open any report file in Google Chrome, Microsoft Edge, Firefox, or Safari.
2. Click the "Print / Save to PDF" button at the top or press Ctrl+P (Cmd+P on Mac).
3. Set the destination to "Save as PDF".
4. Embedded `@media print` rules automatically hide navigation buttons and enforce `break-inside: avoid` on data tables to prevent split rows across pages.
