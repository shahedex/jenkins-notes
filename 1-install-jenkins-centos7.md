# Install Jenkins Server on CentOS 7

## Add Jenkins repository

```console
$ wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins.io/redhat-stable/jenkins.repo
$ rpm --import http://pkg.jenkins.io/redhat-stable/jenkins.io.key
```

## Install Jenkins and Java

```console
$ yum install jenkins java-1.8.0-openjdk –y
```

## Start and Enable Jenkins Service

```console
$ systemctl start jenkins
$ systemctl enable jenkins
```

## Open the ports 80 and 8080 in OS Firewall

```console
$ firewall-cmd --zone=public --add-port=8080/tcp --permanent
success
$ firewall-cmd --zone=public --add-service=http --permanent
success
$ firewall-cmd --reload
success
```

## Get Jenkins admin password for logging in to Jenkins

```console
$ grep -A 5 password /var/log/jenkins/jenkins.log
```

or

```console
$ cat /var/lib/jenkins/secrets/initialAdminPassword
```

## --------------------------------------------------------------
Now go to <server.ip>:8080 to get the Jenkins Dashboard and enter the password.