# Fase 1: Detalles de configuración de la VPC

Para la creación del contenedor de red, los parámetros seleccionados en la consola se definen de la siguiente manera:

> [!abstract] Recursos que se van a crear
> **Solo la VPC**: Esta opción indica que AWS creará únicamente el límite lógico de la red. No se generarán subredes, gateways ni tablas de enrutamiento de forma automática, permitiendo una construcción manual y personalizada de cada componente.

> [!quote] Etiqueta de nombre
> **VPC-Jesus**: Es el identificador asignado al recurso mediante etiquetas (Tags). Este nombre permite organizar y filtrar la red dentro del panel de administración de AWS.

> [!settings] Bloque de CIDR IPv4
> **Entrada manual**: Permite definir específicamente el rango de direcciones IP privadas que tendrá la red.
> **10.0.0.0/24**: Este valor determina el tamaño de la red.
> **Observación**: Un bloque /24 permite un total de 256 direcciones IP. AWS reserva siempre 5 direcciones para gestión interna, dejando 251 disponibles. Si se planea seguir fielmente el diagrama de arquitectura con múltiples subredes, un bloque /16 (65,536 direcciones) ofrecería mayor flexibilidad para la segmentación.

> [!attention] Bloque de CIDR IPv6
> **Sin bloque de CIDR IPv6**: Se ha optado por no asignar direccionamiento IPv6. En entornos de infraestructura como servicio (IaaS) destinados a pruebas, trabajar exclusivamente con IPv4 simplifica la configuración de las reglas de filtrado de los Security Groups.

> [!info] Tenencia
> **Predeterminado**: Indica que la VPC y las instancias que se lancen en ella se ejecutarán sobre hardware compartido con otros usuarios de AWS. Es la opción estándar y de menor costo.

> [!check] Control de cifrado de VPC
> **Ninguno**: No se aplica una capa de cifrado de red adicional gestionada por AWS para el tráfico entre instancias. Esto evita costos operativos y de procesamiento innecesarios para un entorno de laboratorio.
