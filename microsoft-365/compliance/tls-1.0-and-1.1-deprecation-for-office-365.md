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
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332683"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>Deshabilitar TLS 1.0 y 1.1 para Microsoft 365

> [!IMPORTANT]
> Hemos detenido temporalmente la deshabilitación de TLS 1.0 y 1.1 para clientes comerciales debido a COVID-19. A medida que las cadenas de suministro se han ajustado y algunos países abren una copia de seguridad, reiniciamos el lanzamiento de cumplimiento tls 1.2 el 15 de octubre de 2020. El lanzamiento continuará durante las siguientes semanas y meses.

A partir del 31 de octubre de 2018, los protocolos seguridad de la capa de transporte (TLS) 1.0 y 1.1 están en desuso para el servicio Microsoft 365 transporte. El efecto para los usuarios finales es mínimo. Este cambio se publicó durante más de dos años, con el primer anuncio público realizado en diciembre de 2017. Este artículo solo está pensado para cubrir el cliente local de Office 365 en relación con el servicio de Office 365, pero también puede aplicarse a problemas de TLS locales con Office y Office Online Server/Office Web Apps.

Para SharePoint y OneDrive, deberá actualizar y configurar .NET para admitir TLS 1.2. Para obtener información, [vea How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

## <a name="office-365-and-tls-overview"></a>Office 365 de TLS y de seguridad

El Office se basa en el servicio Windows web (WINHTTP) para enviar y recibir tráfico a través de protocolos TLS. El Office puede usar TLS 1.2 si el servicio web del equipo local puede usar TLS 1.2. Todos Office pueden usar protocolos TLS, ya que los protocolos TLS y SSL forman parte del sistema operativo y no son específicos del Office cliente.

### <a name="on-windows-8-and-later-versions"></a>En Windows 8 versiones posteriores

De forma predeterminada, los protocolos TLS 1.2 y 1.1 están disponibles si no hay dispositivos de red configurados para rechazar el tráfico tls 1.2.

### <a name="on-windows-7"></a>En Windows 7

Los protocolos TLS 1.1 y 1.2 no están disponibles sin la actualización [de KB 3140245.](https://support.microsoft.com/help/3140245) La actualización soluciona este problema y agrega la siguiente subclave del Registro:

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 7 usuarios que no tienen esta actualización se ven afectados a partir del 31 de octubre de 2018. [KB 3140245](https://support.microsoft.com/help/3140245) tiene detalles sobre cómo cambiar la configuración de WINHTTP para habilitar los protocolos TLS.

#### <a name="more-information"></a>Más información

El valor de la clave del Registro **DefaultSecureProtocols** que describe el artículo de KB determina qué protocolos de red se pueden usar:

|Valor DefaultSecureProtocols|Protocolo habilitado|
|-|-|
|0x00000008|Habilita SSL 2.0 de manera predeterminada|
|0x00000020|Habilita SSL 3.0 de manera predeterminada|
|0x00000080|Habilita TLS 1.0 de manera predeterminada|
|0x00000200|Habilita TLS 1.1 de manera predeterminada|
|0x00000800|Habilita TLS 1.2 de manera predeterminada|

## <a name="office-clients-and-tls-registry-keys"></a>Office clientes y claves del Registro TLS

Puede hacer referencia a [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306). Este es un artículo general para administradores de TI y es documentación oficial sobre el cambio de TLS 1.2.

En la tabla siguiente se muestran los valores de clave del Registro adecuados Office 365 clientes después del 31 de octubre de 2018.

|Protocolos habilitados para Office 365 servicio después del 31 de octubre de 2018|Valor hexadecimal|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> No use los protocolos SSL 2.0 y 3.0, que también se pueden establecer mediante la clave **DefaultSecureProtocols.** Ssl 2.0 y 3.0 se consideran protocolos obsoletos e inseguros. El procedimiento recomendado es terminar con el uso de SSL 2.0 y SSL 3.0, aunque la decisión de hacerlo depende en última instancia de lo que mejor se adapte a las necesidades del producto. Para obtener más información acerca de las vulnerabilidades de SSL 3.0, consulte [KB 3009008](https://support.microsoft.com/help/3009008).

Puede usar la calculadora de Windows predeterminada en modo programador para configurar los mismos valores de clave del Registro de referencia. Para obtener más información, vea [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).

Independientemente de si la actualización Windows 7 ([KB 3140245](https://support.microsoft.com/help/3140245)) está instalada o no, la subclave del Registro DefaultSecureProtocols no está presente y debe agregarse manualmente o a través de un objeto de directiva de grupo (GPO). Es decir, a menos que tenga que personalizar qué protocolos seguros están habilitados o restringidos, esta clave no es necesaria. Solo necesita la actualización Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)).

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>Actualizar y configurar el .NET Framework para admitir TLS 1.2

Deberá actualizar las aplicaciones que llamen Microsoft 365 a través de TLS 1.0 o TLS 1.1 para usar TLS 1.2. .NET 4.5 tiene como valor predeterminado TLS 1.1. Para actualizar la configuración de .NET, vea [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).

## <a name="more-information"></a>Más información

Para obtener más información, vea [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="references"></a>Referencias

Los siguientes recursos proporcionan instrucciones para asegurarse de que los clientes usan TLS 1.2 o una versión posterior y deshabilitar TLS 1.0 y 1.1:

- Si tiene clientes de Windows 7 que se conecten a Office 365, asegúrese de que TLS 1.2 sea el protocolo seguro predeterminado en WinHTTP en Windows. Para obtener más información, vea [KB 3140245- Update to enable TLS 1.1 and TLS 1.2 as default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).
- Para solucionar el uso débil de TLS mediante la eliminación de dependencias tls 1.0 y 1.1, consulte Compatibilidad con [TLS 1.2 en Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- [La nueva funcionalidad IIS](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) facilita la búsqueda de clientes en [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) y [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) que se conectan al servicio mediante el uso de protocolos de seguridad débiles.
- Obtenga más información sobre cómo [resolver el problema tls 1.0](https://www.microsoft.com/download/details.aspx?id=55266).
- Para obtener información general sobre nuestro enfoque de la seguridad, consulte el [Centro de confianza de Office 365](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Preparación para la degradación de TLS 1.0/1.1: Office 365 Skype Empresarial](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Guía de TLS de Exchange Server, parte 1: Preparación para TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Orientación TLS de Exchange Server Parte 2: Habilitación de TLS 1.2 e identificación de clientes que no lo utilicen](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Orientación TLS de Exchange Server Parte 3: Desactivar TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Habilitar la compatibilidad con TLS 1.1 y TLS 1.2 en Office Online Server](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

