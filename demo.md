# Com engegar una màquina virtual amb microstack

Microstack ofereix una imatge de demostracio basada en Ubuntu anomenada *CirrOS*, es una *tiny linux* que permet aixecar una maquina virtual petita per veure el funcionament d'openstack.

## Creant i engegant la màquina virtual amb la imatge CirrOS
```
root@microstack-v2:~# microstack launch cirros --name mycirros
Launching server ...
Allocating floating ip ...
Server mycirros launched! (status is BUILD)

Access it with `ssh -i /home/root/snap/microstack/common/.ssh/id_microstack cirros@10.20.20.2`
You can also visit the OpenStack dashboard at http://161.22.45.253:80

```
Un cop creada, hem d'esperar uns segons que s'engegui i poder accedir per ssh amb la clau. Ja estan a dins pots crear una contrasenya per no utilitzar la clau.
## Accedint a la màquina virtual amb SSH

```
root@microstack-v2:~# ssh -i /home/root/snap/microstack/common/.ssh/id_microstack cirros@10.20.20.2
$ uname -a
Linux mycirros 4.4.0-28-generic #47-Ubuntu SMP Fri Jun 24 10:09:13 UTC 2016 x86_64 GNU/Linux
$ pwd
/home/cirros
```

## Mostra les configuracions de la màquina virtual recentment creada

```
root@microstack-v2:~# microstack.openstack server show mycirros
+-------------------------------------+----------------------------------------------------------+
| Field                               | Value                                                    |
+-------------------------------------+----------------------------------------------------------+
| OS-DCF:diskConfig                   | MANUAL                                                   |
| OS-EXT-AZ:availability_zone         | nova                                                     |
| OS-EXT-SRV-ATTR:host                | microstack-v2                                            |
| OS-EXT-SRV-ATTR:hypervisor_hostname | microstack-v2                                            |
| OS-EXT-SRV-ATTR:instance_name       | instance-00000005                                        |
| OS-EXT-STS:power_state              | Running                                                  |
| OS-EXT-STS:task_state               | None                                                     |
| OS-EXT-STS:vm_state                 | active                                                   |
| OS-SRV-USG:launched_at              | 2021-05-17T11:05:11.000000                               |
| OS-SRV-USG:terminated_at            | None                                                     |
| accessIPv4                          |                                                          |
| accessIPv6                          |                                                          |
| addresses                           | test=192.168.222.203, 10.20.20.2                         |
| config_drive                        |                                                          |
| created                             | 2021-05-17T11:04:57Z                                     |
| flavor                              | m1.tiny (1)                                              |
| hostId                              | 436ca40f02d8ce269d7b6be6cda0c5ddbe4a18c6f4479601b13d21f8 |
| id                                  | f91c6173-0701-4314-b84e-555ac4f928be                     |
| image                               | cirros (ccc60c5d-a19c-41eb-9f98-70cd5d62c700)            |
| key_name                            | microstack                                               |
| name                                | mycirros                                                 |
| progress                            | 0                                                        |
| project_id                          | 773932d230804fbfbc39b88bca6d70fe                         |
| properties                          |                                                          |
| security_groups                     | name='default'                                           |
| status                              | ACTIVE                                                   |
| updated                             | 2021-05-17T11:05:12Z                                     |
| user_id                             | 3687bc329d8c4801905a57f2c6db6a49                         |
| volumes_attached                    |                                                          |
+-------------------------------------+----------------------------------------------------------+
```

[Torna](README.md)