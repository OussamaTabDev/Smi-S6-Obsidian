### **📌 JSP (JavaServer Pages) – Complete Guide**

JSP (**JavaServer Pages**) is a **server-side technology** used to create **dynamic web pages** in Jakarta EE (formerly Java EE). It **combines HTML and Java code**, making it easier to generate dynamic content compared to Servlets.

✅ **JSP is often used for:**

- Generating **dynamic HTML content**
- Displaying **database data**
- Handling **form submissions**
- Building **views** in MVC (Model-View-Controller) architecture

---

## **1️⃣ How JSP Works**

When a browser requests a `.jsp` file:

1. Tomcat **converts the JSP file into a Java Servlet**.
2. The **Servlet generates an HTML response**.
3. The **browser receives the response** and displays the page.

---

## **2️⃣ Basic JSP Syntax**

JSP files use special tags to embed Java code inside HTML.

### **📝 Example: Basic JSP File (`index.jsp`)**

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head><title>My First JSP</title></head>
<body>
    <h1>Welcome to JSP!</h1>
    <p>Current time: <%= new java.util.Date() %></p>
</body>
</html>
```

✅ **Explanation:**

- `<%@ page %>` → **Page directive**, defines settings (e.g., character encoding).
- `<%= new java.util.Date() %>` → **JSP expression**, outputs the current date/time.
- Tomcat **compiles** this JSP file into a Servlet and sends the generated **HTML** to the browser.

📌 **URL to access this page:**

```
http://localhost:8080/yourapp/index.jsp
```

---

## **3️⃣ JSP Scripting Elements**

|Element|Syntax|Purpose|
|---|---|---|
|**Expression**|`<%= value %>`|Outputs a value in the HTML page|
|**Declaration**|`<%! code %>`|Declares variables/methods (runs once)|
|**Scriptlet**|`<% code %>`|Runs Java code inside the page|
|**Directive**|`<%@ ... %>`|Configures the JSP page|
|**Comment**|`<%-- comment --%>`|Hidden comment (not sent to browser)|

---

### **🔹 JSP Expressions (`<%= %>`)**

Used to **print values** inside the HTML page.

Example:

```jsp
<p>Current time: <%= new java.util.Date() %></p>
```

🔹 Prints: `Current time: Mon Mar 04 12:30:00 UTC 2025`

---

### **🔹 JSP Declarations (`<%! %>`)**

Used to **declare variables and methods**.

Example:

```jsp
<%! int counter = 0; %>
<p>Counter: <%= counter %></p>
```

🔹 **Runs once** when the page loads.

---

### **🔹 JSP Scriptlets (`<% %>`)**

Used to **run Java code** inside the page.

Example:

```jsp
<%
    int num = 5;
    out.println("<p>Number: " + num + "</p>");
%>
```

🔹 Prints: `Number: 5`

---

### **🔹 JSP Directives (`<%@ %>`)**

Used to configure the page.

Example:

```jsp
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
```

🔹 Sets the **MIME type** (HTML output) and **encoding**.

---

## **4️⃣ JSP with Forms (Handling User Input)**

JSP can **process form data** using `request.getParameter()`.

### **🔹 Example: Form (`form.jsp`)**

```jsp
<form action="hello.jsp" method="post">
    <input type="text" name="username" placeholder="Enter your name">
    <button type="submit">Submit</button>
</form>
```

### **🔹 Example: Process Form Data (`hello.jsp`)**

```jsp
<%@ page contentType="text/html" %>
<html>
<body>
    <h1>Hello, <%= request.getParameter("username") %>!</h1>
</body>
</html>
```

📌 **User enters "John" → Page displays:**

```
Hello, John!
```

---

## **5️⃣ JSP with Java Beans (Separation of Logic)**

Instead of writing Java logic inside JSP, we can use **JavaBeans** to separate **business logic**.

### **🔹 JavaBean (`User.java`)**

```java
public class User {
    private String name;
    
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
}
```

### **🔹 JSP Using Bean (`user.jsp`)**

```jsp
<jsp:useBean id="user" class="User" scope="session"/>
<jsp:setProperty name="user" property="name" value="John Doe"/>

<p>Welcome, <jsp:getProperty name="user" property="name"/>!</p>
```

✅ **Separates Java logic from HTML.**

---

## **6️⃣ JSP with Database (JDBC Example)**

JSP can fetch and display **data from a database**.

### **🔹 Example: Display Users from MySQL (`users.jsp`)**

```jsp
<%@ page import="java.sql.*" %>
<html>
<body>
    <h1>User List</h1>
    <ul>
    <%
        Connection conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/mydb", "root", "password");
        Statement stmt = conn.createStatement();
        ResultSet rs = stmt.executeQuery("SELECT username FROM users");

        while (rs.next()) {
            out.println("<li>" + rs.getString("username") + "</li>");
        }
        conn.close();
    %>
    </ul>
</body>
</html>
```

📌 **Displays a list of users from MySQL.**

---

## **7️⃣ JSP vs Servlets**

|Feature|JSP|Servlets|
|---|---|---|
|**Syntax**|HTML with Java|Pure Java|
|**Best for**|Views (HTML output)|Business logic|
|**Performance**|Slower (compiles to Servlet)|Faster|

📌 **Best Practice:** Use **Servlets for logic**, JSP for **view (UI).**

---

## **8️⃣ JSTL (JSP Standard Tag Library)**

JSTL makes JSP cleaner by replacing Java code with **tags**.

🔹 Example: Looping Without Java Code

```jsp
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<c:forEach var="num" begin="1" end="5">
    <p>Number: ${num}</p>
</c:forEach>
```

📌 **More readable than `<% for (...) { %> ... <% } %>`.**

---

## **9️⃣ JSP Lifecycle**

JSP follows this lifecycle in Tomcat:

1. **JSP Request** (User visits `index.jsp`)
2. **JSP is compiled** into a Servlet
3. **Servlet executes**, generating HTML
4. **Response is sent to the browser**

✅ **JSP is converted into a Servlet behind the scenes.**

---

## **🔟 Summary: Why Use JSP?**

✔ **Easy to write** (mixes HTML + Java).  
✔ **Faster than Servlets for UI development**.  
✔ **Works with JavaBeans & JSTL** for clean code.  
✔ **Good for MVC architecture (Model-View-Controller)**.

---

## **📌 What’s Next?**

Do you want:  
1️⃣ **A full JSP + Servlet + Database project?**  
2️⃣ **More exercises on JSP?**  
3️⃣ **An explanation of JSP with MVC?**

Let me know! 🚀