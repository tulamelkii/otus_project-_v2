*__This is "Building High-Availability Cluster on the platform : Wordpress, Galera Mariadb, Nginx with floating ip(keepalived),ELK,Prometheus,Bacula"__*
 
 ![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/vip2.png) 


 **_My errors :_**
 
- *First I created Wordpress + Postgres and for two days I could not make friends between the two systems. When I saw the error logs "Postgress is not supported" I realized "what am I doing" :)*
- *My next mistake: I'm working with someone else's image and I have a lot of problems installing other software.*
- *I didn't understand whether I could create a cluster or not. Not believing in my skills, I create a small stand with 1 nginx and 2 Wordpress servers.*

**_The next step was to build an interesting stand:_**
- *First: i created my image with Packer and upload to Vagrant (https://app.vagrantup.com/tulamelkii/boxes/VDebian12)*
- *This stand is built in VirtualBox 6.1. Virtual machines running Linux VDebian 6.1.0-13-amd64 x86_64.*
- *step I created two nginx in front with internal and external floating IP address (Why did I create two floating IP addresses? I want to login to my stand by one IP address. (if nginx is not working). NextIP*
 *address balancing in my cluster for Galera)*
- *I created a 3 node high availability cluster for Wordpress. There are 3 multimasters in this cluster (Galera cluster). If my node dies, I won't feel it. And my data will be saved.*

**_My WordPress:_**

![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/2023-12-17_16-51.png)

- *After I created ELK, it is a really big stand. This is Elasticsearch + Logstash + kibana +filebeat(agent)*
- *This is a stack that I created for the first time, I have never worked on this stack, but now I know that it is a very powerful tool.*
- *This is a stand, I made a few rules and created only 1 grok to filter nginx and apache2 logs.*
  
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/kibana.png) 
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/kibana.png.png)

 **_Next step i create monitoring_**
 
- *I created monitoring with Docker. It's really cool. I created 3 docker containers on Prometheus servers: Grafana, Nodexporter agent, and also created similar docker agents on different nodes.*
- *i created CAdvisor for monitoring but i can't conecting to Prometheus dashbord. This is only necessary for the healthy life of my docker containers.*
 ![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/Prometheus.png)
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/Prom3.png)

- *And the finishing tools are backup. I actually spent a lot of time thinking about backup. When I was doing my homework for backup I created in borg*
- *But this time I wanted something new. and I said it could be bacula. And it's a really complex system. this is a layer cake from programs*
- *I read the manual for this system in three or four days. A lot of people don't like this stack (it's a really complex system. But once you understand how to work with this tool, you will say that it's really a* *great system (very flexible and powerful)*
- *first I created only a console tool, but I wanted to make + baculum (this is a web interface for bacula)*
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/baculum.png)
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/baculm2.png)

- *Oh, of course, I forgot to show CAdevisor and Prometheus*
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/Prometheus3.png)

- **_This is health monitoring for my Docker container. I haven't done monitoring for Prometheus, but I believe I can!_**
  
![image](https://github.com/tulamelkii/otus_project-_v2/blob/main/images/Cadvisor.png)

**_This is stend created with:_**

- *Packer*
- *Ansible*
- *Vagrant*
- *Galera cluster (Mariadb)*
- *Postgres*
- *Kibana*
- *Grafana*
- *Elasticsearc*
- *Logstash*
- *Filebeat*
- *Keepalived ip*
- *Nginx*
- *Apache*
- *Bacula*
- *Baculum*
- *Docker*
- *Ntp*
- *Wordpress*
- *Nodexporter*
- *CAdvisor*
 
 **_in fact, this is my first interesting project in my entire life and I did it :)_**
 
 **_Only step by step helpful to you_**
 
 **_Thanks for all)see you soon for the  new project........)_**
 
 **_And happy New Year hohoho......_**
