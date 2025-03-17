### **📌 Getting Started with Jakarta / Java EE Web Development on Tomcat**

Now that you've chosen **Tomcat**, let’s go step by step to create a **Jakarta EE web application**.

---

## **1️⃣ Install Required Tools**

Before we start, make sure you have the following installed:

🔹 **Java Development Kit (JDK 17 or later)** – Download from [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html) or [AdoptOpenJDK](https://adoptium.net/).  
🔹 **Apache Tomcat 10+** – Download from [Tomcat Official Website](https://tomcat.apache.org/download-10.cgi).  
🔹 **IDE (Optional but recommended)** – Use **Eclipse, IntelliJ IDEA, or VS Code**.

---

## **2️⃣ Setup Tomcat**

1️⃣ **Extract Tomcat**

- Download and unzip Tomcat into a folder (e.g., `C:\tomcat\` or `/opt/tomcat/`).  
    2️⃣ **Run Tomcat**
- Open a terminal and navigate to the Tomcat `bin` folder.
- Run the startup script:
    - **Windows:** `startup.bat`
    - **Linux/macOS:** `./startup.sh`
- Open your browser and go to:
    
    ```
    http://localhost:8080
    ```
    
- You should see the **Tomcat Welcome Page**.

---

## **3️⃣ Create a Simple Jakarta EE Web Application**

### **📂 Project Structure**

```
my-web-app/
│── src/main/java/ (Java classes)
│── src/main/webapp/ (HTML, JSP, CSS, JS)
│── WEB-INF/web.xml (Configuration)
│── pom.xml (If using Maven)
```

### **📝 Create a Simple Servlet**

📌 Servlets handle HTTP requests and send responses.

🔹 **Create `HelloServlet.java` inside `src/main/java/`**

```java
import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import java.io.IOException;

@WebServlet("/hello")
public class HelloServlet extends HttpServlet {
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        response.setContentType("text/plain");
        response.getWriter().write("Hello, Jakarta EE on Tomcat!");
    }
}
```

**what is [[setContextType.text]]**

✅ **What this does?**

- The `@WebServlet("/hello")` annotation maps this servlet to `http://localhost:8080/my-web-app/hello`.
- It responds with **"Hello, Jakarta EE on Tomcat!"** when accessed.

---

## **4️⃣ Configure Deployment in Tomcat**

### **1️⃣ Add `web.xml` Configuration File**

📌 Inside `WEB-INF/web.xml`, add:

```xml
<web-app xmlns="http://jakarta.ee/xml/ns/jakartaee" version="5.0">
    <display-name>My Jakarta EE App</display-name>
</web-app>
```

- This tells Tomcat it's a **Jakarta EE Web App**.
- Jakarta EE 9+ uses **`jakarta.*`** instead of `javax.*`.

---

### **5️⃣ Package and Deploy the Application**

📌 If using **Maven**, run:

```sh
mvn package
```

- This creates a `WAR` file (`my-web-app.war`) in `target/` folder.

📌 **Deploy to Tomcat**

- Copy `my-web-app.war` to `tomcat/webapps/` directory.
- Restart Tomcat and open:
    
    ```
    http://localhost:8080/my-web-app/hello
    ```
    
- You should see:
    
    ```
    Hello, Jakarta EE on Tomcat!
    ```
    

---

### **🎯 Next Steps**

✅ **Add [[JSP pages]]** to serve dynamic HTML content.  
✅ **Use JDBC or JPA** to connect to a database.  
✅ **Add filters and session management** for authentication.

Would you like help with **JSP, database integration, or session handling next?** 🚀