# Com aixecar una VM amb microstack

Microstack ofereix una imatge de demostracio basada en Ubuntu anomenada *CirrOS*, es una *tiny linux* que permet aixecar una maquina virtual petita per veure el funcionament d'openstack.

**Totes les ordres d'openstack poden utilitzar-se amb microstack.**

**Exemple:**

```
root@microstack-v2:~# microstack.openstack --help | more
usage: openstack [--version] [-v | -q] [--log-file LOG_FILE] [-h] [--debug]
                 [--os-cloud <cloud-config-name>]
                 [--os-region-name <auth-region-name>]
                 [--os-cacert <ca-bundle-file>] [--os-cert <certificate-file>]
                 [--os-key <key-file>] [--verify | --insecure]
                 [--os-default-domain <auth-domain>]
[...]
```

### Mostra les configuracions de la VM creada

```
root@microstack-v2:~# microstack.openstack server show vm-cirros
+-------------------------------------+----------------------------------------------------------+
| Field                               | Value                                                    |
+-------------------------------------+----------------------------------------------------------+
| OS-DCF:diskConfig                   | MANUAL                                                   |
| OS-EXT-AZ:availability_zone         | nova                                                     |
| OS-EXT-SRV-ATTR:host                | microstack-v2                                            |
| OS-EXT-SRV-ATTR:hypervisor_hostname | microstack-v2                                            |
| OS-EXT-SRV-ATTR:instance_name       | instance-00000004                                        |
| OS-EXT-STS:power_state              | Running                                                  |
| OS-EXT-STS:task_state               | None                                                     |
| OS-EXT-STS:vm_state                 | active                                                   |
| OS-SRV-USG:launched_at              | 2021-05-15T08:26:38.000000                               |
| OS-SRV-USG:terminated_at            | None                                                     |
| accessIPv4                          |                                                          |
| accessIPv6                          |                                                          |
| addresses                           | test=192.168.222.54, 10.20.20.118                        |
| config_drive                        |                                                          |
| created                             | 2021-05-15T08:26:29Z                                     |
| flavor                              | m1.tiny (1)                                              |
| hostId                              | 436ca40f02d8ce269d7b6be6cda0c5ddbe4a18c6f4479601b13d21f8 |
| id                                  | b76e2e25-e7e0-453e-a740-8aabe411a258                     |
| image                               | cirros (ccc60c5d-a19c-41eb-9f98-70cd5d62c700)            |
| key_name                            | microstack                                               |
| name                                | vm-cirros                                                |
| progress                            | 0                                                        |
| project_id                          | 773932d230804fbfbc39b88bca6d70fe                         |
| properties                          |                                                          |
| security_groups                     | name='default'                                           |
| status                              | ACTIVE                                                   |
| updated                             | 2021-05-15T08:26:39Z                                     |
| user_id                             | 3687bc329d8c4801905a57f2c6db6a49                         |
| volumes_attached                    |                                                          |
+-------------------------------------+----------------------------------------------------------+
```

