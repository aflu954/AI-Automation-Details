🎯 Objective
Your goal is to build an n8n workflow that automatically cleans a messy Excel file and produces a clean, standardized dataset.
📝 Scenario
You have received an Excel file from a client containing customer data. The file contains several issues that need to be resolved before it can be used for business operations:
Empty rows
Duplicate records
Inconsistent capitalization
Extra spaces before and after text
Missing values
Invalid phone numbers
Invalid email addresses
Mixed date formats
📊 Sample Columns & Data Pattern
Full Name
Email
Phone
City
Registration Date
john doe
john@gmail.com
01712345678
dhaka
01/05/2025
JOHN DOE
john@gmail.com
01712345678
Dhaka
May 1, 2025
Sarah Khan
sarah@gmail
01987654321
Chittagong
2025-05-03
Ahmed Ali
(Missing)
01811111111
DHAKA
03-05-2025

🛠 Core Tasks
📥 Step 1: Import the Excel File
Upload the Excel file into n8n.
Read all rows from the spreadsheet.
Expected Output: All records should be available inside the workflow.
❌ Step 2: Remove Empty Rows
Identify and remove rows where key fields like Full Name, Email, or Phone are completely empty.
Expected Output: No completely empty records remain.
✂️ Step 3: Trim Extra Spaces
Clean all text fields by removing leading spaces, trailing spaces, and multiple spaces between words.
Example: John Doe ➡️ John Doe
🔠 Step 4: Standardize Capitalization
Names & Cities: Convert to Proper Case (Capitalize the first letter of each word).
Before: john doe / DHAKA / DhAkA
After: John Doe / Dhaka
📧 Step 5: Validate Email Addresses
Remove records where the email format is invalid.
Valid: john@gmail.com
Invalid: john@gmail, john@
Expected Output: Only valid email addresses remain.
📱 Step 6: Validate Phone Numbers
Keep only Bangladeshi mobile numbers that start with 01 and contain exactly 11 digits.
Valid: 01712345678, 01812345678
Invalid: 1712345678 (10 digits), 017123456789 (12 digits)
📅 Step 7: Standardize Dates
Convert all mixed date formats into a single standard format: YYYY-MM-DD.
Before: 01/05/2025, May 1, 2025, 03-05-2025
After: 2025-05-01
👥 Step 8: Remove Duplicate Records
Identify duplicates based on Email OR Phone Number.
Keep only the first occurrence.
Expected Output: No duplicate customers remain.
✨ Step 9: Create a Clean Dataset
Generate a final dataset with the structure: Full Name | Email | Phone | City | Registration Date. All data must be valid, consistent, and duplicate-free.
📤 Step 10: Export the Clean File
Export the final cleaned dataset into a new Excel file named: clean_customers.xlsx.
🎁 Bonus Tasks (Optional but Recommended)
Bonus 1 (Customer ID Generation): Add a new column named Customer ID using the format: CUST-0001, CUST-0002, CUST-0003, etc.
Bonus 2 (Create a Summary Report): Generate a summary at the end showing:
Total Rows Imported
Rows Removed (Empty/Invalid)
Duplicate Rows Removed
Invalid Emails Removed
Invalid Phones Removed
Final Row Count
📥 Deliverables for Submission
To successfully complete this assignment, please submit:
✅ n8n Workflow JSON file.
✅ Original Excel File (The messy one used for testing).
✅ Cleaned Excel File (clean_customers.xlsx).b  
✅ Screenshot of your complete n8n workflow.
✅ Summary Report (Text format or screenshot).
✅ Must Submit the Screen Record Video
🏆 Success Criteria
A submission will be considered successful if:
All messy data is cleaned correctly according to the steps.
No duplicate records exist.
All emails and phone numbers are verified and valid.
Dates are perfectly standardized.
The final Excel file is exported successfully.
The workflow runs automatically without requiring manual intervention.
