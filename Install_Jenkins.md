You can install Jenkins using the rpm or by setting up the repo. Set up the repo is easy because update can be done easily in the future.

# 1.] Install wget 
```
yum -y install wget
```

# 2.] Get the repo of Jenkins
```
wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
```

# 3.] Import Jenkins Key through rpm
```
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
```

# 4.] Install Jenkins
```
yum -y install jenkins
```
# 5.] Start Jenkins Service
```
service jenkins start
```

# 6.] Access Jenkins 
By default jenkins runs at port `8080`, You can access jenkins at
`http://YOUR-SERVER-PUBLIC-IP:8080`
