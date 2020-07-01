---
title: TLS 1,0 y 1,1 en desuso para Office 365
description: Describe el desuso de TLS 1,0 y 1,1 para Office 365.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 611b6970c3ecb95f4cdf046b96a5e3aa9155391d
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937376"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>TLS 1,0 y 1,1 en desuso para Office 365

A partir del 31 de octubre de 2018, los protocolos de seguridad de la capa de transporte (TLS) 1,0 y 1,1 están en desuso para el servicio de Office 365. Se espera que el efecto de los usuarios finales sea mínimo. Este cambio se ha hecho público durante casi dos años, con el primer anuncio público realizado en diciembre de 2017. Este artículo solo se diseñó para cubrir el cliente local de Office 365 en relación con el servicio Office 365, pero también se puede aplicar a problemas de TLS locales con Office y Office Online Server/Office Web Apps.

## <a name="office-and-tls-overview"></a>Información general de Office y TLS

El cliente de Office se basa en el servicio Web de Windows (WINHTTP) para enviar y recibir tráfico a través de protocolos TLS. El cliente de Office puede usar TLS 1,2 Si el servicio Web del equipo local puede usar TLS 1,2. Todos los clientes de Office pueden usar protocolos TLS, ya que los protocolos TLS y SSL forman parte del sistema operativo y no son específicos del cliente de Office.

### <a name="on-windows-8-and-later-versions"></a>En Windows 8 y versiones posteriores

De forma predeterminada, los protocolos TLS 1,2 y 1,1 están disponibles si no hay ningún dispositivo de red configurado para rechazar el tráfico de TLS 1,2.

### <a name="on-windows-7"></a>En Windows 7

Los protocolos TLS 1,1 y 1,2 no están disponibles sin la actualización [KB 3140245](https://support.microsoft.com/help/3140245) . La actualización soluciona este problema y agrega la siguiente subclave del registro:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Los usuarios de Windows 7 que no tienen esta actualización se ven afectados desde el 31 de octubre de 2018. [KB 3140245](https://support.microsoft.com/help/3140245) tiene detalles sobre cómo cambiar la configuración de WinHTTP para habilitar los protocolos TLS.

#### <a name="more-information"></a>Más información

El valor de la clave del registro **DefaultSecureProtocols** que describe el artículo de KB determina qué protocolos de red se pueden usar:

|Valor DefaultSecureProtocols|Protocolo habilitado|
|-|-|
|0x00000008|Habilita SSL 2.0 de manera predeterminada|
|0x00000020|Habilita SSL 3.0 de manera predeterminada|
|0x00000080|Habilita TLS 1.0 de manera predeterminada|
|0x00000200|Habilita TLS 1.1 de manera predeterminada|
|0x00000800|Habilita TLS 1.2 de manera predeterminada|

## <a name="office-clients-and-tls-registry-keys"></a>Clientes de Office y claves de registro de TLS

Puede consultar [KB 4057306 preparar el uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306). Este es un artículo general para los administradores de ti y es documentación oficial sobre el cambio de TLS 1,2.

En la siguiente tabla se muestran los valores de clave del registro correspondientes en los clientes de Office 365 después del 31 de octubre de 2018.

|Protocolos habilitados para el servicio de Office 365 después del 31 de octubre de 2018|Valor hexadecimal|
|-|-|
|TLS 1,0 + 1,1 + 1,2|0x00000A80|
|TLS 1,1 + 1,2|0x00000A00|
|TLS 1,0 + 1,2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> No se recomienda usar los protocolos SSL 2,0 y 3,0, que también se pueden establecer mediante la clave **DefaultSecureProtocols** . SSL 2,0 y 3,0 se consideran protocolos en desuso. El procedimiento recomendado es finalizar el uso de SSL 2,0 y SSL 3,0, aunque la decisión de hacerlo en última instancia depende de lo que mejor se adapte a las necesidades del producto. Para obtener más información acerca de las vulnerabilidades de 3,0 de SSL, consulte [KB 3009008](https://support.microsoft.com/help/3009008).

Puede usar la calculadora de Windows predeterminada en el modo de programador para configurar los mismos valores de clave del registro de referencia. Para obtener más información, consulte [KB 3140245 Update para habilitar tls 1,1 y tls 1,2 como protocolos seguros predeterminados en WinHTTP en Windows](https://support.microsoft.com/help/3140245).

Independientemente de si la actualización de Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) está instalada o no, la subclave del registro DefaultSecureProtocols no está presente y debe agregarse de forma manual o a través de un objeto de directiva de grupo (GPO). Es decir, a menos que tenga que personalizar Qué protocolos seguros están habilitados o restringidos, esta clave no es necesaria. Solo necesita la actualización de Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).
