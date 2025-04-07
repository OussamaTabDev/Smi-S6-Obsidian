

``` JSP


<%@ page contentType="text/html;charset=UTF-8" language="java" %>

<!DOCTYPE html>

<html>

<head>

<title>Solution de Equation degré 2</title>

<style>

body {

font-family: Arial;

text-align: center;

margin-top: 50px;

border: 2.5px solid black;

padding: 20px;

}

.math { font-size: 24px; margin: 20px; }

input { width: 50px; text-align: center; padding: 5px; }

button {

padding: 8px 15px;

background: #4CAF50;

color: white;

border: none;

cursor: pointer;

margin-top: 10px;

}

.result {

margin-top: 20px;

padding: 15px;

background: #f0f0f0;

border-radius: 5px;

}

</style>

</head>

<body>

<h1>Résoudre Equation</h1>

<div class="math">

Ax<sup>2</sup> + Bx + C = 0

</div>

<form method="post">

A = <input type="text" name="a" required><br><br>

B = <input type="text" name="b" required><br><br>

C = <input type="text" name="c" required><br><br>

<button type="submit">Calculer</button>

</form>

  

<%-- معالجة البيانات فقط عند إرسال النموذج --%>

<%

if ("POST".equalsIgnoreCase(request.getMethod())) {

try {

double a = Double.parseDouble(request.getParameter("a"));

double b = Double.parseDouble(request.getParameter("b"));

double c = Double.parseDouble(request.getParameter("c"));

double delta = b*b - 4*a*c;

String result;

if (delta > 0) {

double x1 = (-b + Math.sqrt(delta))/(2*a);

double x2 = (-b - Math.sqrt(delta))/(2*a);

result = "Deux solutions réelles: x₁ = " + String.format("%.2f", x1) +

", x₂ = " + String.format("%.2f", x2);

} else if (delta == 0) {

double x = -b/(2*a);

result = "Une solution réelle: x = " + String.format("%.2f", x);

} else {

result = "Pas de solutions réelles";

}

%>

<div class="result">

<h3>Résultats:</h3>

<p>Pour A = <%= a %>, B = <%= b %>, C = <%= c %></p>

<p><%= result %></p>

</div>

<%

} catch (NumberFormatException e) {

%>

<div class="result" style="color: red;">

Erreur: Veuillez entrer des nombres valides

</div>

<%

} catch (Exception e) {

%>

<div class="result" style="color: red;">

Erreur: <%= e.getMessage() %>

</div>

<%

}

}

%>

</body>

</html>
```


of him


```Xml

<!DOCTYPE html>

<html lang="fr">

<head>

<meta charset="UTF-8" />

<meta name="viewport" content="width=device-width, initial-scale=1.0"/>

<title>Résolution Équation 2nd degré</title>

<style>

body {

background: #f0f4f8;

font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;

display: flex;

justify-content: center;

align-items: center;

height: 100vh;

}

  

.forum-container {

background: white;

padding: 2rem;

border-radius: 15px;

box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);

width: 400px;

}

  

h2 {

text-align: center;

color: #333;

margin-bottom: 1.5rem;

}

  

label {

display: block;

margin-bottom: 0.5rem;

font-weight: 600;

}

  

input[type="number"] {

width: 100%;

padding: 0.6rem;

margin-bottom: 1rem;

border: 1px solid #ccc;

border-radius: 8px;

font-size: 1rem;

}

  

button {

width: 100%;

padding: 0.7rem;

border: none;

background-color: #007bff;

color: white;

font-size: 1rem;

border-radius: 8px;

cursor: pointer;

transition: background 0.3s ease;

}

  

button:hover {

background-color: #0056b3;

}

  

.result {

margin-top: 1.5rem;

background-color: #f1f8ff;

padding: 1rem;

border-radius: 10px;

border: 1px solid #cfe2ff;

color: #003366;

font-weight: 500;

}

</style>

</head>

<body>

<div class="forum-container">

<h2>Forum - Équation du 2nd Degré</h2>

<form id="equationForm" method="post">

<label for="a">Coefficient a :</label>

<input type="number" name="a" required value="<%= request.getParameter("a") != null ? request.getParameter("a") : "" %>" >

  

<label for="b">Coefficient b :</label>

<input type="number" name="b" required value="<%= request.getParameter("b") != null ? request.getParameter("b") : "" %>" >

  

<label for="c">Coefficient c :</label>

<input type="number" name="c" required value="<%= request.getParameter("c") != null ? request.getParameter("c") : "" %>" >

  

<button type="submit">Résoudre</button>

</form>

  

<%

String result ;

double Delta = 0.0 ;

if ("POST".equalsIgnoreCase(request.getMethod())){

double A = Double.parseDouble(request.getParameter("a"));

double B = Double.parseDouble(request.getParameter("b"));

double C = Double.parseDouble(request.getParameter("c"));

//x = (-b ± √(b² - 4ac)) / 2a

Delta = B*B - 4 * A * C;

if (Delta > 0.0 ){

double x1 = (-B + Math.sqrt(Delta) ) / (2 * A);

double x2 = (-B - Math.sqrt(Delta) ) / (2 * A);

result = "le vars est : X1 = " + String.format("%.2f",x1) + " , X2 = " + String.format("%.2f",x2);

}else if(Delta == 0.0 ){

double x = -B/(2*A);

  

result = "Une solution réelle: x = " + String.format("%.2f", x);

}else{

result = "Pas de solutions réelles";

}

}else{

result = "Please Enter some Vars";

}

  

%>

<div id="solution" class="result" style="">

<%=Delta %>

<br>

<%= result %>

</div>

</div>

  

  

</body>

</html>



```


To convert your JSP application to use a servlet-based approach, you'll need to create a servlet class that handles the logic and then update your JSP to be a simple view. Here's how to implement this:

1. First, create a servlet class:

```java
import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/solveEquation")
public class QuadraticEquationServlet extends HttpServlet {
    
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        // Just forward to the JSP page for initial display
        request.getRequestDispatcher("/WEB-INF/quadratic.jsp").forward(request, response);
    }
    
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        
        String result = "Entrez les coefficients et cliquez sur Résoudre";
        
        try {
            double a = Double.parseDouble(request.getParameter("a"));
            double b = Double.parseDouble(request.getParameter("b"));
            double c = Double.parseDouble(request.getParameter("c"));
            
            double delta = b*b - 4 * a * c;
            
            if (a == 0) {
                result = "Ce n'est pas une équation du second degré (a = 0)";
            } else if (delta > 0) {
                double x1 = (-b + Math.sqrt(delta)) / (2 * a);
                double x2 = (-b - Math.sqrt(delta)) / (2 * a);
                result = "Deux solutions réelles : x₁ = " + String.format("%.2f", x1) + " et x₂ = " + String.format("%.2f", x2);
            } else if (delta == 0) {
                double x = -b / (2 * a);
                result = "Une solution réelle : x = " + String.format("%.2f", x);
            } else {
                result = "Pas de solutions réelles (delta < 0)";
            }
        } catch (NumberFormatException e) {
            result = "Veuillez entrer des valeurs numériques valides";
        }
        
        // Store the result in the request object
        request.setAttribute("result", result);
        
        // Forward back to the JSP
        request.getRequestDispatcher("/WEB-INF/quadratic.jsp").forward(request, response);
    }
}
```

2. Now modify your JSP file to be a view only:

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Résolution Équation 2nd degré</title>
    <style>
        body {
            background: #f0f4f8;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .form-container {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            width: 400px;
        }
        h2 {
            text-align: center;
            color: #333;
            margin-bottom: 1.5rem;
        }
        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }
        input[type="number"] {
            width: 100%;
            padding: 0.6rem;
            margin-bottom: 1rem;
            border: 1px solid #ccc;
            border-radius: 8px;
            font-size: 1rem;
        }
        button {
            width: 100%;
            padding: 0.7rem;
            border: none;
            background-color: #007bff;
            color: white;
            font-size: 1rem;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.3s ease;
        }
        button:hover {
            background-color: #0056b3;
        }
        .result {
            margin-top: 1.5rem;
            background-color: #f1f8ff;
            padding: 1rem;
            border-radius: 10px;
            border: 1px solid #cfe2ff;
            color: #003366;
            font-weight: 500;
        }
    </style>
</head>
<body>
    <div class="form-container">
        <h2>Équation du 2nd Degré</h2>
        <form id="equationForm" method="post" action="${pageContext.request.contextPath}/solveEquation">
            <label for="a">Coefficient a :</label>
            <input type="number" name="a" id="a" required value="${param.a}">
            
            <label for="b">Coefficient b :</label>
            <input type="number" name="b" id="b" required value="${param.b}">
            
            <label for="c">Coefficient c :</label>
            <input type="number" name="c" id="c" required value="${param.c}">
            
            <button type="submit">Résoudre</button>
        </form>
        
        <div class="result">
            ${result != null ? result : "Entrez les coefficients et cliquez sur Résoudre"}
        </div>
    </div>
</body>
</html>
```

3. Configure your web application structure:

```
YourApp/
├── src/
│   └── main/
│       ├── java/
│       │   └── QuadraticEquationServlet.java
│       └── webapp/
│           ├── WEB-INF/
│           │   ├── web.xml
│           │   └── quadratic.jsp
│           └── index.html (optional redirect to servlet)
```

4. Update your web.xml file (if not using annotations):

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd"
         version="4.0">
    
    <servlet>
        <servlet-name>QuadraticEquationServlet</servlet-name>
        <servlet-class>QuadraticEquationServlet</servlet-class>
    </servlet>
    
    <servlet-mapping>
        <servlet-name>QuadraticEquationServlet</servlet-name>
        <url-pattern>/solveEquation</url-pattern>
    </servlet-mapping>
    
    <welcome-file-list>
        <welcome-file>index.html</welcome-file>
    </welcome-file-list>
</web-app>
```

5. Optional - Create an index.html to redirect to your servlet:

```html
<!DOCTYPE html>
<html>
<head>
    <meta http-equiv="Refresh" content="0; URL=solveEquation" />
</head>
<body>
    <p>Redirecting to Quadratic Equation Solver...</p>
</body>
</html>
```

Key benefits of this servlet approach:

1. Separation of concerns - business logic is in the servlet, presentation in the JSP
2. Better maintainability - you can update the UI without touching the calculation logic
3. Improved security - JSP file is in WEB-INF, not directly accessible
4. Better code organization - follows the MVC pattern
5. Easier to extend - you can add more features like saving equations or history

To compile and deploy:

1. Compile your servlet class
2. Place all files in the correct structure
3. Package as a WAR file
4. Deploy to your servlet container (like Tomcat, Jetty, etc.)