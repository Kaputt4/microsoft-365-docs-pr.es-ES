---
title: Deshabilitación de TLS 1.0 y 1.1 en Microsoft 365 GCC High y DoD
description: Describe cómo Microsoft deshabilita la compatibilidad con TLS 1.1 y 1.0 en GCC entornos high y DoD en Microsoft 365.
author: kccross
manager: laurawi
ms.localizationpriority: medium
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: bad0dc997f2c564670858d2ac35b2cd3177e0578
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760397"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>Deshabilitación de TLS 1.0 y 1.1 en Microsoft 365 GCC High y DoD

## <a name="summary"></a>Resumen

Con el fin de cumplir con los estándares de cumplimiento más recientes para el Programa Federal de Administración de Riesgos y Autorización (FedRAMP), estamos deshabilitando las versiones 1.1 y 1.0 de seguridad de la capa de transporte (TLS) en Microsoft 365 para GCC entornos high y dod. Este cambio se anunció anteriormente mediante Soporte técnico de Microsoft en [Preparación para el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

La seguridad de los datos es importante y estamos comprometidos con la transparencia sobre los cambios que podrían afectar al uso del servicio.

Aunque la [implementación de Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) no tiene vulnerabilidades de seguridad conocidas, seguimos comprometidos con los estándares de cumplimiento de FedRAMP. Por lo tanto, hemos deshabilitado TLS 1.1 y 1.0 en Microsoft 365 en GCC entornos high y DoD el 15 de enero de 2020. Para obtener información sobre cómo quitar las dependencias de TLS 1.1 y 1.0, consulte las notas del producto siguientes:

[Resolución del problema de TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>Más información

A partir del 15 de enero de 2020, Microsoft 365 en los entornos GCC High y DoD deshabilitarán TLS 1.1 y 1.0.

Para el 15 de enero de 2020, todas las combinaciones de servidores cliente y servidores de explorador deben usar tls versión 1.2 (o una versión posterior) para asegurarse de que todas las conexiones se pueden realizar sin problemas para Microsoft 365. Esto puede requerir actualizaciones de determinadas combinaciones de servidores cliente y servidores de explorador.

Para SharePoint y OneDrive, deberá actualizar y configurar .NET para admitir TLS 1.2. Para obtener información, vea [How to enable TLS 1.2 on clients (Cómo habilitar TLS 1.2 en clientes](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)).

Debe actualizar los equipos cliente para asegurarse de mantener el acceso ininterrumpido a Office 365 GCC High y DoD.

Tendrá que actualizar las aplicaciones que llaman a Microsoft 365 API a través de TLS 1.0 o TLS 1.1 para usar TLS 1.2. .NET 4.5 tiene como valor predeterminado TLS 1.1. Para actualizar la configuración de .NET, consulte [Habilitación de seguridad de la capa de transporte (TLS) 1.2 en los clientes](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client). Para obtener más información, vea [Preparar el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

Sabemos que las siguientes aplicaciones cliente no pueden usar TLS 1.2:

- Android 4.3 y versiones anteriores
- Firefox versión 5.0 y versiones anteriores
- Internet Explorer 8-10 en Windows 7 y versiones anteriores
- Internet Explorer 10 en Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 y versiones anteriores

Aunque el análisis actual de las conexiones a los servicios de Microsoft Online muestra que la mayoría de los servicios y puntos de conexión ven poco uso de TLS 1.1 y 1.0, estamos proporcionando un aviso de este cambio para que pueda actualizar los clientes o servidores afectados según sea necesario antes de que finalice la compatibilidad con TLS 1.1 y 1.0. Si usa cualquier infraestructura local para escenarios híbridos o Servicios de federación de Active Directory (AD FS) (AD FS), asegúrese de que la infraestructura puede admitir conexiones entrantes y salientes que usen TLS 1.2 (o una versión posterior).

Además de las interrupciones que puede experimentar si usa los clientes enumerados que no pueden usar TLS 1.2, la eliminación de TLS 1.1 y 1.0 impedirá que pueda usar el siguiente producto de Microsoft:

- Teléfono Lync

## <a name="references"></a>Referencias

Para obtener instrucciones y referencias que ayuden a asegurarse de que los clientes usan TLS 1.2, consulte [Preparación para el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
