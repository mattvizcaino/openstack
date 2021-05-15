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

