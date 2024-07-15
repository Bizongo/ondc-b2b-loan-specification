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
    <input required type="hidden" id="formId" name="formId" value="FO1"><br>
    <label for="financials">Last 2 year Tax Audit report</label>
    <input required type="file" id="financials" name="financials" accept=".pdf, .zip" required><br><br>
    <label for="financials">Last 2 year ITR</label>
    <input required type="file" id="financials" name="financials" accept=".pdf, .zip" required><br><br>
    <input required type="hidden" id="formId" name="formId" value="FO1"><br>
    <input required type="submit" value="Submit"><br>
  </form>
</body>
```



---

<p align="center">

[← Back to Previous File](on_search_2.md) | [Next File →](search_3.md)

</p>

