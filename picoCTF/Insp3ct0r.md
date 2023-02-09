# Insp3ct0r
# Category
Web Exploitation
# Problem Description
Kishor Balan tipped us off that the following code may need inspection: https://jupiter.challenges.picoctf.org/problem/44924/ (link) or http://jupiter.challenges.picoctf.org:44924
# Approach
![Screenshot from 2023-02-09 12-24-02](https://user-images.githubusercontent.com/90185630/217739496-7ad9bc30-9281-464b-a275-577a4db1f405.png)
Website is asking me to inspect it and also says that it is made using HTML, CSS and JavaScript.<br>
On inspecting I found part 1/3 of the flag: `picoCTF{tru3_d3`<br>
Looking at the CSS I found part 2/3 of the flag: `t3ct1ve_0r_ju5t`<br>
And finally looking at the JavaScript I found part 3/3 of the flag: `_lucky?f10be399}`<br>
On concatenating the 3 parts I get my flag.
# Flag
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?f10be399}
