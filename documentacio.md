# Open Stack 
## Documentació

Openstack es una plataforma de computació al cloud de codi obert que admet 
tot tipus de entorns. Es una implementacio simple, amb escalabilitat 
massiva i un conjunt extens de caracteristiques. Proporciona solucions 
de IaaS *(Infrastructure as a Service)* a través d'una varietat de serveis. 
Cada servei ofereix una interficie de programació d'aplicacions *(API)* que facilita 
la integració.

A continuació la llista de serveis i les seves respectives API:
### Serveis
* Telemetry Alarming services (aodh)
* Key Manager service (barbican)
* Resource reservation service (blazar)
* Telemetry Data Collection service (ceilometer)
* Block Storage service (cinder)
* Rating service (cloudkitty)
* DNS service (designate)
* **Image service (glance)**
* Orchestration service (heat)
* **Dashboard (horizon)**
* Bare Metal service (ironic)
* **Identity service (keystone)**
* Shared File Systems service (manila)
* Application Catalog service (murano)
* **Networking service (neutron)**
* **Compute service (nova)**
* Load-balancer service (octavia)
* Placement service (placement)
* Data Processing service (sahara)
* Clustering service (senlin)
* Software Development Lifecycle Automation service (solum)
* Object Storage service (swift)
* NFV Orchestration service (tacker)
* Database service (trove)
* Containers service (zun) 


## Ordres openstack (microstack)

Amb l'ordre següent podem veure els components que utilitza openstack per funcionar amb la versió de microstack.

```
root@microstack-v2:~# microstack.openstack catalog list
+-----------+-----------+---------------------------------------------------------------------------+
| Name      | Type      | Endpoints                                                                 |
+-----------+-----------+---------------------------------------------------------------------------+
| keystone  | identity  | microstack                                                                |
|           |           |   admin: http://161.22.45.253:5000/v3/                                    |
|           |           | microstack                                                                |
|           |           |   internal: http://161.22.45.253:5000/v3/                                 |
|           |           | microstack                                                                |
|           |           |   public: http://161.22.45.253:5000/v3/                                   |
|           |           |                                                                           |
| placement | placement | microstack                                                                |
|           |           |   internal: http://161.22.45.253:8778                                     |
|           |           | microstack                                                                |
|           |           |   admin: http://161.22.45.253:8778                                        |
|           |           | microstack                                                                |
|           |           |   public: http://161.22.45.253:8778                                       |
|           |           |                                                                           |
| cinderv2  | volumev2  | microstack                                                                |
|           |           |   public: http://161.22.45.253:8776/v2/773932d230804fbfbc39b88bca6d70fe   |
|           |           | microstack                                                                |
|           |           |   admin: http://161.22.45.253:8776/v2/773932d230804fbfbc39b88bca6d70fe    |
|           |           | microstack                                                                |
|           |           |   internal: http://161.22.45.253:8776/v2/773932d230804fbfbc39b88bca6d70fe |
|           |           |                                                                           |
| glance    | image     | microstack                                                                |
|           |           |   internal: http://161.22.45.253:9292                                     |
|           |           | microstack                                                                |
|           |           |   public: http://161.22.45.253:9292                                       |
|           |           | microstack                                                                |
|           |           |   admin: http://161.22.45.253:9292                                        |
|           |           |                                                                           |
| nova      | compute   | microstack                                                                |
|           |           |   public: http://161.22.45.253:8774/v2.1                                  |
|           |           | microstack                                                                |
|           |           |   admin: http://161.22.45.253:8774/v2.1                                   |
|           |           | microstack                                                                |
|           |           |   internal: http://161.22.45.253:8774/v2.1                                |
|           |           |                                                                           |
| cinderv3  | volumev3  | microstack                                                                |
|           |           |   internal: http://161.22.45.253:8776/v3/773932d230804fbfbc39b88bca6d70fe |
|           |           | microstack                                                                |
|           |           |   admin: http://161.22.45.253:8776/v3/773932d230804fbfbc39b88bca6d70fe    |
|           |           | microstack                                                                |
|           |           |   public: http://161.22.45.253:8776/v3/773932d230804fbfbc39b88bca6d70fe   |
|           |           |                                                                           |
| neutron   | network   | microstack                                                                |
|           |           |   admin: http://161.22.45.253:9696                                        |
|           |           | microstack                                                                |
|           |           |   public: http://161.22.45.253:9696                                       |
|           |           | microstack                                                                |
|           |           |   internal: http://161.22.45.253:9696                                     |
|           |           |                                                                           |
+-----------+-----------+---------------------------------------------------------------------------+

```

Disposem de ordres per poder consultar,afegir o esborrar imatges, instancies, xarxes...

Per engegar una instancia amb tot per defecte, es una instrucció sencilla:

```microstack launch <imatge> --name <nom>```

### Visualitzar les instancies que tenim 
```
root@microstack-v2:~# microstack.openstack server list
+--------------------------------------+-----------+--------+------------------------------------+---------------+----------+
| ID                                   | Name      | Status | Networks                           | Image         | Flavor   |
+--------------------------------------+-----------+--------+------------------------------------+---------------+----------+
| b76e2e25-e7e0-453e-a740-8aabe411a258 | vm-cirros | ACTIVE | test=192.168.222.54, 10.20.20.118  | cirros        | m1.tiny  |
| 562d8831-d269-4005-acb4-3c32c8178415 | test      | ERROR  |                                    |               | m1.small |
| 1fc4b2a1-ce36-41a4-a272-205b90a37205 | test      | ERROR  |                                    | fedoracloud27 | m1.tiny  |
| edf71082-4c50-4537-96fd-ec7ec712fd56 | test      | ACTIVE | test=192.168.222.180, 10.20.20.175 | cirros        | m1.tiny  |
+--------------------------------------+-----------+--------+------------------------------------+---------------+----------+
```

### Visualitzar les imatges disponibles
```
root@microstack-v2:~# microstack.openstack image list
+--------------------------------------+---------------+--------+
| ID                                   | Name          | Status |
+--------------------------------------+---------------+--------+
| ccc60c5d-a19c-41eb-9f98-70cd5d62c700 | cirros        | active |
| 9ede85cc-9deb-42df-8712-c371f93a3943 | debian9       | active |
| aa178bbd-68e9-4729-80aa-fd5ad4842c5b | fedoracloud27 | active |
+--------------------------------------+---------------+--------+

```

### Crear i visualitzar els tamanys per les VM
```
root@microstack-v2:~# microstack.openstack flavor create --ram 512 --disk 1 --vcpus 1 m1.mytiny
+----------------------------+--------------------------------------+
| Field                      | Value                                |
+----------------------------+--------------------------------------+
| OS-FLV-DISABLED:disabled   | False                                |
| OS-FLV-EXT-DATA:ephemeral  | 0                                    |
| disk                       | 1                                    |
| id                         | ac93701d-f60b-4766-9992-94bf42f8fb49 |
| name                       | m1.mytiny                            |
| os-flavor-access:is_public | True                                 |
| properties                 |                                      |
| ram                        | 512                                  |
| rxtx_factor                | 1.0                                  |
| swap                       |                                      |
| vcpus                      | 1                                    |
+----------------------------+--------------------------------------+
root@microstack-v2:~# microstack.openstack flavor list
+--------------------------------------+-----------+-------+------+-----------+-------+-----------+
| ID                                   | Name      |   RAM | Disk | Ephemeral | VCPUs | Is Public |
+--------------------------------------+-----------+-------+------+-----------+-------+-----------+
| 1                                    | m1.tiny   |   512 |    1 |         0 |     1 | True      |
| 2                                    | m1.small  |  2048 |   20 |         0 |     1 | True      |
| 3                                    | m1.medium |  4096 |   20 |         0 |     2 | True      |
| 4                                    | m1.large  |  8192 |   20 |         0 |     4 | True      |
| 5                                    | m1.xlarge | 16384 |   20 |         0 |     8 | True      |
| ac93701d-f60b-4766-9992-94bf42f8fb49 | m1.mytiny |   512 |    1 |         0 |     1 | True      |
+--------------------------------------+-----------+-------+------+-----------+-------+-----------+

```















































