# Ascii
## Category
Miscellaneous
## Problem Description
Can you read the flag?

[generate.py](https://static.insomnihack.ch/media/generate-5612300a7e5a0bf0120c06ab3ccbc3cb0003e209d1e6667d70bf0797d82a307c.py)

[output.txt](https://static.insomnihack.ch/media/output-82af45781b1a0057f2bf9b69d1702976928383941b7f9651de8e2c819935bcf2.txt)
## Approach
Reversing generate.py using the following code with output.txt as text.

```py
def splitText(text):
    a = text.split("\n")
    b = []
    for i in range(25):
        b.append(a[i].replace("#", "_"))
    return '\n'.join(b)

text1, text2, text3 = splitText(res)
text1 = text1.replace("\n", "_")
text2 = text2.replace("\n", "_")
text3 = text3.replace("\n", "_")
text1 = text1[4:-1]
text2 = text2[4:-1]
text3 = text3[4:-1]
```

From the above code I got the following output.

```
text1 = INS_A_B
text2 = C_D_E
text3 = F_G_H
```

On concatenating text1, text2 and text3 I get `INSA_B_C_D_E_F_G_H`.
## Flag
INSA_B_C_D_E_F_G_H

```
Flag is incorrect
```
