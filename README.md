# Smart Credit 3-B Standalone HTML Reports

This repository provides standalone, semantic HTML5 replicas of Smart Credit 3-Bureau credit reports. Each file contains embedded CSS, making it completely self-contained without external stylesheet dependencies or build steps.

## Live Demo
- Demo Portal: https://smart-credit-demo.vercel.app

## File Structure
- index.html: Demo portal page for navigation between sample reports.
- report-1-johnathan-doe.html: Standalone report for a prime borrower profile.
- report-2-sarah-connor.html: Standalone report for a subprime borrower profile.
- README.md: Technical documentation and editing guide.
- assets/: Directory reserved for custom logos and graphics (e.g., SmartCreditLogo-removebg-preview.png).

## How to Create a New Report

To generate a new credit report for a different borrower using this template, follow these steps:

1. **Duplicate an Existing Template**
   - Copy `report-1-johnathan-doe.html` and rename it to match the new borrower (e.g., `report-3-michael-scott.html`).

2. **Update Borrower Metadata**
   - Open the new file and update the `<title>` tag in the `<head>` section.
   - Edit borrower details inside the `.meta-table` block at the top of the file (Name, Report Date, Current Address, Reference Number, DOB, SSN).

3. **Populate Report Sections**
   - Update each commented section in sequential order (`SECTION 1` through `SECTION 7`) with the borrower's specific credit data.

4. **Add to Navigation Portal (Optional)**
   - Open `index.html` and add a new card link pointing to your newly created file (`./report-3-michael-scott.html`).

## How to Modify Report Content

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

## Styling & Layout Customization

All styling is located inside the `<style>` block in the `<head>` section of each report file:
- Logo Size: Adjust `style="height: 75px;"` on the `<img>` tag for browser view, and `max-height: 65px !important;` under `@media print` for PDF exports.
- Page Width: Adjust `max-width: 850px;` under `body` to change overall page container width.
- Fonts: Change `font-family: Arial, Helvetica, sans-serif;` under `body` to modify typography.
- Table Borders: Modify `border: 1px solid #666;` under `table.data-table th, table.data-table td` to change table line thickness or color.

## Printing and PDF Export

1. Open any report file in Google Chrome, Microsoft Edge, Firefox, or Safari.
2. Click the "Print / Save to PDF" button at the top or press Ctrl+P (Cmd+P on Mac).
3. Set the destination to "Save as PDF" and select paper size (A4 or US Letter).
4. Embedded `@media print` rules automatically hide navigation buttons and enforce `break-inside: avoid` on data tables to prevent split rows across pages.
