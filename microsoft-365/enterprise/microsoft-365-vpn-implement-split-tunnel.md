---
title: Implementación de túnel dividido de VPN para Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: Cómo implementar el túnel dividido de VPN para Microsoft 365
ms.openlocfilehash: ee8c0929682370d581c9d1b5c738d682d3f91a01
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320443"
---
# <a name="implementing-vpn-split-tunneling-for-microsoft-365"></a>Implementación de túnel dividido de VPN para Microsoft 365

>[!NOTE]
>Este artículo forma parte de un conjunto de artículos que abordan la optimización Microsoft 365 usuarios remotos.

>- Para obtener información general sobre cómo usar el túnel dividido de VPN para optimizar la conectividad Microsoft 365 usuarios remotos, vea [Overview: VPN split tunneling for Microsoft 365](microsoft-365-vpn-split-tunnel.md).
>- Para obtener una lista detallada de escenarios de túnel dividido de VPN, consulte [Escenarios de túnel dividido de VPN comunes para Microsoft 365](microsoft-365-vpn-common-scenarios.md).
>- Para obtener instrucciones sobre cómo proteger el Teams de medios en entornos de túnel dividido de VPN, consulte [Securing Teams media traffic for VPN split tunneling](microsoft-365-vpn-securing-teams.md).
>- Para obtener información sobre cómo configurar stream y eventos en directo en entornos VPN, consulte [Special considerations for Stream and live events in VPN environments](microsoft-365-vpn-stream-and-live-events.md).
>- Para obtener información sobre cómo optimizar Microsoft 365 el rendimiento de los inquilinos en todo el mundo para los usuarios de China, [vea optimización Microsoft 365 rendimiento para los usuarios de China](microsoft-365-networking-china.md).

La estrategia recomendada por Microsoft para optimizar la conectividad de los trabajadores remotos se centra en mitigar rápidamente los problemas y proporcionar un alto rendimiento con unos sencillos pasos. Estos pasos ajustan el enfoque de VPN heredado para algunos puntos de conexión definidos que omiten los servidores VPN con cuello de botella. Se puede aplicar un modelo de seguridad equivalente o incluso superior en diferentes capas para que no sea necesario proteger todo el tráfico de salida de la red corporativa. En la mayoría de los casos, esto se puede lograr eficazmente en cuestión de horas y, a continuación, es escalable a otras cargas de trabajo según la demanda de requisitos y el tiempo lo permita.

## <a name="implement-vpn-split-tunneling"></a>Implementación de túnel dividido de VPN

En este artículo, encontrará los _sencillos_ pasos necesarios para migrar la arquitectura de cliente VPN de un túnel forzado de _VPN_ a un túnel forzado de VPN con algunas excepciones de confianza, modelo de túnel dividido [de VPN #2](microsoft-365-vpn-common-scenarios.md#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) en escenarios de túnel dividido de [VPN comunes para Microsoft 365](microsoft-365-vpn-common-scenarios.md).

En el siguiente diagrama se muestra cómo funciona la solución recomendada de túnel dividido de VPN:

![Detalle de la solución VPN de túnel dividido.](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. Identificar los puntos de conexión que se deben optimizar

En el [Microsoft 365](urls-and-ip-address-ranges.md) de direcciones IP y direcciones IP, Microsoft identifica claramente los puntos de conexión clave que necesita para optimizarlos y los clasifica como **Optimizar**. Actualmente, solo hay cuatro direcciones URL y 20 subredes IP que deben optimizarse. Este pequeño grupo de puntos de conexión representa entre el 70 % y el 80 % del volumen de tráfico al servicio de Microsoft 365, incluidos los puntos de conexión confidenciales de latencia, como los de Teams multimedia. Básicamente, este es el tráfico que debemos tener especial cuidado y es también el tráfico que pondrá una presión increíble en las rutas de red tradicionales y la infraestructura VPN.

Las direcciones URL de esta categoría tienen las siguientes características:

- Son los puntos de conexión que pertenecen a Microsoft, que también se encarga de administrarlos y alojarlos en su infraestructura
- Se les ofrece IP
- Tienen una baja tasa de cambio y un número esperado reducido (actualmente, 20 subredes IP)
- Tienen ancho de banda o son sensibles a la latencia
- Se les puede proporcionar elementos de seguridad necesarios directamente en el servicio en lugar de en línea en la red
- Cuenta con alrededor del 70-80 % del volumen de tráfico al servicio Microsoft 365 cliente

Para obtener más información sobre Microsoft 365 y cómo se clasifican y administran, consulte [Managing Microsoft 365 endpoints](managing-office-365-endpoints.md).

#### <a name="optimize-urls"></a>Optimización de direcciones URL

Las direcciones URL que se deben optimizar actualmente se muestran en la siguiente tabla. En la mayoría de los casos, solo debería necesitar usar puntos de conexión de URL en un [archivo PAC de explorador](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic) en el que los puntos de conexión se configuren para enviarse directamente, en lugar de hacerlo al proxy.

| Optimización de direcciones URL | Puerto/Protocolo | Objetivo |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | Esta es una de las direcciones URL primarias que Outlook usa para conectarse a su servidor de Exchange Online y tiene un alto volumen de uso de ancho de banda y recuento de conexiones. Se requiere una baja latencia de red para las características en línea, entre las que se incluyen: búsqueda instantánea, otros calendarios de buzón, búsqueda libre/ocupada, administrar reglas y alertas, archivo de Exchange Online y mensajes de correo electrónico que salen de la bandeja de salida. |
| <https://outlook.office.com> | TCP 443 | Esta dirección URL se usa para que Outlook Online Web Access se conecte al servidor de Exchange Online y es sensible a la latencia de red. La conectividad es especialmente importante para la carga y descarga de archivos grandes con SharePoint Online. |
| \<tenant\>https://.sharepoint.com | TCP 443 | Esta es la dirección URL principal de SharePoint Online y tiene un uso de ancho de banda alto. |
| \<tenant\>https://-my.sharepoint.com | TCP 443 | Esta es la dirección URL principal de OneDrive para la Empresa y tiene un gran uso de ancho de banda y posiblemente un alto número de conexiones de la Herramienta de sincronización de OneDrive para la Empresa. |
| Direcciones IP del contenido multimedia de Teams (sin URL) | UDP 3478, 3479, 3480 y 3481 | Asignación de detección de retransmisión y tráfico en tiempo real. Estos son los puntos de conexión usados para Skype Empresarial y Microsoft Teams tráfico multimedia (llamadas, reuniones, etc.). La mayoría de los puntos de conexión se proporcionan cuando el cliente de Microsoft Teams establece una llamada (que se incluye en las direcciones IP mostradas para el servicio). El uso del protocolo UDP es necesario para obtener la calidad multimedia ideal.   |

En los ejemplos anteriores, **el espacio** empresarial debe reemplazarse por su Microsoft 365 de inquilino. Por ejemplo, **contoso.onmicrosoft.com** usaría _contoso.sharepoint.com_ y _contoso-my.sharepoint.com_.

#### <a name="optimize-ip-address-ranges"></a>Optimización de intervalos de direcciones IP

En el momento de escribir los intervalos de direcciones IP a los que corresponden estos puntos de conexión son los siguientes. Se recomienda encarecidamente que use un [script](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category) como este ejemplo, el servicio web [DE IP y URL de Microsoft 365](microsoft-365-ip-web-service.md) o la página [URL/IP](urls-and-ip-address-ranges.md) para comprobar si hay actualizaciones al aplicar la configuración y poner una directiva en su lugar para hacerlo con regularidad.

```markdown
104.146.128.0/17
13.107.128.0/22
13.107.136.0/22
13.107.18.10/31
13.107.6.152/31
13.107.64.0/18
131.253.33.215/32
132.245.0.0/16
150.171.32.0/22
150.171.40.0/22
204.79.197.215/32
23.103.160.0/20
40.104.0.0/15
40.108.128.0/17
40.96.0.0/13
52.104.0.0/14
52.112.0.0/14
52.96.0.0/14
52.120.0.0/14
```

### <a name="2-optimize-access-to-these-endpoints-via-the-vpn"></a>2. Optimizar el acceso a estos puntos de conexión a través de la VPN

Ya identificados los puntos de conexión críticos, se deben desviar del túnel de VPN y permitirles usar la conexión a Internet local del usuario para conectarse directamente al servicio. La forma en que se logra esto varía en función de la plataforma del equipo y del producto de VPN que se use, pero la mayoría de las soluciones de VPN permite una configuración sencilla de las directivas para aplicar esta lógica. Para obtener instrucciones sobre el túnel dividido específico de la plataforma de VPN, consulte [Guías para obtener más información sobre las plataformas VPN comunes](#howto-guides-for-common-vpn-platforms).

Si desea probar la solución manualmente, puede ejecutar el siguiente ejemplo de PowerShell para emular la solución en el nivel de la tabla de rutas. Este ejemplo agrega una ruta para cada subred IP del contenido multimedia de Teams a la tabla de rutas. Puede probar el rendimiento del contenido multimedia de Teams antes y después, y observar la diferencia de rutas en los extremos especificados.

#### <a name="example-add-teams-media-ip-subnets-into-the-route-table"></a>Ejemplo: agregar subredes IP del contenido multimedia de Teams a la tabla de rutas

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18" # Teams Media endpoints
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

En el script anterior, _$intIndex_ es el índice de la interfaz conectada a Internet (puede buscarla si ejecuta **get-netadapter** en PowerShell y se fija en el valor de _ifIndex_) y _$Gateway_ es la puerta de enlace predeterminada de esa interfaz (puede buscarla si ejecuta **ipconfig** en un símbolo del sistema o **(Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop** en PowerShell).

Una vez que haya agregado las rutas, puede confirmar que la tabla de rutas es la correcta, para ello, ejecute **route print** en un símbolo del sistema o PowerShell. El resultado debe contener las rutas que agregó y mostrar el índice de la interfaz (_22_ en este ejemplo) y la puerta de enlace para dicha interfaz (_192.168.1.1_ en este ejemplo):

![Enruta la salida de impresión.](../media/vpn-split-tunneling/vpn-route-print.png)

Para agregar rutas para  todos los intervalos de direcciones IP actuales en la categoría Optimizar, puede usar la siguiente variación de script para consultar el servicio [web DE IP y DIRECCIÓN URL de Microsoft 365](microsoft-365-ip-web-service.md) para el conjunto actual de subredes IP de Optimizar y agregarlas a la tabla de rutas.

#### <a name="example-add-all-optimize-subnets-into-the-route-table"></a>Ejemplo: agregar subredes IP de la categoría Optimizar a la tabla de rutas

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
# Query the web service for IPs in the Optimize category
$ep = Invoke-RestMethod ("https://endpoints.office.com/endpoints/worldwide?clientrequestid=" + ([GUID]::NewGuid()).Guid)
# Output only IPv4 Optimize IPs to $optimizeIps
$destPrefix = $ep | where {$_.category -eq "Optimize"} | Select-Object -ExpandProperty ips | Where-Object { $_ -like '*.*' }
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

Si ha agregado accidentalmente rutas con parámetros incorrectos o si simplemente desea revertir los cambios, puede quitar las rutas que acaba de agregar con el siguiente comando:

```powershell
foreach ($prefix in $destPrefix) {Remove-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

<!--- remmed until we add more reliable interface selection logic
#### Example script to add Teams Media subnets to the route table

```powershell
$adapter = get-netadapter | ? {$_.Status -eq "Up"}
$adapterIndex = $adapter.ifIndex
$gateway = (Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop

$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18"
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```
-->

El cliente VPN debe configurarse para que el tráfico a las direcciones IP de la categoría **Optimizar** se enrute de esta forma. Esto permite que el tráfico use recursos locales de Microsoft, como puertas frontales de servicio de Microsoft 365, como la puerta principal de [Azure](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/) que ofrecen servicios Microsoft 365 y puntos de conexión de conectividad lo más cerca posibles de los usuarios. Esto nos permite ofrecer niveles de alto rendimiento a los usuarios en cualquier lugar del mundo y aprovecha al máximo la red [global de clase mundial de Microsoft](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/), que probablemente se encuentra a unos milisegundos de la salida directa de los usuarios.

## <a name="howto-guides-for-common-vpn-platforms"></a>Guías paso a paso para plataformas VPN comunes

En esta sección se proporcionan vínculos a guías detalladas para implementar túneles divididos Microsoft 365 tráfico de los asociados más comunes en este espacio. Se agregarán guías adicionales a medida que estén disponibles.

- **Windows 10 vpn**: [optimizar el tráfico Microsoft 365 para los trabajadores remotos con el cliente VPN Windows 10 cliente VPN nativo](/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco AnyConnect**: [Optimize Anyconnect Split Tunnel for Office 365 (Optimización del túnel dividido de AnyConnect para Office 365)](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo Alto GlobalProtect**: [optimizar el tráfico Microsoft 365 mediante vpn split Tunnel excluir la ruta de acceso](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5 Redes BIG-IP APM**: optimizar el tráfico Microsoft 365 acceso remoto a través de [VPN al usar BIG-IP APM](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365)
- **Citrix Gateway**: [optimización del túnel dividido de VPN de Citrix Gateway para Office365](https://docs.citrix.com/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Pulse Secure**: [Vpn Tunneling: Cómo configurar la tunelización dividida para excluir Microsoft 365 aplicaciones](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417)
- **VPN de punto de** comprobación: [cómo configurar la configuración de Tunnel para Microsoft 365 y otras aplicaciones SaaS](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="related-articles"></a>Artículos relacionados

[Información general: Túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[Escenarios comunes de túnel dividido de VPN para Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[Proteger el tráfico Teams multimedia para el túnel dividido de VPN](microsoft-365-vpn-securing-teams.md)

[Consideraciones especiales para stream y eventos en directo en entornos VPN](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365 optimización del rendimiento para usuarios de China](microsoft-365-networking-china.md)

[Principios de conectividad de red de Microsoft 365](microsoft-365-network-connectivity-principles.md)

[Evaluar la conectividad de red de Microsoft 365](assessing-network-connectivity.md)

[Microsoft 365 de red y rendimiento](network-planning-and-performance.md)

[Formas alternativas para que los profesionales de seguridad y de TI logren controles de seguridad modernos en los escenarios de trabajo remoto específicos (blog del Equipo de Seguridad de Microsoft)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Mejorando el rendimiento de la VPN en Microsoft: usando perfiles de VPN de Windows 10 para permitir conexiones automáticas ](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Funcionando con VPN: cómo Microsoft mantiene conectado a su personal remoto](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Red global de Microsoft](/azure/networking/microsoft-global-network)
