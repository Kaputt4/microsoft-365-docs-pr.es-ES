---
title: Migración entre inquilinos de OneDrive
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: Migración entre inquilinos de OneDrive
ms.openlocfilehash: 0d2076ed4b74cd8bbe21e5d7e7b6e1d0189f822d
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68537425"
---
# <a name="cross-tenant-onedrive-migration"></a>Migración entre inquilinos de OneDrive

>[!Note]
> La información de este artículo hace referencia a la **migración entre inquilinos de OneDrive**. [Obtenga información sobre la migración de buzones entre inquilinos aquí.](/microsoft-365/enterprise/cross-tenant-mailbox-migration)

Durante las fusiones o desinversiones, normalmente se necesita la capacidad de mover las cuentas de OneDrive de usuario a un nuevo inquilino de Microsoft 365. Con la migración entre inquilinos de OneDrive, los administradores de inquilinos pueden usar herramientas conocidas como *PowerShell de SharePoint Online* para realizar la transición de los usuarios a su nueva organización.

Los administradores de SharePoint de dos inquilinos independientes pueden usar el cmdlet *Set-SPOCrossTenantRelationship* para establecer una relación de organización y el comando *Start-SPOCrossTenantUserContentMove* para iniciar los movimientos de OneDrive entre inquilinos.

Se pueden programar hasta 4000 cuentas de OneDrive para la migración de antemano en un momento dado. Una vez programadas, las migraciones se producen sin que los datos del usuario salgan de la nube de Microsoft 365 y con una interrupción mínima, lo que requiere solo unos minutos en los que OneDrive de un usuario será de solo lectura. Una vez completadas las migraciones, se coloca una redirección en la ubicación de OneDrive original del usuario, por lo que los vínculos a archivos y carpetas pueden seguir funcionando en la nueva ubicación. 

>[!Important]
>- Cada usuario que tenga su multiinquilino migrado de OneDrive debe tener licencia para la migración de datos de usuario entre inquilinos.
>- La migración entre inquilinos de OneDrive no se puede usar para los clientes que usan El cifrado de servicio con la clave de cliente de Microsoft Purview. [Más información sobre el cifrado de servicios con la clave de cliente de Microsoft Purview: Microsoft Purview](/microsoft-365/compliance/customer-key-overview?view=o365-worldwide)