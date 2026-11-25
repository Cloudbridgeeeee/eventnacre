# EventNacre — proposed AWS architecture

EventNacre uses AWS to read supplier invoices, classify spending and forecast budgets — keeping financial data secure and separated per business.

## Request flow

1. Supplier invoices
2. Amazon S3
3. Textract
4. Bedrock
5. SageMaker AI
6. DynamoDB
7. Finance approval

## Services

### Amazon Textract

**Role:** Read supplier invoices

Extracts supplier names, amounts, VAT, line items and dates from invoices and receipts, including photos taken on site.

### Amazon Bedrock

**Role:** Classify expenses and summarise

Classifies invoice lines into your event budget categories and drafts profitability summaries for finance to edit.

### Amazon SageMaker AI

**Role:** Forecast budget deviations

Trains on past events to forecast the final cost of each budget line from committed spend, flagging likely overspends early.

### Amazon S3

**Role:** Store invoices and estimates

Keeps every invoice and estimate encrypted and versioned as the audit trail behind each figure.

### Amazon DynamoDB

**Role:** Hold budgets and expenses

Stores events, budget lines, expenses, forecasts and approvals for fast, collaborative budget tracking.

## Principles

- **Finance approves** — Classifications are reviewed before reporting.
- **Invoice-linked** — Every figure links to its source document.
- **Financial confidentiality** — Your margins and supplier prices stay private.

## Safeguards

- **Finance team approves** — Classifications and forecasts are reviewed before they appear in reports.
- **Not accounting advice** — EventNacre supports planning; statutory accounts and tax stay with your accountants.
- **Source-linked figures** — Every expense links back to its invoice.
- **Confidential finances** — Encrypted and access-controlled by role.

## MVP scope

We import estimates and supplier invoices for recent and upcoming events, classify the expenses with your finance team and deliver budget dashboards with deviation forecasts.

- Estimate and invoice import
- Expense classification with review
- Budget vs actual dashboards
- Deviation forecasts
- Event profitability report
