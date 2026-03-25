function doPost(e) {
  try {
    var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
    var data = JSON.parse(e.postData.contents);
    sheet.appendRow([data.name, data.dept, data.phone, data.desc, data.date]);
    return ContentService.createTextOutput(&quot;Success&quot;);
  } catch (err) {
    return ContentService.createTextOutput(&quot;Error: &quot; + err.message);
  }
}
