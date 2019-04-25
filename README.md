# Ansible Project - Devops

The goal of this project is to deploy a webapp behind a HAProxy.

## RUN the project

**Open your terminal, and run**

```bash
cd ansible
vagrant up
ansible-playbook -i hosts playbook.yml
```

**Open your navigator**

- [http://192.168.201.10](http://192.168.201.10)
- [http://192.168.201.10:9000/info](http://192.168.201.10:9000/info)

## What should the students do ?

- The webapp instances should be accessible at [http://192.168.201.10](http://192.168.201.10)
- HAProxy should display stats on /info
- The data are stored and indexed with Mongodb and Elasticsearch. Therefore, each of these apps should be deployed on separate instances.

## ESIEE Setup (only when you are at the school)

In order to run the playbooks at the school, you need to install some vagrant plugins.

```
$ export http_proxy=http://cache.lan.esiee.fr:3128
$ export https_proxy=http://cache.lan.esiee.fr:3128
$ export VAGRANT_DISABLE_STRICT_DEPENDENCY_ENFORCEMENT=1

$ vagrant plugin install vagrant-proxyconf
$ vagrant plugin install vagrant-hostmanager
```

Disable proxy on firefox

```
Paramètre -> Avancé ->
“Connexion
Configurer la façon dont Firefox se connecte à Internet”
-> Paramètre -> Cocher “Pas de proxy”
```

## Vagrant

For this project, 5 Vagrant machines are provided:

- haproxy: 192.168.201.10
- app1: 192.168.201.11
- app2: 192.168.201.12
- mongodb: 192.168.201.13
- elasticsearch: 192.168.201.14

**To create the Vms**, just run

```
$ cd ansible
$ vagrant up
```

**To enter the Vms**, just run

```
$ cd ansible
$ vagrant ssh <vm_name> (ex: vagrant ssh app1)
```

## Usefull

```bash
vagrant status
```

**Exit app :**

```bash
exit
```
```
or CTRL + D
```

**Links:**

- https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-centos-7
- https://www.elastic.co/guide/en/beats/filebeat/current/setup-repositories.html
- https://github.com/elastic/ansible-elasticsearch/
- https://github.com/Asymmetrik/ansible-roles/tree/master/mongo
