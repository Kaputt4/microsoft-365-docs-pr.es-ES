---
title: Preguntas más frecuentes sobre detección de dispositivos
description: Buscar respuestas a preguntas más frecuentes (preguntas frecuentes) sobre la detección de dispositivos
keywords: detección de dispositivos, detección, pasiva, proactiva, red, visibilidad, servidor, estación de trabajo, incorporación, dispositivos no administrados
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c61e69b5c8d414ab229fa8bf64eb657a6e40304
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245965"
---
# <a name="device-discovery-frequently-asked-questions"></a>Preguntas más frecuentes sobre detección de dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Encuentre respuestas a las preguntas más frecuentes (preguntas frecuentes) sobre la detección de dispositivos.

## <a name="what-is-basic-discovery-mode"></a>¿Qué es el modo de detección básico?
Este modo permite que todos los dispositivos integrados de Microsoft Defender para Endpoint recopile datos de red y detecte dispositivos vecinos. Los puntos de conexión incorporados recopilan eventos de la red de forma pasiva y extraen información del dispositivo de ellos. No se iniciará tráfico de red. Los puntos de conexión incorporados simplemente extraerán datos de cada tráfico de red que ve un dispositivo incorporado. Estos datos se usan para enumerar dispositivos no administrados en la red.

## <a name="can-i-disable-basic-discovery"></a>¿Puedo deshabilitar la detección básica?
Tienes la opción de desactivar la detección de dispositivos a través de la [página Características avanzadas.](advanced-features.md) Sin embargo, perderás visibilidad en dispositivos no administrados en la red. 

## <a name="what-is-standard-discovery-mode"></a>¿Qué es el modo de detección estándar?
 En este modo, los puntos de conexión incorporados a Microsoft Defender para Endpoint pueden sondear activamente los dispositivos observados en la red para enriquecer los datos recopilados (con una cantidad insignificante de tráfico de red). Este modo es muy recomendable para crear un inventario de dispositivos confiable y coherente. Si decide deshabilitar este modo y seleccionar el modo de detección básico, es probable que solo obtenga una visibilidad limitada de los puntos de conexión no administrados en la red.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>¿Puedo controlar qué dispositivos realizan la detección estándar?
 Puedes personalizar la lista de dispositivos que se usan para realizar la detección estándar. Puedes habilitar la detección estándar en todos los dispositivos incorporados que también admiten esta funcionalidad (actualmente solo Windows 10 dispositivos) o seleccionar un subconjunto o subconjuntos de los dispositivos especificando sus etiquetas de dispositivo. En este caso, todos los demás dispositivos se configurarán para ejecutar solo la detección básica. La configuración está disponible en la página configuración de detección de dispositivos.

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>¿Puedo excluir dispositivos no administrados de la lista de inventario de dispositivos?
Sí, puedes aplicar filtros que excluyan los dispositivos no administrados de la lista de inventario de dispositivos. También puede usar la columna de estado de incorporación en las consultas API para filtrar los dispositivos no administrados. 


## <a name="which-onboarded-devices-can-perform-discovery"></a>¿Qué dispositivos incorporados pueden realizar la detección?
 Los dispositivos incorporados que se Windows 10 versión 1809 o posterior pueden realizar la detección.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>¿Qué sucede si mis dispositivos incorporados están conectados a mi red doméstica o al punto de acceso público?
 El motor de detección distingue entre los eventos de red que se reciben en la red corporativa frente a fuera de la red corporativa. Al correlacionar los identificadores de red entre todos los clientes del inquilino, los eventos se diferencian entre los que se recibieron de redes privadas y redes corporativas. Por ejemplo, si la mayoría de los dispositivos del informe de red informan de que están conectados al mismo nombre de red, con la misma puerta de enlace predeterminada y la misma dirección del servidor DHCP, se puede suponer que esta red es probablemente una red corporativa. Los dispositivos de red privada no aparecerán en el inventario y no se sondearán activamente.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>¿Qué protocolos está capturando y analizando?
 De forma predeterminada, todos los dispositivos incorporados que se ejecutan en Windows 10 versión 1809 o posterior capturan y analizan los siguientes protocolos: ARP, CDP, DHCP, DHCPv6, IP (encabezados), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (encabezados), UDP (encabezados), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>¿Qué protocolos usa para el sondeo activo en la detección estándar?
 Cuando un dispositivo está configurado para ejecutar la detección estándar, los servicios expuestos se sondean mediante los siguientes protocolos: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>¿Cómo puedo excluir los destinos de ser sondeados con la detección estándar?
 Si hay dispositivos en la red que no deben ser sondeados activamente, también puedes definir una lista de exclusiones para evitar que se puedan examinar. La configuración está disponible en la página configuración de detección de dispositivos.

## <a name="can-i-exclude-devices-from-being-discovered"></a>¿Puedo excluir los dispositivos para que no se descubran?
 Como la detección de dispositivos usa métodos pasivos para detectar dispositivos en la red, cualquier dispositivo que se comunique con los dispositivos incorporados en la red corporativa se puede detectar y enumerar en el inventario. Solo puedes excluir dispositivos del sondeo activo.

## <a name="how-frequent-is-the-active-probing"></a>¿Qué frecuencia tiene el sondeo activo?
 Los dispositivos se sondearán activamente cuando se observan cambios en las características del dispositivo (cada 1 a 3 semanas) para asegurarse de que la información existente esté actualizada.

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Mi herramienta de seguridad ha creado una alerta UnicastScanner.ps1 actividad de detección de puertos iniciada por ella, ¿qué debo hacer?
 Microsoft firma los scripts de sondeo activos y son seguros. Puede agregar la siguiente ruta de acceso a la lista de exclusión: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>¿Cuál es la cantidad de tráfico que genera el sondeo activo de detección estándar?
 El sondeo activo puede generar hasta 5K de tráfico entre el dispositivo incorporado y el dispositivo sondeado, cada intento de sondeo

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>¿Por qué hay una discrepancia entre los dispositivos "se pueden incorporar" en el inventario de dispositivos y el número de "dispositivos que se incorporarán" en el icono del panel?
Es posible que observes diferencias entre el número de dispositivos enumerados en "se puede incorporar" en el inventario de dispositivos, la recomendación de seguridad "incorporación a Microsoft Defender para endpoint" y el widget de panel "dispositivos para incorporar".

 La recomendación de seguridad y el widget de panel son para dispositivos estables en la red; excluyendo dispositivos efímeros, dispositivos invitados y otros. La idea es recomendar en dispositivos persistentes, lo que también implica en la puntuación de seguridad general de la organización.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>¿Puedo incorporar dispositivos no administrados que se encontraron?
 Sí. Los puntos de conexión no administrados de la red introducen vulnerabilidades y riesgos en la red. Incorporarlos al servicio puede aumentar la visibilidad de seguridad en ellos. 


