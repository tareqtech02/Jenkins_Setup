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
```

Reboot the system
```
reboot
```


Install OpenJDK 11
```
yum install java-11-openjdk-devel -y
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
systemctl start jenkins.service
systemctl enable jenkins.service
systemctl status jenkins.service
```


Check the status of the firewalld service.
```
systemctl status firewalld.service
systemctl stop firewalld.service
systemctl disable firewalld.service
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

Open Google chrome and run your IP with ports 8080
```
http://<IP Address>:8080
```


Get the Admin Password for the Jenkins 
```
cat /var/lib/jenkins/secrets/initialAdminPassword
```
