![openstack](images/logo.png)
# Instalació

Per utilitzar openstack hi ha una versio de prova que ens permet instalar automaticament tots els components necessaris perque funcioni. Dins d'openstack hi ha diferents components amb una funcionalitat cada un. La finalitat d'aquest software es que agafis els components que necessites per montar la teva estructura. 

**MicroStack** proporciona un desplegament d'OpenStack únic o multi-node que pot 
funcionar directament en un equip. Es va fer per als desenvolupadors per a 
prototipar i provar. MicroStack és un OpenStack en un snap que vol dir 
que tots els serveis d'OpenStack i biblioteques de suport estan empaquetades 
juntes en un sol paquet que es pot instal·lar, actualitzar o eliminar fàcilment. 
MicroStack inclou tots els components clau d'OpenStack: **Keystone, Nova, Neutron, 
Glance i Cinder.**

## Requisits necessaris per poder implementar-lo
* Processador Multi-Core
* Sistema Linux 
	* Jo he triat Ubuntu 20.04
* 8 GB de RAM o superior

*Com vaig tenir moltes complicacions per instalar Openstack en una maquina virtual
vaig decidir llogar un cloud a https://clouding.io/ i pagar per els recursos 
necessaris*

**Server:161.22.45.253**

Per instal.lar aquesta petita versio de openstack la comunitat de Canonical ha 
elaborat una forma sencilla de poder fer-ho amb l'eina de gestio i instalacio *snap*.

```
$ sudo snap install microstack --devmode --beta
```

Amb aquesta ordre estan comprimits tots els components basics per a fer funcionar
Openstack en un sol paquet. Finalitza  amb:

```
microstack (beta) ussuri from Canonical✓ installed
```

**Microstack** funciona com un sol servei, un cop instalat cal engegarlo. 
Executant la ordre que l'engega, podem veure el proces d'inicialització de cada un dels components.

```
root@microstack-v2:~# sudo microstack init --auto --control
2021-05-15 18:47:16,705 - microstack_init - INFO - Configuring clustering ...
2021-05-15 18:47:16,824 - microstack_init - INFO - Setting up as a control node.
2021-05-15 18:47:20,920 - microstack_init - INFO - Configuring networking ...
2021-05-15 18:47:27,057 - microstack_init - INFO - Opening horizon dashboard up to *
2021-05-15 18:47:28,336 - microstack_init - INFO - Waiting for RabbitMQ to start ...
Waiting for 161.22.45.253:5672
2021-05-15 18:47:28,802 - microstack_init - INFO - RabbitMQ started!
2021-05-15 18:47:28,802 - microstack_init - INFO - Configuring RabbitMQ ...
2021-05-15 18:47:30,214 - microstack_init - INFO - RabbitMQ Configured!
2021-05-15 18:47:30,243 - microstack_init - INFO - Waiting for MySQL server to start ...
Waiting for 161.22.45.253:3306
2021-05-15 18:47:30,705 - microstack_init - INFO - Mysql server started! Creating databases ...
2021-05-15 18:47:31,679 - microstack_init - INFO - Configuring Keystone Fernet Keys ...
2021-05-15 18:47:41,393 - microstack_init - INFO - Bootstrapping Keystone ...
2021-05-15 18:47:44,806 - microstack_init - INFO - Creating service project ...
2021-05-15 18:47:48,437 - microstack_init - INFO - Keystone configured!
2021-05-15 18:47:48,469 - microstack_init - INFO - Configuring the Placement service...
2021-05-15 18:47:55,224 - microstack_init - INFO - Running Placement DB migrations...
2021-05-15 18:47:59,236 - microstack_init - INFO - Configuring nova control plane services ...
2021-05-15 18:48:02,980 - microstack_init - INFO - Running Nova API DB migrations (this may take a lot of time)...
2021-05-15 18:48:21,004 - microstack_init - INFO - Running Nova DB migrations (this may take a lot of time)...
Waiting for 161.22.45.253:8774
2021-05-15 18:48:49,368 - microstack_init - INFO - Creating default flavors...
2021-05-15 18:49:08,532 - microstack_init - INFO - Configuring nova compute hypervisor ...
2021-05-15 18:49:08,533 - microstack_init - INFO - Checking virtualization extensions presence on the host
2021-05-15 18:49:08,561 - microstack_init - INFO - Hardware virtualization is supported - KVM will be used for Nova instances
2021-05-15 18:49:10,228 - microstack_init - INFO - Configuring the Spice HTML5 console service...
2021-05-15 18:49:10,682 - microstack_init - INFO - Configuring Neutron
Waiting for 161.22.45.253:9696
2021-05-15 18:49:48,901 - microstack_init - INFO - Configuring Glance ...
Waiting for 161.22.45.253:9292
2021-05-15 18:50:10,190 - microstack_init - INFO - Creating security group rules ...
2021-05-15 18:50:17,504 - microstack_init - INFO - Configuring the Cinder services...
2021-05-15 18:51:05,635 - microstack_init - INFO - Running Cinder DB migrations...
2021-05-15 18:51:14,797 - microstack_init - INFO - restarting libvirt and virtlogd ...
2021-05-15 18:51:36,449 - microstack_init - INFO - Complete. Marked microstack as initialized!
root@microstack-v2:~#
```

Un cop engegats tots els serveis, ja podem posar en marxa una maquina virtual
utiltzan tots els components instalats. [Ja podem posar en marxa una maquina virtual](demo.md)

[Torna](README.md)























