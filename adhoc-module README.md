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
    ansible dev -a "ls -a "
    ```
  - Install Apache HTTP Server (httpd) on remote hosts
  - Locate the installation path of the httpd binary on remote hosts
  - Checks the status of the httpd (Apache) service with elevated privileges 
  - Starts the httpd (Apache) service on remote hosts with elevated privileges.
  - Stops the httpd (Apache) service on remote hosts with elevated privileges
  - Removes the httpd package (Apache HTTP Server) from remote hosts with elevated privileges.
    ```
    ansible dev -a "sudo yum install httpd -y"
    ansible dev -a "sudo which httpd"
    ansible dev -b -a "systemctl status httpd" 
    ansible dev -b -a "systemctl start httpd"  
    ansible dev -b -a "systemctl stop httpd"
    ansible dev -b -a "sudo yum remove httpd -y"
    ```

-Copies the file dev.txt from the local system to the remote server 
```
# ansible dev -b -m copy -a "src=/home/ansible/dev.txt dest=/home/ansible".
```
-Moves the directory or file dhan to the backup directory. 
```
ansible dev -b -m shell -a "mv /home/ansible/dhan /home/ansible/backup/".
```
-Remove file from target host
```
ansible dev-b-m shell a "rm /home/ansible/dev.txt".
```
-Change the directory in remote server
```
ansible dev-bm shell a "cd /home/ansible && ls && echo 'Directory changed'".
```
-Create file in target host
```
ansible dev-bm shell a "touch dev.txt".
```
-Create directory in target host
```
ansible dev-b-m shell a "mkdir shan".
```
-Delete directory in target host
```
ansible dev-b-m shell -a "rmdir shan".
```
-Delete file in target host
```
ansible dev -b -m shell -a "rm /home/ansible/dev.txt".
```
-Create file in target host with file permission
```
ansible dev -b -m file -a "path=/home/ansible/shan mode=0777".
```
-remove file in target host with file permission
```
ansible dev -b -m shell -a "rm /home/ansible/sam.txt mode=0777".
```
-Install git in target host 
```
ansible dev -b -m command -a "yum install git -y".
```
-Install docker in target host 
```
ansible dev -b -m command -a "yum install docker -y".
```
-Start docker service 
```
ansible dev -b -m command -a "systemctl start docker.service".
```
-Pull httpd image in target host 
```
ansible dev -b -m shell -a "docker pull httpd".
```
-Run httpd server container in target host 
```
ansible dev -b -m shell -a "docker run -it -d httpd".
```
-List running container in target host 
```
ansible dev -b -m shell -a "docker ps".
```
-Clone a Git repository 
```
ansible dev -b -m shell -a "git clone https://github.com/dharshan224/ansible-commands.git".
```
-List files in specific directory 
```
ansible dev -b -m shell -a "cd ansible-commands && ls"
```





