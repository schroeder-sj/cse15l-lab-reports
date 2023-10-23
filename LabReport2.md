
# Lab Report 2 - Servers and SSH Keys

## Part 1

#### Code for StringServer:

`` import java.io.IOException;
   import java.net.URI;
class Handler implements URLHandler {
String messages = new String();
int counter = 0;
    public String handleRequest(URI url) {
        if (url.getPath().contains("/add-message")){
            String[] parameters = url.getQuery().split("=");
            counter++;
            messages = messages + counter + "." + " " + parameters[1] + "\n";
            return (messages);
        }
        return (messages);
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
} ``

#### Screen Shots of Using Server:

![1]("https://github.com/schroeder-sj/cse15l-lab-reports/blob/main/Screenshot%202023-10-22%20at%209.00.09%20PM.png")

![2]("https://github.com/schroeder-sj/cse15l-lab-reports/blob/main/Screenshot%202023-10-22%20at%209.00.22%20PM.png")

### Screen Shot 1
In this screenshot, the handleRequest method is called and in this case the relevant arguement would be the url. Within this URL, the 
method pulls the string value after ```/add-message?s=``` and then outputs that relevant string in the form of a numerical list. From this
request, the String variable messeges is changed by adding the previous message that is stored in this variable and updating it to include a number
followed by a period, a space, the string parameter from the URL, and then a newline character. The number in this is collected from a counter which 
increments by 1 immediately after this if statement in the method is called. In this case, the messages string adds "1. Goodbye", which is composed of the 
newly incremented counter as well as the string in the URL.

### Screen Shot 2
In this screenshot, the handleRequest method is called and in this case the relevant arguement would be the url. Within this URL, the 
method pulls the string value after ```/add-message?s=``` which is "potatoes" and then outputs that relevant string in the form of a numerical list. From this
request, the String variable messeges is changed by adding the previous message that is stored in this variable and updating it to include a number
followed by a period, a space, the string parameter from the URL, and then a newline character. The number in this is collected from a counter which 
increments by 1 when this if statement in the method is called. In this case, the messages string adds "2. Potatoes" to "1. Goodbye " which is composed of the 
newly incremented counter as well as the string in the URL. This outputs our final result of:
"1. Goodbye 
 2. Potatoes"


## Part 2

![Path to Private Key]("https://github.com/schroeder-sj/cse15l-lab-reports/blob/main/Screenshot%202023-10-22%20at%209.28.07%20PM.png")

![Path to Public Key]("https://github.com/schroeder-sj/cse15l-lab-reports/blob/main/Screenshot%202023-10-22%20at%209.27.25%20PM.png")

![Logging in Via Pub Key]("https://github.com/schroeder-sj/cse15l-lab-reports/blob/main/Screenshot%202023-10-22%20at%209.29.07%20PM.png")

Note on logging in via public key: I use my public key for an HPC environment in which it is required for me to use a very long passphrase, therefore I am unable to 
log in with this key without using a passphrase.

## Part 3
One of the biggest things that I did not know was possible was that you are able to host your own server using command line. I have used local host before to run
jupyter notebooks and other things, but I did not know you could host other things that were not using applications with localhost. This is super beneficial to me
for some of the research I am doing and will make it easier for future developments.



