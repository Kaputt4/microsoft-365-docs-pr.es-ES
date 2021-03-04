---
title: Cambiar la duración de retención para un buzón inactivo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
ms.custom:
- seo-marvel-apr2020
description: Después de que un buzón de Office 365 esté inactivo, cambie la duración de la retención u directiva de retención de Office 365 asignada al buzón inactivo.
ms.openlocfilehash: ec8a4cac7d2ee8e40bd791bd531556d1151c1ad1
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421639"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

Un buzón inactivo se usa para conservar el correo electrónico de un antiguo empleado después de que abandone la organización. Un buzón se vuelve inactivo cuando se coloca una retención por juicio, una retención de In-Place, una directiva de retención de Microsoft 365 o una retención asociada a un caso de exhibición de documentos electrónicos en el buzón y se elimina la cuenta de usuario correspondiente. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. La duración de retención define cuánto tiempo se retienen los elementos en la carpeta Elementos recuperables. Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Después de que un buzón esté inactivo, puede cambiar la duración de la retención o la directiva de retención de Microsoft 365 asignada al buzón inactivo.
  
> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido del buzón, anunciamos la retirada de las In-Place en el Centro de administración de Exchange. Esto significa que debe usar las retenciones por juicio y las directivas de retención de Microsoft 365 para crear un buzón inactivo. A partir del 1 de abril de 2020 no podrá crear nuevas In-Place en Exchange Online. Pero aún podrá cambiar la duración de retención de una retención In-Place en un buzón inactivo. Sin embargo, a partir del 1 de julio de 2020, no podrá cambiar la duración de la retención. Solo podrá eliminar un buzón inactivo quitando la In-Place espera. Los buzones inactivos existentes que están en In-Place conservación se conservarán hasta que se quite la retención. Para obtener más información acerca de la retirada de In-Place, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).
  
## <a name="connect-to-powershell"></a>Conectarse a PowerShell

- Debe usar Exchange Online PowerShell para cambiar la duración de retención de una retención por juicio en un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Pero puede usar Exchange Online PowerShell o el EAC para cambiar la duración de retención de una retención In-Place espera. Puede usar el Centro de seguridad y cumplimiento o powerShell del Centro de seguridad & cumplimiento para cambiar la duración de retención de una directiva de retención de Microsoft 365.
    
- Para conectarse a PowerShell de Exchange Online o PowerShell & centro de cumplimiento, consulte uno de los temas siguientes:
    
  - [Conectarse a Exchange Online mediante PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)
    
  - [Conectarse a PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)
    
- Las retenciones asociadas con casos de exhibición de documentos electrónicos son retenciones infinitas, lo que significa que no hay ninguna duración de retención que se pueda cambiar. Los elementos se mantienen para siempre o hasta que se quita la retención y se elimina el buzón inactivo.
    
- Para obtener más información acerca de los buzones inactivos, vea Buzones inactivos [en Microsoft 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Dado que pueden colocarse distintos tipos de retenciones o una o más directivas de retención de Microsoft 365 en un buzón inactivo, el primer paso consiste en identificar las retenciones en un buzón inactivo.
  
Ejecute el siguiente comando en Exchange Online PowerShell para mostrar la información de retención de todos los buzones inactivos de la organización.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

El valor de **True** para la propiedad **LitigationHoldEnabled** indica que el buzón inactivo está en retención por juicio. Si una directiva de retención de In-Place, de exhibición de documentos electrónicos o de retención de Microsoft 365 se coloca en un buzón inactivo, se muestra un GUID para la directiva de retención o retención como el valor de la propiedad **InPlaceHolds.** Por ejemplo, a continuación se muestran los resultados de cinco buzones inactivos. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```

En la tabla siguiente se identifican los cinco tipos de retención diferentes que se usaron para hacer que cada buzón quedara inactivo.
  
|**Buzón inactivo**|**Tipo de retención**|**Cómo identificar la retención en el buzón inactivo**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Retención por juicio  <br/> |La  *propiedad LitigationHoldEnabled*  se establece en  `True` .  <br/> |
|Pilar Pinilla  <br/> |Retención en contexto  <br/> |La  *propiedad InPlaceHolds*  contiene el GUID de la retención In-Place que se coloca en el buzón inactivo. Puede saber que se trata de una retención In-Place porque el identificador no comienza con un prefijo.  <br/> Puede usar el comando de Exchange Online PowerShell para obtener información sobre la retención In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` en el buzón inactivo.  <br/> |
|Mario Necaise  <br/> |Directiva de retención de Microsoft 365 para toda la organización en el Centro de & seguridad  <br/> |La  *propiedad InPlaceHolds*  está vacía. Esto indica que una o más directivas de retención de Microsoft 365 en toda la organización o (en toda Exchange) se aplican al buzón inactivo. En este caso, puede ejecutar el comando en Exchange Online PowerShell para obtener una lista de los GUID para las directivas de retención de  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` Microsoft 365 en toda la organización. El GUID de las directivas de retención de toda la organización que se aplican a los buzones de Exchange comienzan con el  `mbx` prefijo; por ejemplo,  `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> <br/>Para identificar la directiva de retención de Microsoft 365 que se aplica al buzón inactivo, ejecute el siguiente comando en PowerShell del Centro de seguridad & cumplimiento.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Directiva de retención de Microsoft 365 en el Centro de seguridad & cumplimiento aplicado a buzones específicos  <br/> |La  *propiedad InPlaceHolds*  contiene el GUID de la directiva de retención de Microsoft 365 que se aplica al buzón inactivo. Puede saber que se trata de una directiva de retención que se aplica a buzones específicos porque el GUID comienza por el  `mbx` prefijo. Si el GUID de la directiva de retención aplicada al buzón inactivo comenzó con el prefijo, indicaría que la directiva de retención se aplica a las conversaciones de  `skp` Skype Empresarial.  <br/><br/> Para identificar la directiva de retención de Microsoft 365 que se aplica al buzón inactivo, ejecute el siguiente comando en PowerShell del Centro de seguridad & cumplimiento.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Asegúrese de quitar el  `mbx` prefijo o al ejecutar este  `skp` comando.  <br/> |
|Abraham McMahon  <br/> |Retención de casos de exhibición de documentos electrónicos en el Centro de & seguridad  <br/> |La  *propiedad InPlaceHolds*  contiene el GUID de la retención de casos de exhibición de documentos electrónicos que se coloca en el buzón inactivo. Puede saber que se trata de una retención de casos de exhibición de documentos electrónicos porque el GUID comienza por el  `UniH` prefijo.  <br/> Puede usar el cmdlet de PowerShell del Centro de seguridad & cumplimiento para obtener información sobre el caso de exhibición de documentos electrónicos al que está asociada la retención en el buzón  `Get-CaseHoldPolicy` inactivo. Por ejemplo, puede ejecutar el comando para mostrar el nombre de la retención  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` de casos que está en el buzón inactivo. Asegúrese de quitar el  `UniH` prefijo al ejecutar este comando.  <br/><br/> Para identificar el caso de exhibición de documentos electrónicos al que está asociada la retención en el buzón inactivo, ejecute los siguientes comandos.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Nota:** No se recomienda usar retenciones de exhibición de documentos electrónicos para buzones inactivos. Esto se debe a que los casos de exhibición de documentos electrónicos están destinados a casos específicos con límite de tiempo relacionados con un problema legal. En algún momento, un caso legal probablemente finalizará y las retenciones asociadas con el caso se quitarán y el caso de exhibición de documentos electrónicos se cerrará (o se eliminará). De hecho, si una retención que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y la retención se libera o el caso de exhibición de documentos electrónicos se cierra o elimina, el buzón inactivo se eliminará permanentemente. 

Para obtener más información acerca de las directivas de retención de Microsoft 365, vea [Learn about retention policies and retention labels](retention.md).
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Paso 2: cambiar la duración de retención para un buzón inactivo

Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es cambiar la duración para la retención. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Cambiar la duración de una retención por juicio.

A continuación se muestra cómo usar Exchange Online PowerShell para cambiar la duración de retención de una retención por juicio que se coloca en un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, se cambia la duración de retención a un período de tiempo ilimitado.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

El resultado es que los elementos del buzón inactivo se conservan indefinidamente o hasta que se quita la retención o se cambia la duración de la retención a un valor diferente.
  
> [!TIP]
> La mejor manera de identificar un buzón inactivo es usando el valor **Distinguished Name** o **Exchange GUID**. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Cambiar la duración de una conservación local

 In-Place las retenciones se han retirado y ya no se pueden modificar. Si un buzón inactivo tiene una retención In-Place aplicación, no puede cambiar la duración de retención. Solo puede quitar la retención In-Place, lo que dará como resultado la eliminación del buzón inactivo. Para obtener más información, vea [Eliminar un buzón inactivo.](delete-an-inactive-mailbox.md#remove-in-place-holds)
  
## <a name="more-information"></a>Más información

- **¿Cómo se calcula la duración de retención para un elemento en un buzón inactivo?** La duración se calcula desde la fecha original en que un elemento de buzón se recibe o se crea. 
    
- **¿Qué sucede cuando expira la duración de retención?** Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Si no hay ninguna duración especificada para la retención colocada en el buzón inactivo, los elementos de la carpeta Elementos recuperables nunca se purgan (a menos que se cambie la duración de retención del buzón inactivo). 
    
- **¿Se sigue procesando una directiva de retención de Exchange en buzones inactivos?** Si se aplicó una directiva de retención de Exchange (la característica de administración de registros de mensajería o MRM en  Exchange Online) a un buzón cuando se activó, las directivas de eliminación (que son etiquetas de retención configuradas con una acción eliminar retención) seguirán procesandose en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación se mueven a la carpeta Elementos recuperables cuando expira el período de retención. Esos elementos luego se purgan del buzón inactivo cuando expira la duración de retención de un elemento. 
    
    Por el contrario, se ignora cualquier directiva de archivo (que son etiquetas de retención configuradas con una acción de retención **MoveToArchive** ) que esté incluida en la directiva de retención asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Dado que un usuario no puede iniciar sesión en un buzón inactivo, no existen motivos para consumir los recursos del centro de datos para procesar las directivas de archivo. 

- **Para comprobar la nueva duración de retención de una retención por juicio, ejecute los siguientes comandos** 

   ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

- **Al igual que los buzones habituales, el Asistente para carpeta administrada (MFA) también procesa buzones inactivos.** En Exchange Online, mfa procesa buzones aproximadamente una vez cada siete días. Después de cambiar la duración de retención para un buzón inactivo, puede usar el cmdlet **Start-ManagedFolderAssistant** para empezar a procesar inmediatamente la nueva duración de retención para el buzón inactivo. Ejecute el comando siguiente. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Si se colocan muchas retenciones en un buzón inactivo, no se mostrarán todos los GUID de retención.** Puede ejecutar el siguiente comando para mostrar los GUID de todas las retenciones (excepto las retenciones por juicio) que se colocan en un buzón inactivo. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
