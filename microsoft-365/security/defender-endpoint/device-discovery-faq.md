---
title: Preguntas más frecuentes sobre detección de dispositivos
description: Buscar respuestas a preguntas más frecuentes (preguntas frecuentes) sobre la detección de dispositivos
keywords: detección de dispositivos, detección, pasiva, proactiva, red, visibilidad, servidor, estación de trabajo, incorporación, dispositivos no administrados
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 52d9a939a75e012181183d8a6419f44868d1e509
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61164075"
---
# <a name="device-discovery-frequently-asked-questions"></a>Preguntas más frecuentes sobre detección de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- - [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Encuentre respuestas a las preguntas más frecuentes (preguntas frecuentes) sobre la detección de dispositivos.

## <a name="what-is-basic-discovery-mode"></a>¿Qué es el modo de detección básico?
Este modo permite que todos los dispositivos integrados de Microsoft Defender para Endpoint recopile datos de red y detecte dispositivos vecinos. Los puntos de conexión incorporados recopilan eventos de la red de forma pasiva y extraen información del dispositivo de ellos. No se iniciará tráfico de red. Los puntos de conexión incorporados simplemente extraerán datos de cada tráfico de red que ve un dispositivo incorporado. Estos datos se usan para enumerar dispositivos no administrados en la red.


## <a name="can-i-disable-basic-discovery"></a>¿Puedo deshabilitar la detección básica?
Tienes la opción de desactivar la detección de dispositivos a través de la [página Características avanzadas.](advanced-features.md) Sin embargo, perderás visibilidad en dispositivos no administrados en la red. Ten en cuenta que SenseNDR.exe se seguirá ejecutando en los dispositivos incorporados independientemente de que la detección esté desactivada. 

## <a name="what-is-standard-discovery-mode"></a>¿Qué es el modo de detección estándar?
 En este modo, los puntos de conexión incorporados a Microsoft Defender para Endpoint pueden sondear activamente los dispositivos observados en la red para enriquecer los datos recopilados (con una cantidad insignificante de tráfico de red). Solo los dispositivos observados por el modo de detección básico se sondearán activamente en modo estándar. Este modo es muy recomendable para crear un inventario de dispositivos confiable y coherente. Si decide deshabilitar este modo y seleccionar el modo de detección básico, es probable que solo obtenga una visibilidad limitada de los puntos de conexión no administrados en la red.

 El modo estándar también aprovecha los protocolos comunes de detección que usan consultas de multidifusión en la red para encontrar aún más dispositivos, además de los que se han ovserved mediante el método pasivo.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>¿Puedo controlar qué dispositivos realizan la detección estándar?
 Puedes personalizar la lista de dispositivos que se usan para realizar la detección estándar. Puedes habilitar la detección estándar en todos los dispositivos incorporados que también admiten esta funcionalidad (actualmente solo Windows 10 dispositivos) o seleccionar un subconjunto o subconjuntos de los dispositivos especificando sus etiquetas de dispositivo. En este caso, todos los demás dispositivos se configurarán para ejecutar solo la detección básica. La configuración está disponible en la página configuración de detección de dispositivos.

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>¿Puedo excluir dispositivos no administrados de la lista de inventario de dispositivos?
Sí, puedes aplicar filtros para excluir dispositivos no administrados de la lista de inventario de dispositivos. También puede usar la columna de estado de incorporación en las consultas API para filtrar los dispositivos no administrados. 


## <a name="which-onboarded-devices-can-perform-discovery"></a>¿Qué dispositivos incorporados pueden realizar la detección?
 Los dispositivos incorporados que se Windows 10 versión 1809 o posterior, o Windows 11 pueden realizar la detección. Los servidores no pueden realizar la detección en este momento.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>¿Qué sucede si mis dispositivos incorporados están conectados a mi red doméstica o al punto de acceso público?
 El motor de detección distingue entre los eventos de red que se reciben en la red corporativa frente a fuera de la red corporativa. Al correlacionar los identificadores de red entre todos los clientes del inquilino, los eventos se diferencian entre los que se recibieron de redes privadas y redes corporativas. Por ejemplo, si la mayoría de los dispositivos de la organización informan de que están conectados al mismo nombre de red, con la misma puerta de enlace predeterminada y la misma dirección del servidor DHCP, se puede suponer que esta red es probablemente una red corporativa. Los dispositivos de red privada no aparecerán en el inventario y no se sondearán activamente.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>¿Qué protocolos está capturando y analizando?
 De forma predeterminada, todos los dispositivos incorporados que se ejecutan en Windows 10 versión 1809 o posterior, o Windows 11, capturan y analizan los siguientes protocolos: ARP, CDP, DHCP, DHCPv6, IP (encabezados), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (encabezados SYN), UDP (encabezados), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>¿Qué protocolos usa para el sondeo activo en la detección estándar?
 Cuando un dispositivo está configurado para ejecutar la detección estándar, los servicios expuestos se sondean mediante los siguientes protocolos: ARP, FTP, HTTP, HTTPS, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL, RPC, mDNS, DHCP, AFP, CrestonCIP, IphoneSync, WinRM, VNC, SLP

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>¿Cómo puedo excluir los destinos de ser sondeados con la detección estándar?
 Si hay dispositivos en la red que no deben ser sondeados activamente, también puedes definir una lista de exclusiones para evitar que se puedan examinar. La configuración está disponible en la página configuración de detección de dispositivos. 

>[!NOTE]
> Es posible que los dispositivos respondan a los intentos de detección de multidifusión en la red. Esos dispositivos se descubrirán pero no se sondean activamente. 

## <a name="can-i-exclude-devices-from-being-discovered"></a>¿Puedo excluir los dispositivos para que no se descubran?
 Como la detección de dispositivos usa métodos pasivos para detectar dispositivos en la red, cualquier dispositivo que se comunique con los dispositivos incorporados en la red corporativa se puede detectar y enumerar en el inventario. Solo puedes excluir dispositivos del sondeo activo.

## <a name="how-frequent-is-the-active-probing"></a>¿Qué frecuencia tiene el sondeo activo?
 Los dispositivos se sondearán activamente cuando se observan cambios en las características del dispositivo para asegurarse de que la información existente esté actualizada (normalmente, los dispositivos sondeados no más de una vez en un período de tres semanas)

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Mi herramienta de seguridad ha creado una alerta UnicastScanner.ps1 actividad de detección de puertos iniciada por ella, ¿qué debo hacer?
 Microsoft firma los scripts de sondeo activos y son seguros. Puede agregar la siguiente ruta de acceso a la lista de exclusión: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps1`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>¿Cuál es la cantidad de tráfico que genera el sondeo activo de detección estándar?
 El sondeo activo puede generar hasta 50 Kb de tráfico entre el dispositivo incorporado y el dispositivo sondeado, cada intento de sondeo

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>¿Por qué hay una discrepancia entre los dispositivos "se pueden incorporar" en el inventario de dispositivos y el número de "dispositivos que se incorporarán" en el icono del panel?
Es posible que observes diferencias entre el número de dispositivos enumerados en "se puede incorporar" en el inventario de dispositivos, la recomendación de seguridad "incorporación a Microsoft Defender para endpoint" y el widget de panel "dispositivos para incorporar".

 La recomendación de seguridad y el widget de panel son para dispositivos estables en la red; excluyendo dispositivos efímeros, dispositivos invitados y otros. La idea es recomendar en dispositivos persistentes, lo que también implica en la puntuación de seguridad general de la organización.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>¿Puedo incorporar dispositivos no administrados que se encontraron?
 Sí. Puedes incorporar dispositivos no administrados manualmente. Los puntos de conexión no administrados de la red introducen vulnerabilidades y riesgos en la red. Incorporarlos al servicio puede aumentar la visibilidad de seguridad en ellos. 

## <a name="ive-noticed-that-unmanaged-device-health-state-is-always-active-why-is-that"></a>He notado que el estado de mantenimiento del dispositivo no administrado siempre es "Activo", ¿por qué es eso?
Temporalmente, el estado de mantenimiento del dispositivo no administrado será "Activo" durante el período de retención estándar del inventario de dispositivos, independientemente de su estado real.


## <a name="does-standard-discovery-look-like-malicious-network-activity"></a>¿La detección estándar parece una actividad de red malintencionada?
Al considerar la detección estándar, es posible que se pregunte acerca de las implicaciones del sondeo y, específicamente, si las herramientas de seguridad pueden sospechar que dicha actividad es malintencionada. En la siguiente subsección se explica por qué, en casi todos los casos, las organizaciones no deben tener ninguna preocupación acerca de la habilitación de la detección estándar.  

### <a name="probing-is-distributed-across-all-windows-devices-on-the-network"></a>El sondeo se distribuye en todos Windows dispositivos de la red
A diferencia de la actividad malintencionada, que normalmente examinaría toda la red desde un pequeño número de dispositivos en peligro, el sondeo de detección estándar de Microsoft Defender para endpoint se inicia desde todos los dispositivos Windows integrados, lo que hace que la actividad sea benigna y no anómala. El sondeo se administra de forma centralizada desde la nube para equilibrar el intento de sondeo entre todos los dispositivos integrados admitidos en la red.  

### <a name="active-probing-generates-negligible-amount-of-extra-traffic"></a>El sondeo activo genera una cantidad insignificante de tráfico adicional
Normalmente, los dispositivos no administrados no se sondearía más de una vez en un período de tres semanas y generarían menos de 50 KB de tráfico. Normalmente, la actividad malintencionada incluye intentos de sondeo repetitivos elevados y, en algunos casos, exfiltración de datos que genera una cantidad significativa de tráfico de red que las herramientas de supervisión de red pueden identificar como una anomalía. 

### <a name="your-windows-device-already-runs-active-discovery"></a>El dispositivo Windows ya ejecuta la detección activa
Las capacidades de detección activa siempre se han incrustado en el sistema operativo Windows, para buscar dispositivos, puntos de conexión e impresoras cercanos, para facilitar las experiencias de "plug and play" y el uso compartido de archivos entre puntos de conexión de la red. Se implementa una funcionalidad similar en dispositivos móviles, equipos de red y aplicaciones de inventario por nombrar algunas.  

La detección estándar usa los mismos métodos de detección para identificar dispositivos y para tener una visibilidad unificada para todos los dispositivos de la red en el Microsoft 365 Defender inventario de dispositivos. Por ejemplo: la detección estándar identifica los puntos de conexión cercanos en la red de la misma forma Windows listas de impresoras disponibles en la red. 

Las herramientas de seguridad y supervisión de red son diferentes a estas actividades realizadas por los dispositivos de la red. 

### <a name="only-unmanaged-devices-are-being-probed"></a>Solo se están sondando dispositivos no administrados
Las capacidades de detección de dispositivos se han creado solo para detectar e identificar dispositivos no administrados en la red. Esto significa que los dispositivos detectados anteriormente que ya están incorporados con Microsoft Defender para Endpoint no se sondean. 

### <a name="you-can-exclude-network-lures-from-active-probing"></a>Puede excluir los señuelos de red del sondeo activo
La detección estándar admite la exclusión de dispositivos o intervalos (subredes) del sondeo activo. Si tienes señuelos de red implementados, puedes usar la configuración de detección de dispositivos para definir exclusiones basadas en direcciones IP o subredes (un rango de direcciones IP). La definición de estas exclusiones garantizará que esos dispositivos no se sondeerán activamente y no se les avisará. Estos dispositivos solo se detectarán con métodos pasivos (similar al modo de detección básico).
