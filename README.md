# azure-learning
Create VM ,Access the VM and install Jenkins

1.Navigate Azure Portal – create resource group – create virtual machine
2.create VM and give mandatory details  and download the pem file 
3.For best practice to install Jenkins in vm ,install git bash physically
4.Git bash commands 
      1.ssh -i path for the pem file azureuser@public ipaddress
For this ssh -i "C:\Users\Raju\Downloads\first-vm-1_key.pem" azureuser@20.84.68.29

5.install Jenkins by using following commands
  1. sudo apt update
sudo apt install openjdk-17-jre
2. java -version
3.
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install Jenkins

6.If you want to verify whether Jenkins installed or not 
 1.ps -ef | grep Jenkins
Its shows which port Jenkins are running its 8080
7.Finally, we check in port the Jenkins are running or not 
  By default, any cloud provider port rules are blocked, we need to enable this
8.Go to VM -networksettings-create port rule- inbound port rule -add 8080 port
9.verify the ports whether the Jenkins is running or not with the public ip address
    http://20.84.68.29:8080
its shows sign in jenkins


