# Kubernates-Installation


### 1.Install minikube 
First verify docker installed or not in the machine
```bahs
sudo docker version
```

1. linux x84-64
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```
or you should choose according your machine configuration on
https://minikube.sigs.k8s.io/docs/start/

2.To check minikube version
```bash
minikube version
```

3.From a terminal with administrator access
```bash
minikube start
```

### 2.Install Kubernates

1.Install kubectl binary with curl on Linux
 Download the latest release with the command

```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

2.Validate the binary (optional)
Download the kubectl checksum file
```bash
curl -LO "https://dl.k8s.io/$(curl -L -s https://dl.k8s.io/release/stable.txt
```

3.Validate the kubectl binary against the checksum file:
```bash
echo "$(<kubectl.sha256) kubectl" | sha256sum --check
```

If valid, the output is-
kubectl: OK

4.Install kubectl
```bash
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

5.Test to ensure the version you installed is up-to-date:
```bash
kubectl version --client
```

6. verify minikube cluster
```bash
kubectl cluster-info 
```

Or install using .deb package management in ubuntu
1.Update the apt package index and install packages needed to use the Kubernetes apt repository
```bash
sudo apt-get update
```
```bash
sudo apt-get install -y apt-transport-https ca-certificates curl
```

2.Download the Google Cloud public signing key
```bash
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
```

3.Add the Kubernetes apt repository:
```bash
echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
```

4.Update apt package index with the new repository and install kubectl:
```bash
sudo apt-get update
```
```bash
sudo apt-get install -y kubectl
```

5.verify cluster
```bash
kubctl get cluster-info
```



Thanks.


