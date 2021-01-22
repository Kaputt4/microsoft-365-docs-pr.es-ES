---
title: Activar Microsoft 365 Defender en el Centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo habilitar Microsoft 365 Defender y empezar a integrar la respuesta y el incidente de seguridad.
keywords: introducción, habilitar MTP, Protección contra amenazas de Microsoft, M365, seguridad, ubicación de datos, permisos necesarios, elegibilidad de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930227"
---
# <a name="turn-on-microsoft-365-defender"></a>Activar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) unifica el proceso de respuesta a incidentes mediante la integración de funcionalidades clave en Microsoft Defender para Endpoint, Microsoft Defender para Office 365, Microsoft Cloud App Security y Microsoft Defender para Identity. Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.

Microsoft 365 Defender se activa automáticamente cuando los clientes elegibles con los permisos necesarios visitan el Centro de seguridad de Microsoft 365. Lea este artículo para comprender varios requisitos previos y cómo se aprovisiona Microsoft 365 Defender.

## <a name="check-license-eligibility-and-required-permissions"></a>Comprobar la elegibilidad de la licencia y los permisos necesarios

Por lo general, una licencia para un producto de seguridad de Microsoft 365 le da derecho a usar Microsoft 365 Defender en el Centro de seguridad de Microsoft 365 sin costo de licencia adicional. Se recomienda obtener una licencia de Seguridad de Microsoft 365 E5, E5, A5 o A5 o una combinación válida de licencias que proporciona acceso a todos los servicios admitidos.

Para obtener información detallada acerca de las licencias, [lea los requisitos de licencia.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Comprobar el rol

Debe ser administrador **global o** **administrador** de seguridad en Azure Active Directory para activar Microsoft 365 Defender. [Ver los roles en Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servicios admitidos

Microsoft 365 Defender agrega datos de los distintos servicios compatibles que ya ha implementado. Procesará y almacenará datos de forma centralizada para identificar nuevas perspectivas y hacer posibles los flujos de trabajo de respuesta centralizados. Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.

Para obtener la mejor protección y optimizar Microsoft 365 Defender, se recomienda implementar todos los servicios compatibles aplicables en la red. Para obtener más información, [lea acerca de la implementación de los servicios admitidos.](deploy-supported-services.md)

## <a name="before-starting-the-service"></a>Antes de iniciar el servicio

Antes de activar el servicio, el Centro de seguridad de Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)) muestra la página de  configuración de Microsoft 365 Defender cuando selecciona **Incidentes,** Centro de actividades o Búsqueda en el panel de navegación. Estos elementos de navegación no se muestran si no es apto para usar Microsoft 365 Defender.

![Imagen de la página de configuración de Microsoft 365 Defender que se muestra si Microsoft 365 Defender no se ha activado en la configuración de Microsoft 365 Defender en el Centro de seguridad de ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365*

## <a name="starting-the-service"></a>Inicio del servicio

Para activar Microsoft 365 Defender, solo tiene que seleccionar **Activar Microsoft 365 Defender** y aplicar el cambio. También puede obtener acceso a esta opción seleccionando Configuración **(** [security.microsoft.com/settings](https://security.microsoft.com/settings)) en el panel de navegación y, a continuación, **seleccionando Microsoft 365 Defender**.

> [!NOTE]
> Si no ve Configuración **en** el panel de navegación o no puede acceder a la página, compruebe sus permisos y licencias.

### <a name="data-center-location"></a>Ubicación del centro de datos

Microsoft 365 Defender almacenará y procesará datos en la misma ubicación usada por [Microsoft Defender para Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Si no tiene Microsoft Defender para endpoint, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos. La ubicación del centro de datos seleccionado se muestra en la pantalla.

Seleccione **¿Necesita ayuda?** en el Centro de seguridad de Microsoft 365 para ponerse en contacto con el soporte técnico de Microsoft sobre el aprovisionamiento de Microsoft 365 Defender en una ubicación diferente del centro de datos.

> [!NOTE]
> Microsoft Defender para puntos de conexión aprovisiona automáticamente en centros de datos de la Unión Europea (UE) cuando se activa a través de Azure Defender. Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que han aprovisionado Defender para Endpoint de esta manera.

### <a name="confirm-that-the-service-is-on"></a>Confirme que el servicio está activado

Una vez que recibe el servicio, este agrega:

- [Administración de incidentes](incidents-overview.md)
- Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)
- [Capacidades avanzadas de](advanced-hunting-overview.md) búsqueda

![Imagen del panel de navegación del Centro de seguridad de Microsoft 365 con El Centro de seguridad de Microsoft 365 Defender incluye el Centro de seguridad de Microsoft 365 con la administración de incidentes y otras capacidades de ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Obtener datos de Microsoft Defender para identidades

Para compartir datos de Identidad de Microsoft Defender con Microsoft 365 Defender, asegúrese de que la integración de Microsoft Cloud App Security y Microsoft Defender for Identity esté activada. [Obtenga más información sobre esta integración.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="get-assistance"></a>Cómo recibir asistencia

Para obtener respuestas a las preguntas más frecuentes sobre cómo activar Microsoft 365 Defender, [lea las preguntas más frecuentes.](mtp-enable-faq.md)

El personal de soporte técnico de Microsoft puede ayudar a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial. Para obtener ayuda, seleccione **¿Necesita ayuda?** en el Centro de seguridad de Microsoft 365. Al ponerse en contacto con el soporte técnico, mencione Microsoft 365 Defender.

## <a name="related-topics"></a>Temas relacionados

- [Preguntas más frecuentes](mtp-enable-faq.md)
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Introducción a Microsoft 365 Defender](microsoft-threat-protection.md)
- [Introducción a Microsoft Defender para puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Información general de Defender para Office 365](../office-365-security/office-365-atp.md)
- [Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Introducción a Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender para el almacenamiento de datos de puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
