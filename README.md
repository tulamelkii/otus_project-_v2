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

     

 
