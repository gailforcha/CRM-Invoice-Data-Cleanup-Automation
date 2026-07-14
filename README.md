# CRM-Invoice-Data-Cleanup-Automation

This project demonstrates practical data cleaning and invoice extraction skills using Microsoft Excel and Power Query.

The project contains two modules:

1. Dirty retail sales data cleanup
2. PDF invoice data extraction and cleanup

The goal is to show how messy business data can be cleaned, structured, and prepared for reporting or analysis.

---

## Tools Used

- Microsoft Excel
- Power Query
- CSV data cleaning
- PDF invoice extraction
- Data transformation
- Data validation and restructuring

---

## Module 1: Dirty Retail Sales Data Cleanup

### Dataset

The first module uses a dirty retail sales dataset containing transaction records with missing and inconsistent values.
**Data Source:** [Retail Store Sales: Dirty for Data Cleaning (Kaggle)](https://www.kaggle.com/datasets/ahmedmohamed2003/retail-store-sales-dirty-for-data-cleaning)
### Main Cleaning Tasks

- Imported the raw dataset into Power Query
- Promoted headers and assigned correct data types
- Cleaned category formatting
- Created a corrected unit price column
- Reconstructed missing item codes using category and price rules
- Preserved missing quantity, total spent, and discount values where they could not be safely inferred
- Removed old dirty columns from the final cleaned view
- Produced a clean retail sales output table

### Key Cleaning Decisions

| Issue Found | Action Taken | Reason |
|---|---|---|
| Missing unit price | Inferred using `Total Spent / Quantity` where both values were available | The dataset defines total spent as quantity multiplied by unit price |
| Missing item code | Reconstructed using corrected unit price and category code | The dataset follows a fixed item price and category code pattern |
| Missing quantity and total spent | Left blank/null | Missing values could not safely be assumed as zero |
| Missing discount value | Left blank/null | Missing discount does not mean no discount was applied |
| Original item and price columns | Removed from final cleaned output | Final output keeps corrected fields while raw data remains available separately |

---

## Module 2: PDF Invoice Extraction and Cleanup

### Dataset

The second module uses a public invoice PDF dataset. The invoices contain client information, item details, and invoice summary totals.
**Data Source:** [High-Quality OCR-Ready Invoice PDFs (Kaggle)](https://www.kaggle.com/datasets/devp1866/high-quality-ocr-ready-invoice-pdfs)

### Main Extraction and Cleaning Tasks

- Imported PDF invoice data into Excel/Power Query
- Extracted client information from invoice headers
- Extracted invoice item lines into a structured table
- Extracted invoice-level summary totals
- Separated item-level values from invoice-level totals
- Renamed columns for business readability
- Created clean outputs for client information, item details, and invoice summaries

### Cleaned Invoice Outputs

The invoice module is organized into three cleaned tables:

#### 1. Clients Info

Contains client-level invoice information such as:

- PDF name
- Client name
- Address details
- Postal code
- Client tax ID

#### 2. Clients Item List

Contains product-level invoice line items such as:

- PDF name
- Product description
- Quantity
- Unit of measure
- Net price
- Item net worth
- VAT percentage
- Item gross worth

#### 3. Clients Summary

Contains invoice-level totals such as:

- PDF name
- Total net worth
- Total VAT
- Total gross worth

---
## Skills Demonstrated

- Excel Power Query data cleaning
- CSV data cleaning
- PDF invoice extraction
- Missing value handling
- Safe inference of missing values
- Text, number, date, and logical data type handling
- Item code reconstruction
- Invoice line item extraction
- Invoice summary extraction
- Business data restructuring
- Clean workbook organization
- Documentation of cleaning decisions

---
