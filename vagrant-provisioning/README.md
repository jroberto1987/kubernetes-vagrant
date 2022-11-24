**Procedimento para subir o ambiente de um cluster kurbenetes via vagrant, baseado no projeto https://github.com/justmeandopensource/kubernetes https://www.youtube.com/watch?v=2aJSAzLW6fg**

Instalando o vagrant do repositorio no ubuntu 22.04 <br>
`apt-get install vagrant`
`apt-get install git`

Baixar o repositorio com os arquivos do vagrant para subir o ambiente <br>
`git clone https://github.com/jroberto1987/kubernetes-vagrant.git`

Subindo o ambiente no vagrant <br>
`vim cat /etc/vbox/networks.conf`
* 0.0.0.0/0 ::/0

`cd /home/jroberto/kubernetes-vagrant/vagrant-provisioning`
`vagrant up`



Instalado o kubectl no host para acesso ao cluster <br>
`sudo apt-get install -y ca-certificates curl`

`sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg`

`echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list`

`sudo apt-get update`

`sudo apt-get install -y kubectl`

Adicionando a chave de acesso ao cluster <br>
`mkdir ~/.kube`
`scp root@172.16.16.100:/etc/kubernetes/admin.conf /home/jroberto/.kube/config`
`kubectl cluster-info`
`kubectl get nodes`

**Comandos administração vagrant** <br>
vagrant up <br>
vagrant status <br>
vagrant destroy -f <br>