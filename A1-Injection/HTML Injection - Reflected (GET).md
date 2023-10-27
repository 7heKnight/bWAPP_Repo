# 1. Low

In the beginning, I found 2 text box: **First name** and **Last name**, So I tried to input some data: 123 & 456 as following picture.

![HTML_R-G.png](image/HTML_R-G.png)

After submit, the data sent to server via `GET` method in following picture:
- `http://bee.bug/bWAPP/htmli_get.php?firstname=123&lastname=456&form=submit`

Server return Welcome **123 456**

![HTML_R-G_L.png](image/HTML_R-G_L.png)

I changed `lastname` variable as following link: `http://bee.bug/bWAPP/htmli_get.php?firstname=123&lastname=<img/src="x"/onerror="confirm(1337)">&form=submit`

And result is:

![HTML_R-G_L0.png](image/HTML_R-G_L0.png)

---
# 2. Medium
In the beginning, I found 2 text box: **First name** and **Last name**, So I tried to input some data: 123 & 456 as following picture.

![HTML_R-G.png](image/HTML_R-G.png)

After submit, the data sent to server via `GET` method in following picture:
- `http://bee.bug/bWAPP/htmli_get.php?firstname=123&lastname=456&form=submit`

Server return Welcome **123 456**

![HTML_R-G_L.png](image/HTML_R-G_L.png)

I changed `lastname` variable as following link: `http://bee.bug/bWAPP/htmli_get.php?firstname=123&lastname=%3Cscript%3E&form=submit`

I found that the payload inputted into server is sanitized:

![HTML_R-G_M.png](image/HTML_R-G_M.png)

So, I tried to double encode URL as following payload which is encoded `%` into `%25`:
- `%253Cimg%252Fsrc%253D%2522x%2522%252Fonerror%253D%2522confirm%25281337%2529%2522%253E`

And final result:

![HTML_R-G_M0.png](image/HTML_R-G_M0.png)

---
# 3. Remediation

- Validating User Input and only accept word or number only, example given using regular expression: `\w+` or `[a-zA-Z0-9 ]+`
- Using function to filter input: 
	- `$value = htmlentities($_GET['src'], ENT_QUOTES);`
	- `$value = htmlspecialchars($_GET['src'], ENT_QUOTES);`
- Using [sanitize filter php](https://www.php.net/manual/en/filter.filters.sanitize.php)