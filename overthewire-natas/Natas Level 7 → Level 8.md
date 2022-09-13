# Natas Level 7 → Level 8
## Problem Description
Username: natas8 <br>
URL:http://natas8.natas.labs.overthewire.org
## Approach
We have the encoded secret **3d3d516343746d4d6d6c315669563362** and also we know how it was encoded, so, I can decode it in python.

```python
import base64

encodedSecret = "3d3d516343746d4d6d6c315669563362"
secret = base64.b64decode(bytes(bytes.fromhex(encodedSecret)[::-1]))
print(secret)
```
I got the secret **oubWYf2kBq**. Putting it in and voila!
## Password
Sda6t0vkOPkM8YeOZkAGVhFoaplvlJFd
