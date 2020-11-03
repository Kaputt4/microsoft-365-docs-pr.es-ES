---
title: Requisitos previos de Microsoft 365 defender
description: Obtenga información sobre las licencias, los requisitos de hardware y software, y otras opciones de configuración para Microsoft 365 defender
keywords: requisitos, requisitos previos, hardware, software, explorador, MTP, M365, licencia, E5, A5, EMS, compras
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844781"
---
# <a name="microsoft-365-defender-prerequisites"></a>Requisitos previos de Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

Obtenga información sobre licencias y otros requisitos para el aprovisionamiento y el uso de [Microsoft 365 defender](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Requisitos de licencia
Cualquiera de estas licencias le da acceso a las características de Microsoft 365 defender en el centro de seguridad de Microsoft 365 sin costo adicional:

- Microsoft 365 E5 o A5
- Seguridad de Microsoft 365 E5 o de la A5
- Windows 10 Enterprise E5 o A5
- Enterprise Mobility + Security (EMS) E5 o A5 
- Office 365 E5 o A5
- Microsoft Defender para punto de conexión
- Microsoft Defender for Identity 
- Microsoft Cloud App Security
- Defender para Office 365 (plan 2)

> [!NOTE]
> Actualmente, las licencias de prueba para Office 365 no proporcionan acceso a Microsoft 365 defender.

Para obtener más información, [vea los planes de servicio de Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> ¿Todavía no tiene licencia? [Probar o comprar una suscripción a Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Comprobar las licencias existentes
Vaya al centro de administración de 365 de Microsoft ([admin.Microsoft.com](https://admin.microsoft.com/)) para ver las licencias existentes. En el Centro de administración, vaya a **Facturación** > **Licencias**.

>[!NOTE]
> Debe tener asignado el rol de **Administrador de facturación** o de **lector global** [en Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver la información de licencia. Si tiene problemas de acceso, póngase en contacto con un administrador global.

## <a name="required-permissions"></a>Permisos necesarios
Debe ser **administrador global** o **Administrador de seguridad** en Azure active directory para activar Microsoft 365 defender. Para obtener la lista de funciones necesarias para usar Microsoft 365 defender y sobre cómo se regula el acceso a los datos, vea información sobre la [Administración del acceso a Microsoft 365 defender](mtp-permissions.md).

## <a name="browser-requirements"></a>Requisitos de los exploradores
Obtenga acceso a Microsoft 365 defender en el centro de seguridad de Microsoft 365 con Microsoft Edge, Internet Explorer 11 o cualquier explorador Web compatible con HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilidad para US GCC, GCC High y otras instituciones del gobierno de Estados Unidos
Actualmente, Microsoft 365 defender *no* está disponible para:
- Nube de la comunidad de US Government (GCC)
- Nube de US Government Community alta (GCC High)
- Departamento de defensa de los Estados Unidos
- Todos los centros de administración de EEUU con licencias comerciales

## <a name="related-topics"></a>Temas relacionados
- [Información general de Microsoft 365 defender](microsoft-threat-protection.md)
- [Activar Microsoft 365 defender](mtp-enable.md)
- [Administrar acceso y permisos](mtp-permissions.md)
