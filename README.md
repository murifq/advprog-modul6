# Module 6
## Commit 1 notes
**What is inside the handle_connection method?**

It takes ownership of a TcpStream, stream, representing a connection to a client. It creates a BufReader wrapping the TcpStream. This buffered reader allows reading lines from the stream efficiently. It reads lines from the buffered reader (buf_reader.lines()). Each line corresponds to a part of the HTTP request until empty line. It collects the lines into a Vec<String> called http_request. Finally, it prints out the collected HTTP request for debugging purposes.

## Commit 2 notes
**What is inside the handle_connection method?**
![img.png](assets/images/commit2.png)
There are some addtional line in the new handle_connection method. Defines the status line of the HTTP response indicating success. Then gets the length of the contents read from the file. Formats the HTTP response string using the status line, content length, and the contents read from the file. Then send the HTTP response back to the client.

## Commit 3 notes
![img.png](assets/images/commit3.png)
Now my updated handle_connection, can give the different repsonse for different path. Also i do some refactoring. Use an if-else statement to give an appropriate html and status code response.