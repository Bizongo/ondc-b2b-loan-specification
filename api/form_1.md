## Loan Application Form

``` html
<!DOCTYPE html>
<html>
<head>
  <title>Loan Application Form</title>
</head>
<body>
  <h2>Loan Application Details</h2>
  <form id="loan-application-form" method="post" action="https://buyer-app-abc.becknprotocol.io/submit-form">
    <input type="hidden" name="transaction_id" value="uuid-90215d70-c146-48a9-8c11-680123456789">

    <h3>GST Information</h3>
    <label for="gst-number">GSTIN:</label>
    <input type="text" id="gst-number" name="gst_number" required><br><br>

    <label for="business-name">Business Name:</label>
    <input type="text" id="business-name" name="business_name" required><br><br>

    <label for="business-type">Business Type:</label>
    <select id="business-type" name="business_type" required>
      <option value="">Select Type</option>
      <option value="Proprietorship">Proprietorship</option>
      <option value="Partnership">Partnership</option>
      <option value="Private Limited">Private Limited Company</option>
    </select><br><br>

    <label for="registration-date">Registration Date:</label>
    <input type="date" id="registration-date" name="registration_date" required><br><br>

    <label for="gst-return-period">GST Return Period (MM-YYYY):</label>
    <input type="month" id="gst-return-period" name="gst_return_period" required><br><br>

    <label for="gst-returns-file">Upload GST Returns (ZIP):</label>
    <input type="file" id="gst-returns-file" name="gst_returns_file" accept=".zip"><br><br>

    <h3>Bank Statement</h3>
    <input type="checkbox" id="use-account-aggregator" name="use_account_aggregator">
    <label for="use-account-aggregator"> I have used an Account Aggregator</label><br><br>

    <div id="account-aggregator-details">
      <label for="aggregator-name">Account Aggregator:</label>
      <select id="aggregator-name" name="aggregator_name">
        <option value="perfios">Perfios</option>
      </select><br><br>

      <label for="perfios-summary-file">Upload Perfios Summary (PDF):</label>
      <input type="file" id="perfios-summary-file" name="perfios_summary_file" accept=".pdf"><br><br>
    </div>

    <label for="bank-statement-files">Upload Last 12 Months Bank Statements (PDFs in ZIP):</label>
    <input type="file" id="bank-statement-files" name="bank_statement_files" accept=".zip"><br><br>

    <h3>Loan Details</h3>
    <label for="loan-amount">Loan Amount:</label>
    <input type="number" id="loan-amount" name="loan_amount" required><br><br>

    <label for="max-interest-rate">Maximum Acceptable Interest Rate:</label>
    <input type="number" id="max-interest-rate" name="max_interest_rate" step="0.01"><br><br>

    <button type="submit">Submit</button>
  </form>
</body>
</html>
```




---

<p align="center">

[← Back to Previous File](on_search_1.md) | [Next File →](search_2.md)

</p>

