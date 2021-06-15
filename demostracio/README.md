
# Accés al servidor openstack

Obrir un terminal per accedir per ssh 

Accedirem al usuari creat per accedir com a client anomenat "demo" amb password "demo"



```ssh -i controlador.pem demo@161.22.47.54```

És possible que doni error i aixo pot ser per els permisos de la clau. Cal fer la següent ordre:

```chmod 400 controlador.pem```

I ja ens hauria de deixar accedir.

Des del client podem accedir una instancia propia:

```ssh -i .ssh/key_cirros.pem cirros@demo-openstack```

Des d'aquesta imatge no es pot fer gran cosa ja que es una imatge de mostra. 

Per visualitzar informacio sobre alguns dels elements d'openstack podem fer les següents ordres.

* openstack catalog list
* openstack image list
* openstack image show <nom>
* openstack flavor list
* openstack flavor show <nom>
* openstack volume list
* openstack volume list
* openstack server list
* openstack server show <nom>

[Torna](openstack/README.md)