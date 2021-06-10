---
title: Plan de red con ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: En este artículo, aprenderá sobre Azure ExpressRoute para Office 365 y cómo utilizarlo para la planeación de red.
ms.openlocfilehash: 440d4fafadd7e9b504dc4ffdac1123a2956ed798
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923581"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Plan de red con ExpressRoute para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

ExpressRoute para Office 365 proporciona conectividad de nivel 3 entre la red y los centros de datos de Microsoft. Los circuitos usan anuncios de ruta del Protocolo de puerta de enlace de borde (BGP) de Office 365 servidores front-end. Desde la perspectiva de los dispositivos locales, cuando necesitan seleccionar la ruta de acceso TCP/IP correcta a Office 365, Azure ExpressRoute se ve como una alternativa a Internet.
  
Azure ExpressRoute agrega una ruta de acceso directa a un conjunto específico de características y servicios compatibles que ofrecen los servidores Office 365 los centros de datos de Microsoft. Azure ExpressRoute no reemplaza la conectividad a Internet a centros de datos de Microsoft ni a servicios básicos de Internet, como la resolución de nombres de dominio. Azure ExpressRoute y sus circuitos de Internet deben estar protegidos y redundantes.
  
En la tabla siguiente se destacan algunas diferencias entre las conexiones de Internet y Azure ExpressRoute en el contexto de Office 365.

|**Diferencias en la planeación de red**|**Conexión de red de Internet**|**Conexión de red de ExpressRoute**|
|:-----|:-----|:-----|
| Acceso a los servicios de Internet requeridos, incluidos;  <br/>  Resolución de nombres DNS  <br/>  Comprobación de revocación de certificados  <br/>  Redes de entrega de contenido (CDN)  <br/> |Sí  <br/> |Las solicitudes a DNS o infraestructura CDN propiedad de Microsoft pueden usar la red de ExpressRoute.  <br/> |
| Acceso a Office 365 servicios, incluidos;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype Empresarial Online  <br/>  Office en un explorador  <br/>  Office 365 Portal y autenticación  <br/> |Sí, todas las aplicaciones y características  <br/> |Sí, [aplicaciones y características específicas](./urls-and-ip-address-ranges.md) <br/> |
|Seguridad local en el perímetro.  <br/> |Sí  <br/> |Sí  <br/> |
|Planeación de alta disponibilidad.  <br/> |Conmutación por error a una conexión de red de Internet alternativa  <br/> |Conmutación por error a una conexión alternativa de ExpressRoute  <br/> |
|Conexión directa con un perfil de red predecible.  <br/> |No  <br/> |Sí  <br/> |
|Conectividad IPv6.  <br/> |Sí  <br/> |Sí  <br/> |

Expanda los títulos siguientes para obtener más instrucciones de planeación de red. También hemos registrado una serie de Azure [ExpressRoute](https://channel9.msdn.com/series/aer) de 10 partes para Office 365 training que se adentra más en profundidad.

## <a name="existing-azure-expressroute-customers"></a>Clientes existentes de Azure ExpressRoute

Si usa un circuito existente de Azure ExpressRoute y desea agregar conectividad Office 365 este circuito, debe ver el número de circuitos, las ubicaciones de salida y el tamaño de los circuitos para asegurarse de que satisfagan las necesidades de su uso de Office 365. La mayoría de los clientes requieren ancho de banda adicional y muchos requieren circuitos adicionales.
  
Para habilitar el acceso Office 365 los circuitos existentes de Azure ExpressRoute, [configure](/azure/expressroute/how-to-routefilter-portal) los filtros de ruta para garantizar que los Office 365 acceso a los servicios.
  
La suscripción de Azure ExpressRoute está centrada en el cliente, lo que significa que las suscripciones están vinculadas a los clientes. Como cliente, puede tener varios circuitos de Azure ExpressRoute y tener acceso a muchos recursos de nube de Microsoft a través de esos circuitos. Por ejemplo, puede elegir tener acceso a una máquina virtual hospedada en Azure, un inquilino de prueba de Office 365 y un inquilino de producción de Office 365 a través de un par de circuitos redundantes de Azure ExpressRoute.
  
En esta tabla se describen los dos tipos de relaciones de emparejamiento que puede implementar en los circuitos.

|**Relación de emparejamiento**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**Servicios** <br/> |IaaS: Máquinas virtuales de Azure  <br/> |PaaS: Servicios públicos de Azure  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Inicio de conexión**** <br/> |Cliente a Microsoft  <br/> Microsoft a cliente  <br/> |Cliente a Microsoft  <br/> Microsoft a cliente  <br/> |
|**Compatibilidad con QoS** <br/> |Sin QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1</sup> QoS admite Skype Empresarial solo en este momento.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Planeación de ancho de banda para Azure ExpressRoute

Cada cliente Office 365 tiene necesidades de ancho de banda únicas según el número de personas en cada ubicación, su actividad con cada aplicación Office 365 y otros factores, como el uso de equipos locales o híbridos y configuraciones de seguridad de red.
  
Tener demasiado ancho de banda provocará congestión, retransmisiones de datos y retrasos impredecibles. Tener demasiado ancho de banda dará como resultado un costo innecesario. En una red existente, a menudo se hace referencia al ancho de banda en términos de la cantidad de espacio disponible en el circuito como un porcentaje. Tener un 10 % de espacio en la cabeza probablemente provocará congestión y tener un 80 % de espacio en la cabeza generalmente significa un costo innecesario. Las asignaciones de destino de espacio principal típicas son del 20% al 50 %.
  
Para encontrar el nivel correcto de ancho de banda, el mejor mecanismo es probar el consumo de red existente. Esta es la única forma de obtener una verdadera medida de uso y necesidad, ya que todas las aplicaciones y la configuración de red son de alguna manera únicas. Al medir, querrá prestar mucha atención al consumo total de ancho de banda, la latencia y la congestión tcp para comprender las necesidades de la red.
  
Una vez que tenga una línea base estimada que incluya todas las aplicaciones de red, Office 365 piloto con un grupo pequeño que comprende los diferentes perfiles de personas de su organización para determinar el uso real y use las dos medidas para calcular la cantidad de ancho de banda que necesitará para cada ubicación de oficina. Si se encuentra algún problema de latencia o congestión TCP en las pruebas, es posible que deba acercar la salida a las personas que usan Office 365 o quitar el examen intensivo de red, como descifrado/inspección SSL.
  
Todas nuestras recomendaciones sobre el tipo de procesamiento de red que se recomienda se aplica tanto a ExpressRoute como a los circuitos de Internet. Lo mismo sucede con el resto de las instrucciones de nuestro sitio de optimización [de rendimiento.](./network-planning-and-performance.md)
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Aplicar controles de seguridad a Azure ExpressRoute para Office 365 escenarios

Proteger la conectividad de Azure ExpressRoute comienza por los mismos principios que proteger la conectividad a Internet. Muchos clientes eligen implementar controles de red y perímetro a lo largo de la ruta de acceso de ExpressRoute que conecta su red local a Office 365 y otras nubes de Microsoft. Estos controles pueden incluir firewalls, servidores proxy de aplicaciones, prevención de pérdida de datos, detección de intrusiones, sistemas de prevención de intrusiones, entre otros. En muchos casos, los clientes aplican distintos niveles de controles al tráfico iniciado desde la instalación local que va a Microsoft, frente al tráfico iniciado desde Microsoft que va a la red local del cliente, frente al tráfico iniciado desde local que va a un destino general de Internet.
  
Estos son algunos ejemplos de integración de la seguridad con el modelo de conectividad de [ExpressRoute](/azure/expressroute/expressroute-connectivity-models) que elija implementar.

|**Opción de integración de ExpressRoute**|**Modelo perimetral de seguridad de red**|
|:-----|:-----|
|Colocalizado en un intercambio de nube  <br/> |Instale una nueva infraestructura perimetral o de seguridad existente en la instalación de ubicación en la que se establece la conexión de ExpressRoute.  <br/> Aproveche las instalaciones de co-ubicación exclusivamente para el enrutamiento e interconexión y las conexiones de transporte posterior de la instalación de ubicación en la infraestructura perimetral/de seguridad local.  <br/> |
|Ethernet punto a punto  <br/> |Finalice la conexión de ExpressRoute de punto a punto en la ubicación de la infraestructura perimetral o de seguridad local existente.  <br/> Instale una nueva infraestructura de seguridad/perímetro específica de la ruta de acceso de ExpressRoute y finalice allí la conexión punto a punto.  <br/> |
|IPVPN de cualquier a cualquier  <br/> |Aproveche una infraestructura perimetral o de seguridad local existente en todas las ubicaciones que se desenvía al IPVPN usado para ExpressRoute para Office 365 conectividad.  <br/> Apile el IPVPN usado para ExpressRoute para Office 365 a ubicaciones locales específicas designadas para servir como seguridad/perímetro.  <br/> |

Algunos proveedores de servicios también ofrecen funcionalidad de seguridad administrada/perímetro como parte de sus soluciones de integración con Azure ExpressRoute.
  
Al considerar la ubicación de topología de las opciones perimetrales de red y seguridad que se usan para ExpressRoute para las conexiones Office 365, a continuación se desenvía otras consideraciones
  
- Los controles de profundidad y tipo red/seguridad pueden tener un impacto en el rendimiento y la escalabilidad de la Office 365 usuario.

- Los flujos salientes (locales- \> Microsoft) y entrantes (Microsoft- local) [si están habilitados] pueden \> tener requisitos diferentes. Es probable que sean diferentes de los destinos de Salida a Internet generales.

- Office 365 requisitos de puertos/protocolos y subredes IP necesarias son los mismos si el tráfico se enruta a través de ExpressRoute para Office 365 o a través de Internet.

- La colocación topológica de los controles de seguridad y red del cliente determina el final de la red de extremo a extremo entre el usuario y el servicio Office 365 y puede tener un impacto importante en la latencia y la congestión de la red.

- Se recomienda a los clientes que diseñen su topología de seguridad/perímetro para su uso con ExpressRoute para Office 365 de acuerdo con los procedimientos recomendados para redundancia, alta disponibilidad y recuperación ante desastres.

Este es un ejemplo de Woodgrove Bank que compara las diferentes opciones de conectividad de Azure ExpressRoute con los modelos de seguridad perimetral mencionados anteriormente.
  
### <a name="example-1-securing-azure-expressroute"></a>Ejemplo 1: Proteger Azure ExpressRoute
  
Woodgrove Bank está considerando implementar Azure ExpressRoute y después de planear la arquitectura óptima para enrutamiento con [ExpressRoute](routing-with-expressroute.md) para Office 365 y después de usar las instrucciones anteriores para comprender los requisitos de ancho de banda, están determinando el mejor método para proteger su perímetro.
  
Para Woodgrove, una organización multinacionales con ubicaciones en varios continentes, la seguridad debe abarcar todos los perímetros. La opción de conectividad óptima para Woodgrove es una conexión de varios puntos con varias ubicaciones de emparejamiento de todo el mundo para satisfacer las necesidades de sus empleados en cada continente. Cada continente incluye circuitos redundantes de Azure ExpressRoute dentro del continente y la seguridad debe abarcar todos estos.
  
La infraestructura existente de Woodgrove es confiable y puede administrar el trabajo adicional, por lo que Woodgrove Bank puede usar la infraestructura para su Azure ExpressRoute y la seguridad perimetral de Internet. Si no fuera así, Woodgrove podría optar por comprar equipamiento adicional para complementar su equipo existente o para controlar un tipo de conexión diferente.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Alta disponibilidad y conmutación por error con Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Se recomienda aprovisionar al menos dos circuitos activos de cada salida con ExpressRoute al proveedor de ExpressRoute. Este es el lugar más común en el que vemos errores para los clientes y puede evitarlo fácilmente aprovisionamiento de un par de circuitos de ExpressRoute activos y activos. También recomendamos al menos dos circuitos de Internet activos o activos, ya que muchos Office 365 solo están disponibles a través de Internet.
  
Dentro del punto de salida de la red hay muchos otros dispositivos y circuitos que desempeñan un papel fundamental en la forma en que las personas perciben la disponibilidad. Estas partes de los escenarios de conectividad no están cubiertas por los SLA de ExpressRoute o Office 365, pero desempeñan un papel fundamental en la disponibilidad del servicio de extremo a extremo como perciben los usuarios de su organización.
  
Céntrate en las personas que usan y operan Office 365, si un error de un componente afectaría a la experiencia de los usuarios con el servicio, busca formas de limitar el porcentaje total de personas afectadas. Si un modo de conmutación por error es operacionalmente complejo, tenga en cuenta la experiencia de los usuarios durante mucho tiempo para la recuperación y busque modos de conmutación por error simples y automatizados desde el punto de vista operativo.
  
Fuera de la red, Office 365, ExpressRoute y su proveedor de ExpressRoute tienen diferentes niveles de disponibilidad.
  
### <a name="service-availability"></a>Disponibilidad del servicio
  
- Office 365 servicios están cubiertos por [](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)acuerdos de nivel de servicio bien definidos, que incluyen métricas de disponibilidad y tiempo de actividad para servicios individuales. Una razón Office 365 mantener niveles de disponibilidad de servicio tan altos es la capacidad de los componentes individuales para conmutar sin problemas entre los muchos centros de datos de Microsoft, mediante la red global de Microsoft. Esta conmutación por error se extiende desde el centro de datos y la red hasta los múltiples puntos de salida de Internet y permite la conmutación por error sin problemas desde la perspectiva de las personas que usan el servicio.

- ExpressRoute proporciona un SLA de disponibilidad del [99,9 %](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) en circuitos dedicados individuales entre Microsoft Network Edge y la infraestructura del proveedor o partner de ExpressRoute. Estos niveles de servicio se aplican en el [](/azure/expressroute/expressroute-introduction) nivel de circuito de ExpressRoute, que consta de dos interconexiones independientes entre el equipamiento redundante de Microsoft y el equipamiento del proveedor de red en cada ubicación de emparejamiento.

### <a name="provider-availability"></a>Disponibilidad del proveedor
  
- Las disposiciones de nivel de servicio de Microsoft se detienen en el proveedor o partner de ExpressRoute. Este es también el primer lugar en el que puede tomar decisiones que influirán en su nivel de disponibilidad. Debe evaluar estrechamente las características de arquitectura, disponibilidad y resistencia que el proveedor de ExpressRoute ofrece entre el perímetro de red y la conexión de proveedores en cada ubicación de emparejamiento de Microsoft. Preste especial atención a los aspectos lógicos y físicos de la redundancia, el equipamiento de emparejamiento, los circuitos WAN proporcionados por el operador y los servicios de adición de valor adicional, como servicios NAT o firewalls administrados.

### <a name="designing-your-availability-plan"></a>Diseño del plan de disponibilidad
  
Le recomendamos encarecidamente que planee y diseñe alta disponibilidad y resistencia en los escenarios de conectividad de un extremo a otro para Office 365. Un diseño debe incluir;
  
- no hay puntos únicos de error, incluidos los circuitos de Internet y ExpressRoute.

- minimizar el número de personas afectadas y la duración de ese impacto para los modos de error más esperados.

- optimización para un proceso de recuperación simple, repetible y automático desde los modos de error más esperados.

- admitir todas las demandas del tráfico de red y la funcionalidad a través de rutas redundantes, sin una degradación sustancial.

Los escenarios de conectividad deben incluir una topología de red optimizada para varias rutas de red independientes y activas para Office 365. Esto dará una mejor disponibilidad de extremo a extremo que una topología optimizada solo para redundancia en el nivel de dispositivo o equipamiento individual.
  
> [!TIP]
> Si los usuarios se distribuyen en varios continentes o regiones geográficas y cada una de estas ubicaciones se conecta a través de circuitos WAN redundantes a una única ubicación local donde se encuentra un único circuito de ExpressRoute, los usuarios experimentarán menos disponibilidad de servicio end-to-end que un diseño de topología de red que incluye circuitos de ExpressRoute independientes que conectan las distintas regiones a la ubicación de emparejamiento más cercana.
  
Se recomienda aprovisionar al menos dos circuitos de ExpressRoute con cada circuito que se conecte con una ubicación de emparejamiento geográfica diferente. Debe aprovisionar este par de circuitos activo-activo para cada región en la que los usuarios usarán la conectividad de ExpressRoute para Office 365 servicios. Esto permite que cada región permanezca conectada durante un desastre que afecte a una ubicación principal, como un centro de datos o una ubicación de emparejamiento. Su configuración como activa o activa permite distribuir el tráfico del usuario final en varias rutas de red. Esto reduce el ámbito de las personas afectadas durante las interrupciones del equipo de red o dispositivo.
  
No se recomienda usar un solo circuito de ExpressRoute con Internet como copia de seguridad.
  
### <a name="example-2-failover-and-high-availability"></a>Ejemplo 2: Conmutación por error y alta disponibilidad
  
El diseño multi geográfico de Woodgrove Bank se ha sometido a una revisión de enrutamiento, ancho de banda, seguridad y ahora debe pasar por una revisión de alta disponibilidad. Woodgrove considera que la alta disponibilidad abarca tres categorías; resistencia, confiabilidad y redundancia.
  
La resistencia permite a Woodgrove recuperarse de errores rápidamente. La confiabilidad permite a Woodgrove ofrecer un resultado coherente dentro del sistema. La redundancia permite a Woodgrove desplazarse entre una o más instancias reflejadas de infraestructura.
  
Dentro de cada configuración perimetral, Woodgrove tiene firewalls redundantes, servidores proxy e IDS. Para Norteamérica, Woodgrove tiene una configuración perimetral en su centro de datos de Dallas y otra configuración perimetral en su centro de datos de Virginia. El equipo redundante en cada ubicación ofrece resistencia a esa ubicación.
  
La configuración de red en Woodgrove Bank se basa en algunos principios clave:
  
- Dentro de cada región geográfica, hay varios circuitos de Azure ExpressRoute.

- Cada circuito dentro de una región puede admitir todo el tráfico de red dentro de esa región.

- El enrutamiento claramente preferirá una u otra ruta de acceso según la disponibilidad, la ubicación, y así sucesivamente.

- La conmutación por error entre los circuitos de Azure ExpressRoute se produce automáticamente sin que Woodgrove requiera una configuración o una acción adicionales.

- La conmutación por error entre circuitos de Internet se produce automáticamente sin que Woodgrove requiera una configuración o una acción adicionales.

En esta configuración, con redundancia a nivel físico y virtual, Woodgrove Bank es capaz de ofrecer resistencia local, resistencia regional y resistencia global de una manera confiable. Woodgrove eligió esta configuración después de evaluar un único circuito de Azure ExpressRoute por región, así como la posibilidad de realizar una con error en Internet.
  
Si Woodgrove no pudo tener varios circuitos de Azure ExpressRoute por región, el enrutamiento del tráfico originado en Norteamérica al circuito de Azure ExpressRoute en Asia Pacífico agregaría un nivel de latencia inaceptable y la configuración del reenviador DNS requerido agregaría complejidad.
  
No se recomienda aprovechar Internet como configuración de copia de seguridad. Esto rompe el principio de confiabilidad de Woodgrove, lo que resulta en una experiencia incoherente mediante la conexión. Además, la configuración manual sería necesaria para la conmutación por error teniendo en cuenta los anuncios BGP que se han configurado, la configuración NAT, la configuración dns y la configuración de proxy. Esta complejidad de conmutación por error agregada aumenta el tiempo de recuperación y disminuye su capacidad para diagnosticar y solucionar los pasos implicados.
  
¿Todavía tiene preguntas sobre cómo planear e implementar la administración de tráfico o Azure ExpressRoute? Lea el resto de nuestras instrucciones de [red y rendimiento](./network-planning-and-performance.md) o las preguntas más frecuentes de Azure [ExpressRoute](/azure/expressroute/expressroute-faqs).
  
## <a name="working-with-azure-expressroute-providers"></a>Trabajar con proveedores de Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Elija las ubicaciones de los circuitos según el ancho de banda, la latencia, la seguridad y la planeación de alta disponibilidad. Una vez que sepa las ubicaciones óptimas que desea colocar los circuitos, revise la [lista actual de proveedores por región](/azure/expressroute/expressroute-locations).
  
Trabaje con su proveedor o proveedores para seleccionar las mejores opciones de conectividad, punto a punto, varios puntos o hospedados. Recuerde que puede combinar y coincidir con las opciones de conectividad siempre que el ancho de banda y otros componentes redundantes admitan el enrutamiento y el diseño de alta disponibilidad.
  
Este es un vínculo breve que se puede usar para volver: [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>Temas relacionados
<a name="BKMK_high-availability"> </a>

[Evaluar la conectividad de red de Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)
  
[Enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md)
  
[Implementación de ExpressRoute para Office 365](implementing-expressroute.md)
  
[Uso de comunidades BGP en ExpressRoute para Office 365 escenarios](bgp-communities-in-expressroute.md)
  
[Calidad de medios y rendimiento de conectividad de red en Skype Empresarial Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimización de la red para Skype Empresarial Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute y calidad del servicio en Skype Empresarial Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flujo de llamadas con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)
  
[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)
  
[Intervalos de direcciones IP y URL de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Red de Office 365 y ajuste de rendimiento](network-planning-and-performance.md)
  
[Preguntas frecuentes sobre extremos de Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)