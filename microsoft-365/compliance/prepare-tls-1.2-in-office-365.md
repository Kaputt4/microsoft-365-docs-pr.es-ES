---
title: Preparación para TLS 1.2 en Office 365 y Office 365 GCC
description: Cómo prepararse para usar TLS 1.2 en todas las combinaciones de cliente-servidor y navegador-servidor en Office 365 y Office 365 GCC tras la deshabilitación de la compatibilidad con TLS 1.0 y 1.1.
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
- Office 365 Business
ms.openlocfilehash: b76854442fd74dddddcef778ae03a9d76ceb3cc6
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372503"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>Preparación para TLS 1.2 en Office 365 y Office 365 GCC

## <a name="summary"></a>Resumen

Para proporcionar un cifrado de primera clase a nuestros clientes, Microsoft planea degradar la compatibilidad con las versiones 1.0 y 1.1 de la Seguridad de la capa de transporte (TLS, por sus siglas en inglés) en Office 365 y Office 365 GCC. Entendemos que la seguridad de los datos es importante y estamos garantizamos transparencia en cuanto a los cambios que pueden afectar al uso del servicio TLS.

La [implementación de TLS 1.0 de Microsoft](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) no tiene vulnerabilidades de seguridad conocidas. Sin embargo, debido al potencial para futuros ataques de reducción de protocolo y otras vulnerabilidades de TLS, interrumpimos la compatibilidad con TLS 1.0 y 1.1 en Microsoft Office 365 y Office 365 GCC.

Para obtener información acerca de cómo eliminar las dependencias de TLS 1.0 y 1.1, consulte el siguiente documento técnico: [Resolución del problema con TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266).

## <a name="more-information"></a>Más información

Ya hemos comenzado la interrupción de TLS 1.0 y 1.1 a partir de enero de 2020. No se admiten todos los clientes, dispositivos o servicios que se conecten a Office 365 a través de TLS 1.0 o 1.1 en nuestras instancias DoD o GCC High. Para nuestros clientes comerciales de Office 365, el desuso de TLS 1,0 y 1,1 se iniciará el 15 de octubre de 2020.

Recomendamos que todas las combinaciones de cliente-servidor y navegador-servidor utilicen TLS 1.2 (o una versión posterior) para mantener la conexión con los servicios de Office 365. Es posible que tenga que actualizar ciertas combinaciones cliente-servidor y navegador-servidor.

Se sabe que los siguientes clientes no pueden usar TLS 1.2. Actualice los clientes para garantizar un acceso ininterrumpido al servicio.

- Android 4.3 y versiones anteriores
- Firefox versión 5.0 y versiones anteriores
- Internet Explorer 8-10 en Windows 7 y versiones anteriores
- Internet Explorer 10 en Windows Phone 8
- Safari 6.0.4/OS X10.8.4 y versiones anteriores

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>TLS 1.2 para salas de Microsoft Teams y Surface Hub

Las salas de Microsoft Teams (anteriormente conocidas como Skype Room System V2 SRS V2) han admitido TLS 1.2 desde diciembre de 2018. Se recomienda que los dispositivos de salas tengan instalada la versión 4.0.64.0 o posterior de la aplicación Salas de Microsoft Teams. Para obtener más información, consulte las [Notas de la versión](https://docs.microsoft.com/microsoftteams/room-systems/srs2-release-note). Los cambios son compatibles con versiones anteriores y posteriores.

Surface Hub publicó la compatibilidad con TLS 1.2 en mayo de 2019.

La compatibilidad con TLS 1.2 para Salas de Microsoft Teams y productos Surface Hub también requiere los siguientes cambios en el código del lado servidor:

- Los cambios en el servidor de Skype Empresarial Online se realizaron en vivo en abril de 2019. Ahora, Skype Empresarial Online admite la conexión de Salas de Microsoft Teams y dispositivos Surface Hub mediante TLS 1.2.
- Los clientes de Skype Empresarial Server deben instalar una actualización acumulativa (CU) para usar TLS 1.2 para los sistemas de salas de Microsoft Teams y Surface Hub.

  - La actualización acumulativa 9 (CU9) para Skype Empresarial Server 2015 se publicó en mayo de 2019.
  - La actualización acumulativa 1 (CU1) para Skype for Business Server 2019 estaba programada para abril de 2019, pero se retrasa a junio de 2019.

  > [!NOTE]
  > Los clientes locales de Skype for Business no deben deshabilitar TLS 1.0/1.1 antes de instalar actualizaciones acumulativas específicas para Skype for Business Server.

Si está utilizando una infraestructura local para escenarios híbridos o Servicios de federación de Active Directory, asegúrese de que la infraestructura admite conexiones entrantes y salientes que usen TLS 1.2.

## <a name="references"></a>Referencias

Los siguientes recursos proporcionan instrucciones para asegurarse de que los clientes usan TLS 1.2 o una versión posterior y para deshabilitar TLS 1.0 y 1.1.

- Si tiene clientes de Windows 7 que se conecten a Office 365, asegúrese de que TLS 1.2 sea el protocolo seguro predeterminado en WinHTTP en Windows. Para obtener más información, consulte [KB 3140245 - Actualización para habilitar TLS 1.1 y TLS 1.2 como protocolos seguros predeterminados en WinHTTP en Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).
- Para comenzar a abordar el uso débil de TLS eliminando las dependencias de TLS 1.0 y 1.1, consulte [Compatibilidad con TLS 1.2 en Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- [La nueva funcionalidad IIS](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) facilita la búsqueda de clientes en [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) y [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) que se conectan al servicio mediante el uso de protocolos de seguridad débiles.
- Obtenga más información acerca de cómo  [resolver el problema de TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266).
- Para obtener información general sobre nuestro enfoque de la seguridad, consulte el [Centro de confianza de Office 365](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Preparación para la degradación de TLS 1.0/1.1: Office 365 Skype Empresarial](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Guía de TLS de Exchange Server, parte 1: Preparación para TLS 1.2](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Orientación TLS de Exchange Server Parte 2: Habilitación de TLS 1.2 e identificación de clientes que no lo utilicen](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Orientación TLS de Exchange Server Parte 3: Desactivar TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Habilitar la compatibilidad con TLS 1.1 y TLS 1.2 en Office Online Server](https://docs.microsoft.com/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
