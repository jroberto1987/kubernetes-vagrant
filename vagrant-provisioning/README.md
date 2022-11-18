Procedimento realizado baseado no projeto https://github.com/justmeandopensource/kubernetes


Instalando o vagrant do repositorio no ubuntu 22.04 
apt-get install vagrant

Instalado o kubectl no host para acesso ao cluster
sudo apt-get install -y ca-certificates curl

sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg

echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt-get update
sudo apt-get install -y kubectl

Adicionando a chave de acesso ao cluster
mkdir ~/.kube
scp root@172.16.16.100:/etc/kubernetes/admin.conf /home/jroberto/.kube/config
kubectl cluster-info
kubectl get nodes

vagrant up
vagrant status
vagrant destroy -f