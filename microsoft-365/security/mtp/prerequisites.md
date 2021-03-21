---
title: Requisitos previos de Microsoft 365 Defender
description: Obtenga información sobre los requisitos de licencias, hardware y software y otras opciones de configuración para Microsoft 365 Defender
keywords: requisitos, requisitos previos, hardware, software, explorador, MTP, M365, licencia, E5, A5, EMS, compra
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0184b2c05121e1ea3bf365263df880548f1b9232
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918875"
---
# <a name="microsoft-365-defender-prerequisites"></a>Requisitos previos de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Obtenga información sobre las licencias y otros requisitos para el aprovisionamiento y el [uso de Microsoft 365 Defender](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Requisitos de licencia
Cualquiera de estas licencias le da acceso a las características de Microsoft 365 Defender en el Centro de seguridad de Microsoft 365 sin costo adicional:

- Microsoft 365 E5 o A5
- Microsoft 365 E5 Security o A5 Security
- Windows 10 Enterprise E5 o A5
- Enterprise Mobility + Security (EMS) E5 o A5 
- Office 365 E5 o A5
- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender para Office 365 (Plan 2)

Para obtener más información, vea los planes de servicio de [Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> ¿Todavía no tiene licencia? [Probar o comprar una suscripción a Microsoft 365](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Comprobar las licencias existentes
Vaya al Centro de administración de Microsoft 365 ([admin.microsoft.com](https://admin.microsoft.com/)) para ver las licencias existentes. En el Centro de administración, vaya a **Facturación** > **Licencias**.

>[!NOTE]
> Debe tener asignado el rol De administrador **de** facturación o Lector **global** en [Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver la información de licencia. Si tiene problemas de acceso, póngase en contacto con un administrador global.

## <a name="required-permissions"></a>Permisos necesarios
Debe ser un administrador **global o** un administrador **de seguridad** en Azure Active Directory para activar Microsoft 365 Defender. Para obtener la lista de roles necesarios para usar Microsoft 365 Defender e información sobre cómo se regula el acceso a los datos, lea acerca de cómo administrar el acceso a [Microsoft 365 Defender](mtp-permissions.md).

## <a name="browser-requirements"></a>Requisitos de los exploradores
Accede a Microsoft 365 Defender en el centro de seguridad de Microsoft 365 con Microsoft Edge, Internet Explorer 11 o cualquier explorador web compatible con HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilidad para GCC, GCC High y otras instituciones gubernamentales de EE. UU.
Actualmente, Microsoft 365 Defender *no está* disponible para:
- Nube de la comunidad gubernamental de ESTADOS UNIDOS (GCC)
- Alta nube de la comunidad gubernamental de Estados Unidos (GCC High)
- Departamento de Defensa de ESTADOS UNIDOS
- Todas las instituciones gubernamentales de ESTADOS UNIDOS con licencias comerciales

## <a name="related-topics"></a>Temas relacionados
- [Introducción a Microsoft 365 Defender](microsoft-threat-protection.md)
- [Activar Microsoft 365 Defender](mtp-enable.md)
- [Administrar el acceso y los permisos](mtp-permissions.md)