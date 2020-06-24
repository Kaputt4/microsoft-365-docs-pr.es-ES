---
title: Requisitos previos de la Protección contra amenazas de Microsoft
description: Obtenga más información sobre las licencias, requisitos previos de hardware y software, y otras opciones de configuración que le ofrece Protección contra amenazas de Microsoft.
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
ms.openlocfilehash: c64adf870d3669b983e11093196f59c82b1f59e0
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844911"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Requisitos previos de la Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

Obtenga información sobre licencias y otros requisitos para el aprovisionamiento y el uso de la [protección contra amenazas de Microsoft](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Requisitos de licencia
Cualquiera de estas licencias le da acceso a las características de protección contra amenazas de Microsoft en el centro de seguridad de Microsoft 365 sin costo adicional:

- Microsoft 365 E5 o A5
- Seguridad de Microsoft 365 E5 o de la A5
- Windows 10 Enterprise E5 o A5
- Enterprise Mobility + Security (EMS) E5 o A5 
- Office 365 E5 o A5
- Protección contra amenazas avanzada de Microsoft Defender
- Azure Advanced Threat Protection 
- Microsoft Cloud App Security
- Protección contra amenazas avanzada de Office 365 (plan 2)

> [!NOTE]
> Las licencias de prueba para Office 365 no proporcionan actualmente acceso a la protección contra amenazas de Microsoft.

Para obtener más información, [vea los planes de servicio de Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> ¿Todavía no tiene licencia? [Probar o comprar una suscripción a Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Comprobar las licencias existentes
Vaya al centro de administración de 365 de Microsoft ([admin.Microsoft.com](https://admin.microsoft.com/)) para ver las licencias existentes. En el Centro de administración, vaya a **Facturación** > **Licencias**.

>[!NOTE]
> Debe tener asignado el rol de **Administrador de facturación** o de **lector global** [en Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver la información de licencia. Si tiene problemas de acceso, póngase en contacto con un administrador global.

## <a name="required-permissions"></a>Permisos necesarios
Debe ser **administrador global** o **Administrador de seguridad** en Azure Active Directory para activar la protección contra amenazas de Microsoft. Para obtener la lista de funciones necesarias para usar la protección contra amenazas de Microsoft y obtener información sobre cómo se regula el acceso a los datos, Lea acerca de la [Administración del acceso a la protección contra amenazas de Microsoft](mtp-permissions.md).

## <a name="browser-requirements"></a>Requisitos de los exploradores
Acceda a Microsoft Threat Protection en el centro de seguridad de Microsoft 365 con Microsoft Edge, Internet Explorer 11 o cualquier explorador Web compatible con HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilidad para US GCC, GCC High y otras instituciones del gobierno de Estados Unidos
Actualmente, la protección contra amenazas de Microsoft *no* está disponible para:
- Nube de la comunidad de US Government (GCC)
- Nube de US Government Community alta (GCC High)
- Departamento de defensa de los Estados Unidos
- Todos los centros de administración de EEUU con licencias comerciales

## <a name="related-topics"></a>Temas relacionados
- [Introducción a la Protección contra amenazas de Microsoft](microsoft-threat-protection.md)
- [Habilitar la Protección contra amenazas de Microsoft](mtp-enable.md)
- [Administrar acceso y permisos](mtp-permissions.md)
