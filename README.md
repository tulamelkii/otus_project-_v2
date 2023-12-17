- This is "Building High-Availability Cluster on the platform : Wordpress, Galera Mariadb, Nginx with floating ip(keepalived),ELK,Prometheus,Bacula"
 
 ![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/Virtual.png) 


- My Path an error :
- I created first Wordpress + Postgres and two day i could not make friends between 2 systems.When i see error logs "Postgress not supported" i undestend: "what i do":)
- Next my error : i crete someone else's image and i have alot of prublem for install diferent aplet
- i don't undestend i can create cluster or not. I dont belive my skils and i create litle stend with 1 nginx frontend and 2 backend Wordpress.

Next step i want build interesting stend:
- First: i create my image with Packer and upload to Vagrant (https://app.vagrantup.com/tulamelkii/boxes/VDebian12)
- This is stend building from VirtualBox 6.1. Virtual  machines from Linux VDebian 6.1.0-13-amd64 x86_64.
- Next step i created two nginx on the front with float ip internal and external (why i created two float ip? i want go in my stend to one ip.(if nginx down).Next ip balancing in my cluster for galera)
- I create High-Availability Cluster with 3 nodes for Wordpress.This cluster have 3 multi-master bd (galera cluster).If my nodes die i don't feel it.And my Data will save.
My wordpress:

![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/2023-12-17_16-51.png)

- After i created ELK this is realy big stend. It is Elasticsearch + Logstash + kibana +filebeat(agent)
- This is stack i created first time, i didnt work for this steack, but i now its wery powerfull tools
- This is stend i made few rukes and create only 1 grok for filtering nginx and apache2 log
  
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/kibana.png) 
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/kibana.png.png)

- Next step i create monitoring
- i want try create monitoring for Docker. It's realy cool. I made 3 docker container in prometheus servers: it is Kibana,Nodexporter and agent and simmilar install docker in my nodes.
- i created Advisor for monitoring but i can't conecting to Prometheus dashbord. This is only need for healthy live my docker containers.
 ![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/Prometheus.png)
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/Prom3.png)

- And finish tools it are backup. realy i allots of time think about my backup. When i made my home work for backup i create for borg
- But this time some else new and i say may be bacyla. And its realy dificul system. it's are simmilar paay for tools.
- i read tree or four day only manual for this system. I now alots of people dont like this stack (its realy difficult, but if you one time undestend how to work this sistem you say it realy grayt system(very elastic and powerful)
- First time i created only console tools but i want made + baculum( it is web interfaces for bacula)
![image] (https://github.com/tulamelkii/otus_project-_v2/blob/main/images/baculum.png)
