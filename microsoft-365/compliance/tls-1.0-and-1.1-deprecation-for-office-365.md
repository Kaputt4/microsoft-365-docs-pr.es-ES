---
title: Deshabilitar TLS 1.0 y 1.1 para Microsoft 365
description: Describe la desusación y deshabilitación de TLS 1.0 y 1.1 para Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 3d44e178d351942b4a178ddc1954ddd839665639
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919306"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Deshabilitar TLS 1.0 y 1.1 para Microsoft 365

> [!IMPORTANT]
> Hemos detenido temporalmente la deshabilitación de TLS 1.0 y 1.1 para clientes comerciales debido a COVID-19. A medida que las cadenas de suministro se han ajustado y algunos países abren una copia de seguridad, reiniciamos el lanzamiento de cumplimiento tls 1.2 el 15 de octubre de 2020. El lanzamiento continuará durante las siguientes semanas y meses.

A partir del 31 de octubre de 2018, los protocolos seguridad de la capa de transporte (TLS) 1.0 y 1.1 están en desuso para el servicio de Microsoft 365. El efecto para los usuarios finales es mínimo. Este cambio se publicó durante más de dos años, con el primer anuncio público realizado en diciembre de 2017. Este artículo solo está pensado para cubrir el cliente local de Office 365 en relación con el servicio de Office 365, pero también puede aplicarse a problemas de TLS locales con Office y Office Online Server/Office Web Apps.

Para SharePoint y OneDrive, deberá actualizar y configurar .NET para admitir TLS 1.2. Para obtener información, [vea How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

## <a name="office-365-and-tls-overview"></a>Introducción a Office 365 y TLS

El cliente de Office se basa en el servicio web de Windows (WINHTTP) para enviar y recibir tráfico a través de protocolos TLS. El cliente de Office puede usar TLS 1.2 si el servicio web del equipo local puede usar TLS 1.2. Todos los clientes de Office pueden usar protocolos TLS, ya que los protocolos TLS y SSL forman parte del sistema operativo y no son específicos del cliente de Office.

### <a name="on-windows-8-and-later-versions"></a>En Windows 8 y versiones posteriores

De forma predeterminada, los protocolos TLS 1.2 y 1.1 están disponibles si no hay dispositivos de red configurados para rechazar el tráfico tls 1.2.

### <a name="on-windows-7"></a>En Windows 7

Los protocolos TLS 1.1 y 1.2 no están disponibles sin la actualización [de KB 3140245.](https://support.microsoft.com/help/3140245) La actualización soluciona este problema y agrega la siguiente subclave del Registro:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Los usuarios de Windows 7 que no tienen esta actualización se ven afectados a partir del 31 de octubre de 2018. [KB 3140245](https://support.microsoft.com/help/3140245) tiene detalles sobre cómo cambiar la configuración de WINHTTP para habilitar los protocolos TLS.

#### <a name="more-information"></a>Más información

El valor de la clave del Registro **DefaultSecureProtocols** que describe el artículo de KB determina qué protocolos de red se pueden usar:

|Valor DefaultSecureProtocols|Protocolo habilitado|
|-|-|
|0x00000008|Habilita SSL 2.0 de manera predeterminada|
|0x00000020|Habilita SSL 3.0 de manera predeterminada|
|0x00000080|Habilita TLS 1.0 de manera predeterminada|
|0x00000200|Habilita TLS 1.1 de manera predeterminada|
|0x00000800|Habilita TLS 1.2 de manera predeterminada|

## <a name="office-clients-and-tls-registry-keys"></a>Clientes de Office y claves del Registro TLS

Puede hacer referencia [a KB 4057306 Preparar el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/help/4057306). Este es un artículo general para administradores de TI y es documentación oficial sobre el cambio de TLS 1.2.

En la tabla siguiente se muestran los valores de clave del Registro adecuados en los clientes de Office 365 después del 31 de octubre de 2018.

|Protocolos habilitados para el servicio de Office 365 después del 31 de octubre de 2018|Valor hexadecimal|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> No use los protocolos SSL 2.0 y 3.0, que también se pueden establecer mediante la clave **DefaultSecureProtocols.** Ssl 2.0 y 3.0 se consideran protocolos obsoletos e inseguros. El procedimiento recomendado es terminar con el uso de SSL 2.0 y SSL 3.0, aunque la decisión de hacerlo depende en última instancia de lo que mejor se adapte a las necesidades del producto. Para obtener más información acerca de las vulnerabilidades de SSL 3.0, consulte [KB 3009008](https://support.microsoft.com/help/3009008).

Puedes usar la Calculadora de Windows predeterminada en modo programador para configurar los mismos valores de clave del Registro de referencia. Para obtener más información, consulte [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).

Independientemente de si la actualización de Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) está instalada o no, la subclave del Registro DefaultSecureProtocols no está presente y debe agregarse manualmente o a través de un objeto de directiva de grupo (GPO). Es decir, a menos que tenga que personalizar qué protocolos seguros están habilitados o restringidos, esta clave no es necesaria. Solo necesitas la actualización de Windows 7 SP1 ([KB 3140245).](https://support.microsoft.com/help/3140245)

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Actualizar y configurar el .NET Framework para admitir TLS 1.2

Deberá actualizar las aplicaciones que llaman a las API de Microsoft 365 a través de TLS 1.0 o TLS 1.1 para usar TLS 1.2. .NET 4.5 tiene como valor predeterminado TLS 1.1. Para actualizar la configuración de .NET, vea [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

## <a name="more-information"></a>Más información

Para obtener más información, vea [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).