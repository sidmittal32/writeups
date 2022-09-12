# Android x86
## Category
Forensics
## Problem Description
There are some secrets on this phone image. Please find the flag!<br>
https://csaw-22-main-bucket.s3.amazonaws.com/android_forensics_easy.zip[https://csaw-22-main-bucket.s3.amazonaws.com/android_forensics_easy.zip]
## Approach
Using the ``tsk_recover`` command under sleuthkit[https://www.sleuthkit.org/] I was able to recover all the files in the phone image.

```
siddharth@siddharth-pc:~/Desktop/Cryptonite Tasks/CSAW$ tsk_recover -i raw -o 63 -e android_forensics_easy.dd temp/
Files Recovered: 2030
```

At ``/home/siddharth/Desktop/Cryptonite Tasks/CSAW/temp/android-9.0-r2/data/data/com.example.android.notepad/databases`` I found note_pad.db which contained the following text:

```
to do list:
[ ] wash  dishes
[ ] fold clothes
[done] delete secret note with flag
```

I used ``srch_strings`` to search for secret note.

```
siddharth@siddharth-pc:~/Desktop/Cryptonite Tasks/CSAW$ srch_strings android_forensics_easy.dd | grep "secret note"
secretsecret note
secret note
ZmxhZ3tldjFkZW5jZV9uMHRfZGVsM3RlZH0=secret note
secret note
ZmxhZ3tldjFkZW5jZV9uMHRfZGVsM3RlZH0=secret note
[done] delete secret note with flag
secret note
ZmxhZ3tldjFkZW5jZV9uMHRfZGVsM3RlZH0=secret note
[done] delete secret note with flagto do list:
[done] delete secret note with flag
secret note
ZmxhZ3tldjFkZW5jZV9uMHRfZGVsM3RlZH0=secret note
[done] delete secret note with flagto do list:
[done] delete secret note with flag
```

Converting ``ZmxhZ3tldjFkZW5jZV9uMHRfZGVsM3RlZH0=`` from base64 and voila!
## Flag
flag{ev1dence_n0t_del3ted}
