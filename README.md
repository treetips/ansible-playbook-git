# 概要

yumでgitをインストールしようとすると古いバージョンになりがちです。このplaybookを使う事で、githubのソースコードからコンパイルし、最新バージョンのgitをインストールする事ができるようになります。

バージョンの指定は無く、常にその時の最新バージョンがインストールされます。

# playbook実行環境

Vagrant + CentOS7.1 + ansible v1.9.2  
Vagrant + CentOS6.5 + ansible v1.9.2  
で正常動作している事を確認しています。

# インベントリ

ansible-playbook-git/hosts

```ini
[development]
192.168.33.31

[development:vars]
ansible_ssh_port=22
ansible_ssh_user=vagrant
ansible_ssh_pass=vagrant
```

[development]の部分を任意のIPに変更して下さい。

# 実行方法

```
ansible-playbook -i hosts site.yml
```
