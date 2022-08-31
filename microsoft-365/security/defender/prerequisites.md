---
title: Microsoft 365 Defender requisitos previos
description: Obtenga información sobre las licencias, los requisitos de hardware y software y otras opciones de configuración para Microsoft 365 Defender
keywords: requisitos, requisitos previos, hardware, software, explorador, Microsoft 365 Defender, M365, licencia, E5, A5, EMS, compra
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: f7977ba847036350747347063ab1bba8f8866f53
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479740"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender requisitos previos

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Obtenga información sobre las licencias y otros requisitos para el aprovisionamiento y el uso [de Microsoft 365 Defender](microsoft-365-defender.md).

## <a name="licensing-requirements"></a>Requisitos de licencias
Cualquiera de estas licencias le ofrece acceso a las características de Microsoft 365 Defender a través del portal de Microsoft 365 Defender sin costo adicional:

- Microsoft 365 E5 o A5
- Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5
- Microsoft 365 E3 con el complemento Enterprise Mobility + Security E5
- Microsoft 365 A3 con el complemento seguridad de Microsoft 365 A5
- Windows 10 Enterprise E5 o A5
- Windows 11 Empresas E5 o A5
- Enterprise Mobility + Seguridad (EMS) E5 o A5 
- Office 365 E5 o A5
- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity 
- Microsoft Defender for Cloud Apps
- Defender para Office 365 (Plan 2)

Para obtener más información, [vea los planes de servicio de Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> ¿Aún no tiene licencia? [Probar o comprar una suscripción a Microsoft 365](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>Comprobar las licencias existentes
Vaya a Centro de administración de Microsoft 365 ([admin.microsoft.com](https://admin.microsoft.com/)) para ver las licencias existentes. En el Centro de administración, vaya a **Facturación** > **Licencias**.

>[!NOTE]
> Debe tener asignado el rol Administrador de **facturación** o **Lector global** [en Azure AD](/azure/active-directory/roles/permissions-reference) para poder ver la información de licencia. Si tiene problemas de acceso, póngase en contacto con un administrador global.

## <a name="required-permissions"></a>Permisos necesarios
Debe ser **administrador global** o **administrador de seguridad** en Azure Active Directory para activar Microsoft 365 Defender. Para obtener la lista de roles necesarios para usar Microsoft 365 Defender e información sobre cómo se regula el acceso a los datos, lea sobre [cómo administrar el acceso a Microsoft 365 Defender](m365d-permissions.md).

## <a name="browser-requirements"></a>Requisitos de los exploradores
Acceda a Microsoft 365 Defender en el portal de Microsoft 365 Defender mediante Microsoft Edge, Internet Explorer 11 o cualquier explorador web compatible con HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilidad para el GCC de EE. UU., GCC High y otras instituciones gubernamentales de EE. UU.

Para obtener información relacionada con los clientes del Gobierno de EE. UU., consulte [Microsoft 365 Defender para clientes del Gobierno de EE. UU](usgov.md).

Actualmente, la integración Microsoft Defender para Office 365 en las características unificadas de Microsoft 365 Defender no está disponible para los clientes en las siguientes ubicaciones de centro de datos de Office 365:

- Noruega 
- Sudáfrica 
- Emiratos Árabes Unidos 
- Suecia 
- Singapur 


## <a name="related-topics"></a>Temas relacionados
- [introducción a Microsoft 365 Defender](microsoft-365-defender.md)
- [Activar Microsoft 365 Defender](m365d-enable.md)
- [Administración del acceso y los permisos](m365d-permissions.md)
