# Open Stack 
## Documentació

Openstack es una plataforma de computació al cloud de codi obert que admet tot tipus de entorns. Es una implementacio simple, amb escalabilitat massiva i un conjunt extens de caracteristiques. Proporciona solucions de IaaS (Infrastructure as a Service) a través d'una varietat de serveis. Cada servei ofereix una interficie de programació d'aplicacions que facilita la integració.


Esta guía cubre la implementación paso a paso de los principales servicios de OpenStack utilizando una arquitectura de ejemplo funcional adecuada para nuevos usuarios de OpenStack con suficiente experiencia en Linux. Esta guía no está diseñada para ser utilizada para instalaciones de sistemas de producción, sino para crear una prueba de concepto mínima con el fin de aprender sobre OpenStack.

Después de familiarizarse con la instalación básica, la configuración, el funcionamiento y la resolución de problemas de estos servicios de OpenStack, debe considerar los siguientes pasos para la implementación mediante una arquitectura de producción:

    Determine e implemente los servicios básicos y opcionales necesarios para cumplir con los requisitos de rendimiento y redundancia.

    Aumente la seguridad utilizando métodos como firewalls, cifrado y políticas de servicio.

    Utilice una herramienta de implementación como Ansible, Chef, Puppet o Salt para automatizar la implementación y la gestión del entorno de producción. El proyecto OpenStack tiene un par de proyectos de implementación con guías específicas por versión: 
