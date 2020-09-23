# K3s Clusters

基于 vagrant + ansible + alpine 快速搭建一个 k3s 的集群环境

## 依赖

需要安装 VirtualBox, vagrant 以及 ansible

Ubuntu/Debina

```bash
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install virtualbox vagrant ansible
```

MacOS

```bash
brew cask install virtualbox vagrant
brew install ansible
```

CentOS/Redhat

请自行安装，很少用不太清楚。

## 部署

1. clone 此项目
2. 进入 k3s-clusters 目录下
3. 执行一键命令

PROXY_URL: 在网络不太好的情况下可以设置 http 代理

```bash
git clone https://github.com/yakumioto/vagrants.git

cd vagrants/k3s-clusters

vagrant up --no-provision && \
  vagrant provision --provision-with bootstrap && \
  PROXY_URL="{your_proxy}" vagrant provision --provision-with deploy
```
