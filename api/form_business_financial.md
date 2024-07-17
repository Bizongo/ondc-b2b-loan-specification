``` html
<!DOCTYPE html>
<html>
<head>
  <title>Business & Financial Details Form</title>
</head>
<body>
  <form action="/form/submission/business_financial">
    <label for="shareholding_pattern">Shareholding Pattern</label>
    <input type="file" id="shareholding_pattern" name="shareholding_pattern" accept=".json, .pdf" required><br>
    <label for="financials">Last 2 year Tax Audit report</label>
    <input required type="file" id="tax_audit_report" name="tax_audit_report" accept=".pdf, .zip" required><br><br>
    <label for="financials">Last 2 year ITR</label>
    <input required type="file" id="itr" name="itr" accept=".pdf, .zip" required><br><br>
    <label for="financials">Provisionals of latest FY</label>
    <input required type="file" id="provisionals-latest-fy" name="provisionals-latest-fy" accept=".pdf, .zip" required><br><br>
    <input required type="hidden" id="formId" name="formId" value="FO1"><br>
    <input required type="submit" value="Submit"><br>
  </form>
</body>
```



---

<p align="center">

[← Back to Previous File](on_search_2.md) | [Next File →](search_3.md)

</p>

