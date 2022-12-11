<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="/css/about-blank.css" />
    <link rel="icon" type="image/x-icon" href="https://" />
    <title>about:blank | prxy</title>
  </head>
  <body>
    <div class="console-container">
      <div class="console">
        <h1>about:blank</h1>
        <div class="consolebody">
          <p>Enter a URL you want to be opened in a about:blank page below:</p>
          <p class="console-input"><input id="url-target" value="" autocomplete="on" type="text" autofocus /></p>
          <p>Please make sure you have the https:// on the URL, it is best to just copy the link from the actual search bar!</p>
        </div>
      </div>
      <div class="button-wrapper">
        <button id="create" class="console-button">Create page</button>
        <button class="console-button" onclick="document.getElementById('url-target').value = ''">Clear input</button>
      </div>
      <p class="credit"> . <a href=". ">website</a>.</p>
      <button onclick="alert('Hello there!\n\na system page (about:blank is counted as a system page), .');">What is this?</button>
    </div>
    <script>
      var url = document.getElementById("url-target");
      var urlObj = new window.URL(window.location.href);
      document.getElementById("create").onclick = function () {
        if (url.value.substring(0, 8) !== 'https://' && url.value.substring(0, 7) !== 'http://') {
    		url.value = 'https://' + url.value.split('https://').pop();
        } else if (url.value.substring(0, 7) == 'http://'){
        	url.value = 'https://' + url.value.split('http://').pop();
        };
        win = window.open();
        win.document.body.style.margin = "0";
        win.document.body.style.height = "100vh";
        var iframe = win.document.createElement("iframe");
        iframe.style.border = "none";
        iframe.style.width = "100%";
        iframe.style.height = "100%";
        iframe.style.margin = "0";
        iframe.referrerpolicy = "no-referrer";
        iframe.allow = "fullscreen";
        iframe.src = url.value;
        win.document.body.appendChild(iframe);
        var script = win.document.createElement("script");
        script.src = "../js/main.js";
        win.document.body.appendChild(script);
      };
    </script>
    <script src="https://3kh0.github.io/js/main.js"></script>
  </body>
</html>
