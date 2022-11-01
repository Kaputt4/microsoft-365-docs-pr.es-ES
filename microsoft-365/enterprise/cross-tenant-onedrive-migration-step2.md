---
title: Paso 2 de migración de datos de usuario entre inquilinos de OneDrive
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
description: Paso 2 de la característica de migración entre inquilinos de OneDrive
ms.openlocfilehash: 424636e01b89420979752c7c9b0e61d778319725
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807637"
---
# <a name="step-2-establishing-trust-between-the-source-and-target-tenants"></a>Paso 2: Establecer la confianza entre los inquilinos de origen y de destino

Este es el paso 2 de una solución diseñada para completar una migración entre inquilinos de OneDrive. Para más información, consulte [Introducción a la migración de OneDrive entre inquilinos](cross-tenant-onedrive-migration.md).

- Paso 1: [Conectarse al origen y a los inquilinos de destino](cross-tenant-onedrive-migration-step1.md)
- **Paso 2: [Establecer la confianza entre el inquilino de origen y el inquilino de destino](cross-tenant-onedrive-migration-step2.md)** 
- Paso 3: [Comprobar que se ha establecido la confianza](cross-tenant-onedrive-migration-step3.md) 
- Paso 4: [Creación previa de usuarios y grupos](cross-tenant-onedrive-migration-step4.md)  
- Paso 5: [Preparación de la asignación de identidades](cross-tenant-onedrive-migration-step5.md)
- Paso 6: [Iniciar una migración entre inquilinos de OneDrive](cross-tenant-onedrive-migration-step6.md)
- Paso 7: [Pasos posteriores a la migración](cross-tenant-onedrive-migration-step7.md)

Después de conectarse al inquilino de origen y de destino, el siguiente paso para realizar una migración entre inquilinos de OneDrive es establecer la confianza entre los inquilinos.

Para establecer la confianza, cada administrador de inquilinos de SharePoint Online debe ejecutar comandos específicos en los inquilinos de origen y de destino. Una vez solicitada la confianza, el administrador del inquilino de destino recibirá un correo electrónico en el que se le informa de que otro inquilino está intentando establecer una relación de confianza.

>[!Note]
>El comando "trust" es específico de SharePoint Online. Solo concede permiso al administrador de SharePoint en el inquilino de origen para ejecutar operaciones de migración de OneDrive en el inquilino de destino identificado. 
>
>La concesión de confianza *no* concede al administrador ninguna visibilidad, permiso ni capacidad para colaborar entre el inquilino de origen y el inquilino de destino. 

>[!Important]
>Si es cliente de Microsoft 365 Multi-Geo, debe establecer la confianza entre cada geografía implicada en el proyecto de migración.
>

## <a name="before-you-begin"></a>Antes de empezar

Antes de ejecutar los comandos de confianza, obtenga las direcciones URL de host entre inquilinos para los inquilinos de origen y de destino. Necesitará estas direcciones URL al establecer la relación de confianza entre de origen a destino y de destino a origen. 

**Para obtener las direcciones URL de host entre inquilinos:**

En los inquilinos de origen y de destino, ejecute:

```powershell

Get-SPOCrossTenantHostURL
``` 

 
*Ejemplo:* Ejecute el comando en el inquilino de origen:

 :::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-hosturl-source.png" alt-text="ejemplo de cómo obtener la dirección URL del host para el origen":::

*Ejemplo:* Ejecute el comando en el inquilino de destino:

:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-hosturl-target.png" alt-text="ejemplo de cómo obtener la dirección URL del host para el destino":::
 


## <a name="run-the-trust-commands"></a>Ejecución de los comandos de confianza
Estos comandos envían una solicitud al inquilino con el que desea establecer la confianza.

1. En el inquilino de origen, ejecute este comando para enviar una solicitud de confianza al inquilino de destino:

```powershell

Set-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Target -PartnerCrossTenantHostUrl <TARGETCrossTenantHostUrl>
 
``` 

</br>

2. En el inquilino de destino, ejecute este comando para enviar una solicitud de confianza al inquilino de origen:

```powershell
Set-SPOCrossTenantRelationship -Scenario MnA -PartnerRole Source -PartnerCrossTenantHostUrl <SOURCECrossTenantHostUrl>
```

 
### <a name="parameter-definitions"></a>Definiciones de parámetros

|Parámetro|Definición|
|:-----|:-----|
|PartnerRole|Roles del inquilino del asociado con el que se establece la confianza.  Use *source* si el inquilino del asociado es el origen de las migraciones de OneDrive y *el destino* si el inquilino del asociado es el destino.
|PartnerCrossTenantHostURL|Dirección URL del host entre inquilinos del inquilino asociado. El inquilino del asociado puede determinarlo automáticamente ejecutando: *Get-SPOCrossTenantHostURL* en cada uno de los inquilinos.|

## <a name="sample-trust-email"></a>Correo electrónico de confianza de ejemplo
Lo siguiente en un ejemplo del correo electrónico que se envía a los administradores globales:


:::image type="content" source="../media/cross-tenant-migration/t2t-onedrive-trust-email.png" alt-text="ejemplo de correo electrónico de confianza":::


**Asunto:**  Inquilino de SPO [https://a830edad9050849mnaus093022-my.sharepoint.com/] [setuporupdate] Relación de organización [Scenario=MnA, Role=Source] con nosotros

**Mensaje:**  Inquilino de SPO [https://a830edad9050849mnaus093022-my.sharepoint.com/] [setuporupdate] Relación de organización [Scenario=MnA, Role=Source] con nosotros


## <a name="step-3-verify-that-trust-has-been-established"></a>Paso 3: [Comprobar que se ha establecido la confianza](cross-tenant-onedrive-migration-step3.md)