# Check size Theme

```jsx title="Console"
var script = document.createElement("script");
script.src = "https://code.jquery.com/jquery-1.12.4.js";
document.head.appendChild(script);
$(function () {
  $.getJSON(
    "https://swe16.myharavan.com/admin/sale_channels/web/call/web_api/themes/1000806553/themeforedit",
    function (result) {
      var newResult = result.data.themeFileAsset.map(
        (value, key) => value.file
      );
      var newResult = newResult.sort((a, b) => b.size - a.size);
      console.log(newResult);
    }
  );
});
```
