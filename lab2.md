Hello World!!!

# Lab Report 1 - Remote Access and FileSystem 
Name: Kiruthika Marikumaran 
PID: A17877875
 
---

# ChatServer Code
---
```
//ChatServer.java
import java.io.IOException;
import java.net.URI;
import java.util.*; 

class Handler implements URLHandler {
    ArrayList<String> ans = new ArrayList<>(); 
    String x = ""; 

    public String handleRequest(URI url) {
        if(url.getPath().equals("/")){
            return x; 
        }
        else if(url.getPath().equals("/add-message")){
            String[] parameters = url.getQuery().split("&");
            String[] user = parameters[1].split("="); 
            String[] messages = parameters[0].split("="); 
            if(user[0].equals("user")&&messages[0].equals("s")){
                ans.add(user[1]+": "+messages[1]); 
            }
            x = String.join("\n", ans); 
            return x;
        }
        return "404 Not Found!";

    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```

```
//Server.java

// A simple web server using Java's built-in HttpServer

// Examples from https://dzone.com/articles/simple-http-server-in-java were useful references

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetSocketAddress;
import java.net.URI;

import com.sun.net.httpserver.HttpExchange;
import com.sun.net.httpserver.HttpHandler;
import com.sun.net.httpserver.HttpServer;

interface URLHandler {
    String handleRequest(URI url);
}

class ServerHttpHandler implements HttpHandler {
    URLHandler handler;
    ServerHttpHandler(URLHandler handler) {
      this.handler = handler;
    }
    public void handle(final HttpExchange exchange) throws IOException {
        // form return body after being handled by program
        try {
            String ret = handler.handleRequest(exchange.getRequestURI());
            // form the return string and write it on the browser
            exchange.sendResponseHeaders(200, ret.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(ret.getBytes());
            os.close();
        } catch(Exception e) {
            String response = e.toString();
            exchange.sendResponseHeaders(500, response.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(response.getBytes());
            os.close();
        }
    }
}

public class Server {
    public static void start(int port, URLHandler handler) throws IOException {
        HttpServer server = HttpServer.create(new InetSocketAddress(port), 0);

        //create request entrypoint
        server.createContext("/", new ServerHttpHandler(handler));

        //start the server
        server.start();
        System.out.println("Server Started!");
    }
}


```
# Using /add-message 
---

1. 
<img width="1440" alt="Screen Shot 2024-01-30 at 10 35 19 AM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/0359b0a9-fc05-4e35-bd25-ea3d4bacc798">

- Which methods in your code are called?<br> </br>
In my code the 'public String handleRequest(URI url)' , 'url.getQuery()', 'url.getPath()', 'public static void main(String[] args) throws IOException' and ' Server.start(port, new Handler())' are the important methods that are called for this program in the file ChatServer.java. However only the 'url.getQuery()', 'url.getPath()', and 'public String handleRequest(URI url)' methods are called when I update the link at the page. Because the other 2 methods are called when I first run the program. 
  
- What are the relevant arguments to those methods, and the values of any relevant fields of the class?<br> </br>
In Server.start(port, new Handler()) we need to have the user give a port number to start the server on. And the new Handler() means we are creating a new Handler object for this Server we are opening. That is why in the method 'public static void main(String[] args) throws IOException' we are taking in a String array argument, so the user can input the port number when they create the ChatServer. In the method 
'public String handleRequest(URI url)', the relevant argument is URI url, which is basically the url link we are updating, the method takes in as a argument. In our case the url we are giving in as a argument for this specific request is 'https://0-0-0-0-4000-rgp3mti2t4fvq6smo9r87ema78.us.edusercontent.com/add-message?s=HelloWorld&user=Kiruthika'. And for url.getQuery() method, there are no argumens but basically the URI url argumnet from the handlRequest(URI url) method is used and this method returns the Query portion of the url as a String which is everything after the question mark after the path ends. The method 'url.getPath()' returns the path of the url as a String so we can check if the user is going to normal homepage '/' path, or doing the '/add-message' path in which case we have to check for the message the user is trying to add. In the ChatServer.java file inside the Handler class we have 2 relevant fields. The 'ArrayList<String> ans' and 'String x'. The 'ans' is a ArrayList of Strings that stores all of the messages from the past that have been created using '/add-message?s=<message>&user=<name>' formatted properly using the colon to seperate name and message, as its own value. And the 'x' is the final String that is returned to the page which stores all of the messages form the ArrayList ans together with lines seperating each message. In the beginning the String x is an empty String and the ArrayList ans has no values. However our request changes that. 


- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.<br> </br>
For my specific request I inputted '/add-message?s=HelloWorld&user=Kiruthika' so the ArrayList ans field got a new value at index 0 with the String "Kiruthika: HelloWorld" and the String x was also changed to "Kiruthika: HelloWorld". The field ans was empty before with no values and the String x was a empty String but with my specific request both fields have different values. 


---

2. <img width="1440" alt="Screen Shot 2024-01-30 at 10 37 32 AM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/1cb0c4a0-2a89-4fb9-9808-da2d05c2baaf">

- Which methods in your code are called?<br> </br>
Same methods as before are called. The 'public String handleRequest(URI url)' , 'url.getQuery()', 'url.getPath()' are all called. 

- What are the relevant arguments to those methods, and the values of any relevant fields of the class?<br> </br>
The method 'public String handleRequest(URI url)' has the argument URI url and the url we are giving in now is 'https://0-0-0-0-4000-rgp3mti2t4fvq6smo9r87ema78.us.edusercontent.com/add-message?s=What%20kind%20of%20shoes%20do%20ninja%27s%20wear?&user=Ninja1'. Then for the methods 'url.getQuery()' and 'url.getPath()' there are no arguments however the 1st method simply gets the Query part of the url we gave in as a argument to the method 'public String handleRequest(URI url)'. SO it returns a Sting of everything after the question mark right after the path. And the method 'url.getPath()' returns the path of our url parameter. Right now the values fo our 2 fields are stored from before. So in the ArrayList ans there is one value at index 0 which is the String "Kiruthika: HelloWorld". And String x = "Kiruthika: HelloWorld". 

- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.<br> </br>
After our request there is a second value in the ArrayList ans at index 1 which is the String "Ninja1: What+kind+of+shoes+do+ninja's+wear?" and the value at index 0 is the same as before which is the String "Kiruthika: HelloWorld". And our String x has a new value which is "Kiruthika: HelloWorld\nNinja1: What+kind+of+shoes+do+ninja's+wear?", where the \n indicates a new line. This is because the string x concatenates the all the values in our ArrayList ans using \n. And the ArrayList ans updates a new value at the next index for every new request. 


