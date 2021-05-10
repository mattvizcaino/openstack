# Open Stack 
## Documentació
El proyecto OpenStack es una plataforma de computación en la nube de código abierto que admite todo tipo de entornos en la nube. El proyecto apunta a una implementación simple, escalabilidad masiva y un rico conjunto de características. Expertos en computación en la nube de todo el mundo contribuyen al proyecto.

OpenStack proporciona una solución de infraestructura como servicio (IaaS) a través de una variedad de servicios complementarios. Cada servicio ofrece una interfaz de programación de aplicaciones (API) que facilita esta integración.

Esta guía cubre la implementación paso a paso de los principales servicios de OpenStack utilizando una arquitectura de ejemplo funcional adecuada para nuevos usuarios de OpenStack con suficiente experiencia en Linux. Esta guía no está diseñada para ser utilizada para instalaciones de sistemas de producción, sino para crear una prueba de concepto mínima con el fin de aprender sobre OpenStack.

Después de familiarizarse con la instalación básica, la configuración, el funcionamiento y la resolución de problemas de estos servicios de OpenStack, debe considerar los siguientes pasos para la implementación mediante una arquitectura de producción:

    Determine e implemente los servicios básicos y opcionales necesarios para cumplir con los requisitos de rendimiento y redundancia.

    Aumente la seguridad utilizando métodos como firewalls, cifrado y políticas de servicio.

    Utilice una herramienta de implementación como Ansible, Chef, Puppet o Salt para automatizar la implementación y la gestión del entorno de producción. El proyecto OpenStack tiene un par de proyectos de implementación con guías específicas por versión: 