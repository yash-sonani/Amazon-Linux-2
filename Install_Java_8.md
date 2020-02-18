
# 1. Remove java 7 from current EC2 Server
```
sudo yum remove -y java
```

# 2. Download and install java 8. 
Get the latest version from <https://openjdk.java.net/install/>
```
yum install java-1.8*
```

# 3. Confirm Java Version and set the java home
```
java -version
```

# 4. Check installtion location
```
find /usr/lib/jvm/java-1.8* | head -n 3
```
![Command Output](https://github.com/yash-sonani/Amazon-Linux-2/blob/master/Java_Installation_Path.PNG "Java Installation Path")
# 5. Update bash_profile for permenent changes

```
vi ~./bash_profile
```
# 6. Add below lines in bash_profile file as per your output from set 4

```
(Change JAVA_HOME path as per your output)
JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.222.b10-0.amzn2.0.1.x86_64 
export JAVA_HOME
PATH=$PATH:$JAVA_HOME
```
