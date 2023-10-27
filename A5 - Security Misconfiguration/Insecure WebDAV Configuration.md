
## 1. What is WebDAV
WebDAV (Web Distributed Authoring and Versioning) is a set of extensions to the Hypertext Transfer Protocol (HTTP), which allows user agents to collaboratively author contents directly in an HTTP web server by providing facilities for concurrency control and namespace operations

Following Microsoft defined about [WebDAV](https://learn.microsoft.com/en-us/previous-versions/office/developer/exchange-server-2003/aa142923(v=exchg.65)), We can also known and use following method.

![WebDAV_I0.png](img/WebDAV_I0.png)

---
## 2. Vulnerability

On first look. the Web page is loaded into `/bWAPP/sm_webdav.php`.

![WebDAV_V0.png](img/WebDAV_V0.png)

And here is default on API `/WebDAV/`

![WebDAV_V1.png](img/WebDAV_V1.png)
### 2.1 PUT Method
Trying with PUT method to upload a PHP shell.

![WebDAV_P0.png](img/WebDAV_P0.png)
After created a file success with PHP `system()` call
![WebDAV_P1.png](img/WebDAV_P1.png)

### 2.2 DELETE Method

![WebDAV_D1.png](img/WebDAV_D1.png)

Using `DELETE` Method and success

![WebDAV_D0.png](img/WebDAV_D0.png)

## 3. Tools help determine and exploit
- davtest
![WebDAV_Davtest0.png](img/WebDAV_Davtest0.png)

- cadaver
![WebDAV_Cadaver0.png](img/WebDAV_Cadaver0.png)

## 4. Prevention
- Disable WebDav
- Restrict Access
