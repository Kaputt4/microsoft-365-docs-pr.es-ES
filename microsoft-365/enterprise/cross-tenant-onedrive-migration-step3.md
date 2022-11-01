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
ms.openlocfilehash: 6a42b833ecfc59d96f69d5061a0e6fe64746a8c6
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806175"
---
# <a name="step-3-cross-tenant-onedrive-migration---verifying-trust"></a>Paso 3: Migración entre inquilinos de OneDrive: Comprobación de la confianza

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