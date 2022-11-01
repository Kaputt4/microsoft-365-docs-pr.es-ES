---
title: Paso 7 de migración de datos de usuario entre inquilinos de OneDrive
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
description: Paso 7 de la característica de migración entre inquilinos de OneDrive
ms.openlocfilehash: 22d18111bc45d30fab5cc9012857a979fa510e18
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807593"
---
# <a name="step-7--post-migration-steps"></a>Paso 7: Pasos posteriores a la migración

Este es el paso 7 de una solución diseñada para completar una migración entre inquilinos de OneDrive. Para más información, consulte [Introducción a la migración de OneDrive entre inquilinos](cross-tenant-onedrive-migration.md).

- Paso 1: [Conectarse al origen y a los inquilinos de destino](cross-tenant-onedrive-migration-step1.md)
- Paso 2: [Establecer la confianza entre el inquilino de origen y el inquilino de destino](cross-tenant-onedrive-migration-step2.md) 
- Paso 3: [Comprobar que se ha establecido la confianza](cross-tenant-onedrive-migration-step3.md) 
- Paso 4: [Creación previa de usuarios y grupos](cross-tenant-onedrive-migration-step4.md)  
- Paso 5: [Preparación de la asignación de identidades](cross-tenant-onedrive-migration-step5.md)
- Paso 6: [Iniciar una migración entre inquilinos de OneDrive](cross-tenant-onedrive-migration-step6.md)
- **Paso 7: [Pasos posteriores a la migración](cross-tenant-onedrive-migration-step7.md)**

## <a name="removing-trust-relationship"></a>Eliminación de la relación de confianza

>[!Important]
>Asegúrese de quitar la relación de confianza en los inquilinos de origen y de destino antes de que expiren las licencias de inquilino de origen. Una vez que expiren las licencias, el comando de eliminación de confianza no funcionará en el origen.

1. En el inquilino de origen, ejecute este comando para quitar la relación de confianza entre el inquilino de origen y el inquilino de destino.

```powershell
Remove-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Target -PartnerCrossTenantHostUrl <TARGETCrossTenantHostUrl>

```
</br>

2. En el inquilino de destino, ejecute este comando para quitar la relación de confianza entre el inquilino de destino y el inquilino de origen.

```powershell

Remove-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Target -PartnerCrossTenantHostUrl <TARGETCrossTenantHostUrl>

```


### <a name="parameter-definitions"></a>Definiciones de parámetros

|Parámetro|Definición|
|:-----|:-----|
|PartnerRole|Roles del inquilino del asociado con el que se establece la confianza.  Use *source* si el inquilino del asociado es el origen de las migraciones de OneDrive y *el destino* si el inquilino del asociado es el destino.
|PartnerCrossTenantHostURL|Dirección URL del host entre inquilinos del inquilino asociado.  El inquilino del asociado puede determinarlo automáticamente ejecutando: *Get-SPOCrossTenantHostURL* en cada uno de los inquilinos.|


## <a name="other-post-migration-steps"></a>Otros pasos posteriores a la migración

Una vez completada la migración, los usuarios de OneDrive deben iniciar sesión con su nueva identidad y volver a sincronizar sus archivos en sus dispositivos en el inquilino de destino.

### <a name="onedrive-for-business"></a>OneDrive para la Empresa
Con sus nuevas credenciales, haga que los usuarios inicien sesión en OneDrive mediante el iniciador de aplicaciones de Microsoft 365 o un explorador web.

### <a name="permissions-on-onedrive-content"></a>Permisos en contenido de OneDrive
Los usuarios con permiso para acceder al contenido de OneDrive seguirán teniendo acceso a él, siempre que se hayan incluido en el archivo de asignación de identidades.

### <a name="onedrive-sync-client"></a>Cliente de sincronización de OneDrive
El usuario debe iniciar sesión en el **cliente de sincronización de OneDrive** y en su nueva ubicación de OneDrive mediante su nueva identidad. Una vez completado ese paso, los archivos y carpetas comenzarán a resincronizarse en el dispositivo.

### <a name="sharing-links"></a>Compartir vínculos
Los vínculos compartidos existentes para los archivos migrados se redirigirán automáticamente a la nueva ubicación de destino.
