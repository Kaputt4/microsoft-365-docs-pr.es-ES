---
title: Desuso de TLS 1.0 y 1.1 para Office 365
description: Describe el desuso de TLS 1.0 y 1.1 para Office 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777063"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>Desuso de TLS 1.0 y 1.1 para Office 365
> [!IMPORTANT]
> Hemos detenido temporalmente la aplicación de desuso de TLS 1.0 y 1.1 para los clientes comerciales debido a COVID-19, pero a medida que las cadenas de suministro se han ajustado y se abre una copia de seguridad en determinados países, estamos restablecendo la aplicación de TLS para que comience el 15 de octubre de 2020 y la implementación continuará en las siguientes semanas y meses. 

A partir del 31 de octubre de 2018, los protocolos Seguridad de la capa de transporte (TLS) 1.0 y 1.1 están en desuso para el servicio de Office 365. Se espera que el efecto para los usuarios finales sea mínimo. Este cambio se ha hecho público durante más de dos años, con el primer anuncio público realizado en diciembre de 2017. Este artículo solo está pensado para cubrir el cliente local de Office 365 en relación con el servicio de Office 365, pero también puede aplicarse a problemas de TLS locales con Office y Office Online Server/Office Web Apps.

## <a name="office-and-tls-overview"></a>Información general sobre Office y TLS

El cliente de Office se basa en el servicio web de Windows (WINHTTP) para enviar y recibir tráfico a través de protocolos TLS. El cliente de Office puede usar TLS 1.2 si el servicio web del equipo local puede usar TLS 1.2. Todos los clientes de Office pueden usar protocolos TLS, ya que los protocolos TLS y SSL forman parte del sistema operativo y no son específicos del cliente de Office.

### <a name="on-windows-8-and-later-versions"></a>En Windows 8 y versiones posteriores

De forma predeterminada, los protocolos TLS 1.2 y 1.1 están disponibles si no hay ningún dispositivo de red configurado para rechazar el tráfico TLS 1.2.

### <a name="on-windows-7"></a>En Windows 7

Los protocolos TLS 1.1 y 1.2 no están disponibles sin la actualización [kb 3140245.](https://support.microsoft.com/help/3140245) La actualización soluciona este problema y agrega la siguiente subclave del Registro:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Los usuarios de Windows 7 que no tengan esta actualización se verán afectados a partir del 31 de octubre de 2018. [KB 3140245](https://support.microsoft.com/help/3140245) tiene detalles sobre cómo cambiar la configuración de WINHTTP para habilitar protocolos TLS.

#### <a name="more-information"></a>Más información

El valor de la clave del Registro **DefaultSecureProtocols** que describe el artículo de KB determina qué protocolos de red se pueden usar:

|Valor defaultSecureProtocols|Protocolo habilitado|
|-|-|
|0x00000008|Habilita SSL 2.0 de manera predeterminada|
|0x00000020|Habilita SSL 3.0 de manera predeterminada|
|0x00000080|Habilita TLS 1.0 de manera predeterminada|
|0x00000200|Habilita TLS 1.1 de manera predeterminada|
|0x00000800|Habilita TLS 1.2 de manera predeterminada|

## <a name="office-clients-and-tls-registry-keys"></a>Clientes de Office y claves del Registro TLS

Puede consultar KB 4057306 Preparación para el uso obligatorio de [TLS 1.2 en Office 365.](https://support.microsoft.com/help/4057306) Este es un artículo general para administradores de TI y su documentación oficial sobre el cambio de TLS 1.2.

En la tabla siguiente se muestran los valores de clave del Registro adecuados en los clientes de Office 365 después del 31 de octubre de 2018.

|Protocolos habilitados para el servicio de Office 365 después del 31 de octubre de 2018|Valor hexadecimal|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> No se recomienda usar los protocolos SSL 2.0 y 3.0, que también se pueden establecer mediante la clave **DefaultSecureProtocols.** SSL 2.0 y 3.0 se consideran protocolos en desuso. El procedimiento recomendado es finalizar el uso de SSL 2.0 y SSL 3.0, aunque la decisión de hacerlo depende en última instancia de lo que mejor se adapte a las necesidades de su producto. Para obtener más información acerca de las vulnerabilidades de SSL 3.0, consulte [KB 3009008](https://support.microsoft.com/help/3009008).

Puedes usar la Calculadora de Windows predeterminada en modo programador para configurar los mismos valores de clave del Registro de referencia. Para obtener más información, consulte [KB 3140245 Update para habilitar TLS 1.1 y TLS 1.2](https://support.microsoft.com/help/3140245)como protocolos seguros predeterminados en WinHTTP en Windows.

Independientemente de si la actualización de Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) está instalada o no, la subclave del Registro DefaultSecureProtocols no está presente y debe agregarse manualmente o a través de un objeto de directiva de grupo (GPO). Es decir, a menos que tenga que personalizar qué protocolos seguros están habilitados o restringidos, esta clave no es necesaria. Solo necesitas la actualización de Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)
