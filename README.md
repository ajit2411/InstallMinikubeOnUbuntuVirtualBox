# InstallMinikubeOnUbuntuVirtualBox
Install Minikube on Ubuntu on Virtualbox on Windows 10

#1. install virtual box (virtualbox.org)

#2. download a ubuntu image (osboxes.org)

#3. prepare VM for minikube:

  #a. Update your Ubuntu box 
  sudo apt update && sudo apt upgrade

  #b. install cURL
  sudo apt install curl

  #c. install extension pack
  sudo apt-get install -y virtualbox virtualbox-ext-pack

#4. Prerequisites:
  
  #a. install docker
  curl -fsSL https://get.docker.com -o get-docker.sh
  sh get-docker.sh
  usermod -aG docker <username>
 
  #b. install dependencies:
  sudo apt-get update && sudo apt-get install -y apt-transport-https && sudo apt install -y curl

#4. start to install minikube
 
 #a. install kubectl
 curl -Lo kubectl https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl 
 
 chmod +x kubectl && sudo mv kubectl /usr/bin/.

 which kubectl

 #b. install minikube
 curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 

 chmod +x minikube && sudo mv minikube /usr/local/bin/

 minikube version

 #c. install required component
 sudo apt-get install -y conntrack

 #d. finally we are done with the installation and now start the minikube
 sudo minikube start --vm-driver=none

 #e. start the dashboard
 sudo minikube dashboard

 #f. at this point, everything is successful, now just poke around with following commands
 sudo kubectl api-versions
 sudo kubectl get nodes
 sudo kubectl get pod
 sudo kubectl get namespace
 sudo kubectl cluster-info
 
 #see youtube tutorial of this installation 
 
