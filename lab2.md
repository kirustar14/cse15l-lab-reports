Hello World!!!

# Lab Report 1 - Remote Access and FileSystem 
Name: Kiruthika Marikumaran 
PID: A17877875
 
---

# ChatServer Code

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

1. 
<img width="1440" alt="Screen Shot 2024-01-30 at 10 35 19 AM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/0359b0a9-fc05-4e35-bd25-ea3d4bacc798">

- Which methods in your code are called?
  In my code the 'public String handleRequest(URI url)' , 'url.getQuery()', and ' Server.start(port, new Handler())' are the important methods that are called for this program in the file ChatServer.java. And in 
- What are the relevant arguments to those methods, and the values of any relevant fields of the class?
- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.


2. <img width="1440" alt="Screen Shot 2024-01-30 at 10 37 32 AM" src="https://github.com/kirustar14/cse15l-lab-reports/assets/148379107/1cb0c4a0-2a89-4fb9-9808-da2d05c2baaf">

- Which methods in your code are called?
- What are the relevant arguments to those methods, and the values of any relevant fields of the class?
- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.



