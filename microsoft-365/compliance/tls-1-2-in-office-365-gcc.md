---
title: Deshabilitar TLS 1.0 y 1.1 en Office 365 GCC High y DoD
description: Describe cómo Microsoft deshabilita la compatibilidad con TLS 1.1 y 1.0 en entornos GCC High y DoD en Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: 006f81ee5b17baca4f42a78c5a87a59e8e90648f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166445"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Deshabilitar TLS 1.0 y 1.1 en Office 365 GCC High y DoD

## <a name="summary"></a>Resumen

Para cumplir con los estándares de cumplimiento más recientes para el Programa federal de administración de riesgos y autorización (FedRAMP), estamos deshabilitando las versiones 1.1 y 1.0 de Seguridad de la capa de transporte (TLS) en Microsoft 365 para entornos GCC High y DoD. Este cambio se anunció anteriormente a través del soporte técnico de Microsoft en la preparación para el uso obligatorio de [TLS 1.2 en Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

La seguridad de los datos es importante y nos comprometemos a transparencia sobre los cambios que podrían afectar al uso del servicio.

Aunque la [implementación de Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) no tiene vulnerabilidades de seguridad conocidas, seguimos comprometidos con los estándares de cumplimiento de FedRAMP. Por lo tanto, deshabilitamos TLS 1.1 y 1.0 en Office 365 en entornos GCC High y DoD el 15 de enero de 2020. Para obtener información acerca de cómo quitar dependencias de TLS 1.1 y 1.0, consulte las siguientes white paper:

[Solución del problema de TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)

Debe usar tls versión 1.2 en su lugar. Para obtener más información, vea Prepararse para el uso obligatorio de [TLS 1.2 en Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

Para SharePoint y OneDrive, tendrá que actualizar y configurar .NET para admitir TLS 1.2. Para obtener información, [consulte Cómo habilitar TLS 1.2 en los clientes.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="more-information"></a>Más información

A partir del 15 de enero de 2020, Office 365 en los entornos GCC High y DoD dejará de usar TLS 1.1 y 1.0.

Antes del 15 de enero de 2020, todas las combinaciones de servidores cliente y servidores de explorador deben usar TLS versión 1.2 (o una versión posterior) para asegurarse de que se pueden realizar todas las conexiones sin problemas con los servicios de Office 365. Esto puede requerir actualizaciones de determinadas combinaciones de servidores cliente y servidores de explorador.

Si no actualiza a TLS versión 1.2 (o una versión posterior) antes del 15 de enero de 2020, experimentará problemas al intentar conectarse a Office 365. Además, tendrá que actualizar a TLS 1.2 (o una versión posterior) como parte de la resolución.

Sabemos que los siguientes clientes no pueden usar TLS 1.2:

- Android 4.3 y versiones anteriores
- Firefox versión 5.0 y versiones anteriores
- Internet Explorer 8–10 en Windows 7 y versiones anteriores
- Internet Explorer 10 en Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 y versiones anteriores

Le recomendamos que actualice los clientes para asegurarse de mantener un acceso ininterrumpido a Office 365 GCC High y DoD.

Aunque el análisis actual de las conexiones a los servicios de Microsoft Online muestra que la mayoría de los servicios y puntos de conexión ven muy poco uso de TLS 1.1 y 1.0, estamos proporcionando aviso de este cambio para que pueda actualizar los clientes o servidores afectados según sea necesario antes de que finalice la compatibilidad con TLS 1.1 y 1.0. Si usa alguna infraestructura local para escenarios híbridos o servicios de federación de Active Directory (AD FS), asegúrese de que la infraestructura admite conexiones entrantes y salientes que usan TLS 1.2 (o una versión posterior).

Además de las interrupciones que puede experimentar si usa los clientes enumerados que no pueden usar TLS 1.2, quitar TLS 1.1 y 1.0 le impedirá usar el siguiente producto de Microsoft:

- Teléfono Lync

## <a name="references"></a>Referencias

En el siguiente artículo de soporte técnico se describen instrucciones y referencias para ayudar a garantizar que los clientes usan TLS 1.2:

[Preparación para el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
