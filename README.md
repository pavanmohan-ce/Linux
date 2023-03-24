# Linux  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRbi9aVFq2CV5UxsEhDk4L5Hk_u4nHnSTnsWhnOUNRg4mfdOfWZfJoPGLZL01QvgvIDT8Q&usqp=CAU" width="25" >

> *Linux* is a free and open-source operating system based on the Unix operating system. It is known for its stability, security, and flexibility, and it has become the most popular operating system for servers and supercomputers.

## 1.File Management

- ls       : used to list the files and directories(*excluding hidden files*)
```
ls /var
```
- cat      : used to display the contents of a file. It can also be used to add the data into the file.
 ```
cat abc.txt
```
- more     : used to to display the contents of a file one screen at a time.
```
more abc.txt
```
- tail     : used to display last few lines of the file
```
tail abc.txt
```
- tail -f  : used to to display the last few lines of a file. This is useful for monitoring log files and other files that are updated frequently.
```
tail -f syslog
```
- locate   : used to find files by name. It uses a database of file names and locations to quickly find files.
```
locate abc.txt
```
- cd       : used to change from one directory to another specified directory
```
cd /etc
```
- touch    : used to create a new empty file and can also adds the data into the file
```
touch abc.txt
```
- mkdir    : used to create a new directory
```
mkdir folder
```
- move     : used to move or rename the files and directories
```
mv /tmp/tomcat /opt/Tomcat
```
- rm       : used to remove the files and directories
```
rm abc.txt
```
- rmdir    : used to remove an empty directory
```
rmdir folder
```
- vi       : used to create, edit, and modify text files.
```
vi /folder/abc.txt
```
   ###### It has insertion mode and command mode
  - Esc : helps to switch from insertion mode to command mode
  - i   : helps to switch from command mode to insertion mode
  - dd  : used to delete the entire line where cursor placed
  - x   : used to delete the character from where the cursor is placed
  - q!  : used to quit from the vi without saving (!-forcefully)
  - wq! : used to save and quit (!-forcefully)
 
#### Search for a word in vi and replace a word with new word in vi (:%s/oldword/newword/g)

	s- substitue
	%- used to replace the word in the entire file (in all lines)
	g- global search
  
- cp : used to copy the files nd directories from one location to another.
```
cp /tmp/.tar* /opt/
```
- cp -r : used to recursively copy a directory and its contents to another location.
```
cp -r /tmp/.tar* /opt/
```
- cp -rp : used to recursively copy a directory and its contents to another location, while preserving the permissions and timestamps of the original files and directories. 
```
cp -rp /tmp/.tar* /opt/
```
- sed : used to perform text transformations on a file or input stream. It can be used to search for a particular pattern and replace it with another pattern. 
```
sed 's/abc/123/' file.txt
```
- find : to search for files and directories based on various criteria.
```
find -size -/+1M ; find -mtine -30; find -name ".php*"
```
  - size : To find files based on their size *-size*
  - date : To find files based on their date *-mtime*
  - keyword : To find files based on a specific keyword, *-name*
- grep : used to search for patterns in files or standard input. It stands for "global regular expression print".
```
grep "MySql"
```
- grep -i : used to search for a keyword in a case-insensitive manner
```
grep -i "mysql'
```
- du : used to display the disk space occupied by files or directories
```
du
```
- df : used to display the disk space availble on the file system
```
df
```
- diff : used to display the differences between two different files
```
diff 123.txt abc.txt
```
- wc -l : used to display the count of lines in a specified file
```
wc -l abc.txt
```
- tar : used to archeive the multiple files into a single .tar file
```
tar -cf abc.tar abc ; tar -xf abc.tar
```
- zip : used to compress the file size which is easy to transfer
```
zip abc 123
```
- unzip : used to uncompress the file to attain its original file size
```
unzip abc.zip
```
- ln : used to create the hard link of the specified file in a specified path
```
ln /dir/abc.txt .
```
##### for soft link
```
ln -s /dir/abc.txt .
```
## 2.USER MANAGEMENT

- useradd - : used to create the user
```
useradd pavan
```
- useradd -m : used to create the home directory for a user
```
useradd -m pavan
```
- usermod -aG : used to add a user to an additional group
```
usermod -aG sudo pavan
```
- usermod -G : used to remove a user from a group
```
usermod -G sudo pavan
```
- usermod -s : used to change the login shell of a user
```
usermod -s pavan
```
- usermod -d : used to change the home directory of a user
```
usermod -d /home/pawan pavan
```
- usermod -l : used to change the username of the user
```
usermod -l kumar pavan
```
- usermod -L : used to lock the user
```
usermod -L pavan
```
- usermod -U : used to unlock the user
```
usermod -U pavan
```
- userdel - : used to delete the user
```
userdel pavan
```
- userdel -r : used to del the user along with its home directory
```
userdel -r pavan
```
- passwd - : used to create/change/update the password for a user
```
passwd pavan
```
- passwd -d : used to delete the password of a user
```
passwd -d pavan
```
- passwd -e : used to force the user to change the password
```
passwd -e pavan
```
- passwd -l : used to lock the password of a user
```
passwd -l pavan
```
- passwd -u : used to unlock the passsowrd of a user
```
passwd -u pavan
```
- passwd -n : used to set the minimum password lifetime to change again
```
passwd -n 10 pavan
```

## 3.ACCESS MANAGEMENT

- ssh : used to securely connect to a remote computer or a server and allows secure remote access, file transfer and command execution
```
ssh -i "key.pem" ubuntu@ip_address
```
- scp : used to securely transfer the files between two linux based systems
```
scp -r "key.pem" ./file1 ubuntu@ip_address:/home/ubuntu/
```
- sudo : used to perform administrative tasks without logging in as a root user
```
sudo useradd kumar
```
- su : used to switch from one user to another user / root user
```
su kumar
```
- chmod : used to change the permissions of a file or directory
```
chmod 400 file1 | chmod u+r file1
```
- chown : used to change the owner and group of a file or directory
```
chown user:group file1
```

## 4.CONFIGURATION MANAGEMENT

- env : used to display the current environment variables
```
env MYVAR=myvalue ls

```
- PATH : used to specify the list of directories where executable programs are located
```
export PATH=$HOME/mydir:$PATH

echo $PATH
```
- echo : used to prints out a message to the console
```
echo $PATH
```
- export : used to create an environment variable
```
export PATH=$HOME/mydir:$PATH
```
- hostname : used to prints out the name of the current host
```
hostname
```
- netstat : used to displays the network connections, routing tables and other network interface statistics
```
netstat -tulpn
```
```  -t: Displays TCP connections.
    -u: Displays UDP connections.
    -l: Displays listening ports.
    -p: Shows the process ID (PID) and name that the connection is associated with.
    -n: Shows the numeric address and port numbers, rather than resolving them to host and service names. 
 ```
    
    
- crontab : used to create, view, delete the crontab files which controls the scheduling of commands to be run at specified time
- crontab -e : used to create or edit the crontab file
```
crontab -e
```
*Once the crontab file is open, you can add new entries or modify existing ones using the following syntax:*
```
* * * * * command
```
*The five asterisks represent the minute, hour, day of the month, month, and day of the week on which the command should be run.*

- crontab -l : used to list the current cron jobs
```
crontab -l
```
- kill : used to terminate a process by using pid
```
kill -9 <1682>
```
- pkill : used to sends a signal to a process based on its name
```
pkill <tomcat>
```
- wget : used to downloads file from the internet
```
wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.5/bin/apache-tomcat-10.1.5.tar.gz
```
- curl : used to transfer data between servers using various protocols (HTTPS,HTTPS,SCP)
```
curl  -o outputtxt.html https://ubuntu.com/download/desktop.html
```
- ping : used to test the connectivity between two networked devices
```
ping 8.8.8.8
```
- uname : used to prints out system information
```
uname
```
- history : used to prints out the historty of the executed commands
```
history 
```
- ps : used to displays information about currently running processes
```
ps
```
- ps -ux : used to view the list of processes running on the system, including their resource utilization and ownership information
```
ps -ux
```
- ps -ef : used to view the process tree hierarchy of all processes 
```
ps -ef
```
- ps -ef | grep <pid> : used to view the information about a specific process by its PID
```
ps -ef | grep <1682>
```

## 5.Log Management

- #### Syslog
> *Syslog* is a standard protocol used to log messages from different software applications and system services. It is a way to centralize logging across multiple servers and applications, making it easier to manage and troubleshoot issues.

- #### Journalctl
> *Journalctl* is a command-line utility used to query and view logs collected by the systemd journal. It can be used to search for specific log messages, filter logs based on different criteria, and view logs in various formats.

- #### Custom logs
> *Custom logs* refer to log messages that are generated by custom applications or scripts. It can contain any type of information, from debug messages to application-specific metrics, and are used to help developers and system administrators monitor and troubleshoot their applications.

## 6.Network management

> - **Internal network** refers to the network of devices within an organization or a specific location.
	
> - **External network** refers to the network outside of the organization or location, typically the internet.
	
- A **subnet** is a portion of a larger network
	- A **private subnet** is a subset of IP addresses reserved for use within a private network.They are are typically used for internal communication within an organization.
	 - A **Public subnet** is assigned globally unique IP addresses and can be accessed from the internet. They are used for internet-facing services.
	
- **Ports**

	In computer networking, a port is a communication endpoint for sending and receiving data.
	- **Well-known ports**: *Well-known ports* are predefined and registered with the Internet Assigned Numbers Authority (IANA). They range from 0 to 1023 and are used by commonly recognized services, such as HTTP (port 80), HTTPS (port 443), FTP (port 21), SSH (port 22), Telnet (port 23), and SMTP (port 25).
	- **Registered ports**: *Registered ports* are those in the range of 1024 to 49151. They can be used by applications upon registration with the IANA, but are not as commonly recognized as well-known ports. Examples include Oracle database (port 1521), MySQL (port 3306), and Windows Remote Desktop Protocol (port 3389).
	- **Dynamic or private ports**: *Dynamic or private ports* are those in the range of 49152 to 65535. They are used by the operating system or applications for temporary communication between network endpoints, and are not registered with IANA. These ports are usually assigned by the operating system when a connection is established.
	- **Ephemeral ports**: *Ephemeral ports* are dynamic ports that are assigned by the operating system to a client application when it initiates a connection to a server. These ports typically range from 49152 to 65535, and are used to facilitate communication between the client and server.
	
> - **CIDR** (*Classless Inter-Domain Routing*) is a method of IP address allocation that allows for more efficient use of the available IP address space. *CIDR range calculations* are used to determine the network and host portions of an IP address and subnet mask pair, and to calculate the range of IP addresses that belong to a particular network.
	

> - **HTTP** (Hypertext Transfer Protocol) is a protocol used to transmit data over the internet.
	
> - **HTTPS** (Hypertext Transfer Protocol Secure) is a secure version of HTTP that uses encryption to protect the data transmitted between the web server and the client.
	
	
> - **TCP** (*Transmission Control Protocol*) and **UDP** (*User Datagram Protocol*) are two transport layer protocols used for sending data over IP networks. 
	- TCP provides reliable, ordered, and error-checked delivery of data 
	- UDP provides a faster and simpler connectionless communication.
	

- ifconfig : used to configure and view network interface parameters such as IP address, netmask, broadcast address, and network interface status
```
ifconfig	
```
	
## Application/Web Servers:
- An application or web server is a software program that runs on a computer to serve web applications, web pages, or other network services to client devices.
	- A **web server** is designed to deliver static and dynamic content over the web for delivering content quickly and efficiently. It typically handles client requests for web pages or files, and responds with the appropriate content. Examples of web servers include *Apache HTTP Server*, *NGINX*, and *Microsoft IIS*.
	- An **Application server** is designed to host and manage web applications that require more complex functionality, such as processing user input, managing session data, and communicating with backend databases or other systems. Examples of application servers include *Apache Tomcat*, *JBoss*, and *IBM WebSphere*.
	
## Load Balancing:
> *Load balancing* is a technique used to distribute network traffic across multiple servers or network resources by preventing overload on individual servers and maintaining uptime. Load balancers typically use algorithms to distribute traffic based on factors such as server availability, current traffic levels, and geographic location.

## High Availability:
> *High Availability* (HA) refers to the ability of a network or network infrastructure to maintain its availability and uptime even in the face of failures or outages. The goal of HA is to ensure that critical services or applications remain accessible to users, even if one or more components of the network fail.

- ##### There are several ways to achieve high availability in a network, including

	- **Redundancy**: This involves duplicating critical components of the network, such as switches, routers, or servers, so that if one fails, another can take over without interruption to service.
	- **Load balancing**: This involves distributing traffic across multiple servers or paths to prevent any single server or path from becoming overloaded or unavailable.
	- **Failover**: This involves automatically switching to a backup or secondary system in the event of a failure or outage. For example, if a primary server fails, a secondary server can automatically take over to ensure continuity of service.
	- **Network virtualization**: This involves creating virtual instances of network devices or services, which can be moved or migrated between physical devices as needed to ensure continuous service.
## Create shell script to install Application servers and proxy tools
Installing and configuring **Apache Tomcat** as an Application server and **haproxy** as a proxy tool
```
#!/bin/bash

# Install Java Development Kit (JDK)
sudo apt-get update
sudo apt-get install -y default-jdk

# Install Apache Tomcat server
cd /tmp/
wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.5/bin/apache-tomcat-10.1.5.tar.gz
tar -xzvf apache-tomcat-10.1.5.tar.gz
sudo mv apache-tomcat-10.1.5.tar.gz /opt/tomcat	
chown -R tomcat:tomcat /opt/tomcat
rm -rf /etc/systemd/system/tomcat.service

cat <<EOT>> /etc/systemd/system/tomcat.service
[Unit]
Description=Tomcat
After=network.target
[Service]
Type=forking

User=tomcat
Group=tomcat

Environment="JAVA_HOME=/usr/lib/jvm/java-1.11.0-openjdk-amd64"
Environment="JAVA_OPTS=-Djava.security.egd=file:///dev/urandom"
Environment="CATALINA_BASE=/opt/tomcat"
Environment="CATALINA_HOME=/opt/tomcat"
Environment="CATALINA_PID=/opt/tomcat/temp/tomcat.pid"
Environment="CATALINA_OPTS=-Xms512M -Xmx1024M -server -XX:+UseParallelGC"

ExecStart="/opt/tomcat/bin/startup.sh"
ExecStop="/opt/tomcat/bin/shutdown.sh"

[Install]
WantedBy=multi-user.target
EOT
systemctl daemon-reload
systemctl start tomcat
systemctl enable tomcat

cd /tmp/
wget https://raw.githubusercontent.com/pavanmohan-ce/Linux/master/tomcat-users.xml
wget https://raw.githubusercontent.com/pavanmohan-ce/Linux/master/context.xml
cp tomcat-users.xml /opt/tomcat/conf/tomcat-users.xml
cp context.xml /opt/tomcat/webapps/manager/META-INF/
systemctl restart tomcat
echo "Done"

# Install ha proxy server
sudo apt install haproxy -y	
```
### configure proxy to access application server through proxy
```
# Configure ha proxy server
sudo bash -c 'cat << EOF >> /etc/squid/squid.conf
frontend haproxy_in
        bind *:80
        default_backend haproxy_http
backend haproxy_http
        balance roundrobin
        mode http
        server app_server_name pvt_ip_of_app_server:80 check
EOF'

sudo systemctl restart haproxy
```
