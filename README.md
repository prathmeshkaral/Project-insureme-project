# $\color{red} \textbf{PROJECT-Jenkins-InsureMe}$

$\color {green} \textbf{1. Craete A instance.}$
- ubuntu
- t2.medium
- SG : All traffic
- Storage : 20

$\color{green} \textbf{2. Install Java and jenkins.}$
````
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
````

$\color{green} \textbf{3. Host the public ip of instance with jenkins port.}$
````
pub_ip:8080
````
$\color{green} \textbf{4. Add jenkins passwd.}$
````
sudo cat /var/jenkins_home/secrets/initialAdminPassword
````
$\color{green} \textbf{5. Create User and Login with User.}$
- user : Guru
- passwd : <space>

$\color{red} \textbf{NOTE :}$ When start Using the Jenkins.

$\color{green} \textbf{6. Install Plugins.}$

$\color{purple} \textbf{Dashboard > Manage jenkins > Plugins}$

1. Maven Integration
2. Docker
3. Docker Commons
4. Docker Pipeline
5. Docker API
6. docker-build-step

$\color{green} \textbf{7. Add it in tool.}$
- 
