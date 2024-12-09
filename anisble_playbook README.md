 -to check worker node 
```
---
- name: to check workernode
  hosts: dev
  user: ansible
  become: yes
  connection: ssh

```
- Install java 17 & Maven & jenkins
  ```
  - name: Install Java 17, Maven, and Jenkins on worker nodes
  hosts: dev
  user: ansible
  become: yes
  connection: ssh
  tasks:
    # Install Java 17*
    - name: Install Java 17*
      yum:
        name: java-17*
        state: present

    # Install Maven
    - name: Install Maven
      yum:
        name: maven
        state: present

    # Install Jenkins repository
    - name: Add Jenkins repository to yum
      get_url:
        url: https://pkg.jenkins.io/redhat-stable/jenkins.repo
        dest: /etc/yum.repos.d/jenkins.repo

    # Import Jenkins GPG key
    - name: Import Jenkins GPG key
      rpm_key:
        state: present
        key: https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

    # Upgrade system packages
    - name: Upgrade system packages
      yum:
        name: "*"
        state: latest

    # Install required dependencies for Jenkins
    - name: Install dependencies (java-17*)
      yum:
        name:
          - java-17*
        state: present

    # Install Jenkins
    - name: Install Jenkins
      yum:
        name: jenkins
        state: present

    # Reload systemd daemon to recognize the Jenkins service
    - name: Reload systemd daemon
      systemd:
        daemon_reload: yes

    # Start Jenkins service
    - name: Start Jenkins service
      service:
        name: jenkins
        state: started
        enabled: yes

    # Check Jenkins service status
    - name: Check Jenkins service status
      service:
        name: jenkins
        state: started
      register: jenkins_status

    # Display Jenkins service status
    - name: Display Jenkins service status
      debug:
        var: jenkins_status
```

- dmks
  ```
           :wq
           rjnvrvnrrnkvrnkrnmkr
