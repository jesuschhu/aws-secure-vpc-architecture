# Arquitectura de Red Segura en AWS

## Contexto del Proyecto
Este proyecto consiste en el diseño e implementación de una infraestructura de red empresarial dentro de Amazon Web Services (AWS). El despliegue se centra en la creación de una Virtual Private Cloud (VPC) estructurada en tres capas, permitiendo una separación lógica y física entre los puntos de entrada públicos y los recursos críticos de procesamiento de datos.

La necesidad surge de la arquitectura de aplicaciones web modernas, donde exponer directamente un servidor de aplicaciones a internet representa un riesgo de seguridad elevado. Mediante esta segmentación, se establece un perímetro controlado donde solo los servidores proxy autorizados pueden comunicarse con la capa interna de la aplicación.

## Justificación y Beneficios
La implementación de esta arquitectura responde a los siguientes criterios técnicos:

* **Reducción de la superficie de ataque**: Al ubicar el servidor de aplicaciones en una subred privada, se eliminan los vectores de ataque directos desde el exterior, ya que el recurso carece de una dirección IP pública.
* **Control de tráfico de salida**: El uso de un NAT Gateway permite que los recursos internos realicen peticiones hacia internet (como actualizaciones de seguridad) sin permitir que actores externos inicien conexiones no solicitadas hacia la red privada.
* **Seguridad basada en identidad**: El filtrado de red se gestiona a través de Security Groups que referencian otros grupos de seguridad en lugar de direcciones IP estáticas. Esto permite una red dinámica y escalable donde la confianza se basa en el rol del recurso y no en su ubicación lógica.
* **Administración segura**: El acceso a la infraestructura para tareas de mantenimiento se realiza mediante métodos que no exponen puertos críticos al tráfico global, utilizando un host bastión o servicios de gestión nativos de AWS.

## Diagrama de Arquitectura
El siguiente esquema detalla el flujo de datos, la segmentación de subredes y la ubicación de los componentes de red dentro de la VPC.

![Arquitectura de Red](./assets/diagrama-arquitectura.png)
