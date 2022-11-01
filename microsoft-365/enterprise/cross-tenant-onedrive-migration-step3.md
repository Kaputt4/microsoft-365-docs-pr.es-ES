---
title: Paso 3 de migración de datos de usuario entre inquilinos de OneDrive
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
description: Paso 3 de la característica de migración entre inquilinos de OneDrive
ms.openlocfilehash: c59706de4300f6c505582b74aef4ec7223fb3d08
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807769"
---
# <a name="step-3-verifying-trust"></a>Paso 3: Comprobar la confianza

Este es el paso 3 de una solución diseñada para completar una migración entre inquilinos de OneDrive. Para más información, consulte [Introducción a la migración de OneDrive entre inquilinos](cross-tenant-onedrive-migration.md).

- Paso 1: [Conectarse al origen y a los inquilinos de destino](cross-tenant-onedrive-migration-step1.md)
- Paso 2: [Establecer la confianza entre el inquilino de origen y el inquilino de destino](cross-tenant-onedrive-migration-step2.md) 
- **Paso 3: [Comprobar que se ha establecido la confianza](cross-tenant-onedrive-migration-step3.md)** 
- Paso 4: [Creación previa de usuarios y grupos](cross-tenant-onedrive-migration-step4.md)  
- Paso 5: [Preparación de la asignación de identidades](cross-tenant-onedrive-migration-step5.md)
- Paso 6: [Iniciar una migración entre inquilinos de OneDrive](cross-tenant-onedrive-migration-step6.md)
- Paso 7: [Pasos posteriores a la migración](cross-tenant-onedrive-migration-step7.md)

Antes de continuar con la migración, deberá comprobar que la confianza se ha completado. Un estado de *GoodToProceed*, confirma que se comprueba la confianza.

## <a name="to-verify-trust-has-been-established"></a>Para comprobar que se ha establecido la confianza

1. En el **inquilino de origen** , ejecute:
 
```powershell

Verify-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Target -PartnerCrossTenantHostUrl <TARGETCrossTenantHostUrl>

```
2. En el **inquilino de destino** , ejecute:

```powershell 

Verify-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Source -PartnerCrossTenantHostUrl <SOURCECrossTenantHostUrl>
```

## <a name="troubleshooting-trust-issues"></a>Solución de problemas de confianza

Al comprobar la confianza, los valores posibles

|Valor|Descripción|
|:-----|:-----|
|NotEstablished|La confianza no se ha solicitado localmente.|
|NotEstablishedByPartner|El asociado no ha solicitado la confianza|
|DormantByPartner|La confianza solicitada del asociado se encuentra dentro del período de espera de siete días después de la creación.|
|CouldNotContactPartner|No se pudo ponerse en contacto con el asociado para determinar el estado.|
|GoodToProceed|Comprobado para continuar.|


## <a name="step-4-pre-create-users-and-groups"></a>Paso 4: [Creación previa de usuarios y grupos](cross-tenant-onedrive-migration-step4.md)