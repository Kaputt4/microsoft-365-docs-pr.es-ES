---
title: Preguntas más frecuentes al activar Microsoft 365 Defender
description: Obtenga respuestas a las preguntas más frecuentes sobre licencias, permisos, configuración inicial y otros productos y servicios relacionados con la habilitación de Microsoft 365 Defender
keywords: preguntas más frecuentes, preguntas más frecuentes, GCC, introducción, habilitar MTP, Protección contra amenazas de Microsoft, M365, seguridad, ubicación de datos, permisos necesarios, elegibilidad de licencia, página de configuración
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
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930191"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Preguntas más frecuentes al activar Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Lea las respuestas a las preguntas más frecuentes sobre cómo activar [Microsoft 365 Defender,](microsoft-threat-protection.md)incluidas las licencias y permisos necesarios, la implementación de servicios de soporte técnico y la configuración inicial.

Para obtener instrucciones sobre cómo activar el servicio, [lea Activar Microsoft 365 Defender](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>No tengo una licencia de Microsoft 365 E5. ¿Puedo seguir utilizando Microsoft 365 Defender?

Los clientes con las siguientes licencias que no son E5 pueden usar Microsoft 365 Defender:

- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender para Office 365 (plan 2)
 
Para obtener una lista completa de las licencias admitidas, [lea los requisitos de licencia.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>¿Necesito instalar o implementar algo para empezar a usar Microsoft 365 Defender?

No, Microsoft 365 Defender consolida los datos de los servicios de seguridad de Microsoft 365 que ya ha implementado. Una vez que lo active, las experiencias de incidentes, automatización y búsqueda empezarán a funcionar dentro del ámbito de los productos implementados. Si ninguno de estos productos se implementa correctamente, Microsoft 365 Defender no mostrará ningún dato y no podrá realizar ninguna acción.

Para optimizar las experiencias de Microsoft 365 Defender, se recomienda implementar todos los productos y servicios de seguridad de [Microsoft 365 compatibles.](deploy-supported-services.md) 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>¿Dónde procesa y almacena Microsoft 365 Defender mis datos?
Microsoft 365 Defender selecciona automáticamente una ubicación óptima para el centro de datos donde se procesan y almacenan los datos consolidados. Si tienes Microsoft Defender para Endpoint, selecciona la misma ubicación usada por Defender para Endpoint.

>[!NOTE]
>Microsoft Defender para puntos de conexión aprovisiona automáticamente en centros de datos de la Unión Europea (UE) cuando se activa a través de Azure Defender. Microsoft 365 Defender aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que han aprovisionado Microsoft Defender para Endpoint de esta manera. 

La ubicación del centro de datos se muestra antes y después de aprovisionar el servicio en la página de configuración de Microsoft 365 Defender ( Configuración **> Microsoft 365 Defender**). Si prefiere usar otra ubicación del centro de datos, seleccione ¿Necesita **ayuda?** en el Centro de seguridad de Microsoft 365 para ponerse en contacto con el soporte técnico de Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>¿Dónde puedo acceder a Microsoft 365 Defender?

Microsoft 365 Defender está disponible en el Centro de seguridad de Microsoft 365. Para ir al centro de seguridad, vaya a la dirección [https://security.microsoft.com](https://security.microsoft.com) URL.

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>¿Qué permisos necesito para acceder a Microsoft 365 Defender en el Centro de seguridad de Microsoft 365?

Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden acceder a la funcionalidad y los datos de Microsoft 365 Defender:

- Administrador global
- Administrador de seguridad
- Operador de seguridad
- Lector global
- Lector de seguridad

>[!NOTE]
>La configuración del control de acceso basado en roles en Microsoft Defender para puntos de conexión influye en el acceso a los datos. Para obtener más información, lea acerca [de cómo administrar el acceso a Microsoft 365 Defender.](mtp-permissions.md)

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>¿En qué zona horaria se usa Microsoft 365 Defender de forma predeterminada?
De forma predeterminada, Microsoft 365 Defender muestra información de hora en la zona horaria UTC. Puedes cambiar esta configuración para usar la zona horaria local. [Más información sobre cómo establecer la zona horaria](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>¿Cómo puedo obtener información sobre las nuevas actualizaciones de la interfaz de usuario y la característica de Microsoft 365 Defender?

Microsoft proporciona información periódicamente a través de los distintos canales, incluidos:

- Centro [de mensajes en](../../admin/manage/message-center.md) el Centro de administración de Microsoft 365
- Blogs en la comunidad técnica de [seguridad y cumplimiento & Microsoft 365](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obtenga las últimas experiencias disponibles públicamente al activar las características [de vista previa.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>¿Microsoft 365 Defender está disponible para US Government Community Cloud (GCC) o GCC High?
No está disponible por el momento.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft 365 Defender](microsoft-threat-protection.md)
- [Active Microsoft 365 Defender.](mtp-enable.md)
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Activar la versión preliminar de las características](preview.md)
