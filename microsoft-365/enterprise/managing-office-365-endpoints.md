---
title: Administración de puntos de conexión de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 99cab9d4-ef59-4207-9f2b-3728eb46bf9a
description: Obtenga información sobre cómo administrar puntos de conexión de Office 365 para que funcionen con la arquitectura de red de su organización empresarial.
ms.openlocfilehash: 41dceae78d80a78b023517e8b6c5c5c0d73da2ef
ms.sourcegitcommit: 64262f6f42dcce6a4608b2e3c7ca6190b7009093
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905290"
---
# <a name="managing-office-365-endpoints"></a>Administración de puntos de conexión de Office 365

La mayoría de las organizaciones empresariales que tienen varias ubicaciones de oficina y una WAN de conexión necesitarán configurar la conectividad de red de Office 365. Puede optimizar su red mediante el envío de solicitudes a todas las redes de confianza de Office 365 directamente a través de su firewall, omitiendo así todos los procesos o inspecciones adicionales a nivel de paquetes. Esto reduce la latencia y los requisitos de capacidad perimetrales. Identificar el tráfico de red de Office 365 es el primer paso para ofrecer un rendimiento óptimo a los usuarios. Para obtener más información, consulte Principios de conectividad de red [de Office 365.](microsoft-365-network-connectivity-principles.md)

Microsoft le recomienda tener acceso a los puntos de conexión de red de Office 365 y realizar cambios continuos en ellos mediante la dirección IP de [Office 365](microsoft-365-ip-web-service.md)y el servicio web url.

Independientemente de cómo administre el tráfico de red fundamental de Office 365, Office 365 requiere conectividad a Internet. Otros puntos de conexión de red en los que es necesario tener conectividad se muestran en [Puntos de conexión adicionales no incluidos en el servicio web de URL ni en la dirección IP de Office 365](additional-office365-ip-addresses-and-urls.md).

La forma en que use los puntos de conexión de red de Office 365 dependerá de la arquitectura de red de la organización empresarial. En este artículo se describen varias formas en que las arquitecturas de red de la empresa se pueden integrar con las direcciones IP y URL de Office 365. La forma más sencilla de elegir en qué solicitudes de red confiar es usar dispositivos SD-WAN que admitan la configuración automatizada de Office 365 en cada una de las ubicaciones de la oficina.

## <a name="sd-wan-for-local-branch-egress-of-vital-office-365-network-traffic"></a>SD-WAN para la salida de sucursal local del tráfico de red vital de Office 365

En cada ubicación de sucursal, puede proporcionar un dispositivo SD-WAN que esté configurado para enrutar el tráfico de la categoría Optimizar puntos de conexión de Office 365, o bien las categorías Optimizar y Permitir, directamente a la red de Microsoft. Otro tráfico de red, incluido el tráfico local del centro de datos, el tráfico general de los sitios web de Internet y el tráfico a puntos de conexión de categoría predeterminada de Office 365 se envía a otra ubicación donde tiene un perímetro de red más importante.

Microsoft está trabajando con proveedores de SD-WAN para habilitar la configuración automatizada. Para más información, consulte [Programa para partners de redes de Office 365](microsoft-365-networking-partner-program.md).

<a name="pacfiles"> </a>
## <a name="use-a-pac-file-for-direct-routing-of-vital-office-365-traffic"></a>Usar un archivo PAC para el enrutamiento directo del tráfico fundamental de Office 365

Use archivos PAC o WPAD para administrar las solicitudes de red que están asociadas con Office 365 pero no tienen una dirección IP. Normalmente, las solicitudes de red que se envían a través de un dispositivo proxy o perimetral aumentan la latencia. Mientras que la característica de Inspección e interrupción SSL crea la latencia más grande, otros servicios, como la autenticación de proxy y la búsqueda de la reputación, pueden ocasionar peor rendimiento y una experiencia de usuario deficiente. Además, estos dispositivos de red perimetral necesitan capacidad suficiente para procesar todas las solicitudes de conexión de red. Se recomienda omitir los dispositivos de inspección o proxy para solicitudes de red de Office 365 directas.
  
[PowerShell Gallery Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) es un script de PowerShell que lee los puntos de conexión de red más recientes desde el servicio web URL y la dirección IP de Office 365, y crea un archivo PAC de ejemplo. Puede modificar el script para que se integre con la administración de archivos PAC existente.

![Conectarse a Office 365 a través de firewalls y servidores proxy.](../media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)

**Figura 1: perímetro de red de una empresa simple**

El archivo PAC se implementa en los exploradores web en el punto 1 de la figura 1. Cuando usa un archivo PAC para salida directa de tráfico de red importante de Office 365, también necesita permitir la conectividad a las direcciones IP que se encuentran detrás de estas URL en el firewall perimetral de la red. Esto se hace recuperando las direcciones IP de las mismas categorías de puntos de conexión de Office 365 que se especifican en el archivo PAC y creando las ACL de firewall basándose en esas direcciones. El firewall es el punto 3 de la figura 1.

Por separado, si decide realizar el enrutamiento directo solo para los puntos de conexión de la categoría Optimizar, deberán aparecer en el servidor proxy los puntos de conexión de categoría Permitir necesarios que se envíen al servidor proxy para omitir procesamiento adicional. Por ejemplo, Inspección e interrupción SSL y la autenticación de proxy no son compatibles con los puntos de conexión de las categorías Optimizar y Permitir. El servidor proxy es el punto 2 de la figura 1.

La configuración común es permitir sin procesar todo el tráfico saliente del servidor proxy para las direcciones IP de destino del tráfico de red de Office 365 que llega al servidor proxy. Para obtener información sobre los problemas con Inspección e interrupción SSL, consulte [Uso de dispositivos de red de terceros o soluciones en el tráfico de Office 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).

Hay dos tipos de archivos PAC que el script Get-PacFile generará.

| Tipo | Descripción |
|:-----|:-----|
|**1** <br/> |Enviar tráfico de punto de conexión Optimizar directo y todo lo demás al servidor proxy. <br/> |
|**2** <br/> |Enviar tráfico de punto de conexión Optimizar y Permitir directo y todo lo demás al servidor proxy. Este tipo también se puede usar para enviar todo el tráfico compatible de ExpressRoute para Office 365 a segmentos de red de ExpressRoute y todo los demás al servidor proxy. <br/> |

Este es un ejemplo sencillo de llamada al script de PowerShell:

```powershell
Get-PacFile -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

Hay muchos parámetros que puede pasar al script:

| Parámetro | Descripción |
|:-----|:-----|
|**ClientRequestId** <br/> |Esto es necesario y es un GUID pasado al servicio web que representa el equipo cliente que realiza la llamada. <br/> |
|**Instance** <br/> |La instancia de servicio de Office 365, cuyo valor predeterminado es Worldwide. Esto también se pasa al servicio web. <br/> |
|**TenantName** <br/> |El nombre de su espacio empresarial de Office 365. Se pasa al servicio web y se usa como un parámetro reemplazable en algunas URL de Office 365. <br/> |
|**Tipo** <br/> |El tipo de archivo PAC de proxy que quiere generar. <br/> |

Este es otro ejemplo de la llamada al script de PowerShell con parámetros adicionales:

```powershell
Get-PacFile -Type 2 -Instance Worldwide -TenantName Contoso -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

## <a name="proxy-server-bypass-processing-of-office-365-network-traffic"></a>Omitir el procesamiento del tráfico de red de Office 365 con servidor proxy

En caso de que no se usen archivos PAC para el tráfico de salida directo, aún debería omitir el procesamiento en el perímetro de la red configurando el servidor proxy. Algunos proveedores de servidores proxy han habilitado la configuración automatizada de esto, tal como se describe en el [Programa para partners de redes de Office 365](microsoft-365-networking-partner-program.md).

Si lo hace manualmente, tendrá que obtener los datos de categoría de extremo Optimizar y Permitir del servicio web url y la dirección IP de Office 365 y configurar el servidor proxy para que omita el procesamiento de estos. Es importante evitar Inspección e interrupción SSL y comprobar la autenticación de proxy para los puntos de conexión de las categorías Optimizar y Permitir.
  
<a name="bkmk_changes"> </a>
## <a name="change-management-for-office-365-ip-addresses-and-urls"></a>Administración de cambios de direcciones IP y URL de Office 365  

Además de seleccionar la configuración adecuada para el perímetro de la red, es fundamental que adopte un proceso de administración de cambios para los puntos de conexión de Office 365. Estos puntos de conexión cambian periódicamente y, en caso de que no administre los cambios, puede que termine con usuarios bloqueados o con un rendimiento deficiente cuando se agregue una dirección IP o URL nueva.

Los cambios en las direcciones IP y URL de Office 365 suelen publicarse cerca del último día de cada mes. En ocasiones, los cambios se publicarán fuera de la programación debido a requisitos de funcionamiento, soporte o seguridad.

Cuando se publica un cambio sobre el que es necesario que actúe, debido a que se ha agregado una dirección IP o URL, debería recibir un aviso de 30 días a partir del momento en que se publique el cambio hasta que haya un servicio de Office 365 en ese extremo. Aunque nuestro objetivo es este periodo de notificación, puede que no siempre sea posible debido a requisitos de funcionamiento, soporte o seguridad. Los cambios que no requieran una acción inmediata para mantener la conectividad (como direcciones IP o URL quitadas o cambios menos importantes) no incluyen una notificación previa. Independientemente de la notificación que se proporcione, se enumeran las fechas previstas para cada uno de los cambios en el servicio.

### <a name="change-notification-using-the-web-service"></a>Notificación de cambios con el servicio web

Puede usar el servicio web de URL y la dirección IP de Office 365 para recibir la notificación de cambios. Le recomendamos que llame al método web **/version** una vez por hora para comprobar la versión de los puntos de conexión que está usando para conectarse a Office 365. Si esta versión cambia al compararla con la versión que usa, debe obtener los datos del último punto de conexión en el método web **/endpoints** y, de forma opcional, puede obtener las diferencias con el método web **/changes**. No es necesario llamar a los métodos web **/endpoints** o **/changes** en caso de que no haya ningún cambio en la versión encontrada.

Para más información, consulte [Dirección IP y servicio web de URL de Office 365 ](microsoft-365-ip-web-service.md).

### <a name="change-notification-using-rss-feeds"></a>Notificación de cambios con fuentes RSS

La dirección IP de Office 365 y el servicio web de URL proporcionan una fuente RSS a la que puede suscribirse en Outlook. Hay vínculos a las direcciones URL de RSS en cada una de las páginas específicas de las instancias del servicio de Office 365 para las direcciones IP y URL. Para más información, consulte [Dirección IP y servicio web de URL de Office 365 ](microsoft-365-ip-web-service.md).

### <a name="change-notification-and-approval-review-using-microsoft-flow"></a>Revisión de aprobación y notificación de cambios con Microsoft Flow

Sabemos que es posible que siga requiriendo procesamiento manual para los cambios en los puntos de conexión de red que llegan cada mes. Puede usar Microsoft Flow para crear un flujo que le notifique por correo electrónico y, opcionalmente, realice un proceso de aprobación de los cambios cuando los puntos de conexión de la red de Office 365 cambien. Una vez completada la revisión, puede hacer que el flujo envíe los cambios por correo automáticamente al equipo de administración del servidor proxy y del firewall.

Para obtener información sobre una plantilla y un ejemplo de Microsoft Flow, vea [Usar Microsoft Flow para recibir un correo electrónico para los cambios en las direcciones IP y URL de Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/td-p/240651).
  
<a name="FAQ"> </a>
## <a name="office-365-network-endpoints-faq"></a>Preguntas más frecuentes sobre puntos de conexión de red de Office 365

Vea estas preguntas más frecuentes sobre la conectividad de red de Office 365.
  
### <a name="how-do-i-submit-a-question"></a>¿Cómo envío una pregunta?

Haga clic en el vínculo de la parte inferior para indicar si el artículo le ha sido útil o no y enviar cualquier otra pregunta. Supervisamos los comentarios y actualizamos las preguntas en esta sección de preguntas más frecuentes.
  
### <a name="how-do-i-determine-the-location-of-my-tenant"></a>¿Cómo determino la ubicación de mi espacio empresarial?

 **La ubicación de espacios empresariales** se determina mejor con nuestro [mapa de centros de datos](https://aka.ms/datamaps).
  
### <a name="am-i-peering-appropriately-with-microsoft"></a>¿Estoy emparejando adecuadamente con Microsoft?

 **Las ubicaciones de emparejamiento** se describen con más detalles en el [emparejamiento con Microsoft](https://www.microsoft.com/peering).
  
Con más de 2500 relaciones de emparejamiento ISP a nivel mundial y 70 puntos de presencia, el paso de su red a la nuestra debería realizarse sin problemas. No está de más dedicar unos minutos a asegurarse de que la relación de emparejamiento de su ISP es la mejor, [le mostramos algunos ejemplos aquí](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__guidance/) de entregas de emparejamiento buenas y no tan buenas a nuestra red.
  
<a name="bkmk_MissingIP"> </a>
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a>Puedo ver solicitudes de red a direcciones IP que no están en la lista publicada, ¿es necesario proporcionar acceso para ellas?

Solo proporcionamos direcciones IP para los servidores de Office 365 a los que debería enrutar directamente. Esta no es una lista completa de todas las direcciones IP para las que verá peticiones de red. Verá las solicitudes de red para Microsoft y las direcciones IP de terceros sin publicar. Estas direcciones IP se generan de forma dinámica o se administran de manera que se impide un aviso puntual cuando cambian. Si su firewall no permite el acceso basado en los FQDN para estas solicitudes de red, use un archivo PAC o WPAD para administrar las solicitudes.
  
¿Ve una dirección IP asociada a Office 365 sobre la que quiere obtener más información?
  
1. Compruebe si la dirección IP se incluye en un rango publicado mayor con una calculadora CIDR, como estas para [IPv4](https://www.ipaddressguide.com/cidr) o [IPv6](https://www.ipaddressguide.com/ipv6-cidr). Por ejemplo, 40.96.0.0/13 incluye la dirección IP 40.103.0.1 a pesar de que 40.96 no coincide con 40.103.
2. Compruebe si un partner es el propietario de la IP con una [consulta whois](https://dnsquery.org/). Si es propiedad de Microsoft, puede ser un partner interno. Se muestran muchos puntos de conexión de red de asociados que pertenecen a la categoría _predeterminada_, cuyas direcciones IP no se publican.
3. Es posible que la dirección IP no pertenezca a Office 365 o a una dependencia. La publicación de puntos de conexión de red de Office 365 no incluye todos los puntos de conexión de red de Microsoft.
4. Compruebe el certificado. Con un explorador, conéctese a la dirección IP mediante *HTTPS:// \<IP_ADDRESS\>* y compruebe los dominios enumerados en el certificado para comprender qué dominios están asociados a la dirección IP. Si es una dirección IP propiedad de Microsoft y no está en la lista de direcciones IP de Office 365, es probable que la dirección IP esté asociada a una red CDN de Microsoft como  *MSOCDN.NET*  u otro dominio de Microsoft sin información de IP publicada. Si encuentra que el dominio en el certificado es uno de los que afirmamos indicar la dirección IP, háganoslo saber.

<a name="bkmk_cname"> </a>
### <a name="some-office-365-urls-point-to-cname-records-instead-of-a-records-in-the-dns-what-do-i-have-to-do-with-the-cname-records"></a>Algunas direcciones URL de Office 365 apuntan a registros CNAME en lugar de a registros A de DNS. ¿Qué tengo que hacer con los registros CNAME?

Los equipos cliente necesitan un registro A o AAAA de DNS que incluya una o más direcciones IP para conectarse a un servicio en la nube. Algunas direcciones URL incluidas en Office 365 muestran registros CNAME en lugar de registros A o AAAA. Estos registros CNAME son intermediarios y es posible que haya varios en una cadena. Siempre se resolverán finalmente como un registro A o AAAA para una dirección IP. Por ejemplo, considere la siguiente serie de registros DNS, que se resuelve en la dirección IP _IP_1_:

```console
serviceA.office.com -> CNAME: serviceA.domainA.com -> CNAME: serviceA.domainB.com -> A: IP_1
```

Estas redirecciones de CNAME son una parte normal del DNS y son transparentes para el equipo cliente y para los servidores proxy. Se usan para equilibrar la carga, las redes de entrega de contenido, la alta disponibilidad y la mitigación de incidencias de servicio. Microsoft no publica los registros CNAME de intermediarios, por lo que están sujetos a cambios en cualquier momento y no necesitará configurarlos como permitidos en el servidor proxy.

Un servidor proxy valida la dirección URL inicial, que en el ejemplo anterior es serviceA.office.com, y esta dirección URL se incluiría en la publicación de Office 365. El servidor proxy solicita la resolución DNS de esa dirección URL a una dirección IP y recibirá IP_1. No valida los registros del redireccionamiento CNAME de intermediarios.

Las configuraciones codificadas de forma segura o las listas blancas basadas en FQDN indirectos de Office 365 no se recomiendan, no son compatibles con Microsoft y se sabe que causan problemas de conectividad del cliente. Las soluciones DNS que se bloquean en el redireccionamiento CNAME, o que resuelven incorrectamente las entradas DNS de Office 365, se pueden resolver a través de reenviadores DNS con recursión DNS habilitada o mediante sugerencias de raíz de DNS. Muchos productos perimetrales de red de terceros integran de forma nativa las listas blancas de puntos de conexión de Office 365 recomendadas en su configuración mediante el servicio web url y la dirección [IP de Office 365.](microsoft-365-ip-web-service.md)

<a name="bkmk_akamai"> </a>
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a>¿Por qué veo nombres como nsatc.net o akadns.net en los nombres de dominio de Microsoft?

Office 365 y otros servicios de Microsoft usan varios servicios de terceros como Akamai y MarkMonitor para mejorar su experiencia de Office 365. Para seguir ofreciéndole la mejor experiencia posible, podemos cambiar estos servicios en el futuro. Los dominios de terceros pueden hospedar contenido, como una red CDN, o pueden hospedar un servicio, como un servicio de administración de tráfico geográfico. Algunos de los servicios actualmente en uso son:
  
[MarkMonitor](https://www.markmonitor.com/) está en uso cuando ve solicitudes que incluyen *\* .nsatc.net*. Este servicio proporciona protección y supervisión de nombres de dominio para protegerse de comportamiento malintencionado.
  
[ExactTarget](https://www.marketingcloud.com/) está en uso cuando ve solicitudes a *\* .exacttarget.com*. Este servicio ofrece administración y supervisión de vínculos de correo contra comportamiento malintencionado.
  
[Akamai](https://www.akamai.com/) está en uso cuando vea las solicitudes que incluyen uno de los siguientes FQDN. Este servicio ofrece servicios de red de entrega de contenido y DNS geográfico.
  
```console
*.akadns.net
*.akam.net
*.akamai.com
*.akamai.net
*.akamaiedge.net
*.akamaihd.net
*.akamaized.net
*.edgekey.net
*.edgesuite.net
```

<a name="bkmk_thirdparty"> </a>
### <a name="i-have-to-have-the-minimum-connectivity-possible-for-office-365"></a>Tengo que tener la conectividad mínima posible para Office 365

Puesto que Office 365 es un conjunto de servicios creado para funcionar a través de Internet, las promesas de confiabilidad y disponibilidad se basan en la cantidad de servicios de Internet estándar que están disponibles. Por ejemplo, los servicios de Internet estándar como DNS, CRL y CDN deben ser accesibles para usar Office 365 al igual que deben ser accesibles para usar la mayoría de servicios modernos de Internet.

El conjunto de aplicaciones de Office 365 se divide en las principales áreas de servicio. Se pueden habilitar selectivamente para la conectividad y hay un área común, que es una dependencia para todos y siempre es necesaria.

| Área de servicios | Descripción |
|:-----|:-----|
|**Exchange** <br/> |Exchange Online y Exchange Online Protection <br/> |
|**SharePoint** <br/> |SharePoint Online y OneDrive para la Empresa <br/> |
|**Skype Empresarial Online y Microsoft Teams** <br/> |Skype Empresarial y Microsoft Teams <br/> |
|**Común** <br/> |Office 365 Pro Plus, Office en un explorador, Azure AD y otros puntos de conexión de red comunes <br/> |

Además de los servicios de Internet básicos, hay servicios de terceros que solo se usan para integrar características. Aunque son necesarios para la integración, se marcan como opcionales en el artículo de puntos de conexión de Office 365, lo que significa que la funcionalidad principal del servicio seguirá funcionando si el punto de conexión no es accesible. Cualquier extremo de red que sea necesario tendrá el atributo necesario establecido en true. Cualquier extremo de red que sea opcional tendrá el atributo necesario establecido en false y el atributo de notas detallará la funcionalidad que falta si se bloquea la conectividad.
  
Si está intentando usar Office 365 y está buscando servicios de terceros no son accesibles, querrá asegurarse de que todos los [FQDN marcados](urls-and-ip-address-ranges.md)como obligatorios u opcionales en este artículo se permiten a través del proxy y el firewall.
  
<a name="bkmk_consumer"> </a>
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a>¿Cómo puedo bloquear el acceso a los servicios al consumidor de Microsoft?

Si restringe el acceso a nuestros servicios al consumidor, será bajo su responsabilidad. La única manera confiable de bloquear los servicios al consumidor es restringir el acceso al FQDN *login.live.com*. Este FQDN lo usa un amplio conjunto de servicios, incluidos los que no van dirigidos al consumidor, como MSDN, TechNet, etc. Este FQDN también lo usa el programa de Intercambio de archivos seguro del Soporte técnico de Microsoft y es necesario para transferir archivos con el fin de facilitar la solución de problemas para los productos de Microsoft.  Si se restringe el acceso a este FQDN, es posible que también sea necesario incluir excepciones a la regla para las solicitudes de red asociadas a estos servicios.
  
Tenga en cuenta que bloquear el acceso solo a los servicios al consumidor de Microsoft no impide la capacidad de que alguien en su red filtre la información mediante un espacio empresarial de Office 365 u otro servicio.

<a name="bkmk_IPOnlyFirewall"> </a>
### <a name="my-firewall-requires-ip-addresses-and-cannot-process-urls-how-do-i-configure-it-for-office-365"></a>El Firewall requiere direcciones IP y no puede procesar URL. ¿Cómo lo configuro para Office 365?

Office 365 no proporciona direcciones IP de todos los puntos de conexión de red necesarios. Algunas se proporcionan solo como direcciones URL y se clasifican como predeterminadas. Las direcciones URL de la categoría predeterminada necesarias deben permitirse a través de un servidor proxy. Si no tiene un servidor proxy, vea cómo ha configurado las solicitudes web para las direcciones URL que los usuarios escriben en la barra de direcciones de un explorador web; el usuario tampoco proporciona una dirección IP. Las direcciones URL de categoría predeterminadas de Office 365 que no proporcionan direcciones IP deben configurarse de la misma manera.

## <a name="related-topics"></a>Temas relacionados

[Dirección IP de Office 365 y servicio web de URL](microsoft-365-ip-web-service.md)

[Intervalos IP del centro de datos de Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Espacio IP público de Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)
  
[Requisitos de infraestructura de red para Microsoft Intune](https://docs.microsoft.com/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[ExpressRoute y Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[Intervalos de direcciones IP y URL de Office 365](urls-and-ip-address-ranges.md)
  
[Administrar ExpressRoute para la conectividad de Office 365](managing-expressroute-for-connectivity.md)
  
[Principios de conectividad de red de Office 365](microsoft-365-network-connectivity-principles.md)
