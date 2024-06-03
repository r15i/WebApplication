# Introduction
> [!DEFINITION] Definition
> A servlet is a Java technology-based **Web component**, managed by a **container**, that generates **dynamic content**

> [!NOTE] Pros
> Servlets are platform-independent Java **classes** that are compiled to platform-neutral byte code that can be **loaded dynamically** into and run by a Java technology-enabled Web server

**N.B. Servlets are not thread-safe** -> How to handle this?
![[Pasted image 20240603112647.png]]
using final prevents any concurrences issues

----
# Servlet Lifecyle
+  `init(ServletConfig)` 
+ `service(ServletRequest, ServletResponse)`
+ `destroy()`
# log4j2 
# GET and POST Methods
## GET
+ To retrieve info from the server
+ **Idempotent** (memo: $\frac{de^x}{dx} = e^x$ so the funtion $\frac{d}{dx}$ is idempotent)
+ Parameters visible in URL
## POST
+ Send info to server
+ Not idempotent