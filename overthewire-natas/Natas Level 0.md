# Natas Level 0
## Problem Description
Username: natas0 <br>
Password: natas0 <br>
URL: http://natas0.natas.labs.overthewire.org
## Approach

```
siddharth@siddharth-pc:~$ curl 'http://natas0.natas.labs.overthewire.org/' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:104.0) Gecko/20100101 Firefox/104.0' -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8' -H 'Accept-Language: en-US,en;q=0.5' -H 'Accept-Encoding: gzip, deflate' -H 'Authorization: Basic bmF0YXMwOm5hdGFzMA==' -H 'Connection: keep-alive' -H 'Cookie: __utma=176859643.203424577.1663008070.1663008070.1663008070.1; __utmb=176859643.5.10.1663008070; __utmc=176859643; __utmz=176859643.1663008070.1.1.utmcsr=(direct)|utmccn=(direct)|utmcmd=(none); __utmt=1' -H 'Upgrade-Insecure-Requests: 1' -H 'If-Modified-Since: Thu, 01 Sep 2022 06:27:54 GMT' -H 'If-None-Match: "396-5e797b6b5a71a-gzip"' --compressed
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas0", "pass": "natas0" };</script></head>
<body>
<h1>natas0</h1>
<div id="content">
You can find the password for the next level on this page.

<!--The password for natas1 is g9D9cREhslqBKtcA2uocGHPfMZVzeFK6 -->
</div>
</body>
</html>

```

## Password
g9D9cREhslqBKtcA2uocGHPfMZVzeFK6
