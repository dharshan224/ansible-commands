# ansible-commands 
- use the commands
  - Prints the current working directory on each host 
    ```
    ansible dev -a "pwd"
    ``` 
  - Lists the files in the current directory on each host
    ```
    ansible dev -a "ls"
    ```
  - Lists all files (including hidden ones) in the current directory on each host
    ```
    ansible dev -a "ls -a"
    ```
  - Install Apache HTTP Server (httpd) on remote hosts
    ```
    ansible dev -a "sudo yum install httpd -y"
    ansible dev -a "which httpd"
    
    ## To Copy the FILE
## To move the file
- 


