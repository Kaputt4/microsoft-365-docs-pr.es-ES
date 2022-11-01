---
title: Paso 1 de migración de datos de usuario entre inquilinos de OneDrive
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
description: Paso 1 de la característica de migración entre inquilinos de OneDrive
ms.openlocfilehash: 59bb8047f1b85d1f8d9cc4843ecc3e0337cef5c2
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807549"
---
# <a name="step-1-connect-to-the-source-and-target-tenants"></a>Paso 1: Conexión a los inquilinos de origen y de destino

Este es el paso 1 de una solución diseñada para completar una migración entre inquilinos de OneDrive. Para más información, consulte [Introducción a la migración de OneDrive entre inquilinos](cross-tenant-onedrive-migration.md).

- **Paso 1: [Conectarse al origen y a los inquilinos de destino](cross-tenant-onedrive-migration-step1.md)**
- Paso 2: [Establecer la confianza entre el inquilino de origen y el inquilino de destino](cross-tenant-onedrive-migration-step2.md) 
- Paso 3: [Comprobar que se ha establecido la confianza](cross-tenant-onedrive-migration-step3.md) 
- Paso 4: [Creación previa de usuarios y grupos](cross-tenant-onedrive-migration-step4.md)  
- Paso 5: [Preparación de la asignación de identidades](cross-tenant-onedrive-migration-step5.md)
- Paso 6: [Iniciar una migración entre inquilinos de OneDrive](cross-tenant-onedrive-migration-step6.md)
- Paso 7: [Pasos posteriores a la migración](cross-tenant-onedrive-migration-step7.md)

## <a name="before-you-begin"></a>Antes de empezar

- **Microsoft Office SharePoint Online PowerShell**. Confirme que tiene instalada la versión más reciente. Si no es así, [descargue el Shell de administración de SharePoint Online desde el Centro de descarga oficial de Microsoft](/download/details.aspx?id=35588).
- Ser administrador de SharePoint Online o administrador global de Microsoft 365 en los inquilinos de origen y de destino


### <a name="connect-to-both-tenants"></a>Conexión a ambos inquilinos

1. Inicie sesión en el Shell de administración de SharePoint como administrador de SharePoint Online o administrador global de Microsoft 365.
2. Ejecute lo siguiente escribiendo la dirección URL del inquilino **de origen** : 

    ```powershell
    Connect-SPOService -url https://<TenantName>-admin.sharepoint.com
    ```

3. Cuando se le solicite, inicie sesión en el inquilino de **origen** con el nombre de usuario y la contraseña de Administración.
 
4. Ejecute lo siguiente escribiendo la dirección URL del inquilino de **destino** : 

    ```powershell
    Connect-SPOService -url https://<TenantName>-admin.sharepoint.com
    ```

5. Cuando se le solicite, inicie sesión en el inquilino de **destino** con el nombre de usuario y la contraseña de Administración.

>[!Important]
>**Clientes de Microsoft 365 Multi-Geo:** Debe tratar cada geografía como un inquilino independiente. Proporcione las direcciones URL específicas de geografía correctas a lo largo del proceso de migración.

## <a name="step-2-establish-trust-between-the-source-and-target-tenants"></a>Paso 2: [Establecer la confianza entre los inquilinos de origen y de destino](cross-tenant-onedrive-migration-step2.md)