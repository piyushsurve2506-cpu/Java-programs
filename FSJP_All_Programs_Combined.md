# FSJP Practical Programs

Each section below is the source for the named file. For HTML projects, keep linked files in the same folder. See the ZIP's README for setup notes.


## `README.md`

```markdown
# FSJP Practical Programs (Java, HTML, CSS, JavaScript, JSP, Servlet)

This folder contains sample solutions for all 13 questions from the supplied list.

## How to use
- Java programs: open Eclipse, create a Java project, then create a separate class for each `.java` file. Keep the class name the same as the filename.
- HTML/CSS/JavaScript: open the `.html` file in a browser. Keep linked `.css` and `.js` files in the same folder as shown.
- JSP and Servlet: these require a Java web project and a servlet container such as Apache Tomcat. The servlet example uses `javax.servlet`, suitable for older Java EE / Tomcat 9 setups. For Tomcat 10+, change `javax.servlet` imports to `jakarta.servlet`.
- These are educational examples. Adapt names and output formatting to your college requirements.

## Programs
1. `01_ArithmeticOperations/ArithmeticOperations.java`
2. `02_CarClass/Car.java`
3. `03_ConstructorOverloading/ConstructorOverloading.java`
4. `04_MethodOverloading/MethodOverloading.java`
5. `05_SingleInheritance/SingleInheritance.java`
6. `06_MultilevelInheritance/MultilevelInheritance.java`
7. `07_ExceptionHandling/ExceptionHandling.java`
8. `08_CSS_Types/index.html` and `external.css`
9. `09_StaticWebpage/index.html` and `style.css`
10. `10_EmailValidation/index.html`
11. `11_JSP_Objects/objects.jsp`
12. `12_DOM_BackgroundColor/index.html`
13. `13_HTTP_Servlet/HelloServlet.java`

## Upload to GitHub
To keep the source files visible on GitHub, extract this ZIP first, then upload the files/folders to your repository. Uploading the ZIP alone stores it as a downloadable archive, but does not display each source file separately.
```


## `01_ArithmeticOperations/ArithmeticOperations.java`

```java
import java.util.Scanner;

public class ArithmeticOperations {
    private double first;
    private double second;

    public ArithmeticOperations(double first, double second) {
        this.first = first;
        this.second = second;
    }

    public void displayResults() {
        System.out.println("Addition = " + (first + second));
        System.out.println("Subtraction = " + (first - second));
        System.out.println("Multiplication = " + (first * second));

        if (second != 0) {
            System.out.println("Division = " + (first / second));
            System.out.println("Remainder = " + (first % second));
        } else {
            System.out.println("Division and remainder are not possible when the second number is zero.");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter first number: ");
        double a = sc.nextDouble();
        System.out.print("Enter second number: ");
        double b = sc.nextDouble();

        ArithmeticOperations obj = new ArithmeticOperations(a, b);
        obj.displayResults();
        sc.close();
    }
}
```


## `02_CarClass/Car.java`

```java
class Car {
    String brand;
    String color;
    int speed;

    void displayDetails() {
        System.out.println("Brand: " + brand);
        System.out.println("Color: " + color);
        System.out.println("Speed: " + speed + " km/h");
    }

    public static void main(String[] args) {
        Car myCar = new Car(); // creating an object
        myCar.brand = "Toyota";
        myCar.color = "White";
        myCar.speed = 80;
        myCar.displayDetails();
    }
}
```


## `03_ConstructorOverloading/ConstructorOverloading.java`

```java
public class ConstructorOverloading {
    String name;
    int age;

    ConstructorOverloading() {
        name = "Unknown";
        age = 0;
    }

    ConstructorOverloading(String n) {
        name = n;
        age = 0;
    }

    ConstructorOverloading(String n, int a) {
        name = n;
        age = a;
    }

    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        ConstructorOverloading obj1 = new ConstructorOverloading();
        ConstructorOverloading obj2 = new ConstructorOverloading("Amit");
        ConstructorOverloading obj3 = new ConstructorOverloading("Neha", 20);

        obj1.display();
        obj2.display();
        obj3.display();
    }
}
```


## `04_MethodOverloading/MethodOverloading.java`

```java
public class MethodOverloading {
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }

    double add(double a, double b) {
        return a + b;
    }

    public static void main(String[] args) {
        MethodOverloading obj = new MethodOverloading();
        System.out.println("Sum of two integers: " + obj.add(10, 20));
        System.out.println("Sum of three integers: " + obj.add(10, 20, 30));
        System.out.println("Sum of two decimal numbers: " + obj.add(2.5, 3.5));
    }
}
```


## `05_SingleInheritance/SingleInheritance.java`

```java
class Animal {
    void eat() {
        System.out.println("Animal eats food.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks.");
    }
}

public class SingleInheritance {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();  // inherited method
        d.bark();
    }
}
```


## `06_MultilevelInheritance/MultilevelInheritance.java`

```java
class LivingThing {
    void grow() {
        System.out.println("Living things grow.");
    }
}

class Animal extends LivingThing {
    void eat() {
        System.out.println("Animals eat food.");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks.");
    }
}

public class MultilevelInheritance {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.grow();
        d.eat();
        d.bark();
    }
}
```


## `07_ExceptionHandling/ExceptionHandling.java`

```java
public class ExceptionHandling {
    public static void main(String[] args) {
        try {
            int a = 10;
            int b = 0;
            int result = a / b;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Exception caught: cannot divide by zero.");
        } finally {
            System.out.println("Finally block always executes.");
        }
    }
}
```


## `08_CSS_Types/index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Types of CSS</title>
    <!-- External CSS -->
    <link rel="stylesheet" href="external.css">

    <!-- Internal CSS -->
    <style>
        h2 {
            color: darkgreen;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1 style="color: blue;">Inline CSS Example</h1>
    <h2>Internal CSS Example</h2>
    <p>This paragraph is styled using the external CSS file.</p>
</body>
</html>
```


## `08_CSS_Types/external.css`

```css
body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    padding: 20px;
}

p {
    color: darkred;
    font-size: 18px;
}
```


## `09_StaticWebpage/index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>My College Webpage</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Welcome to My Webpage</h1>
        <p>A simple static webpage using HTML and CSS</p>
    </header>

    <main>
        <h2>About Me</h2>
        <p>I am a student learning programming and web development.</p>

        <h2>My Subjects</h2>
        <ul>
            <li>Java Programming</li>
            <li>HTML and CSS</li>
            <li>JavaScript</li>
        </ul>
    </main>

    <footer>
        <p>Created for a college practical.</p>
    </footer>
</body>
</html>
```


## `09_StaticWebpage/style.css`

```css
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #f4f7fb;
    color: #222;
}

header {
    background-color: #245a9b;
    color: white;
    text-align: center;
    padding: 24px;
}

main {
    padding: 20px;
}

h2 {
    color: #245a9b;
}

footer {
    text-align: center;
    padding: 12px;
    background-color: #ddd;
}
```


## `10_EmailValidation/index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Email Validation</title>
</head>
<body>
    <h2>Validate Email Address</h2>
    <form onsubmit="return validateEmail();">
        <label for="email">Enter email:</label>
        <input type="text" id="email" name="email">
        <button type="submit">Validate</button>
    </form>
    <p id="message"></p>

    <script>
        function validateEmail() {
            const email = document.getElementById("email").value.trim();
            const pattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            const message = document.getElementById("message");

            if (pattern.test(email)) {
                message.textContent = "Valid email address.";
                message.style.color = "green";
            } else {
                message.textContent = "Please enter a valid email address.";
                message.style.color = "red";
            }
            return false; // keep the result on this page
        }
    </script>
</body>
</html>
```


## `11_JSP_Objects/objects.jsp`

```jsp
<%@ page import="java.util.Date" %>
<!DOCTYPE html>
<html>
<head>
    <title>JSP Implicit and Explicit Objects</title>
</head>
<body>
    <h2>JSP Implicit Objects</h2>
    <p>Request method: <%= request.getMethod() %></p>
    <p>Server name: <%= request.getServerName() %></p>
    <p>Session ID: <%= session.getId() %></p>
    <p>Application server info: <%= application.getServerInfo() %></p>
    <p>Current date using out: <% out.println(new Date()); %></p>

    <h2>Explicit Object</h2>
    <%
        Date today = new Date(); // explicitly creating an object
    %>
    <p>Date object created in JSP: <%= today %></p>
</body>
</html>
```


## `12_DOM_BackgroundColor/index.html`

```html
<!DOCTYPE html>
<html>
<head>
    <title>Change Background Automatically</title>
</head>
<body>
    <h2>Background color changes every 5 seconds</h2>
    <p>The DOM is used to change the background color.</p>

    <script>
        const colors = ["lightblue", "lightyellow", "lightgreen", "pink", "lavender"];
        let index = 0;

        function changeBackground() {
            document.body.style.backgroundColor = colors[index];
            index = (index + 1) % colors.length;
        }

        changeBackground();
        setInterval(changeBackground, 5000);
    </script>
</body>
</html>
```


## `13_HTTP_Servlet/HelloServlet.java`

```java
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/hello")
public class HelloServlet extends HttpServlet {
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        response.setContentType("text/html;charset=UTF-8");

        PrintWriter out = response.getWriter();
        out.println("<!DOCTYPE html>");
        out.println("<html><head><title>Hello Servlet</title></head><body>");
        out.println("<h1>Hello! This is an HTTP Servlet.</h1>");
        out.println("</body></html>");
    }
}
```
