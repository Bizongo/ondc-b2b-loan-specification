## Loan Application Form

``` html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Bank Statement & GST Returns</title>
</head>

<body>
  <form action="/form/submission/gst_bank_statement">
    <label for="gstinProfile">GSTIN Profile</label><br>
    <input required name="gstinProfile" type="file" accept=".json"/><br>
    <label for="gstr1">GSTR1</label><br>
    <input required name="gstr1" type="file"  accept=".json"/><br>
    <label for="gstr2A">GSTR2A</label><br>
    <input required name="gstr2A" type="file" accept=".json" /><br>
    <label for="gstr3B">GSTR3B</label><br>
    <input required name="gstr3B" type="file" accept=".json"/><br>
    <label for="bank_statement_files">Upload Last 12 Months Bank Statements:</label><br>
    <input required type="file" id="bank_statement_files" name="bank_statement_files" accept=".pdf, .xlsx, .xls"><br>
    <label for="mime_type">Select Bank Statement format</label><br>
    <select required id="mime_type" name="mime_type">
      <option value="">Select File Type</option>
      <option value="application/pdf">PDF</option>
      <option value="application/vnd.openxmlformats-officedocument.spreadsheetml.sheet">Excel (XLSX)</option>
      <option value="application/vnd.ms-excel">Excel (XLS)</option>
    </select><br>
    <input required type="hidden" id="formId" name="formId" value="FO1"><br>
    <input required type="submit" value="Submit"><br>
  </form>
</body>
</html>
```




---

<p align="center">

[← Back to Previous File](on_search_1.md) | [Next File →](search_2.md)

</p>

