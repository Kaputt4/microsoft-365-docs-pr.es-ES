---
title: Microsoft 365 Defender requisitos previos
description: Obtenga información sobre los requisitos de licencias, hardware y software y otras opciones de configuración para Microsoft 365 Defender
keywords: requisitos, requisitos previos, hardware, software, explorador, Microsoft 365 Defender, M365, licencia, E5, A5, EMS, compra
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
ms.openlocfilehash: d136ae298abdf876a9be6f58634940ec71c07e47
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792345"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender requisitos previos

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Obtenga información sobre las licencias y otros requisitos para aprovisionar y usar [Microsoft 365 Defender](microsoft-365-defender.md).

## <a name="licensing-requirements"></a>Requisitos de licencias
Cualquiera de estas licencias le da acceso a Microsoft 365 Defender características de Microsoft 365 Defender portal sin costo adicional:

- Microsoft 365 E5 o A5
- Microsoft 365 E3 con el Seguridad de Microsoft 365 E5 complemento
- Microsoft 365 A3 con el complemento Microsoft 365 A5 seguridad
- Windows 10 Enterprise E5 o A5
- Windows 11 Enterprise E5 o A5
- Enterprise Mobility + Seguridad (EMS) E5 o A5 
- Office 365 E5 o A5
- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender para Office 365 (Plan 2)

Para obtener más información, [vea el Microsoft 365 Enterprise de servicio](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> ¿Todavía no tiene licencia? [Probar o comprar una suscripción a Microsoft 365](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>Comprobar las licencias existentes
Vaya a Centro de administración de Microsoft 365 ([admin.microsoft.com](https://admin.microsoft.com/)) para ver las licencias existentes. En el Centro de administración, vaya a **Facturación** > **Licencias**.

>[!NOTE]
> Debe tener asignado el  rol  Administrador de facturación o Lector global [en Azure AD](/azure/active-directory/roles/permissions-reference) para poder ver la información de licencia. Si tiene problemas de acceso, póngase en contacto con un administrador global.

## <a name="required-permissions"></a>Permisos necesarios
Debe ser un administrador **global o** **un** administrador de seguridad en Azure Active Directory para activar Microsoft 365 Defender. Para obtener la lista de roles necesarios para usar Microsoft 365 Defender información sobre cómo se regula el acceso a los datos, lea acerca de cómo administrar el acceso a [Microsoft 365 Defender](m365d-permissions.md).

## <a name="browser-requirements"></a>Requisitos de los exploradores
Acceda Microsoft 365 Defender en el portal de Microsoft 365 Defender con Microsoft Edge, Internet Explorer 11 o cualquier explorador web compatible con HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilidad para estados GCC, GCC High y otras instituciones gubernamentales de EE. UU.
Actualmente, Microsoft 365 Defender *no está* disponible para:
- Us Government Community Cloud High (GCC High)
- Departamento de Defensa de ESTADOS UNIDOS
- Todas las instituciones gubernamentales de ESTADOS UNIDOS con licencias comerciales


Actualmente, Microsoft Defender para Office 365 integración en las características de Microsoft 365 Defender unificadas no están disponibles para los clientes en las siguientes ubicaciones Office 365 centro de datos:

- Brasil 
- Alemania 
- Noruega 
- Singapur 
- Sudáfrica
- Suiza 
- Emiratos Árabes Unidos 


## <a name="related-topics"></a>Temas relacionados
- [Microsoft 365 Defender introducción](microsoft-365-defender.md)
- [Activar Microsoft 365 Defender](m365d-enable.md)
- [Administrar el acceso y los permisos](m365d-permissions.md)
