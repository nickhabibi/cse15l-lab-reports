<style>
    img[alt=sshot], img[alt=keys] {
        width:500px;
    }
</style>

# Lab Report 2

## Part 1

Code for StringServer.java:

```
import java.io.IOException;
import java.net.URI;

class StringServer {
    public static void main(String[] args) throws IOException{
        if (args.length == 0) {
            System.out.println("Error: enter a port.");
            return;
        }
        Server.start(Integer.parseInt(args[0]), new Handler());
    }
}

class Handler implements URLHandler {
    
    String message = "";
    int num = 1;

    public String handleRequest(URI url) {

        if (url.getPath().contains("/add-message")) {

            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                message += num + ". " + parameters[1] + "\n";
                num++;
            }
        } else if (!url.getPath().equals("/")) {
            return "Error: path not found.\n";
        }

        return message;
    }
}
```

When making a request, the `handleRequest` method in the `Handler` class is called and receives the request URL as input. 

The class `Handler` contains variables `message` and `num`. Initially, the value for `message` is `""` and the value for `num` is `1`.

The `handleRequest` method checks if the path in the URL contains `/add-message` and then checks if the query in the URL looks like this: `s=<string>`. The method then adds the `<string>` part of the query and the value in `num` as index, followed by `n\`, to the `message` variable. Finally, the method returns the new value of `message` which gets output by the server.

- When adding `/add-message?s=Hello World` to the URL and making a request to the server, `handleRequest` adds the string "hello world" as well as its current index value `num` to the `message` variable. Then, `num` gets incremented. The method returns the new value of `message` and the server outputs that value which looks like this:

![sshot](./images/lab-2-1.png)

The new value for `num` is now `2` and the new value for `message` is `"1. Hello World\n"`.

- When adding `/add-message?s=UCSD` to the URL and making another request, `handleRequest` adds "UCSD" and its current index value `num` to the `message` variable which then gets output by the server.

![sshot](./images/lab-2-2.png)

The new value for `num` is now 3 and the new value for `message` is `"1. Hello World\n2. UCSD\n"`.

## Part 2

- The path to the *private key* for logging into `ieng6` using SSH

![keys](images/lab-2-3.png)

- The path to the *public key* for logging into `ieng6` using SSH

![keys](images/lab-2-4.png)

- Logging into `ieng6` without being asked for a password

![login](images/lab-2-5.png)

## Part 3

On week 2 and week 3, I learned how to create a URL handler in java to be used by an http server. I also learned how to start an http server by compiling and running the java file and specifying the port of the server as a command-line argument.

Before this, I didn't have much experience with github so I gained a lot of experience working with github and using git commands like `clone`, `add`, `commit`, and `push`.

I also learned about setting up SSH keys and using `scp` to copy the public key stored on my local computer into a file on the remote `ieng6` host.
