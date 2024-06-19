``` html
<!DOCTYPE html>
<html>
<head>
  <title>Invoice Upload</title>
</head>
<body>
  <h2>Invoice Upload</h2>

  <label for="invoice_file">Upload Invoice (PDF):</label>
  <input type="file" id="invoice_file" name="invoice_file" accept=".pdf"><br><br>

  <label for="invoice_number">Invoice Number:</label>
  <input type="text" id="invoice_number" name="invoice_number" required><br><br>

  <label for="invoice_date">Invoice Date:</label>
  <input type="date" id="invoice_date" name="invoice_date" required><br><br>

  <label for="invoice_amount">Invoice Amount (INR):</label>
  <input type="number" id="invoice_amount" name="invoice_amount" required><br><br>

  <label for="vendor_name">Vendor Name:</label>
  <input type="text" id="vendor_name" name="vendor_name" required><br><br>

  <input type="submit" value="Submit Invoice">
</body>
</html>
```



---

<p align="center">

[← Back to Previous File](on_confirm.md) | [Next File →](update.md)

</p>

