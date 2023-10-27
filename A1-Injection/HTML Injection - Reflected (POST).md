# 1. Low
First look, looked similar with [HTML Injection - Reflected (GET)](HTML%20Injection%20-%20Reflected%20(GET).md). So I am gonna analysis and find out parameters sent by `POST` method.

![HTML_R-P_L0.png](image/HTML_R-P_L0.png)

So, I am going to resend it with old payload which is used in **HTMLi GET** 😛, but changed from `onerror` to `onmouseover` event: `<img/src="x"/onmouseover="confirm(1337)">`

![HTML_R-P_L1.png](image/HTML_R-P_L1.png)

And here is the result when moving the mouse over the picture:

![HTML_R-P_L2.png](image/HTML_R-P_L2.png)

---
# 2. Medium

First look, looked similar with [HTML Injection - Reflected (GET)](HTML%20Injection%20-%20Reflected%20(GET).md). So I am gonna analysis and find out parameters sent by `POST` method.

![HTML_R-P_L0.png](image/HTML_R-P_L0.png)

So, I am going to resend it with old payload which is used in **HTMLi GET** 😁, but changed from `onerror` to `onmouseover` event: `%253Cimg%252Fsrc%253D%2522x%2522%252Fonmouseover%253D%2522confirm%25281337%2529%2522%253E`

![HTML_R-P_M0.png](image/HTML_R-P_M0.png)

And here is the result when moving the mouse over the picture:

![HTML_R-P_M1.png](image/HTML_R-P_M1.png)


---
# 3. Remediation

- Validating User Input and only accept word or number only, example given using regular expression: `\w+` or `[a-zA-Z0-9 ]+`
- Using function to filter input: 
	- `$value = htmlentities($_GET['src'], ENT_QUOTES);`
	- `$value = htmlspecialchars($_GET['src'], ENT_QUOTES);`
- Using [sanitize filter php](https://www.php.net/manual/en/filter.filters.sanitize.php)