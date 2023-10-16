# Lab Report 2
## Part 1
### Code
```java
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String str = "";
    int num = 0;
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return str;
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    num++;
                    str += num+". "+parameters[1]+"\n";
                    return str;
                }
            }
            return "404 Not Found!";
        }
    }
}

class StringServer {
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
### Output 1
![screenshot 1](lab2.png)
The methods that are called are handleRequest(), getPath(), equals(), contains(), getQuery(), and split(). 
The relevant arguments are "http://localhost:4500/add-message?s=Hello", "/", "=", "s". 
The url changes to "http://localhost:4500/add-message?s=Hello", "/", "=", "s". The int variable num changes from 0 to 1, String str changes from "" to "1. Hello \n". 

### Output 2
![screenshot 2](lab2_2.png)
The methods that are called are handleRequest(), getPath(), equals(), contains(), getQuery(), and split(). 
The relevant arguments are "http://localhost:4500/add-message?s=How%20are%20you", "/", "=", "s". 
The url changes to "http://localhost:4500/add-message?s=How%20are%20you". The int variable num changes from 1 to 2, String str changes from "1. Hello \n" to "1. Hello \n2. How are you\n". 

## Part 2
### Path to Private Key
<img width="756" alt="Screen Shot 2023-10-16 at 4 10 14 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/0cbe3772-7885-453b-8801-bffa12156773">

### Path to Public Key
<img width="723" alt="Screen Shot 2023-10-16 at 4 10 31 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/a6570979-7eb5-41cd-8c8f-1d2da5a656d9">

### Login without Password
<img width="978" alt="Screen Shot 2023-10-16 at 4 11 56 PM" src="https://github.com/RunnnnWang/cse15l-lab-reports/assets/130102197/41ab1edd-6dcc-4898-9bb9-e1ffae3e838d">

## Part 3
In week 2 lab I learned how to run a server using the code being provided. I was able to manipulate the path and query to make the URL do different things. I also learned what is a port. In week 3 lab, I learned that scp means secure copy and it basically downloads files between remote host and local host, or between remote and remote hosts. I also learned mdkir which makes a directory. 

