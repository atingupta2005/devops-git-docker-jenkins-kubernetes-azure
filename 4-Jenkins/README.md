# Jenkins Installation

- Reference:
	- https://www.jenkins.io/doc/book/installing/linux/


- Java Installation
```
sudo apt update
sudo apt install openjdk-11-jdk
java -version
```

- Jenkins Installation
```
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
    /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get install jenkins
```