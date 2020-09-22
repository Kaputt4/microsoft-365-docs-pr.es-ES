---
title: Preguntas más frecuentes acerca de la activación de la protección contra amenazas de Microsoft
description: Obtenga respuestas a las preguntas más frecuentes acerca de las licencias, los permisos, la configuración inicial y otros productos y servicios relacionados con la habilitación de la protección contra amenazas de Microsoft
keywords: Preguntas más frecuentes, preguntas más frecuentes, GCC, introducción, habilitar MTP, protección contra amenazas de Microsoft, M365, seguridad, ubicación de los datos, permisos necesarios, requisitos de licencia, página de configuración
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
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198844"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Preguntas más frecuentes acerca de la activación de la protección contra amenazas de Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

Lea las respuestas a las preguntas más comunes sobre la activación de la [protección contra amenazas de Microsoft](microsoft-threat-protection.md), incluidas las licencias y los permisos necesarios, la implementación de los servicios de soporte y la configuración inicial.

Para obtener instrucciones sobre cómo activar el servicio, [consulte activar la protección contra amenazas de Microsoft](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>No tengo una licencia de Microsoft 365 E5. ¿Puedo seguir usando Microsoft Threat Protection?

Los clientes con las siguientes licencias que no son E5 pueden usar la protección contra amenazas de Microsoft:

- Protección contra amenazas avanzada de Microsoft Defender
- Azure Advanced Threat Protection
- Microsoft Cloud App Security
- Protección contra amenazas avanzada de Office 365 (plan 2)
 
Para obtener una lista completa de las licencias admitidas, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>¿Es necesario instalar o implementar algo para empezar a usar la protección contra amenazas de Microsoft?

No, la protección contra amenazas de Microsoft consolida datos de los servicios de seguridad de Microsoft 365 que ya ha implementado. Una vez que la haya activado, los incidentes, la automatización y las experiencias de búsqueda empezarán a trabajar en el ámbito de los productos implementados. Si ninguno de estos productos se ha implementado correctamente, la protección contra amenazas de Microsoft no mostrará ningún dato y no podrá realizar ninguna acción.

Para optimizar sus experiencias de protección contra amenazas de Microsoft, le recomendamos que implemente *todos los* [servicios y productos de seguridad 365 de Microsoft](deploy-supported-services.md)compatibles.

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>¿Dónde procesa y almacena mis datos los datos de protección contra amenazas de Microsoft?
Microsoft Threat Protection selecciona automáticamente una ubicación óptima para el centro de datos donde se procesan y almacenan los datos consolidados. Si cuenta con ATP de Microsoft defender, selecciona la misma ubicación que ha usado ATP de Microsoft defender.

>[!NOTE]
>Microsoft defender ATP se aprovisiona automáticamente en los centros de datos de la Unión Europea (UE) cuando se activa a través del centro de seguridad de Azure. Microsoft Threat Protection aprovisionará automáticamente en el mismo centro de datos de la UE a los clientes que hayan aprovisionado ATP de Microsoft defender de este modo. 

La ubicación del centro de datos se muestra antes y después de aprovisionar el servicio en la página de configuración de Microsoft Threat Protection (**configuración > protección contra amenazas de Microsoft**). Si prefiere usar otra ubicación de centro de datos, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365, póngase en contacto con el soporte técnico de Microsoft.

## <a name="where-can-i-access-microsoft-threat-protection"></a>¿Dónde se puede obtener acceso a Microsoft Threat Protection?

La protección contra amenazas de Microsoft está disponible en el centro de seguridad de Microsoft 365. Para ir al centro de seguridad, vaya a la dirección URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>¿Qué permisos necesito para tener acceso a Microsoft Threat Protection en el centro de seguridad de Microsoft 365?

Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden acceder a los datos y a la funcionalidad de protección contra amenazas de Microsoft:

- Administrador global
- Administrador de seguridad
- Operador de seguridad
- Lector global
- Lector de seguridad

>[!NOTE]
>Configuración de control de acceso basada en roles en ATP de Microsoft defender influencia en el acceso a los datos. Para obtener más información, consulte Acerca de la [Administración del acceso a la protección contra amenazas de Microsoft](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>¿Con qué zona horaria se ha predeterminado la protección contra amenazas de Microsoft?
De forma predeterminada, Microsoft Threat Protection muestra la información de hora en la zona horaria UTC. Puede cambiar esta configuración para que use la zona horaria local. [Obtener información sobre la configuración de la zona horaria](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>¿Cómo puedo obtener más información sobre las nuevas actualizaciones de la interfaz de usuario y la interfaz de Microsoft Threat Protection?

Microsoft proporciona información de forma regular a través de los distintos canales, entre los que se incluyen:

- [Centro de mensajes](../../admin/manage/message-center.md) en el centro de administración de Microsoft 365
- Blogposts en la [comunidad tecnológica de Microsoft 365 security & cumplimiento normativo](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obtenga las últimas experiencias disponibles públicamente activando [las características de vista previa](preview.md).

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>¿Está disponible la protección contra amenazas de Microsoft en la nube de la comunidad del gobierno de los EE. UU. (GCC) o en GCC High?
No está disponible por el momento.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la Protección contra amenazas de Microsoft](microsoft-threat-protection.md)
- [Activar la protección contra amenazas de Microsoft](mtp-enable.md).
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Activar las características de vista previa](preview.md)
