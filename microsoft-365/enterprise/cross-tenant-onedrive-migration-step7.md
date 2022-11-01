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
ms.openlocfilehash: acd9130b6058ef0dceae0dcc8c6e60699a4fd39e
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806130"
---
# <a name="step-7--post-migration-steps"></a>Paso 7: Pasos posteriores a la migración

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
