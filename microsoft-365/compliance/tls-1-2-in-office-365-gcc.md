---
title: Desuso de TLS 1,0 y 1,1 en Office 365 GCC High y DoD
description: Describe cómo Microsoft pasa la fecha hacia adelante para descontinuar la compatibilidad con TLS 1,1 y 1,0 en los entornos altos y DoD de GCC en Office 365 y preparar el uso de TLS 1,2.
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
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158885"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Desuso de TLS 1,0 y 1,1 en Office 365 GCC High y DoD

## <a name="summary"></a>Resumen

Para cumplir con los últimos estándares de cumplimiento para el programa de administración de riesgos y autorización Federal (FedRAMP), estamos descartando las versiones 1,1 y 1,0 de seguridad de la capa de transporte (TLS) en Microsoft Office 365 para los entornos de GCC altos y DoD. Este cambio se anunció anteriormente a través del soporte técnico de Microsoft [para preparar el uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

La seguridad de los datos es importante y estamos comprometidos con la transparencia de los cambios que puedan afectar al uso del servicio.

Aunque la [implementación de Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) no tiene vulnerabilidades de seguridad conocidas, seguimos comprometidos con los estándares de cumplimiento de FedRAMP. Por lo tanto, se dejará de usar TLS 1,1 y 1,0 en Office 365 en los entornos alto y DoD de GCC a partir del 15 de enero de 2020. Para obtener información acerca de cómo quitar dependencias TLS 1,1 y 1,0, consulte las siguientes notas del producto:

[Solución del problema de TLS 1,0](https://www.microsoft.com/download/details.aspx?id=55266)

Al preparar este cambio para TLS 1,1 y 1,0, recomendamos que use TLS versión 1,2 en su lugar. Para obtener más información, vea [preparación para el uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="more-information"></a>Más información

A partir del 15 de enero de 2020, Office 365 en los entornos alto y DoD de GCC dejará de estar en desuso las características TLS 1,1 y 1,0.

Por el 15 de enero de 2020, todas las combinaciones de servidores cliente y servidores de explorador deben usar TLS versión 1,2 (o una versión posterior) para asegurarse de que se pueden realizar todas las conexiones sin problemas con los servicios de Office 365. Esto puede requerir actualizaciones a determinadas combinaciones de servidores cliente y servidores de explorador.

Si no actualiza a la versión 1,2 de TLS (o a una versión posterior) antes del 15 de enero de 2020, tendrá problemas cuando intente conectarse a Office 365. Además, se le pedirá que actualice a TLS 1,2 (o una versión posterior) como parte de la solución.

Sabemos que los siguientes clientes no pueden usar TLS 1,2:

- Android 4.3 y versiones anteriores
- Firefox versión 5.0 y versiones anteriores
- Internet Explorer 8 – 10 en Windows 7 y versiones anteriores
- Internet Explorer 10 en Windows Phone 8,0
- Safari 6.0.4/OS X 10.8.4 y versiones anteriores

Le recomendamos que actualice los clientes para asegurarse de que mantiene un acceso ininterrumpido a Office 365 GCC High y DoD.

Aunque el análisis actual de las conexiones a Microsoft Online Services muestra que la mayoría de los servicios y extremos ven muy poco TLS 1,1 y el uso de 1,0, hemos proporcionado este cambio para que pueda actualizar los clientes o servidores afectados según sea necesario antes de que finalice la compatibilidad con TLS 1,1 y 1,0. Si usa una infraestructura local para entornos híbridos o servicios de Federación de Active Directory (AD FS), asegúrese de que la infraestructura puede admitir conexiones entrantes y salientes que usen TLS 1,2 (o una versión posterior).

Además de las interrupciones que puede experimentar si usa los clientes enumerados que no pueden usar TLS 1,2, quitar TLS 1,1 y 1,0 le impedirá usar el siguiente producto de Microsoft:

- Lync Phone

## <a name="references"></a>Referencias

El siguiente artículo de soporte técnico describe las instrucciones y referencias que le ayudarán a asegurarse de que los clientes usan TLS 1,2:

[Preparación del uso obligatorio de TLS 1,2 en Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
