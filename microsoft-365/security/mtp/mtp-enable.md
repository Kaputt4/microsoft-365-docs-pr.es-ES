---
title: Habilitar la Protección contra amenazas de Microsoft en el Centro de seguridad de Microsoft 365
description: Obtenga información acerca de cómo habilitar la Protección contra amenazas de Microsoft y empiece a integrar su gestión de incidentes de seguridad y la respuesta a ellos.
keywords: Introducción, habilitación de MTP, protección contra amenazas de Microsoft, M365, seguridad, ubicación de datos, permisos necesarios, requisitos de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 73f76dee8a59229138f906e593a84220c7f70aee
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235219"
---
# <a name="turn-on-microsoft-threat-protection"></a>Habilitar la Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft



La Protección contra amenazas de Microsoft unifica el proceso de respuesta a incidentes de seguridad mediante la integración de las capacidades clave en la Protección contra amenazas avanzada (ATP) de Microsoft Defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP. Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.

## <a name="check-license-eligibility-and-required-permissions"></a>Comprobar la elegibilidad de la licencia y los permisos necesarios
Los clientes con Microsoft 365 E5, la seguridad de Microsoft 365 E5 o una combinación equivalente de licencias pueden usar la protección contra amenazas de Microsoft. Para obtener más información, [lea los requisitos de licencia](prerequisites.md#licensing-requirements).

Debe ser **administrador global** o **Administrador de seguridad** en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para activar la protección contra amenazas de Microsoft.

## <a name="start-using-the-service"></a>Empiece a usar el servicio
Microsoft Threat Protection agrega datos de los diversos servicios integrados. Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer que los flujos de trabajo de respuesta centralizados sean posibles.

Antes de activar el servicio, el centro de seguridad 365 de Microsoft ([Security.Microsoft.com](https://security.microsoft.com)) no muestra los **incidentes** ni las opciones del **centro de actividades** en el panel de navegación.

![Imagen del panel de navegación del centro de seguridad de Microsoft 365 sin](../../media/mtp-off.png)
Microsoft Threats Features Microsoft*365 centro de seguridad con Microsoft Threat Protection* desactivado

Para activar la protección contra amenazas de Microsoft, seleccione **configuración** en el panel de navegación. En la **[página Configuración](https://security.microsoft.com/settings)**, vaya a la**opción de activación/exclusión**de **Microsoft Threat Protection** > .

>[!NOTE]
>Si no ve la **configuración** en el panel de navegación o no pudo obtener acceso a la página, compruebe los permisos y las licencias.

### <a name="select-data-center-location"></a>Seleccionar la ubicación del centro de datos
Si su organización dispone de ATP de Microsoft Defender, los datos se almacenarán y procesarán en la misma ubicación del centro de datos que seleccionara para [sus datos de ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Si no tiene ATP de Microsoft defender, se le pedirá que elija una nueva ubicación del centro de datos específicamente para la Protección contra amenazas de Microsoft. 

Debe proporcionar el consentimiento antes de que los datos se compartan entre los servicios y se agreguen.

### <a name="confirm-that-the-service-is-on"></a>Confirme que el servicio está activado
Una vez que recibe el servicio, este agrega:

- [Administración de incidentes](incidents-overview.md)
- Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)
- [Características de búsqueda](advanced-hunting-overview.md) avanzadas en la página de **Búsqueda**

![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con](../../media/mtp-on.png)
Microsoft Threat Protection características de*Microsoft 365 Security Center con incidentes de administración de incidentes y otras capacidades de protección contra amenazas de Microsoft*

### <a name="getting-azure-atp-data"></a>Obtener datos de Azure ATP
Para compartir datos de Azure ATP con la Protección contra amenazas de Microsoft, asegúrese de que esté activada la integración entre Microsoft Cloud App Security y Azure ATP. [Infórmese de esta integración](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Deshabilitar la Protección contra amenazas de Microsoft
Para dejar de usar la Protección contra amenazas de Microsoft, vaya a **Configuración** > **** Protección contra amenazas de Microsoft > **** Participar/No participar en el Centro de seguridad de Microsoft 365. Anule la selección de **Activar la Protección contra amenazas de Microsoft** y guarde los cambios.

Los datos se eliminarán de forma permanente y se quitarán las características correspondientes del centro de seguridad de Microsoft 365.

## <a name="get-assistance"></a>Cómo recibir asistencia

El personal de soporte técnico de Microsoft puede ayudarle a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial. Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365. Al ponerse en contacto con el soporte técnico, mencione Microsoft Threat Protection.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la Protección contra amenazas de Microsoft](microsoft-threat-protection.md)
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Introducción al ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Introducción al ATP de Office 365](../office-365-security/office-365-atp.md)
- [Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Introducción al ATP de Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Almacenamiento de datos del ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
