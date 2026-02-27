Arquitectura de Red Segura en AWS
Introducción

Este proyecto documenta el despliegue de una infraestructura de red segmentada en Amazon Web Services. El diseño se basa en un modelo de tres capas para separar los recursos de acceso público de los servidores críticos alojados en zonas privadas .

Objetivos técnicos:

    Aislamiento de recursos: Implementar servidores en subredes sin direccionamiento público para mitigar vectores de ataque directos desde internet .

    Control de flujo: Configurar salida a internet para recursos privados mediante un NAT Gateway, restringiendo conexiones entrantes no solicitadas .

    Gestión de accesos: Establecer perímetros de seguridad mediante Security Groups que utilizan referencias cruzadas en lugar de reglas basadas en direcciones IP estáticas .

