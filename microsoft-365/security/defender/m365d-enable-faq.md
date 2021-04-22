---
title: Preguntas más frecuentes al activar Microsoft 365 Defender
description: Obtenga respuestas a las preguntas más frecuentes sobre licencias, permisos, configuración inicial y otros productos y servicios relacionados con la habilitación de Microsoft 365 Defender
keywords: preguntas más frecuentes, preguntas frecuentes, GCC, introducción, habilitar Microsoft 365 Defender, Microsoft 365 Defender, M365, seguridad, ubicación de datos, permisos necesarios, elegibilidad de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933438"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Preguntas más frecuentes al activar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Lea las respuestas a las preguntas más frecuentes sobre cómo activar [Microsoft 365 Defender,](microsoft-365-defender.md)incluidas las licencias y permisos necesarios, la implementación de servicios de soporte técnico y la configuración inicial.

Para obtener instrucciones sobre cómo activar el servicio, [lea Activar Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>No tengo una licencia de Microsoft 365 E5. ¿Puedo seguir utilizando Microsoft 365 Defender?

Los clientes con las siguientes licencias que no son de E5 pueden usar Microsoft 365 Defender:

- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender para Office 365 (Plan 2)
 
Para obtener una lista completa de licencias admitidas, [lea los requisitos de licencias](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>¿Necesito instalar o implementar algo para empezar a usar Microsoft 365 Defender?

No, Microsoft 365 Defender consolida los datos de los servicios de seguridad de Microsoft 365 que ya ha implementado. Una vez que lo actives, las experiencias de incidentes, automatización y búsqueda empezarán a funcionar dentro del ámbito de los productos implementados. Si ninguno de estos productos está implementado correctamente, Microsoft 365 Defender no mostrará ningún dato y no podrá realizar ninguna acción.

Para optimizar las experiencias de Microsoft 365 Defender, se recomienda implementar todos los productos y servicios de seguridad de [Microsoft 365 compatibles.](deploy-supported-services.md) 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>¿Dónde procesa y almacena Microsoft 365 Defender mis datos?
Microsoft 365 Defender selecciona automáticamente una ubicación óptima para el centro de datos donde se procesan y almacenan los datos consolidados. Si tienes Microsoft Defender para Endpoint, selecciona la misma ubicación usada por Defender para Endpoint.

>[!NOTE]
>Microsoft Defender para endpoint aprovisiona automáticamente en centros de datos de la Unión Europea (UE) cuando se activa a través de Azure Defender. Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que han aprovisionado Microsoft Defender para Endpoint de esta manera. 

La ubicación del centro de datos se muestra antes y después de aprovisionar el servicio en la página de configuración de Microsoft 365 Defender (**Configuración > Microsoft 365 Defender**). Si prefiere usar otra ubicación del centro de datos, seleccione **¿Necesita ayuda?** en el Centro de seguridad de Microsoft 365 para ponerse en contacto con el soporte técnico de Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>¿Dónde puedo obtener acceso a Microsoft 365 Defender?

Microsoft 365 Defender está disponible en el Centro de seguridad de Microsoft 365. Para ir al centro de seguridad, vaya a la dirección URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>¿Qué permisos necesito para tener acceso a Microsoft 365 Defender en el Centro de seguridad de Microsoft 365?

Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden tener acceso a la funcionalidad y los datos de Microsoft 365 Defender:

- Administrador global
- Administrador de seguridad
- Operador de seguridad
- Lector global
- Lector de seguridad

>[!NOTE]
>La configuración de control de acceso basada en roles en Microsoft Defender para endpoint influye en el acceso a los datos. Para obtener más información, lea acerca [de cómo administrar el acceso a Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>¿En qué zona horaria se usa Microsoft 365 Defender de forma predeterminada?
De forma predeterminada, Microsoft 365 Defender muestra información de hora en la zona horaria UTC. Puede cambiar esta configuración para usar la zona horaria local. [Obtenga información sobre cómo establecer la zona horaria](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>¿Cómo puedo obtener información sobre las nuevas actualizaciones de la interfaz de usuario y la característica de Microsoft 365 Defender?

Microsoft proporciona información periódicamente a través de los distintos canales, incluidos:

- El [centro de mensajes](../../admin/manage/message-center.md) del Centro de administración de Microsoft 365
- Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obtenga las últimas experiencias disponibles públicamente al activar las [características de vista previa.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>¿Microsoft 365 Defender está disponible para us Government Community Cloud (GCC) o GCC High?
No está disponible por el momento.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft 365 Defender](microsoft-365-defender.md)
- [Active Microsoft 365 Defender](m365d-enable.md).
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Activar la versión preliminar de las características](preview.md)
