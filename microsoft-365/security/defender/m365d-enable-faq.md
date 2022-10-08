---
title: Preguntas más frecuentes al activar Microsoft 365 Defender
description: Obtenga respuestas a las preguntas más frecuentes sobre licencias, permisos, configuración inicial y otros productos y servicios relacionados con la habilitación de Microsoft 365 Defender
keywords: preguntas más frecuentes, preguntas frecuentes, GCC, introducción, habilitación de Microsoft 365 Defender, Microsoft 365 Defender, M365, seguridad, ubicación de datos, permisos necesarios, elegibilidad de licencia, página de configuración
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 782751ad3a554250095bdfe020a2ccf01b4ccba0
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68051396"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Preguntas más frecuentes al activar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Lea las respuestas a las preguntas más frecuentes sobre cómo activar [Microsoft 365 Defender](microsoft-365-defender.md), incluidas las licencias y permisos necesarios, la implementación de servicios de soporte técnico y la configuración inicial.

Para obtener instrucciones sobre cómo activar el servicio, [lea Activar Microsoft 365 Defender](m365d-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>No tengo una licencia de Microsoft 365 E5. ¿Puedo seguir usando Microsoft 365 Defender?

Los clientes con las siguientes licencias que no sean E5 pueden usar Microsoft 365 Defender:

- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Defender para Office 365 (Plan 2)

Para obtener una lista completa de las licencias admitidas, [lea los requisitos de licencia](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>¿Es necesario instalar o implementar algo para empezar a usar Microsoft 365 Defender?

No, Microsoft 365 Defender consolida los datos de los servicios de seguridad de Microsoft 365 que ya ha implementado. Una vez que lo active, las experiencias de incidentes, automatización y búsqueda comenzarán a funcionar dentro del ámbito de los productos implementados. Si ninguno de estos productos se implementa correctamente, Microsoft 365 Defender no mostrará ningún dato y no podrá realizar ninguna acción.

Para optimizar las experiencias de Microsoft 365 Defender, se recomienda implementar *todos los* [productos y servicios de seguridad de Microsoft 365](deploy-supported-services.md) compatibles.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>¿Dónde Microsoft 365 Defender procesar y almacenar mis datos?

Microsoft 365 Defender selecciona automáticamente una ubicación óptima para el centro de datos donde se procesan y almacenan los datos consolidados. Si tiene Microsoft Defender para punto de conexión, selecciona la misma ubicación usada por Defender para punto de conexión.

>[!NOTE]
>Microsoft Defender para punto de conexión automáticamente las disposiciones en los centros de datos de la Unión Europea (UE) cuando se activa a través de Microsoft Defender for Cloud. Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que hayan aprovisionado Microsoft Defender para punto de conexión de esta manera.

La ubicación del centro de datos se muestra antes y después de aprovisionar el servicio en la página de configuración de Microsoft 365 Defender (**Configuración > Microsoft 365 Defender**). Si prefiere usar otra ubicación del centro de datos, seleccione **¿Necesita ayuda?** en el portal de Microsoft 365 Defender para ponerse en contacto con el soporte técnico de Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>¿Dónde puedo acceder a Microsoft 365 Defender?

Microsoft 365 Defender está disponible en: <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a>.

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender"></a>¿Qué permisos necesito para acceder a Microsoft 365 Defender?

Las cuentas asignadas a los siguientes roles de Azure Active Directory (Azure AD) pueden acceder a Microsoft 365 Defender funcionalidad y datos:

- Administrador global
- Administrador de seguridad
- Operador de seguridad
- Lector global
- Lector de seguridad
- Administrador de cumplimiento
- Administrador de datos de cumplimiento
- Administrador de la aplicación
- Administrador de aplicaciones en la nube


> [!NOTE]
> La configuración del control de acceso basado en el rol en Microsoft Defender para punto de conexión influye en el acceso a los datos. Para obtener más información, lea sobre [administrar el acceso a Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>¿A qué zona horaria Microsoft 365 Defender tiene como valor predeterminado?

De forma predeterminada, Microsoft 365 Defender muestra información de hora en la zona horaria UTC. Puede cambiar esta configuración para usar la zona horaria local. [Más información sobre cómo establecer la zona horaria](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>¿Cómo puedo obtener información sobre las nuevas actualizaciones de la interfaz de usuario y las características de Microsoft 365 Defender?

Microsoft proporciona periódicamente información a través de los diversos canales, entre los que se incluyen:

- El [centro de mensajes](../../admin/manage/message-center.md) de Centro de administración de Microsoft 365
- Blogposts en la [comunidad técnica de cumplimiento & seguridad de Microsoft 365](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obtenga las experiencias más recientes disponibles públicamente activando [las características de versión preliminar](preview.md).

## <a name="related-topics"></a>Temas relacionados

- [introducción a Microsoft 365 Defender](microsoft-365-defender.md)
- [Active Microsoft 365 Defender](m365d-enable.md).
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Activar la versión preliminar de las características](preview.md)
