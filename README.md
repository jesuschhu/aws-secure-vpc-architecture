# Fase 1: Detalles de configuración de la VPC

Para la creación del contenedor de red, los parámetros seleccionados en la consola se definen de la siguiente manera:

### Recursos que se van a crear
**Solo la VPC**: Esta opción indica que AWS creará únicamente el límite lógico de la red. No se generarán subredes, gateways ni tablas de enrutamiento de forma automática, permitiendo una construcción manual y personalizada de cada componente.

### Etiqueta de nombre
**VPC-Jesus**: Es el identificador asignado al recurso mediante etiquetas (Tags). Este nombre permite organizar y filtrar la red dentro del panel de administración de AWS.

### Bloque de CIDR IPv4
**Entrada manual**: Permite definir específicamente el rango de direcciones IP privadas que tendrá la red.
**10.0.0.0/16**: Este valor determina el tamaño de la red.
> **Nota técnica**: Un bloque /16 proporciona 65,536 direcciones IP. Se elige sobre un bloque /24 para garantizar que exista espacio suficiente al segmentar la arquitectura en subredes públicas y privadas, evitando limitaciones de direccionamiento a futuro.

### Bloque de CIDR IPv6
**Sin bloque de CIDR IPv6**: Se ha optado por no asignar direccionamiento IPv6 para simplificar la configuración de las reglas de filtrado en los Security Groups y Network ACLs.

### Tenencia
**Predeterminado**: Indica que la VPC y las instancias se ejecutarán sobre hardware compartido, siendo la opción estándar para optimizar costos en entornos de desarrollo o laboratorio.

### Control de cifrado de VPC
**Ninguno**: No se aplica una capa de cifrado de red adicional gestionada por AWS para el tráfico entre instancias, evitando latencia o costos innecesarios en esta fase.
