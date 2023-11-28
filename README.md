## Ensure an internet connection is available.

Download and add the Jenkins repository configuration file to /etc/yum.repos.d/.
```
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
```


Import the Jenkins repository GPG key.
```
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
```

Update the Systme
```
sudo yum upgrade -y
reboot
```


Install fontconfig and Java 11 OpenJDK.
```
yum install fontconfig java-17-openjdk -y
```


Check the installed Java version.
```
java --version
```


Install Jenkins using Yum.
```
yum install jenkins -y
```

Reload the system
```
sudo systemctl daemon-reload
```



Check the status of the Jenkins service.
```
systemctl status jenkins.service
```


Check the status of the firewalld service.
```
systemctl status firewalld.service
```


Check the installed Jenkins version.
```
jenkins --version
```

## If you want to install same version with mine 
Search for available Jenkins package versions.
```
yum search jenkins --showduplicates | grep -i 2.426.1
```

Install a specific version of the Jenkins package (e.g., version 2.42xxx).
```
yum install jenkins-2.426.1-1.1.noarch

```