---
title: Activar Microsoft 365 defender en el centro de seguridad de Microsoft 365
description: Obtenga información sobre cómo habilitar Microsoft 365 defender e iniciar la integración de su incidente de seguridad y respuesta.
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
ms.openlocfilehash: b5bb99ed4b8cee7ea920679e20f69c7a0e002d26
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843641"
---
# <a name="turn-on-microsoft-365-defender"></a>Activar Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

[Microsoft 365 defender](microsoft-threat-protection.md) unifica el proceso de respuesta ante incidentes mediante la integración de capacidades clave en Microsoft defender para el punto de conexión, Microsoft defender para Office 365, Microsoft Cloud App Security y Microsoft defender para identidad. Esta experiencia unificada aporta potentes características a las que puede acceder desde el Centro de seguridad de Microsoft 365.

Microsoft 365 defender se activa automáticamente cuando los clientes elegibles con los permisos necesarios visitan el centro de seguridad de Microsoft 365. Lea este artículo para conocer los diversos requisitos previos y la forma en que se aprovisionó Microsoft 365 defender.

## <a name="check-license-eligibility-and-required-permissions"></a>Comprobar la elegibilidad de la licencia y los permisos necesarios
Una licencia a un producto de seguridad 365 de Microsoft generalmente le da derecho a usar Microsoft 365 defender en el centro de seguridad de Microsoft 365 sin costo de licencias adicional. Le recomendamos que obtenga una licencia de seguridad de Microsoft 365 E5, E5 Security, A5 o a5 o una combinación válida de licencias que proporcione acceso a todos los servicios admitidos.

Para obtener información detallada sobre la licencia, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Comprobar el rol
Debe ser **administrador global** o **Administrador de seguridad** en Azure active directory para activar Microsoft 365 defender. [Ver sus roles en Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servicios admitidos
Microsoft 365 defender agrega datos de los diversos servicios compatibles que ya ha implementado. Procesará y almacenará datos de forma centralizada para identificar nuevos conocimientos y hacer que los flujos de trabajo de respuesta centralizados sean posibles. Lo hace sin afectar a las implementaciones, la configuración o los datos existentes asociados con los servicios integrados.

Para obtener la mejor protección y optimizar Microsoft 365 defender, se recomienda implementar todos los servicios admitidos aplicables en la red. Para obtener más información, [Consulte acerca de la implementación de servicios compatibles](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Antes de iniciar el servicio
Antes de activar el servicio, el centro de seguridad 365 de Microsoft ( [Security.Microsoft.com](https://security.microsoft.com)) muestra la página de configuración de Microsoft 365 defender al seleccionar **incidentes** , **centro de actividades** o **caza** en el panel de navegación. Estos elementos de navegación no se muestran si no es elegible para usar Microsoft 365 defender.

![Imagen de la página de configuración de Microsoft 365 defender que se muestra si no se activó la configuración de Microsoft 365 defender ](../../media/mtp-enable/mtp-settings.png)
 *365 en Microsoft 365 Security Center*

## <a name="starting-the-service"></a>Inicio del servicio
Para activar Microsoft 365 defender, simplemente seleccione **Activar microsoft 365 defender** y aplicar el cambio. También puede tener acceso a esta opción si selecciona **configuración** ( [Security.Microsoft.com/Settings](https://security.microsoft.com/settings)) en el panel de navegación y, a continuación, selecciona **Microsoft 365 defender**.

>[!NOTE]
>Si no ve la **configuración** en el panel de navegación o no pudo obtener acceso a la página, compruebe los permisos y las licencias.

### <a name="data-center-location"></a>Ubicación del centro de datos
Microsoft 365 defender almacenará y procesará datos en la [misma ubicación usada por Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Si no tiene Microsoft defender para el punto de conexión, se selecciona automáticamente una nueva ubicación del centro de datos en función de la ubicación de los servicios de seguridad de Microsoft 365 activos. La ubicación del centro de datos seleccionada se muestra en la pantalla. 

Seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365, póngase en contacto con el soporte técnico de Microsoft sobre el aprovisionamiento de Microsoft 365 defender en una ubicación diferente del centro de datos. 

>[!NOTE]
>Microsoft defender for Endpoint provisiones de forma automática en los centros de datos de la Unión Europea (UE) cuando se activa a través de Azure defender *. Microsoft 365 defender aprovisionará automáticamente en el mismo centro de datos de la UE para los clientes que hayan proporcionado defender para el punto de conexión de esta manera. 

### <a name="confirm-that-the-service-is-on"></a>Confirme que el servicio está activado
Una vez que recibe el servicio, este agrega:

- [Administración de incidentes](incidents-overview.md)
- Un centro de actividades para administrar [una investigación y respuestas automáticas](mtp-autoir.md)
- Funcionalidades de [búsqueda avanzada](advanced-hunting-overview.md)

![Imagen del panel de navegación del centro de seguridad de Microsoft 365 con Microsoft 365 para el ](../../media/mtp-enable/mtp-on.png)
 *centro de seguridad de Microsoft 365 con administración de incidentes y otras capacidades de Microsoft 365 defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Obtención de Microsoft defender para datos de identidad
Para compartir Microsoft defender para obtener datos de identidad con Microsoft 365 defender, asegúrese de que la opción Microsoft Cloud App Security y Microsoft defender para la integración de identidades están activadas. [Infórmese de esta integración](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a>Desactivar Microsoft 365 defender
Para dejar de usar Microsoft 365 defender, vaya a **configuración**  >  **Microsoft 365 defender**  >  **participar/participar** en el centro de seguridad de Microsoft 365. Desactive **Activar Microsoft 365 defender** y aplicar los cambios.

Se quitarán las características correspondientes del centro de seguridad de Microsoft 365.

## <a name="get-assistance"></a>Cómo recibir asistencia

Para obtener respuestas a las preguntas más comunes sobre cómo activar Microsoft 365 defender, [Lea las preguntas más frecuentes](mtp-enable-faq.md).

El personal de soporte técnico de Microsoft puede ayudarle a aprovisionar o desaprovisionar el servicio y los recursos relacionados en su espacio empresarial. Para obtener ayuda, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365. Al ponerse en contacto con el soporte técnico, mencione Microsoft 365 defender.

## <a name="related-topics"></a>Temas relacionados

- [Preguntas más frecuentes](mtp-enable-faq.md)
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Información general de Microsoft 365 defender](microsoft-threat-protection.md)
- [Información general de Microsoft defender para Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Información general de defender para Office 365](../office-365-security/office-365-atp.md)
- [Introducción a Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Información general de Microsoft defender para identidad](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft defender para el almacenamiento de datos de extremo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
