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
ms.openlocfilehash: b9bb72707e11e3257eabac093e4a76daa903bf40
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806290"
---
# <a name="step-1-cross-tenant-onedrive-migration---connect-to-the-source-and-target-tenants"></a>Paso 1: Migración de OneDrive entre inquilinos: conexión a los inquilinos de origen y de destino

El primer paso de la migración entre inquilinos de OneDrive es conectarse al inquilino de origen y de destino de SharePoint.

## <a name="before-you-begin"></a>Antes de empezar

- **Microsoft Office SharePoint Online PowerShell**. Confirme que tiene instalada la versión más reciente. Si no es así, [descargue el Shell de administración de SharePoint Online desde el Centro de descarga oficial de Microsoft](/download/details.aspx?id=35588).
- Sea administrador de SharePoint Online o administrador global de Microsoft 365 en los inquilinos de origen y de destino.


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