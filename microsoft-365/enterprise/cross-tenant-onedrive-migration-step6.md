---
title: Paso 6 de migración de datos de usuario entre inquilinos de OneDrive
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
description: Paso 6 de la característica de migración entre inquilinos de OneDrive
ms.openlocfilehash: 6ebf12c11388d35daa4e8261c193af721af88124
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806210"
---
# <a name="step-6-start-a-onedrive-cross-tenant-migration"></a>Paso 6: Iniciar una migración entre inquilinos de OneDrive

Ahora está listo para iniciar la migración de OneDrive.  Antes de iniciar cualquier migración entre inquilinos, siga estos pasos. 

1. Asegúrese de que ha comprobado el estado de compatibilidad. si ve un estado compatible en el inquilino de origen, puede continuar. Ejecutar:

```powershell
Get-SPOCrossTenantCompatibilityStatus –PartnerCrossTenantHostURL [Target tenant hostname]
```

2. Para iniciar la migración, un Administración de SharePoint Online o una Administración global de Microsoft 365 del inquilino de origen debe ejecutar el siguiente comando:

```PowerShell
Start-SPOCrossTenantUserContentMove  -SourceUserPrincipalName <…> -TargetUserPrincipalName <…> -TargetCrossTenantHostUrl <…>
```

|Parámetros|Description|
|:-----|:-----|
|SourceUserPrincipalName|Nombre principal de usuario del usuario propietario de OneDrive en el inquilino de origen.|
|TargetUserPrincipalName|Nombre principal de usuario del usuario propietario de OneDrive en el inquilino de destino.|
|TargetCrossTenantHostUrl|Dirección URL del host entre inquilinos del inquilino de destino. Para buscar TargetCrossTenantHostUrl, ejecute *Get-SPOCrossTenantHostUrl* en el inquilino.|

Ejemplo:

```Powershell

Start-SPOCrossTenantUserContentMove -SourceUserPrincipalName DiegoS@M365x016651.OnMicrosoft.com -TargetUserPrincipalName
        Test-Diego@M365x946316.OnMicrosoft.com -TargetCrossTenantHostUrl https://m365x946316-my.sharepoint.com/ 

```

Para programar una migración más adelante, puede usar y anexar el comando anterior con uno de los parámetros siguientes. 

Estos comandos pueden ser útiles al planear lotes masivos de migraciones de OneDrive.  Puede poner en cola o migrar hasta 4000 migraciones de OneDrive por lote.  Si el número de usuarios supera los 4000, cree lotes independientes y programe su ejecución una vez que el lote actual esté cerca de completarse.

|Parámetro|Descripción|
|:-----|:-----|
|PreferredMoveBeginDate|Es probable que la migración comience en este momento especificado. La hora debe especificarse en hora universal coordinada (UTC).|
|PreferredMoveEndDate|Es probable que la migración se complete en este momento especificado, de la mejor manera posible. La hora debe especificarse en hora universal coordinada (UTC).|


## <a name="onedrive-status-pre-migration"></a>Migración previa al estado de OneDrive

Antes de iniciar la migración, el estado de OneDrive de origen actual de los usuarios será similar al siguiente ejemplo.  Este ejemplo procede del inquilino de origen de los usuarios, que muestra sus archivos y carpetas actuales.


:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-status-premigration.png" alt-text="estado anterior a la migración":::

## <a name="cancelling-a-onedrive-migration"></a>Cancelación de una migración de OneDrive

Puede detener la migración entre inquilinos de OneDrive de un usuario mediante el siguiente comando, siempre que la migración no esté en curso o con el estado Correcto.

```powershell

Stop-SPOCrossTenantUserContentMove – SourceUserPrincipalName [UPN name of user who you wish to stop]

Stop-SPOCrossTenantUserContentMove – SourceUserPrincipalName DiegoS@M365x016651.OnMicrosoft.com
```

## <a name="determining-current-status-of-a-migration"></a>Determinación del estado actual de una migración

Después de iniciar la migración, puede comprobar su estado mediante el siguiente comando en el inquilino de origen o de destino:

**Formato de comando de origen**
```powershell

Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL [Target URL]
```
Ejemplo:

```Powershell
Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL  https://m365x946316-my.sharepoint.com/

```

**Comando de destino:** 

```powershell

Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL [Source URL]
Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL  https://m365x016551-my.sharepoint.com/
```

Para buscar el estado de la migración de un usuario específico, use el parámetro *UserPrincipalName* :

```powershell

Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL <PartnerCrossTenantHostURL> -SourceUserPrincipalName <UPN>
Get-SPOUserAndContentMoveState -PartnerCrossTenantHostURL https://m365x946316-my.sharepoint.com -SourceUserPrincipalName DiegoS@M365x016651.OnMicrosoft.com
```

Para obtener el estado del movimiento en función del UPN de un usuario determinado, pero con más información, use el parámetro *-Verbose* .

Ejemplo:

```PowerShell

Get-SPOCrossTenantUserContentMoveState -PartnerCrossTenantHostURL https://ttesttenant-my.sharepoint.com -SourceUserPrincipalName User3@stesttenant.onmicrosoft.com -Verbose 

```


## <a name="migration-states"></a>Estados de migración


|Estado|Descripción|
|:-----|:-----|
|NotStarted|La migración aún no se ha iniciado.|
|Scheduled|La migración está ahora en la cola y está programada para ejecutarse cuando una ranura esté disponible.|
|ReadytoTrigger|La migración está en su fase previa al vuelo y comenzará la migración en breve.|
|InProgress|La migración está en curso en uno de los siguientes estados: </br>-Validación </br>-Copia de seguridad </br>-Restaurar </br>-Limpieza|
|Correcto|La migración se ha completado correctamente.|
|Reprogramado|Es posible que la migración no se haya completado y se haya vuelto a poner en cola para otro paso.|
|Error |No se pudo completar la migración.|


 
## <a name="post-migration-status-checks"></a>Comprobaciones de estado posteriores a la migración

**Inquilino de destino:** Una vez completada correctamente la migración, compruebe el estado del usuario en el inquilino de destino iniciando sesión en su nueva cuenta de OneDrive. 

**Inquilino de origen:** Dado que el usuario se ha migrado correctamente al inquilino de destino, ya no tiene una cuenta activa de OneDrive en el origen.


## <a name="step-7-post-migration-steps"></a>Paso 7: [Pasos posteriores a la migración](cross-tenant-onedrive-migration-step7.md)