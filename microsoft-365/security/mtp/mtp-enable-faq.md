---
title: Preguntas más frecuentes al activar Microsoft 365 defender
description: Obtenga respuestas a las preguntas más comunes sobre licencias, permisos, configuración inicial y otros productos y servicios relacionados con la habilitación de Microsoft 365 defender
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
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920495"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Preguntas más frecuentes al activar Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Lea las respuestas a las preguntas más comunes sobre cómo activar [Microsoft 365 defender](microsoft-threat-protection.md), incluidas las licencias y los permisos necesarios, la implementación de los servicios de soporte y la configuración inicial.

Para obtener instrucciones sobre cómo activar el servicio, [consulte activar Microsoft 365 defender](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>No tengo una licencia de Microsoft 365 E5. ¿Puedo seguir usando Microsoft 365 defender?

Los clientes con las siguientes licencias que no son E5 pueden usar Microsoft 365 defender:

- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender para Office 365 (plan 2)
 
Para obtener una lista completa de las licencias admitidas, [Lea los requisitos de licencia](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>¿Es necesario instalar o implementar algo para empezar a usar Microsoft 365 defender?

No, Microsoft 365 defender consolida datos de los servicios de seguridad de Microsoft 365 que ya ha implementado. Una vez que la haya activado, los incidentes, la automatización y las experiencias de búsqueda empezarán a trabajar en el ámbito de los productos implementados. Si ninguno de estos productos se ha implementado correctamente, Microsoft 365 defender no mostrará ningún dato y no podrá realizar ninguna acción.

Para optimizar la experiencia de Microsoft 365 defender, recomendamos implementar *todos los* [servicios y productos de seguridad de Microsoft 365](deploy-supported-services.md)compatibles.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>¿Dónde procesa y almacena mis datos los datos Microsoft 365 defender?
Microsoft 365 defender selecciona automáticamente una ubicación óptima para el centro de datos donde se procesan y almacenan los datos consolidados. Si tiene Microsoft defender para el punto de conexión, selecciona la misma ubicación que usa defender para el punto de conexión.

>[!NOTE]
>Microsoft defender for Endpoint se aprovisiona automáticamente en los centros de datos de la Unión Europea (UE) cuando se activa a través de Azure defender. Microsoft 365 defender aprovisionará automáticamente en el mismo centro de datos de la UE para los clientes que han aprovisionado Microsoft defender para el punto de conexión de esta manera. 

La ubicación del centro de datos se muestra antes y después de que se aprovisione el servicio en la página de configuración de Microsoft 365 defender ( **settings > Microsoft 365 defender** ). Si prefiere usar otra ubicación de centro de datos, seleccione **¿necesita ayuda?** en el centro de seguridad de Microsoft 365, póngase en contacto con el soporte técnico de Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>¿Dónde puedo obtener acceso a Microsoft 365 defender?

Microsoft 365 defender está disponible en el centro de seguridad de Microsoft 365. Para ir al centro de seguridad, vaya a la dirección URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>¿Qué permisos necesito para tener acceso a Microsoft 365 defender en el centro de seguridad de Microsoft 365?

Las cuentas asignadas a los siguientes roles de Azure Active Directory (AD) pueden tener acceso a los datos y la funcionalidad de Microsoft 365 defender:

- Administrador global
- Administrador de seguridad
- Operador de seguridad
- Lector global
- Lector de seguridad

>[!NOTE]
>Configuración de control de acceso basada en roles en Microsoft defender para el acceso a datos de la influencia del punto de conexión. Para obtener más información, consulte Acerca de la [Administración del acceso a Microsoft 365 defender](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>¿Cuál es la zona horaria predeterminada de Microsoft 365 defender?
De forma predeterminada, Microsoft 365 defender muestra la información de hora en la zona horaria UTC. Puede cambiar esta configuración para que use la zona horaria local. [Obtener información sobre la configuración de la zona horaria](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>¿Cómo puedo obtener más información sobre las nuevas actualizaciones de la interfaz de usuario y la característica de Microsoft 365 defender?

Microsoft proporciona información de forma regular a través de los distintos canales, entre los que se incluyen:

- [Centro de mensajes](../../admin/manage/message-center.md) en el centro de administración de Microsoft 365
- Blogposts en la [comunidad tecnológica de Microsoft 365 security & cumplimiento normativo](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Obtenga las últimas experiencias disponibles públicamente activando [las características de vista previa](preview.md).

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>¿Está disponible Microsoft 365 defender para la nube de la comunidad de administración de Estados Unidos (GCC) o GCC High?
No está disponible por el momento.

## <a name="related-topics"></a>Temas relacionados

- [Información general de Microsoft 365 defender](microsoft-threat-protection.md)
- [Active Microsoft 365 defender](mtp-enable.md).
- [Requisitos de licencia y otros requisitos previos](prerequisites.md)
- [Implementación de servicios compatibles](deploy-supported-services.md)
- [Activar la versión preliminar de las características](preview.md)
