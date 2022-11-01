---
title: Paso 4 de migración de datos de usuarios entre inquilinos de OneDrive
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sharepoint-migration
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: Paso 4 de la característica de migración entre inquilinos de OneDrive
ms.openlocfilehash: 107bb6e2b8ab08d871b0671491bc9098e02ed034
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807747"
---
# <a name="step-4-pre-creating-users-and-groups"></a>Paso 4: Creación previa de usuarios y grupos

Este es el paso 4 de una solución diseñada para completar una migración entre inquilinos de OneDrive. Para más información, consulte [Introducción a la migración de OneDrive entre inquilinos](cross-tenant-onedrive-migration.md).

- Paso 1: [Conectarse al origen y a los inquilinos de destino](cross-tenant-onedrive-migration-step1.md)
- Paso 2: [Establecer la confianza entre el inquilino de origen y el inquilino de destino](cross-tenant-onedrive-migration-step2.md) 
- Paso 3: [Comprobar que se ha establecido la confianza](cross-tenant-onedrive-migration-step3.md) 
- **Paso 4: [Creación previa de usuarios y grupos](cross-tenant-onedrive-migration-step4.md)**  
- Paso 5: [Preparación de la asignación de identidades](cross-tenant-onedrive-migration-step5.md)
- Paso 6: [Iniciar una migración entre inquilinos de OneDrive](cross-tenant-onedrive-migration-step6.md)
- Paso 7: [Pasos posteriores a la migración](cross-tenant-onedrive-migration-step7.md)


## <a name="identify-users-and-groups-to-be-migrated"></a>Identificación de usuarios y grupos que se van a migrar

Para asegurarse de que los permisos de OneDrive se conservan como parte de la migración, es necesario crear un archivo de asignación para alinear a los usuarios del inquilino de origen con el inquilino de destino.

1. Identifique la lista completa de sitios de OneDrive que se migrarán del origen al inquilino de destino.
2. Prepare una lista completa de usuarios y grupos que se migrarán al inquilino de destino.

## <a name="pre-create-users-and-groups-on-the-target-tenant"></a>Creación previa de usuarios y grupos en el inquilino de destino

1. Cree previamente usuarios y grupos según sea necesario en el directorio del inquilino de destino.
2. Todos los usuarios cuyas cuentas de OneDrive migran al inquilino de destino deben tener nuevas identidades de usuario creadas para ellos en el inquilino de destino.
3. A todos los usuarios cuyas cuentas de OneDrive se van a migrar al inquilino de destino se les debe asignar la licencia de OneDrive adecuada.
4. Los usuarios que permanezcan en el inquilino de origen pero necesiten acceso a los recursos que migran al inquilino de destino deben tener nuevas identidades de invitado creadas para ellos en el inquilino de destino.
5. Los usuarios creados previamente deben agregarse como miembros de los grupos de seguridad o grupos unificados adecuados antes de que comience la migración de OneDrive. 
6. Si el nombre de usuario o grupo ya existe en el inquilino de destino, cree un usuario o grupo con un nombre diferente y anote el nombre para el paso siguiente.
7. Se recomienda que las creaciones de sitios de OneDrive estén restringidas en el inquilino de destino para evitar que los usuarios creen sitios de OneDrive.

>[!Note]
>Para obtener más información sobre cómo restringir la creación de sitios de OneDrive, consulte [Deshabilitar la creación de OneDrive para algunos usuarios](/sharepoint/manage-user-profiles#disable-onedrive-creation-for-some-users).

## <a name="step-5-prepare-the-identity-mapping-file"></a>Paso 5: [Preparación del archivo de asignación de identidades](cross-tenant-onedrive-migration-step5.md)