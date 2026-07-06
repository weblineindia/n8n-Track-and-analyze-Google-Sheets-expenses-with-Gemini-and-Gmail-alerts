# Expense Leak Detector

*Smart Expense Monitoring in Minutes*

---

This n8n workflow reads your expenses from Google Sheets, categorizes them using predefined keywords, summarizes spending per category, generates AI-powered financial advice using Gemini, stores results in another sheet and sends email alerts for high or normal expenses.

### Quick Start Guide

1. Import the workflow into n8n

2. Connect:
   - Google Sheets OAuth2
   - Google Gemini API
   - Gmail OAuth2

3. Update the **Settings node**:
   - Budget limit
   - Recipient email
   - Sender name

4. Ensure:
   - **Sheet1** → `Date, Description, Amount`
   - **Sheet2** → `Date, Category, Total Spent, AI Report, Status, Reviewed On`

5. Click **"Execute Workflow"**

---

# What It Does

This workflow automates your expense tracking and financial analysis using a combination of Google Sheets and AI.

It begins by fetching raw expense data from a Google Sheet (Sheet1), where each row contains a date, description and amount. The workflow then processes each row by cleaning the data and assigning a category such as Food, Transport, Subscription, Shopping, Utilities, Health or Other using predefined keyword matching.

Once categorized, it aggregates total spending per category and evaluates whether the spending exceeds a defined budget limit. Based on this evaluation, it generates a detailed, personalized financial advisory report using Google Gemini AI.

Finally, the workflow stores all results in another sheet (Sheet2) and sends an email notification—either a high expense alert or a normal summary—based on the spending status.

---

# Who’s It For

- Individuals managing personal finances
- Freelancers tracking monthly expenses
- Families monitoring household spending
- Finance enthusiasts wanting AI-driven insights
- Anyone using Google Sheets for expense tracking

---

## Requirements

To use this workflow, you need:

- [**n8n account** (Self-hosted or Cloud)](https://n8n.partnerlinks.io/om1efg2qgvwi)
- Google Sheets account with read and write access
- Google Gemini API key
- Gmail account connected via OAuth2 for sending email notifications
- A Google Sheet with the following structure:
  - **Sheet1 (Input):** `Date`, `Description`, `Amount`
  - **Sheet2 (Output):** `Date`, `Category`, `Total Spent`, `AI Report`, `Status`, `Reviewed On`

For custom workflow implementation, AI integrations or business process automation, explore our **Process Automation Solutions**:

- https://www.weblineindia.com/process-automation-solutions.html
# How To Set Up

## 1. Import Workflow

Import the provided JSON file into n8n.

## 2. Connect Credentials

- **Google Sheets OAuth2** → For reading and writing data
- **Google Gemini API** → For AI report generation
- **Gmail OAuth2** → For sending emails

## 3. Prepare Google Sheets

### Sheet1 (Input)

| Date | Description | Amount |
|------|-------------|--------|

### Sheet2 (Output)

| Date | Category | Total Spent | AI Report | Status | Reviewed On |
|------|----------|-------------|-----------|--------|-------------|

## 4. Configure Settings Node

Update the **"Settings — Change These Before Running"** node:

- `Budget Limit` → Threshold for high expense detection
- `Send Report To Email` → Recipient email
- `Email Sender Name` → Display name
- `Currency Symbol` → Example: Rs.
- `Report Period` → Example: This Month

## 5. Run Workflow

- Click **"Execute Workflow"**
- The workflow will:
  - Read expenses
  - Categorize them
  - Generate AI insights
  - Save results
  - Send email alerts

---

# How It Works (Step-by-Step Flow)

1. **Manual Trigger**
   - Starts the workflow

2. **Read Expenses**
   - Fetches rows from Sheet1

3. **Settings Node**
   - Stores all configurable values

4. **Clean & Categorize**
   - Converts description to lowercase
   - Assigns categories using **hardcoded keyword logic**

5. **Summarize**
   - Groups data by category
   - Calculates total spend

6. **Build AI Fields**
   - Prepares structured input for Gemini

7. **Gemini AI**
   - Generates detailed financial advisory report

8. **Collect Data**
   - Formats data for storage and email

9. **Save to Sheet2**
   - Appends results

10. **Condition Check**
   - Determines if expense is high or normal

11. **Email Notifications**
   - Sends:
     - High Expense Alert OR
     - Normal Summary
---

# How To Customize Nodes

## 1. Categorization Logic

- Modify the **"Clean and Categorise Each Expense Row"** node.
- Add or update keyword checks for categories.

## 2. Budget Threshold

- Change `Budget Limit` in the Settings node.

## 3. AI Prompt

- Edit the **"Ask Gemini to Write Expense Report"** node.
- Customize the tone, format or financial advice style.

## 4. Email Content

- Modify:
  - Subject lines
  - Email body
  - Sender name

## 5. Currency & Region

- Update:
  - Currency symbol
  - Date format (if needed)

---

# Add-Ons (Enhancements)

- Add a **Schedule Trigger** for automatic daily, weekly or monthly execution.
- Integrate **Slack**, **Microsoft Teams**, **WhatsApp** or other notification channels.
- Build interactive dashboards using **Looker Studio** or **Power BI**.
- Store reports in **Notion**, **Airtable** or a database.
- Support multi-user or multi-department expense tracking.
- Generate downloadable PDF expense reports.
- Add OCR support to automatically process receipts.
- Integrate accounting platforms such as QuickBooks or Xero.

---

# Use Case Examples

1. **Monthly Personal Expense Review**
   - Automatically analyze and summarize monthly spending.

2. **High Spending Alerts**
   - Get notified when a category exceeds your budget.

3. **Subscription Cost Optimization**
   - Identify unnecessary recurring expenses.

4. **Family Budget Monitoring**
   - Track combined household expenses.

5. **Freelancer Expense Tracking**
   - Monitor business versus personal expenses.

There can be many more variations of this workflow depending on your specific requirements.

---

# Troubleshooting Guide

| Issue | Possible Cause | Solution |
|-------|----------------|----------|
| No data fetched | Incorrect Sheet ID or worksheet | Verify the Google Sheet configuration |
| Categories not accurate | Keyword mismatch | Update the categorization logic |
| AI report not generated | Invalid Gemini API key | Reconnect or verify API credentials |
| Emails not sent | Gmail credentials not connected | Reauthorize Gmail OAuth2 |
| Sheet2 not updating | Column mismatch | Ensure the output sheet has the correct headers |
| Always shows "Normal Expense" | Budget limit too high | Adjust the Budget Limit value |
| Missing email recipient | Recipient email not configured | Update the email address in the Settings node |

---

# Need Help?

Need assistance setting up, customizing or extending this workflow? Our automation experts can help you build scalable AI-powered expense tracking solutions tailored to your business or personal finance needs.

Whether you want to:

- Customize expense categorization and budget rules
- Enhance AI-generated financial insights and reports
- Integrate additional services like Slack, WhatsApp or databases
- Build end-to-end finance and business process automation

👉 **Explore our Process Automation Solutions:**  
https://www.weblineindia.com/process-automation-solutions.html

👉 **Contact WeblineIndia** to discuss your automation requirements:  
https://www.weblineindia.com/contact-us.html
