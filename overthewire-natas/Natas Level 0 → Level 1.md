# Natas Level 0 → Level 1
## Problem Description
Username: natas1 <br>
URL: http://natas1.natas.labs.overthewire.org
## Approach

```
siddharth@siddharth-pc:~$ curl 'http://natas1.natas.labs.overthewire.org/' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:104.0) Gecko/20100101 Firefox/104.0' -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8' -H 'Accept-Language: en-US,en;q=0.5' -H 'Accept-Encoding: gzip, deflate' -H 'Authorization: Basic bmF0YXMxOmc5RDljUkVoc2xxQkt0Y0EydW9jR0hQZk1aVnplRks2' -H 'Connection: keep-alive' -H 'Cookie: __utma=176859643.203424577.1663008070.1663008070.1663008070.1; __utmb=176859643.8.10.1663008070; __utmc=176859643; __utmz=176859643.1663008070.1.1.utmcsr=(direct)|utmccn=(direct)|utmcmd=(none); __utmt=1' -H 'Upgrade-Insecure-Requests: 1' -H 'If-Modified-Since: Thu, 01 Sep 2022 06:27:54 GMT' -H 'If-None-Match: "427-5e797b6b23c14-gzip"' --compressed
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas1", "pass": "g9D9cREhslqBKtcA2uocGHPfMZVzeFK6" };</script></head>
<body oncontextmenu="javascript:alert('right clicking has been blocked!');return false;">
<h1>natas1</h1>
<div id="content">
You can find the password for the
next level on this page, but rightclicking has been blocked!

<!--The password for natas2 is h4ubbcXrWqsTo7GGnnUMLppXbOogfBZ7 -->
</div>
</body>
</html>

```

## Password
h4ubbcXrWqsTo7GGnnUMLppXbOogfBZ7
