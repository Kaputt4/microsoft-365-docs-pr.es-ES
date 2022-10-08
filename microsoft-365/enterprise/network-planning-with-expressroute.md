---
title: Plan de red con ExpressRoute para Office 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
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
description: En este artículo, obtendrá información sobre Azure ExpressRoute para Office 365 y cómo usarlo para el planeamiento de red.
ms.openlocfilehash: 9ec6626bb84645557373fbf15c183fac708e8237
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68189789"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Plan de red con ExpressRoute para Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

ExpressRoute para Office 365 proporciona conectividad de nivel 3 entre la red y los centros de datos de Microsoft. Los circuitos usan anuncios de ruta del Protocolo de puerta de enlace de borde (BGP) de los servidores front-end de Office 365. Desde la perspectiva de los dispositivos locales, cuando necesitan seleccionar la ruta de acceso TCP/IP correcta para Office 365, Azure ExpressRoute se ve como una alternativa a Internet.
  
Azure ExpressRoute agrega una ruta de acceso directa a un conjunto específico de características y servicios admitidos que ofrecen Office 365 servidores dentro de los centros de datos de Microsoft. Azure ExpressRoute no reemplaza la conectividad de Internet a los centros de datos de Microsoft ni a los servicios básicos de Internet, como la resolución de nombres de dominio. Azure ExpressRoute y los circuitos de Internet deben estar protegidos y redundantes.
  
En la tabla siguiente se resaltan algunas diferencias entre las conexiones de Internet y Azure ExpressRoute en el contexto de Office 365.

|**Diferencias en el planeamiento de red**|**Conexión de red a Internet**|**Conexión de red de ExpressRoute**|
|:-----|:-----|:-----|
| Acceso a los servicios de Internet necesarios, incluidos;  <br/>  Resolución de nombres DNS  <br/>  Comprobación de revocación de certificados  <br/>  Redes de entrega de contenido (CDN)  <br/> |Yes  <br/> |Las solicitudes a la infraestructura de DNS o CDN propiedad de Microsoft pueden usar la red ExpressRoute.  <br/> |
| Acceso a Office 365 servicios, incluidos;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype Empresarial Online  <br/>  Office en un explorador  <br/>  Office 365 Portal y autenticación  <br/> |Sí, todas las aplicaciones y características  <br/> |Sí, [aplicaciones y características específicas](./urls-and-ip-address-ranges.md) <br/> |
|Seguridad local en el perímetro.  <br/> |Sí  <br/> |Sí  <br/> |
|Planeamiento de alta disponibilidad.  <br/> |Conmutación por error a una conexión de red de Internet alternativa  <br/> |Conmutación por error a una conexión de ExpressRoute alternativa  <br/> |
|Conexión directa con un perfil de red predecible.  <br/> |No  <br/> |Sí  <br/> |
|Conectividad IPv6.  <br/> |Sí  <br/> |Sí  <br/> |

Expanda los títulos siguientes para obtener más instrucciones de planeamiento de red.

## <a name="existing-azure-expressroute-customers"></a>Clientes de Azure ExpressRoute existentes

Si usa un circuito ExpressRoute de Azure existente y desea agregar Office 365 conectividad a través de este circuito, debe examinar el número de circuitos, las ubicaciones de salida y el tamaño de los circuitos para asegurarse de que satisfacen las necesidades del uso de Office 365. La mayoría de los clientes requieren ancho de banda adicional y muchos requieren más circuitos.
  
Para habilitar el acceso a Office 365 a través de los circuitos de Azure ExpressRoute existentes, [configure los filtros de ruta](/azure/expressroute/how-to-routefilter-portal) para asegurarse de que los servicios de Office 365 sean accesibles.
  
La suscripción de Azure ExpressRoute está centrada en el cliente, lo que significa que las suscripciones están vinculadas a los clientes. Como cliente, puede tener varios circuitos ExpressRoute de Azure y acceder a muchos recursos en la nube de Microsoft a través de esos circuitos. Por ejemplo, puede optar por acceder a una máquina virtual hospedada de Azure, a un inquilino de prueba de Office 365 y a un inquilino de producción de Office 365 a través de un par de circuitos ExpressRoute de Azure redundantes.
  
En esta tabla se describen los dos tipos de relaciones de emparejamiento que puede elegir implementar en los circuitos.

|**Relación de emparejamiento**|**Privado de Azure**|**Microsoft**|
|:-----|:-----|:-----|
|**Servicios** <br/> |IaaS: Azure Virtual Machines  <br/> |PaaS: servicios públicos de Azure  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Iniciación de la conexión**** <br/> |Cliente a Microsoft  <br/> Microsoft al cliente  <br/> |Cliente a Microsoft  <br/> Microsoft al cliente  <br/> |
|**Compatibilidad con QoS** <br/> |Sin QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> QoS solo admite Skype Empresarial en este momento.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Planeamiento del ancho de banda para Azure ExpressRoute

Cada Office 365 cliente tiene necesidades de ancho de banda únicas en función del número de personas en cada ubicación, de su actividad con cada aplicación Office 365 y de otros factores, como el uso de equipos híbridos o locales y configuraciones de seguridad de red.
  
Tener demasiado poco ancho de banda provocará congestión, retransmisiones de datos y retrasos imprevisibles. Tener demasiado ancho de banda dará lugar a costos innecesarios. En una red existente, a menudo se hace referencia al ancho de banda en términos de la cantidad de espacio para la cabeza disponible en el circuito como un porcentaje. Tener un 10 % de espacio para la cabeza probablemente provocará congestión y tener un 80 % de espacio para la cabeza generalmente significa un costo innecesario. Las asignaciones de destino de espacio principal típicas son del 20 % al 50 %.
  
Para encontrar el nivel adecuado de ancho de banda, el mejor mecanismo es probar el consumo de red existente. Esta es la única manera de obtener una verdadera medida de uso y necesidad, ya que cada configuración de red y aplicaciones son de alguna manera únicas. Al medir, querrá prestar mucha atención al consumo total de ancho de banda, la latencia y la congestión TCP para comprender sus necesidades de red.
  
Una vez que tenga una línea base estimada que incluya todas las aplicaciones de red, Office 365 piloto con un grupo pequeño que consta de los distintos perfiles de personas de su organización para determinar el uso real y usar las dos medidas para calcular la cantidad de ancho de banda que necesitará para cada ubicación de la oficina. Si hay problemas de latencia o congestión TCP en las pruebas, es posible que tenga que acercar la salida a las personas que usan Office 365 o quitar el examen intensivo de red, como el descifrado o la inspección ssl.
  
Todas nuestras recomendaciones sobre qué tipo de procesamiento de red se recomienda se aplican a los circuitos ExpressRoute e Internet. Lo mismo sucede con el resto de las instrucciones de nuestro [sitio de optimización del rendimiento](./network-planning-and-performance.md).
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Aplicación de controles de seguridad a Azure ExpressRoute para escenarios de Office 365

La protección de la conectividad de Azure ExpressRoute comienza con los mismos principios que la protección de la conectividad a Internet. Muchos clientes deciden implementar controles perimetrales y de red a lo largo de la ruta de acceso de ExpressRoute que conecta su red local a Office 365 y otras nubes de Microsoft. Estos controles pueden incluir firewalls, servidores proxy de aplicaciones, prevención de pérdida de datos, detección de intrusiones, sistemas de prevención de intrusiones, etc. En muchos casos, los clientes aplican distintos niveles de controles al tráfico iniciado desde el entorno local que va a Microsoft, frente al tráfico iniciado desde Microsoft que va a la red local del cliente, frente al tráfico iniciado desde el entorno local que va a un destino general de Internet.
  
Estos son algunos ejemplos de integración de la seguridad con el [modelo de conectividad de ExpressRoute](/azure/expressroute/expressroute-connectivity-models) que elija implementar.

|**Opción de integración de ExpressRoute**|**Modelo perimetral de seguridad de red**|
|:-----|:-----|
|Colocación en un intercambio en la nube  <br/> |Instale nueva infraestructura perimetral o de seguridad existente en la instalación de colocación donde se establece la conexión de ExpressRoute.  <br/> Use la instalación de colocación únicamente con fines de enrutamiento/interconexión y conexiones de transporte de regreso desde la instalación de colocación a la infraestructura de seguridad/perímetro local.  <br/> |
|Ethernet de punto a punto  <br/> |Finalice la conexión ExpressRoute de punto a punto en la ubicación de la infraestructura perimetral o de seguridad local existente.  <br/> Instale una nueva infraestructura de seguridad o perímetro específica de la ruta de acceso de ExpressRoute y finalice allí la conexión de punto a punto.  <br/> |
|IPVPN de cualquier a cualquier  <br/> |Use una infraestructura perimetral o de seguridad local existente en todas las ubicaciones que salen al IPVPN que se usa para ExpressRoute para Office 365 conectividad.  <br/> Redireccionar el IPVPN usado para ExpressRoute para Office 365 a ubicaciones locales específicas designadas para servir como seguridad o perímetro.  <br/> |

Algunos proveedores de servicios también ofrecen funcionalidad de seguridad administrada o perimetral como parte de sus soluciones de integración con Azure ExpressRoute.
  
Al considerar la ubicación de la topología de las opciones de perímetro de red o seguridad que se usan para ExpressRoute para conexiones Office 365, a continuación se indican consideraciones adicionales.
  
- La profundidad y el tipo de controles de red o seguridad pueden afectar al rendimiento y la escalabilidad de la experiencia del usuario Office 365.

- Los flujos salientes (locales de\> Microsoft) y entrantes (Microsoft\> local) [si están habilitados] pueden tener requisitos diferentes. Es probable que sean diferentes de los destinos salientes a los destinos generales de Internet.

- Office 365 requisitos de puertos o protocolos y subredes IP necesarias son los mismos, independientemente de si el tráfico se enruta a través de ExpressRoute para Office 365 o a través de Internet.

- La colocación topológica de los controles de seguridad o red del cliente determina la red final entre el usuario y Office 365 servicio y puede tener un impacto sustancial en la latencia y la congestión de la red.

- Se recomienda a los clientes diseñar su topología de seguridad o perímetro para su uso con ExpressRoute para Office 365 de acuerdo con los procedimientos recomendados para la redundancia, la alta disponibilidad y la recuperación ante desastres.

Este es un ejemplo de Contoso que compara las distintas opciones de conectividad de Azure ExpressRoute con los modelos de seguridad perimetral descritos anteriormente.
  
### <a name="example-1-securing-azure-expressroute"></a>Ejemplo 1: Protección de Azure ExpressRoute
  
Contoso está pensando en implementar Azure ExpressRoute y después de planear la arquitectura óptima para el [enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md) y después de usar las instrucciones anteriores para comprender los requisitos de ancho de banda, están determinando el mejor método para proteger su perímetro.
  
Para Contoso, una organización multinacional con ubicaciones en varios continentes, la seguridad debe abarcar todos los perímetros. La opción de conectividad óptima para Contoso es una conexión de varios puntos con varias ubicaciones de emparejamiento de todo el mundo para atender las necesidades de sus empleados en cada continente. Cada continente incluye circuitos Azure ExpressRoute redundantes dentro del continente y la seguridad debe abarcar todos ellos.
  
La infraestructura existente de Contoso es confiable y puede controlar el trabajo adicional, como resultado, Contoso puede usar la infraestructura para su seguridad perimetral de Azure ExpressRoute e Internet. Si este no fuera el caso, Contoso podría optar por comprar más equipos para complementar su equipo existente o para controlar un tipo diferente de conexión.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Alta disponibilidad y conmutación por error con Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Se recomienda aprovisionar al menos dos circuitos activos desde cada salida con ExpressRoute al proveedor de ExpressRoute. Este es el lugar más común donde vemos errores para los clientes y puede evitarlo fácilmente aprovisionando un par de circuitos ExpressRoute activos o activos. También recomendamos al menos dos circuitos de Internet activos o activos porque muchos servicios de Office 365 solo están disponibles a través de Internet.
  
Dentro del punto de salida de la red hay muchos otros dispositivos y circuitos que desempeñan un papel fundamental en la forma en que las personas perciben la disponibilidad. Estas partes de los escenarios de conectividad no están cubiertas por ExpressRoute ni Office 365 ACUERDOs de Nivel de Servicio, pero desempeñan un papel fundamental en la disponibilidad del servicio de un extremo a otro según lo perciban los usuarios de la organización.
  
Céntrese en las personas que usan y operan Office 365, si un error de un componente afectaría a la experiencia de las personas que usan el servicio, busque formas de limitar el porcentaje total de personas afectadas. Si un modo de conmutación por error es operativamente complejo, tenga en cuenta la experiencia de los usuarios durante mucho tiempo para la recuperación y busque modos de conmutación por error operativos simples y automatizados.
  
Fuera de la red, Office 365, ExpressRoute y el proveedor de ExpressRoute tienen distintos niveles de disponibilidad.
  
### <a name="service-availability"></a>Disponibilidad del servicio
  
- Office 365 servicios están [cubiertos por contratos de nivel de servicio bien definidos](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement), que incluyen métricas de tiempo de actividad y disponibilidad para servicios individuales. Una de las razones por las que Office 365 puede mantener niveles de disponibilidad de servicio tan altos es la capacidad de los componentes individuales de conmutar por error sin problemas entre los muchos centros de datos de Microsoft mediante la red global de Microsoft. Esta conmutación por error se extiende desde el centro de datos y la red hasta los múltiples puntos de salida de Internet y permite la conmutación por error sin problemas desde la perspectiva de las personas que usan el servicio.

- ExpressRoute [proporciona un Acuerdo de Nivel de Servicio de disponibilidad del 99,9 %](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) en circuitos dedicados individuales entre Microsoft Network Edge y el proveedor de ExpressRoute o la infraestructura de asociados. Estos niveles de servicio se aplican en el nivel de circuito ExpressRoute, que consta de [dos interconexiones independientes](/azure/expressroute/expressroute-introduction) entre el equipo redundante de Microsoft y el equipo del proveedor de red en cada ubicación de emparejamiento.

### <a name="provider-availability"></a>Disponibilidad del proveedor
  
- Las disposiciones de nivel de servicio de Microsoft se detienen en el proveedor o asociado de ExpressRoute. Este es también el primer lugar en el que puede tomar decisiones que influirán en el nivel de disponibilidad. Debe evaluar de cerca las características de arquitectura, disponibilidad y resistencia que ofrece el proveedor de ExpressRoute entre el perímetro de red y la conexión de los proveedores en cada ubicación de emparejamiento de Microsoft. Preste mucha atención a los aspectos lógicos y físicos de la redundancia, el equipo de emparejamiento, los circuitos WAN proporcionados por el operador y los servicios adicionales de adición de valor, como los servicios NAT o los firewalls administrados.

### <a name="designing-your-availability-plan"></a>Diseño del plan de disponibilidad
  
Se recomienda planear y diseñar la alta disponibilidad y resistencia en los escenarios de conectividad de un extremo a otro para Office 365. Un diseño debe incluir;
  
- No hay puntos de error únicos, incluidos los circuitos De Internet y ExpressRoute.

- Minimizar el número de personas afectadas y la duración de ese impacto para los modos de error más esperados.

- Optimización para un proceso de recuperación simple, repetible y automático a partir de los modos de error más esperados.

- Compatibilidad con las demandas completas del tráfico de red y la funcionalidad a través de rutas de acceso redundantes, sin degradación sustancial.

Los escenarios de conectividad deben incluir una topología de red optimizada para varias rutas de acceso de red independientes y activas para Office 365. Esto producirá una mejor disponibilidad de un extremo a otro que una topología optimizada solo para redundancia en el nivel de dispositivo o equipo individual.
  
> [!TIP]
> Si los usuarios se distribuyen entre varios continentes o regiones geográficas y cada una de esas ubicaciones se conecta a través de circuitos WAN redundantes a una única ubicación local donde se encuentra un único circuito ExpressRoute, los usuarios experimentarán menos disponibilidad de servicio de un extremo a otro que un diseño de topología de red que incluye circuitos ExpressRoute independientes que conectan las distintas regiones a la ubicación de emparejamiento más cercana.
  
Se recomienda aprovisionar al menos dos circuitos ExpressRoute con cada circuito que se conecte a con una ubicación de emparejamiento geográfica diferente. Debe aprovisionar este par de circuitos activo-activo para cada región en la que los usuarios usarán la conectividad de ExpressRoute para Office 365 servicios. Esto permite que cada región permanezca conectada durante un desastre que afecta a una ubicación principal, como un centro de datos o una ubicación de emparejamiento. Configurarlas como activas o activas permite que el tráfico del usuario final se distribuya entre varias rutas de acceso de red. Esto reduce el alcance de las personas afectadas durante las interrupciones del dispositivo o del equipo de red.
  
No se recomienda usar un único circuito ExpressRoute con Internet como copia de seguridad.
  
### <a name="example-2-failover-and-high-availability"></a>Ejemplo 2: Conmutación por error y alta disponibilidad
  
El diseño multi geográfico de Contoso se ha sometido a una revisión del enrutamiento, el ancho de banda, la seguridad y ahora debe pasar por una revisión de alta disponibilidad. Contoso piensa que la alta disponibilidad abarca tres categorías; resistencia, confiabilidad y redundancia.
  
La resistencia permite a Contoso recuperarse rápidamente de los errores. La confiabilidad permite a Contoso ofrecer un resultado coherente dentro del sistema. La redundancia permite a Contoso moverse entre una o varias instancias reflejadas de la infraestructura.
  
Dentro de cada configuración perimetral, Contoso tiene firewalls, servidores proxy e IDS redundantes. Por Norteamérica, Contoso tiene una configuración perimetral en su centro de datos de Dallas y otra configuración perimetral en su centro de datos de Virginia. El equipo redundante de cada ubicación ofrece resistencia a esa ubicación.
  
La configuración de red en Contoso se basa en algunos principios clave:
  
- Dentro de cada región geográfica, hay varios circuitos ExpressRoute de Azure.

- Cada circuito dentro de una región puede admitir todo el tráfico de red dentro de esa región.

- El enrutamiento prefiere claramente una u otra ruta de acceso en función de la disponibilidad, la ubicación, etc.

- La conmutación por error entre circuitos ExpressRoute de Azure se produce automáticamente sin necesidad de una configuración o acción adicional por parte de Contoso.

- La conmutación por error entre circuitos de Internet se produce automáticamente sin necesidad de una configuración o acción adicional por parte de Contoso.

En esta configuración, con redundancia en el nivel físico y virtual, Contoso es capaz de ofrecer resistencia local, resistencia regional y resistencia global de forma confiable. Contoso eligió esta configuración después de evaluar un único circuito ExpressRoute de Azure por región, así como la posibilidad de conmutar por error a Internet.
  
Si Contoso no pudiera tener varios circuitos ExpressRoute de Azure por región, el enrutamiento del tráfico originado en Norteamérica al circuito ExpressRoute de Azure en Asia Pacífico agregaría un nivel inaceptable de latencia y la configuración del reenviador DNS necesaria agrega complejidad.
  
No se recomienda usar Internet como configuración de copia de seguridad. Esto interrumpe el principio de confiabilidad de Contoso, lo que da lugar a una experiencia incoherente mediante la conexión. Además, se requeriría una configuración manual para conmutar por error teniendo en cuenta los anuncios BGP que se han configurado, la configuración nat, la configuración de DNS y la configuración del proxy. Esta complejidad de conmutación por error agregada aumenta el tiempo de recuperación y reduce su capacidad para diagnosticar y solucionar los pasos implicados.
  
¿Sigue teniendo preguntas sobre cómo planear e implementar la administración de tráfico o Azure ExpressRoute? Lea el resto de nuestra [guía de rendimiento y red](./network-planning-and-performance.md) o las [preguntas más frecuentes sobre Azure ExpressRoute](/azure/expressroute/expressroute-faqs).
  
## <a name="working-with-azure-expressroute-providers"></a>Trabajar con proveedores de Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Elija las ubicaciones de los circuitos en función del ancho de banda, la latencia, la seguridad y el planeamiento de alta disponibilidad. Una vez que conozca las ubicaciones óptimas, le gustaría colocar circuitos [para revisar la lista actual de proveedores por región](/azure/expressroute/expressroute-locations).
  
Trabaje con su proveedor o proveedores para seleccionar las mejores opciones de conectividad, punto a punto, multipunto o hospedadas. Recuerde que puede combinar y combinar las opciones de conectividad siempre que el ancho de banda y otros componentes redundantes admitan el diseño de enrutamiento y alta disponibilidad.
  
Este es un vínculo breve que se puede usar para volver: [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>Temas relacionados
<a name="BKMK_high-availability"> </a>

[Evaluar la conectividad de red de Office 365](assessing-network-connectivity.md)
  
[Azure ExpressRoute para Office 365](azure-expressroute.md)
  
[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)
  
[Enrutamiento con ExpressRoute para Office 365](routing-with-expressroute.md)
  
[Implementación de ExpressRoute para Office 365](implementing-expressroute.md)
  
[Uso de comunidades BGP en ExpressRoute para escenarios de Office 365](bgp-communities-in-expressroute.md)
  
[Calidad de medios y rendimiento de conectividad de red en Skype Empresarial Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimización de la red para Skype Empresarial Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute y calidad del servicio en Skype Empresarial Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Flujo de llamadas con ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Ajuste del rendimiento de Office 365 mediante líneas base y el historial de rendimiento](performance-tuning-using-baselines-and-history.md)
  
[Plan de solución de problemas de rendimiento para Office 365](performance-troubleshooting-plan.md)
  
[Direcciones URL e intervalos de direcciones IP de Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Red de Office 365 y ajuste de rendimiento](network-planning-and-performance.md)
  
[Preguntas frecuentes sobre extremos de Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)