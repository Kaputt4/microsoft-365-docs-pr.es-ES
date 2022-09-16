---
title: Preguntas más frecuentes sobre la detección de dispositivos
description: Búsqueda de respuestas a las preguntas más frecuentes (P+F) sobre la detección de dispositivos
keywords: detección, detección, pasiva, proactiva, red, visibilidad, servidor, estación de trabajo, dispositivos incorporados y no administrados
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 62a00f3ebfd981d2263c5adc2028983c68499125
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67736352"
---
# <a name="device-discovery-frequently-asked-questions"></a>Preguntas más frecuentes sobre la detección de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- - [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Encuentre respuestas a las preguntas más frecuentes sobre la detección de dispositivos.

## <a name="what-is-basic-discovery-mode"></a>¿Qué es el modo de detección básico?

Este modo permite a cada Microsoft Defender para punto de conexión dispositivo incorporado recopilar datos de red y detectar dispositivos vecinos. Los puntos de conexión incorporados recopilan eventos de forma pasiva en la red y extraen información del dispositivo de ellos. No se iniciará ningún tráfico de red. Los puntos de conexión incorporados simplemente extraerán datos de cada tráfico de red que vea un dispositivo incorporado. Estos datos se usan para enumerar dispositivos no administrados en la red.

## <a name="can-i-disable-basic-discovery"></a>¿Puedo deshabilitar la detección básica?

Tiene la opción de desactivar la detección de dispositivos a través de la página [Características avanzadas](advanced-features.md) . Sin embargo, perderá visibilidad en los dispositivos no administrados de la red. Tenga en cuenta que SenseNDR.exe seguirá ejecutándose en los dispositivos incorporados, independientemente de que la detección esté desactivada. 

## <a name="what-is-standard-discovery-mode"></a>¿Qué es el modo de detección estándar?

En este modo, los puntos de conexión incorporados a Microsoft Defender para punto de conexión pueden sondear activamente los dispositivos observados en la red para enriquecer los datos recopilados (con una cantidad insignificante de tráfico de red). Solo los dispositivos observados por el modo de detección básico se sondearán activamente en modo estándar. Este modo es muy recomendable para crear un inventario de dispositivos confiable y coherente. Si decide deshabilitar este modo y seleccionar Modo de detección básico, es probable que solo obtenga visibilidad limitada de los puntos de conexión no administrados en la red.

 El modo estándar también aprovecha los protocolos de detección comunes que usan consultas de multidifusión en la red para encontrar aún más dispositivos, además de los que se observaron mediante el método pasivo.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>¿Puedo controlar qué dispositivos realizan la detección estándar?

Puede personalizar la lista de dispositivos que se usan para realizar la detección estándar. Puede habilitar la detección estándar en todos los dispositivos incorporados que también admiten esta funcionalidad (actualmente Windows 10 o versiones posteriores y solo dispositivos windows server 2019 o posteriores) o seleccionar un subconjunto o subconjuntos de los dispositivos especificando sus etiquetas de dispositivo. En este caso, todos los demás dispositivos se configurarán para ejecutar solo la detección básica. La configuración está disponible en la página configuración de detección de dispositivos.

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>¿Puedo excluir dispositivos no administrados de la lista de inventario de dispositivos?

Sí, puede aplicar filtros para excluir dispositivos no administrados de la lista de inventario de dispositivos. También puede usar la columna de estado de incorporación en consultas de API para filtrar dispositivos no administrados.

## <a name="which-onboarded-devices-can-perform-discovery"></a>¿Qué dispositivos incorporados pueden realizar la detección?

Los dispositivos incorporados que se ejecutan en Windows 10 versión 1809 o posterior, Windows 11, Windows Server 2019 o Windows Server 2022 pueden realizar la detección.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>¿Qué ocurre si mis dispositivos incorporados están conectados a mi red doméstica o al punto de acceso público?

El motor de detección distingue entre los eventos de red que se reciben en la red corporativa y fuera de la red corporativa. Al correlacionar los identificadores de red entre todos los clientes del inquilino, los eventos se diferencian entre los que se recibieron de redes privadas y redes corporativas. Por ejemplo, si la mayoría de los dispositivos de la organización informan de que están conectados al mismo nombre de red, con la misma puerta de enlace predeterminada y la misma dirección del servidor DHCP, se puede suponer que esta red es probablemente una red corporativa. Los dispositivos de red privada no aparecerán en el inventario y no se sondearán activamente.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>¿Qué protocolos está capturando y analizando?

De forma predeterminada, todos los dispositivos incorporados que se ejecutan en Windows 10 versión 1809 o posterior, Windows 11, Windows Server 2019 o Windows Server 2022 capturan y analizan los protocolos siguientes: ARP, CDP, DHCP, DHCPv6, IP (encabezados), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (encabezados SYN), UDP (encabezados), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>¿Qué protocolos usa para el sondeo activo en la detección estándar?
Cuando un dispositivo está configurado para ejecutar la detección estándar, los servicios expuestos se sondean mediante los siguientes protocolos: ARP, FTP, HTTP, HTTPS, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL, RPC, mDNS, DHCP, AFP, CrestonCIP, IphoneSync, WinRM, VNC, SLP, LDAP


## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>¿Cómo puedo excluir los destinos de que se sondean con la detección estándar?

Si hay dispositivos en la red que no se deben sondear activamente, también puede definir una lista de exclusiones para evitar que se examinen. La configuración está disponible en la página configuración de detección de dispositivos.

> [!NOTE]
> Es posible que los dispositivos sigan respondiendo a los intentos de detección de multidifusión en la red. Esos dispositivos se detectarán, pero no se sondearán activamente. 

## <a name="can-i-exclude-devices-from-being-discovered"></a>¿Puedo excluir los dispositivos de que se detecten?

A medida que la detección de dispositivos usa métodos pasivos para detectar dispositivos en la red, cualquier dispositivo que se comunique con los dispositivos incorporados en la red corporativa se puede detectar y enumerar en el inventario. Solo puede excluir dispositivos del sondeo activo.

## <a name="how-frequent-is-the-active-probing"></a>¿Con qué frecuencia es el sondeo activo?

Los dispositivos se sondearán activamente cuando se observen cambios en las características del dispositivo para asegurarse de que la información existente está actualizada (normalmente, los dispositivos sondean no más de una vez en un período de tres semanas).

## <a name="my-security-tool-raised-alert-on-unicastscannerps1--psscript_guidps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Mi herramienta de seguridad ha generado una alerta en UnicastScanner.ps1/PSScript_{GUID}.ps1 o la actividad de examen de puertos iniciada por ella, ¿qué debo hacer?

Los scripts de sondeo activos están firmados por Microsoft y son seguros. Puede agregar la siguiente ruta de acceso a la lista de exclusión: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps1`

## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>¿Cuál es la cantidad de tráfico que genera el sondeo activo de detección estándar?

El sondeo activo puede generar hasta 50 Kb de tráfico entre el dispositivo incorporado y el dispositivo sondeado, cada intento de sondeo

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>¿Por qué hay una discrepancia entre los dispositivos "se pueden incorporar" en el inventario de dispositivos y el número de "dispositivos que se van a incorporar" en el icono del panel?

Es posible que observe diferencias entre el número de dispositivos enumerados en "se puede incorporar" en el inventario de dispositivos, la recomendación de seguridad "incorporar a Microsoft Defender para punto de conexión" y el widget de panel "dispositivos para incorporar".

 La recomendación de seguridad y el widget del panel son para dispositivos que son estables en la red; excluyendo dispositivos efímeros, dispositivos invitados y otros. La idea es recomendar en dispositivos persistentes, lo que también implica la puntuación de seguridad general de la organización.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>¿Puedo incorporar dispositivos no administrados que se encontraron?

Sí. Puede incorporar dispositivos no administrados manualmente. Los puntos de conexión no administrados de la red presentan vulnerabilidades y riesgos en la red. Incorporarlos al servicio puede aumentar la visibilidad de seguridad en ellos.

## <a name="ive-noticed-that-unmanaged-device-health-state-is-always-active-why-is-that"></a>He observado que el estado de mantenimiento del dispositivo no administrado siempre es "Activo", ¿por qué es así?

Temporalmente, el estado de mantenimiento del dispositivo no administrado será "Activo" durante el período de retención estándar del inventario de dispositivos, independientemente de su estado real.

## <a name="does-standard-discovery-look-like-malicious-network-activity"></a>¿La detección estándar es similar a la actividad de red malintencionada?

Al considerar la detección estándar, es posible que se pregunte sobre las implicaciones del sondeo y, en concreto, si las herramientas de seguridad podrían sospechar que dicha actividad es malintencionada. En la subsección siguiente se explica por qué, en casi todos los casos, las organizaciones no deben preocuparse por habilitar la detección estándar.  

### <a name="probing-is-distributed-across-all-windows-devices-on-the-network"></a>El sondeo se distribuye entre todos los dispositivos Windows de la red

A diferencia de la actividad malintencionada, que normalmente examinaría toda la red desde un pequeño número de dispositivos en peligro, el sondeo de detección estándar de Microsoft Defender para punto de conexión se inicia desde todos los dispositivos Windows incorporados, lo que hace que la actividad sea benigna y no anómala. El sondeo se administra de forma centralizada desde la nube para equilibrar el intento de sondeo entre todos los dispositivos incorporados admitidos en la red.  

### <a name="active-probing-generates-negligible-amount-of-extra-traffic"></a>El sondeo activo genera una cantidad insignificante de tráfico adicional.

Los dispositivos no administrados normalmente se sondean no más de una vez en un período de tres semanas y generan menos de 50 KB de tráfico. La actividad malintencionada suele incluir intentos de sondeo repetitivos elevados y, en algunos casos, filtración de datos que genera una cantidad significativa de tráfico de red que se puede identificar como una anomalía mediante las herramientas de supervisión de red.

### <a name="your-windows-device-already-runs-active-discovery"></a>El dispositivo Windows ya ejecuta la detección activa

Las funcionalidades de detección activa siempre se han insertado en el sistema operativo Windows, para encontrar dispositivos, puntos de conexión e impresoras cercanos, para facilitar las experiencias de "plug and play" y el uso compartido de archivos entre los puntos de conexión de la red. Una funcionalidad similar se implementa en dispositivos móviles, equipos de red y aplicaciones de inventario solo por nombrar algunos.  

La detección estándar usa los mismos métodos de detección para identificar dispositivos y tener una visibilidad unificada de todos los dispositivos de la red en el inventario de dispositivos Microsoft 365 Defender. Por ejemplo: la detección estándar identifica los puntos de conexión cercanos de la red de la misma manera que Windows muestra las impresoras disponibles en la red. 

Las herramientas de seguridad y supervisión de red son diferentes a las actividades que realizan los dispositivos de la red. 

### <a name="only-unmanaged-devices-are-being-probed"></a>Solo se están sondeando dispositivos no administrados

Las funcionalidades de detección de dispositivos se han creado para detectar e identificar solo dispositivos no administrados en la red. Esto significa que los dispositivos detectados anteriormente que ya están incorporados con Microsoft Defender para punto de conexión no se sondean.

### <a name="you-can-exclude-network-lures-from-active-probing"></a>Puede excluir los señuelos de red del sondeo activo.

La detección estándar admite la exclusión de dispositivos o intervalos (subredes) del sondeo activo. Si tiene señuelos de red implementados, puede usar la configuración de detección de dispositivos para definir exclusiones basadas en direcciones IP o subredes (un intervalo de direcciones IP). La definición de esas exclusiones garantizará que esos dispositivos no se sondeen activamente y no se alertarán. Esos dispositivos se detectarán solo mediante métodos pasivos (similares al modo de detección básico).
