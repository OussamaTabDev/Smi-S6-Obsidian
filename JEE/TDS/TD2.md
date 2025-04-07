
1. create index.html and access by this code on  web.xml
```xml
<welcome-file-list>

<welcome-file>newIndex.html</welcome-file> 

<\welcome-file-list>
```
2. creating Dynamic page begging with Servlet class 
```xml
<servlet>

<servlet-name>acbd</servlet-name>

<servlet-class>toProject.FirstPage</servlet-class> # PAkages.ClassName

</servlet>

<servlet-mapping>

<servlet-name>acbd</servlet-name> # like ID 

<url-pattern>/acbd</url-pattern> # URL

</servlet-mapping>
```

