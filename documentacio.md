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


Amb l'ordre següent podem veure els components que utilitza openstack per funcionar en aquesta versió de microstack.

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
