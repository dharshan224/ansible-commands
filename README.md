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
  - Locate the installation path of the httpd binary on remote hosts
  - Check the status of Apache HTTP Server (httpd)
  - Start the Apache HTTP Server (httpd)
  - Stop the Apache HTTP Server (httpd)
  - Remove Apache HTTP Server (httpd)
    ```
    ansible dev -a "sudo yum install httpd -y"
    ansible dev -a "sudo which httpd"
    ansible dev -a "sudo systemctl status httpd"
    ansible dev -a "sudo systemctl start httpd"
    ansible dev -a "sudo systemctl stop httpd"
    ansible dev -a "sudo yum remove httpd -y"
    ```
    
    
## To Copy the FILE

## To move the file
- 


