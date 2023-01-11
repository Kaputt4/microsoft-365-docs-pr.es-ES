---
title: Administración del tamaño del buzón del grupo de Microsoft 365
description: Obtenga información sobre la administración del tamaño del buzón de grupo en Microsoft 365.
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
search.appverid: ''
ms.reviewer: ''
author: serdars
ms.author: serdars
ms.openlocfilehash: 7651903eecf899b15306ed7ec81fa15eed131450
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68384039"
---
# <a name="microsoft-365-group-mailbox-size-management"></a>Administración del tamaño del buzón de grupo de Microsoft 365 

Cada grupo de Microsoft 365 viene equipado con un buzón dedicado que almacena los correos electrónicos recibidos en el grupo. El buzón de grupo también lo usan aplicaciones como SharePoint Online, Yammer, Teams, etc. El buzón de grupo está equipado con una cuota de almacenamiento inicial de 50 GB. Si se alcanza la cuota de buzón de grupo, los correos electrónicos se envían a los grupos NDR. Por lo tanto, se recomienda quitar el contenido anterior de los buzones de grupo para asegurarse de que el buzón de grupo no alcanza su cuota. 

Las siguientes maneras le ayudan a comprender cómo funciona el cálculo de cuotas, los procedimientos recomendados o el enfoque proactivo adoptado para asegurarse de que el buzón de grupo no alcanza su cuota. Y el curso de acción que se va a realizar si el buzón de grupo ha alcanzado o superado su cuota.

## <a name="proactive-approach-to-keep-group-mailbox-size-in-check"></a>Enfoque proactivo para mantener el tamaño del buzón de grupo activo 

Puede crear directivas de retención para asegurarse de que el correo electrónico anterior de los grupos se quita automáticamente al alcanzar el límite de tiempo especificado. Para obtener más información, sobre los pasos para crear una directiva de retención para el grupo de Microsoft 365, consulte [Creación y configuración de directivas de retención](/microsoft-365/compliance/create-retention-policies). Las directivas de retención tardan más tiempo en limpiar los datos, por lo que deben aplicarse durante la creación de un buzón de grupo. Las directivas de retención no se pueden usar como herramienta para vaciar o quitar inmediatamente los datos de un buzón de grupo.

## <a name="to-monitor-the-group-mailbox-size"></a>Para supervisar el tamaño del buzón de grupo: 

Use el siguiente comando para comprobar la cuota actual asignada para el buzón de grupo:

```PowerShell
Get-Mailbox -GroupMailbox <groupname> |ft ProhibitSendReceiveQuota,ProhibitSendQuota,IssueWarningQuota 
```

Y use el siguiente comando para comprobar el tamaño actual del buzón de grupo:

```PowerShell
Get-MailboxStatistics <groupname> | ft TotalDeletedItemSize,TotalItemSize 
```

## <a name="steps-to-follow-when-the-group-mailbox-has-reached-its-limit"></a>Pasos que se deben seguir cuando el buzón de grupo ha alcanzado su límite:  

Como se mencionó anteriormente, el buzón de grupo se usa para que varias aplicaciones almacenen datos. Una vez que el buzón de grupo ha alcanzado su cuota, es importante identificar las carpetas que ocupan más datos y realizar la acción adecuada. 

1. Comience con el siguiente comando para confirmar que se ha superado la cuota de buzón de grupo: 

   ```PowerShell
   Get-MailboxStatistics <groupname> |ft TotalItemSize,TotalDeletedItemSize 
   ```

   El buzón de grupo se distribuye en varios `TargetQuota`, es decir, Sistema, Recuperable y Usuario. Las carpetas que coinciden con `TargetQuota` "User" son las únicas que se tienen en cuenta en el cálculo de la cuota de grupo.  

2. Use el siguiente comando para comprobar el tamaño de carpeta que ocupa los datos de usuario: 

   ```PowerShell
   Get-MailboxFolderStatistics <groupname> | where { $_.TargetQuota -like 'User' } | ft Name,FolderPath,FolderType,FolderSize 

   Get-MailboxFolderStatistics <groupname> -FolderScope NonIPMRoot | where { $_.TargetQuota -like 'User' } | ft Name,FolderType,*size* 
   ```
3. Compruebe la cuota o el tamaño de las carpetas.

4. Si la carpeta que consume el espacio es , como se `SharePointWebPartsConnectorMessages`mencionó en [Uso del elemento web conector](https://support.microsoft.com/en-us/office/use-the-connector-web-part-db0756aa-f78f-4b74-8b19-be5dca0420e1?ns=spostandard&version=16&syslcid=1033&uilcid=1033&appver=spo160&helpid=wssenduser_useconnectorwebpart_fl862286&ui=en-us&rs=en-us&ad=us), haga lo siguiente:

   1. Deshabilite el conector si no se usa. 

   2. Espere a que los mensajes se borren de forma predeterminada en 90 días. 

5. Si no hay ninguna carpeta especial que ocupe el tamaño del buzón de grupo, [aplique la directiva de retención del buzón de correo de grupo](/microsoft-365/compliance/create-retention-policies) y espere a que la directiva de retención limpie los correos electrónicos del buzón de grupo. 
  

