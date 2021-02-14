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
description: En este artículo, aprenderá sobre Azure ExpressRoute para Office 365 y cómo utilizarlo para planear la red.
ms.openlocfilehash: 7159640adeae1b4a4ff364683f939a97b6e06a92
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693940"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Plan de red con ExpressRoute para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

ExpressRoute para Office 365 proporciona conectividad de nivel 3 entre la red y los centros de datos de Microsoft. Los circuitos usan los anuncios de ruta del Protocolo de puerta de enlace de borde (BGP) de los servidores front-end de Office 365. Desde la perspectiva de los dispositivos locales, cuando necesitan seleccionar la ruta tcp/IP correcta a Office 365, Azure ExpressRoute se ve como una alternativa a Internet.
  
Azure ExpressRoute agrega una ruta de acceso directa a un conjunto específico de características y servicios admitidos que ofrecen los servidores de Office 365 dentro de los centros de datos de Microsoft. Azure ExpressRoute no reemplaza la conectividad a Internet a centros de datos de Microsoft ni servicios básicos de Internet, como la resolución de nombres de dominio. Azure ExpressRoute y sus circuitos de Internet deben ser seguros y redundantes.
  
En la tabla siguiente se destacan algunas diferencias entre las conexiones de Internet y Azure ExpressRoute en el contexto de Office 365.

|**Diferencias en la planeación de la red**|**Conexión de red a Internet**|**Conexión de red de ExpressRoute**|
|:-----|:-----|:-----|
| Acceso a los servicios de Internet necesarios, incluidos;  <br/>  Resolución de nombres DNS  <br/>  Comprobación de revocación de certificados  <br/>  Redes de entrega de contenido (CDN)  <br/> |Sí  <br/> |Las solicitudes a la infraestructura de DNS y/o red CDN propiedad de Microsoft pueden usar la red de ExpressRoute.  <br/> |
| Acceso a los servicios de Office 365, incluidos;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype Empresarial Online  <br/>  Office en un explorador  <br/>  Autenticación y portal de Office 365  <br/> |Sí, todas las aplicaciones y características  <br/> |Sí, [aplicaciones y características específicas](https://aka.ms/o365endpoints) <br/> |
|Seguridad local en el perímetro.  <br/> |Sí  <br/> |Sí  <br/> |
|Planeación de alta disponibilidad.  <br/> |Conmutación por error a una conexión de red de Internet alternativa  <br/> |Conmutación por error a una conexión de ExpressRoute alternativa  <br/> |
|Conexión directa con un perfil de red predecible.  <br/> |No  <br/> |Sí  <br/> |
|Conectividad IPv6.  <br/> |Sí  <br/> |Sí  <br/> |

Expanda los títulos siguientes para obtener más instrucciones de planeación de red. También hemos grabado una serie de Aprendizaje de Azure ExpressRoute para [Office 365](https://channel9.msdn.com/series/aer) de 10 partes que se profundizará.

## <a name="existing-azure-expressroute-customers"></a>Clientes existentes de Azure ExpressRoute

Si usa un circuito existente de Azure ExpressRoute y desea agregar conectividad de Office 365 a través de este circuito, debe ver el número de circuitos, las ubicaciones de salida y el tamaño de los circuitos para asegurarse de que satisfacen las necesidades de su uso de Office 365. La mayoría de los clientes requieren ancho de banda adicional y muchos requieren circuitos adicionales.
  
Para habilitar el acceso a Office 365 a través de los circuitos existentes de Azure ExpressRoute, [configure](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) los filtros de ruta para garantizar que los servicios de Office 365 sean accesibles.
  
La suscripción de Azure ExpressRoute está centrada en el cliente, lo que significa que las suscripciones están vinculadas a los clientes. Como cliente, puede tener varios circuitos de Azure ExpressRoute y acceder a muchos recursos de nube de Microsoft a través de esos circuitos. Por ejemplo, puede elegir tener acceso a una máquina virtual hospedada en Azure, un inquilino de prueba de Office 365 y un inquilino de producción de Office 365 a través de un par de circuitos redundantes de Azure ExpressRoute.
  
En esta tabla se describen los dos tipos de relaciones de emparejamiento que puede elegir implementar en los circuitos.

|**Relación de emparejamiento**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**Servicios** <br/> |IaaS: Máquinas virtuales de Azure  <br/> |PaaS: servicios públicos de Azure  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Inicio de conexión**** <br/> |Cliente a Microsoft  <br/> De Microsoft a cliente  <br/> |Cliente a Microsoft  <br/> De Microsoft a cliente  <br/> |
|**Compatibilidad con QoS** <br/> |Sin QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> QoS solo admite Skype Empresarial en este momento.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Planeación del ancho de banda para Azure ExpressRoute

Cada cliente de Office 365 tiene necesidades de ancho de banda únicas según el número de personas en cada ubicación, su actividad con cada aplicación de Office 365 y otros factores, como el uso de equipos locales o híbridos y configuraciones de seguridad de red.
  
Tener demasiado ancho de banda provocará congestión, retransmisiones de datos y retrasos impredecibles. Tener demasiado ancho de banda dará como resultado un costo innecesario. En una red existente, a menudo se hace referencia al ancho de banda en términos de la cantidad de espacio disponible en el circuito como un porcentaje. Tener un 10 % de espacio para la cabeza probablemente provocará congestión y tener un 80 % de espacio en la cabeza generalmente significa un costo innecesario. Las asignaciones de destino típicas son del 20 % al 50 %.
  
Para encontrar el nivel correcto de ancho de banda, el mejor mecanismo es probar el consumo de red existente. Esta es la única forma de obtener una verdadera medida de uso y necesidad, ya que cada configuración de red y aplicaciones son de alguna manera únicas. Al medir, querrá prestar especial atención al consumo total de ancho de banda, la latencia y la congestión tcp para comprender sus necesidades de red.
  
Una vez que tenga una línea base estimada que incluya todas las aplicaciones de red, pilote Office 365 con un pequeño grupo que incluya los diferentes perfiles de personas de su organización para determinar el uso real y use las dos medidas para calcular la cantidad de ancho de banda que necesitará para cada ubicación de la oficina. Si se han encontrado problemas de latencia o congestión tcp en las pruebas, es posible que tenga que acercar la salida a las personas que usan Office 365 o quitar el análisis intensivo de la red, como el descifrado o la inspección de SSL.
  
Todas nuestras recomendaciones sobre el tipo de procesamiento de red que se recomienda se aplica tanto a ExpressRoute como a los circuitos de Internet. Lo mismo sucede con el resto de las instrucciones de nuestro sitio de ajuste [de rendimiento.](https://aka.ms/tune)
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Aplicar controles de seguridad a Azure ExpressRoute para escenarios de Office 365

La protección de la conectividad de Azure ExpressRoute empieza por los mismos principios que la protección de la conectividad a Internet. Muchos clientes eligen implementar controles perimetrales y de red a lo largo de la ruta de Acceso de ExpressRoute que conectan su red local con Office 365 y otras nubes de Microsoft. Estos controles pueden incluir firewalls, servidores proxy de aplicaciones, prevención de fuga de datos, detección de intrusiones, sistemas de prevención de intrusiones, entre otros. En muchos casos, los clientes aplican distintos niveles de controles al tráfico iniciado desde un entorno local que va a Microsoft, en comparación con el tráfico iniciado desde Microsoft que va a la red local del cliente, frente al tráfico iniciado desde un entorno local que va a un destino general de Internet.
  
Estos son algunos ejemplos de integración de la seguridad con el modelo de conectividad de [ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-connectivity-models) que elija implementar.

|**Opción de integración de ExpressRoute**|**Modelo perimetral de seguridad de red**|
|:-----|:-----|
|Colocalizado en un intercambio de nube  <br/> |Instale una infraestructura de seguridad o perímetro nueva o aproveche la existente en la instalación de ubicación en la que se establece la conexión de ExpressRoute.  <br/> Aprovechar las instalaciones de ubicación en co-ubicación exclusivamente para fines de enrutamiento e interconexión y conexiones de reencargador desde la instalación de ubicación en la infraestructura de seguridad/perímetro local.  <br/> |
|Ethernet de punto a punto  <br/> |Finalice la conexión de ExpressRoute de punto a punto en la ubicación existente de la infraestructura perimetral o de seguridad local.  <br/> Instale una nueva infraestructura de seguridad/perímetro específica de la ruta de Acceso de ExpressRoute y finalice allí la conexión punto a punto.  <br/> |
|IPVPN de cualquiera a cualquiera  <br/> |Aproveche una infraestructura perimetral o de seguridad local existente en todas las ubicaciones que se desenlace en el IPVPN usado para la conectividad de ExpressRoute para Office 365.  <br/> Redirir el IPVPN usado para ExpressRoute para Office 365 a ubicaciones locales específicas designadas para servir como seguridad/perímetro.  <br/> |

Algunos proveedores de servicios también ofrecen funcionalidad de seguridad administrada/perímetro como parte de sus soluciones de integración con Azure ExpressRoute.
  
Al considerar la ubicación de la topología de las opciones de perímetro de red/seguridad usadas para ExpressRoute para conexiones de Office 365, a continuación se den otras consideraciones.
  
- Los controles de profundidad y tipo de red/seguridad pueden tener un impacto en el rendimiento y la escalabilidad de la experiencia de usuario de Office 365.

- Los flujos salientes (locales- \> Microsoft) y entrantes (Microsoft- \> local) [si están habilitados] pueden tener requisitos diferentes. Es probable que sean distintos de los destinos salientes a los destinos generales de Internet.

- Los requisitos de Office 365 para puertos/protocolos y subredes IP necesarias son los mismos si el tráfico se enruta a través de ExpressRoute para Office 365 o a través de Internet.

- La colocación superior de los controles de seguridad y red del cliente determina el extremo final de la red entre el usuario y el servicio de Office 365 y puede tener un impacto considerable en la latencia y congestión de la red.

- Se recomienda a los clientes diseñar su topología de seguridad/perímetro para su uso con ExpressRoute para Office 365 de acuerdo con los procedimientos recomendados para redundancia, alta disponibilidad y recuperación ante desastres.

Este es un ejemplo de Woodgrove Bank que compara las diferentes opciones de conectividad de Azure ExpressRoute con los modelos de seguridad perimetral descritos anteriormente.
  
### <a name="example-1-securing-azure-expressroute"></a>Ejemplo 1: Proteger Azure ExpressRoute
  
Woodgrove Bank está considerando implementar Azure ExpressRoute y después de planear la arquitectura óptima para el enrutamiento con ExpressRoute para [Office 365](routing-with-expressroute.md) y después de usar las instrucciones anteriores para comprender los requisitos de ancho de banda, están determinando el mejor método para proteger su perímetro.
  
Para Woodgrove, una organización nacional con ubicaciones en varios continentes, la seguridad debe abarcar todos los perímetros. La opción de conectividad óptima para Woodgrove es una conexión de varios puntos con varias ubicaciones de emparejamiento en todo el mundo para satisfacer las necesidades de sus empleados en cada continente. Cada continente incluye circuitos redundantes de Azure ExpressRoute dentro del continente y la seguridad debe abarcar todos ellos.
  
La infraestructura existente de Woodgrove es confiable y puede gestionar el trabajo adicional, como resultado, Woodgrove Bank puede usar la infraestructura para su Azure ExpressRoute y la seguridad perimetral de Internet. Si este no fuera el caso, Woodgrove podría elegir comprar equipos adicionales para complementar su equipo existente o para controlar un tipo diferente de conexión.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Alta disponibilidad y conmutación por error con Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Se recomienda aprovisionar al menos dos circuitos activos de cada salida con ExpressRoute al proveedor de ExpressRoute. Este es el lugar más común donde vemos errores para los clientes y puede evitarlo fácilmente aprovisionando un par de circuitos de ExpressRoute activos/activos. También se recomiendan al menos dos circuitos de Internet activos/activos porque muchos servicios de Office 365 solo están disponibles a través de Internet.
  
Dentro del punto de salida de la red hay muchos otros dispositivos y circuitos que desempeñan un papel fundamental en la percepción de la disponibilidad por parte de los usuarios. Estas partes de los escenarios de conectividad no están cubiertas por Los CONTRATOs de nivel de servicio de ExpressRoute u Office 365, pero desempeñan un papel fundamental al final de la disponibilidad del servicio tal como la perciben los usuarios de su organización.
  
Céntrate en las personas que usan y usan Office 365, si un error de un componente afectaría a la experiencia de los usuarios que usan el servicio, busca formas de limitar el porcentaje total de personas afectadas. Si un modo de conmutación por error es operativamente complejo, tenga en cuenta la experiencia de los usuarios de mucho tiempo de recuperación y busque modos de conmutación por error sencillos y automatizados desde el punto de vista operativo.
  
Fuera de la red, Office 365, ExpressRoute y su proveedor de ExpressRoute tienen diferentes niveles de disponibilidad.
  
### <a name="service-availability"></a>Disponibilidad del servicio
  
- Los servicios de Office 365 [](https://technet.microsoft.com/library/office-365-service-level-agreement.aspx)están cubiertos por contratos de nivel de servicio bien definidos, que incluyen métricas de tiempo de actividad y disponibilidad para servicios individuales. Una razón por la que Office 365 puede mantener niveles de disponibilidad de servicio tan altos es la capacidad de los componentes individuales de conmutar por error sin problemas entre los distintos centros de datos de Microsoft, mediante la red global de Microsoft. Esta conmutación por error se extiende desde el centro de datos y la red hasta varios puntos de salida de Internet, y permite la conmutación por error sin problemas desde la perspectiva de las personas que usan el servicio.

- ExpressRoute proporciona un SLA de disponibilidad del [99,9 %](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) en circuitos dedicados individuales entre Microsoft Network Edge y la infraestructura del proveedor o socio de ExpressRoute. Estos niveles de servicio se aplican en el [](https://azure.microsoft.com/documentation/articles/expressroute-introduction/) nivel de circuito de ExpressRoute, que consta de dos interconexiones independientes entre el equipo redundante de Microsoft y el equipo del proveedor de red en cada ubicación de emparejamiento.

### <a name="provider-availability"></a>Disponibilidad del proveedor
  
- Las disposiciones de nivel de servicio de Microsoft se detienen en el proveedor o partner de ExpressRoute. Este también es el primer lugar en el que puede tomar decisiones que influirán en el nivel de disponibilidad. Debe evaluar estrechamente las características de arquitectura, disponibilidad y resistencia que el proveedor de ExpressRoute ofrece entre el perímetro de red y la conexión de proveedores en cada ubicación de emparejamiento de Microsoft. Preste especial atención a los aspectos lógicos y físicos de la redundancia, el equipo de emparejamiento, los circuitos WAN proporcionados por el operador y cualquier valor adicional que agregue servicios como servicios NAT o firewalls administrados.

### <a name="designing-your-availability-plan"></a>Diseño del plan de disponibilidad
  
Le recomendamos encarecidamente que planee y diseñe alta disponibilidad y resistencia en los escenarios de conectividad de un extremo a otro para Office 365. Un diseño debe incluir;
  
- ningún punto único de error, incluidos los circuitos de Internet y ExpressRoute.

- minimizar el número de personas afectadas y la duración de ese impacto para los modos de error más esperados.

- optimización para un proceso de recuperación simple, repetible y automático de la mayoría de los modos de error previstos.

- admitir todas las demandas del tráfico de red y la funcionalidad a través de rutas redundantes, sin una degradación considerable.

Los escenarios de conectividad deben incluir una topología de red optimizada para varias rutas de red independientes y activas a Office 365. Esto dará una mejor disponibilidad de un extremo a otro que una topología optimizada solo para redundancia en el nivel de dispositivo o equipo individual.
  
> [!TIP]
> Si los usuarios se distribuyen en varios continentes o regiones geográficas y cada una de estas ubicaciones se conecta a través de circuitos WAN redundantes a una única ubicación local donde se encuentra un único circuito de ExpressRoute, los usuarios experimentarán menos disponibilidad de servicio de un extremo a otro que un diseño de topología de red que incluya circuitos independientes de ExpressRoute que conecten las distintas regiones a la ubicación de emparejamiento más cercana.
  
Se recomienda aprovisionar al menos dos circuitos de ExpressRoute con cada circuito que se conecte con una ubicación de emparejamiento geográfica diferente. Debe aprovisionar este par activo-activo de circuitos para cada región donde los usuarios usarán la conectividad de ExpressRoute para los servicios de Office 365. Esto permite que cada región permanezca conectada durante un desastre que afecta a una ubicación principal, como un centro de datos o una ubicación de emparejamiento. Configurarlos como activos/activos permite que el tráfico del usuario final se distribuye en varias rutas de red. Esto reduce el ámbito de las personas afectadas durante las interrupciones del dispositivo o del equipo de red.
  
No se recomienda usar un solo circuito de ExpressRoute con Internet como copia de seguridad.
  
### <a name="example-2-failover-and-high-availability"></a>Ejemplo 2: Conmutación por error y alta disponibilidad
  
El diseño multi-geográfico de Woodgrove Bank se ha sometido a una revisión de enrutamiento, ancho de banda, seguridad y ahora debe pasar por una revisión de alta disponibilidad. Woodgrove piensa que la alta disponibilidad abarca tres categorías; resistencia, confiabilidad y redundancia.
  
La resistencia permite a Woodgrove recuperarse rápidamente de errores. La confiabilidad permite a Woodgrove ofrecer un resultado coherente dentro del sistema. La redundancia permite a Woodgrove desplazarse entre una o más instancias reflejadas de infraestructura.
  
Dentro de cada configuración perimetral, Woodgrove tiene firewalls redundantes, servidores proxy e IDS. Para Norteamérica, Woodgrove tiene una configuración perimetral en su centro de datos de Dallas y otra configuración perimetral en su centro de datos de Dallas. El equipo redundante de cada ubicación ofrece resistencia a esa ubicación.
  
La configuración de red de Woodgrove Bank se basa en algunos principios clave:
  
- Dentro de cada región geográfica, hay varios circuitos de Azure ExpressRoute.

- Cada circuito dentro de una región puede admitir todo el tráfico de red dentro de esa región.

- El enrutamiento prefiere claramente una u otra ruta según la disponibilidad, la ubicación, entre otras.

- La conmutación por error entre circuitos de Azure ExpressRoute se produce automáticamente sin que Woodgrove requiera ninguna acción o configuración adicional.

- La conmutación por error entre circuitos de Internet se produce automáticamente sin que Woodgrove requiera ninguna acción o configuración adicional.

En esta configuración, con redundancia a nivel físico y virtual, Woodgrove Bank es capaz de ofrecer resistencia local, resistencia regional y resistencia global de una forma confiable. Woodgrove eligió esta configuración después de evaluar un único circuito de Azure ExpressRoute por región, así como la posibilidad de realizar una con error en Internet.
  
Si Woodgrove no pudo tener varios circuitos de Azure ExpressRoute por región, el tráfico de enrutamiento que se origina en Norteamérica al circuito de Azure ExpressRoute en Asia Pacífico agregaría un nivel de latencia inaceptable y la configuración de reenviador DNS necesaria agrega complejidad.
  
No se recomienda usar Internet como configuración de copia de seguridad. Esto rompe el principio de confiabilidad de Woodgrove, lo que resulta en una experiencia incoherente al usar la conexión. Además, la configuración manual sería necesaria para la conmutación por error teniendo en cuenta los anuncios BGP que se han configurado, la configuración NAT, la configuración DNS y la configuración de proxy. Esta complejidad de conmutación por error agregada aumenta el tiempo de recuperación y disminuye su capacidad para diagnosticar y solucionar los pasos necesarios.
  
¿Aún tiene preguntas sobre cómo planear e implementar la administración de tráfico o Azure ExpressRoute? Lea el resto de nuestras instrucciones [de red y rendimiento](https://aka.ms/tune) o las preguntas más frecuentes sobre Azure [ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-faqs/)
  
## <a name="working-with-azure-expressroute-providers"></a>Trabajar con proveedores de Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Elija las ubicaciones de los circuitos según el ancho de banda, la latencia, la seguridad y la planeación de alta disponibilidad. Una vez que conozca las ubicaciones óptimas que le gustaría colocar circuitos, revise la lista [actual de proveedores por región.](https://azure.microsoft.com/documentation/articles/expressroute-locations/)
  
Trabaje con su proveedor o proveedores para seleccionar las mejores opciones de conectividad, punto a punto, varios puntos u hospedado. Recuerde que puede mezclar y hacer coincidir las opciones de conectividad siempre que el ancho de banda y otros componentes redundantes admitan el enrutamiento y el diseño de alta disponibilidad.
  
Este es un vínculo breve que se puede usar para volver: [https://aka.ms/planningexpressroute365](https://aka.ms/planningexpressroute365)
  
## <a name="related-topics"></a>Temas relacionados
<a name="BKMK_high-availability"> </a>

[Evaluar la conectividad de red de Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)
  
[Enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md)
  
[Implementación de ExpressRoute para Office 365](implementing-expressroute.md)
  
[Uso de comunidades de BGP en ExpressRoute para escenarios de Office 365](bgp-communities-in-expressroute.md)
  
[Calidad de medios y rendimiento de conectividad de red en Skype Empresarial Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimización de la red para Skype Empresarial Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute y calidad del servicio en Skype Empresarial Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flujo de llamadas con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)
  
[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)
  
[Direcciones URL e intervalos de direcciones IP de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Red de Office 365 y ajuste de rendimiento](network-planning-and-performance.md)
  
[Preguntas frecuentes sobre extremos de Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
