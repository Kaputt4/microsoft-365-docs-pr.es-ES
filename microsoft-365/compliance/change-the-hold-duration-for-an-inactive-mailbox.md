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
description: Una vez que un buzón de correo de Office 365 se convierte en inactivo, cambie la duración de la Directiva de retención de Office 365 o suspensión asignada al buzón inactivo.
ms.openlocfilehash: 675e6eb36f762a50c3caafce07d09fda9ba9d98e
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126381"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

Un buzón inactivo se usa para conservar el correo electrónico de un antiguo empleado después de que abandone la organización. Un buzón se vuelve inactivo cuando se coloca en el buzón una retención por juicio, una retención local, una directiva de retención de Microsoft 365 o una retención asociada a un caso de exhibición de documentos electrónicos, y se elimina la cuenta de usuario correspondiente. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. La duración de retención define cuánto tiempo se retienen los elementos en la carpeta Elementos recuperables. Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Una vez que un buzón se convierte en inactivo, puede cambiar la duración de la retención o la Directiva de retención de Microsoft 365 asignada al buzón inactivo.
  
> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido de los buzones, estamos anunciando la retirada de conservaciones locales en el centro de administración de Exchange. Esto significa que debe usar las suspensiones por juicio y las directivas de retención de Microsoft 365 para crear un buzón inactivo. A partir del 1 de abril de 2020, no podrá crear nuevas retenciones locales en Exchange Online. Pero todavía podrá cambiar la duración de retención de una conservación local colocada en un buzón inactivo. Sin embargo, a partir del 1 de julio de 2020, no podrá cambiar la duración de retención. Solo se podrá eliminar un buzón inactivo si se quita la retención local. Los buzones inactivos existentes que se encuentran en conservación local se conservarán hasta que se quite la retención. Para obtener más información acerca de la retirada de suspensiones locales, consulte [jubilación de las herramientas de eDiscovery heredadas](legacy-ediscovery-retirement.md).
  
## <a name="connect-to-powershell"></a>Conectarse a PowerShell

- Debe usar Exchange Online PowerShell para cambiar la duración de retención para una retención por juicio en un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Pero puede usar Exchange Online PowerShell o el EAC para cambiar la duración de retención para una conservación local. Puede usar el centro de seguridad y cumplimiento o el PowerShell del centro de cumplimiento de & de seguridad para cambiar la duración de retención de una directiva de retención de Microsoft 365.
    
- Para conectarse al PowerShell del centro de seguridad & cumplimiento de Exchange Online, consulte uno de los siguientes temas:
    
  - [Conectarse a Exchange Online mediante PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [Conectarse a PowerShell del Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=799771)
    
- Las retenciones asociadas con casos de eDiscovery son suspensiones infinitas, lo que significa que no hay duración de retención que pueda cambiarse. Los elementos se mantienen para siempre o hasta que se quita la retención y se elimina el buzón inactivo.
    
- Para obtener más información acerca de los buzones inactivos, consulte [buzones inactivos en Microsoft 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Como se pueden colocar distintos tipos de suspensiones o una o varias directivas de retención de Microsoft 365 en un buzón inactivo, el primer paso es identificar las retenciones en un buzón inactivo.
  
Ejecute el siguiente comando en Exchange Online PowerShell para mostrar la información de retención de todos los buzones inactivos de la organización.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

El valor de **True** para la propiedad **LitigationHoldEnabled** indica que el buzón inactivo está en retención por juicio. Si una conservación local, una retención de exhibición de documentos electrónicos o una directiva de retención de Microsoft 365 se coloca en un buzón inactivo, se muestra un GUID para la Directiva de retención o retención como el valor de la propiedad **InPlaceHolds** . Por ejemplo, a continuación se muestran los resultados de cinco buzones inactivos. 
  
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

En la siguiente tabla se identifican los cinco tipos de retención que se usaron para convertir cada buzón en inactivo.
  
|**Buzón inactivo**|**Tipo de retención**|**Cómo identificar la retención en el buzón inactivo**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Retención por juicio  <br/> |La propiedad *LitigationHoldEnabled* se establece en `True` .  <br/> |
|Pilar Pinilla  <br/> |Retención en contexto  <br/> |La propiedad *InPlaceHolds* contiene el GUID de la retención local que está colocada en el buzón inactivo. Puede decir que se trata de una conservación local porque el identificador no comienza con un prefijo.  <br/> Puede usar el `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` comando en Exchange Online PowerShell para obtener información sobre la conservación local en el buzón inactivo.  <br/> |
|Mario Necaise  <br/> |Directiva de retención de Microsoft 365 para toda la organización en el centro de seguridad & cumplimiento  <br/> |La propiedad *InPlaceHolds* está vacía. Esto indica que una o varias directivas de retención de Microsoft 365 de toda la organización o de todo el mundo se aplican al buzón inactivo. En este caso, puede ejecutar el `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` comando en Exchange Online PowerShell para obtener una lista de los GUID de las directivas de retención de Microsoft 365 de toda la organización. El GUID de las directivas de retención de toda la organización que se aplican a los buzones de Exchange comienzan con el `mbx` prefijo; por ejemplo, `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> <br/>Para identificar la Directiva de retención de Microsoft 365 que se aplica al buzón inactivo, ejecute el siguiente comando en el PowerShell del centro de cumplimiento de & de seguridad.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |Directiva de retención de 365 de Microsoft en el centro de cumplimiento de & de seguridad que se aplica a buzones específicos  <br/> |La propiedad *InPlaceHolds* contiene el GUID de la Directiva de retención de Microsoft 365 que se aplica al buzón inactivo. Puede decir que se trata de una directiva de retención que se aplica a buzones específicos, ya que el GUID comienza con el `mbx` prefijo. Si el GUID de la Directiva de retención aplicada al buzón inactivo comenzó con el `skp` prefijo, indicaría que la Directiva de retención se aplica a las conversaciones de Skype empresarial.  <br/><br/> Para identificar la Directiva de retención de Microsoft 365 que se aplica al buzón inactivo, ejecute el siguiente comando en el PowerShell del centro de cumplimiento de & de seguridad.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Asegúrese de quitar el `mbx` `skp` prefijo o cuando ejecute este comando.  <br/> |
|Abraham McMahon  <br/> |suspensión de casos de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento  <br/> |La propiedad *InPlaceHolds* contiene el GUID de la suspensión de casos de exhibición de documentos electrónicos que se coloca en el buzón inactivo. Puede decir que se trata de una suspensión de casos de exhibición de documentos electrónicos porque el GUID comienza por el `UniH` prefijo.  <br/> Puede usar el `Get-CaseHoldPolicy` cmdlet en el PowerShell del centro de cumplimiento de & de seguridad para obtener información sobre el caso de eDiscovery con el que está asociado la retención en el buzón inactivo. Por ejemplo, puede ejecutar el comando `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` para mostrar el nombre de la suspensión de mayúsculas y minúsculas que se encuentra en el buzón inactivo. Asegúrese de quitar el `UniH` prefijo al ejecutar este comando.  <br/><br/> Para identificar el caso de eDiscovery al que está asociado la retención en el buzón inactivo, ejecute los siguientes comandos.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Nota:** No se recomienda usar la retención de exhibición de documentos electrónicos para los buzones inactivos. Esto se debe a que los casos de eDiscovery están pensados para casos específicos y de tiempo limitado relacionados con problemas legales. En algún momento, es probable que finalice un caso legal y se quitarán las suspensiones asociadas al caso y se cerrará (o eliminará) el caso de exhibición de documentos electrónicos. De hecho, si una retención que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y la retención se suelta o el caso de exhibición de documentos electrónicos se cierra o se elimina, el buzón inactivo se eliminará permanentemente. 

Para obtener más información acerca de las directivas de retención de Microsoft 365, consulte [información sobre las directivas de retención y las etiquetas de retención](retention.md).
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Paso 2: cambiar la duración de retención para un buzón inactivo

Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es cambiar la duración para la retención. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Cambiar la duración de una retención por juicio.

Esta es la manera de usar Exchange Online PowerShell para cambiar la duración de retención para una retención por juicio que se coloca en un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, se cambia la duración de retención a un período de tiempo ilimitado.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

El resultado es que los elementos del buzón inactivo se conservan indefinidamente o hasta que se quita la retención o hasta que la duración de retención se cambia a un valor diferente.
  
> [!TIP]
> The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Cambiar la duración de una conservación local

 Puede usar el EAC o Exchange Online PowerShell para cambiar la duración de retención para una conservación local. 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>Usar el EAC para cambiar la duración de retención

1. Si conoce el nombre de la conservación local que quiere cambiar, vaya al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la conservación local colocada en el buzón inactivo. Use el GUID de conservación local que obtuvo en el [paso 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Seleccione la conservación local que quiera cambiar y, después, seleccione **Editar** ![ icono Editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. En la página propiedades **de la &amp; retención de exhibición de** documentos electrónicos local, seleccione **conservación local**. 
    
5. Realice una de las siguientes acciones en función de la duración de retención actual:
    
    1. Seleccione **retenido indefinidamente** para retener elementos durante un período de tiempo ilimitado. 
    
    2. Seleccione **especificar el número de días que se retendrán los elementos relacionados con la fecha de recepción** para los elementos de un período específico. Type the number of days that you want to hold items for. 
    
    ![Captura de pantalla del cambio de duración para una conservación local](../media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. Seleccione **Guardar**.
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Usar Exchange Online PowerShell para cambiar la duración de retención

1. Si conoce el nombre de la conservación local que quiere cambiar, vaya al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la conservación local colocada en el buzón inactivo. Use el GUID de conservación local que obtuvo en el [paso 1](#step-1-identify-the-holds-on-an-inactive-mailbox).

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, la duración de retención se cambia a 2.555 días (aproximadamente siete años). 
    
    ```powershell
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     Para cambiar la duración de retención a un período de tiempo ilimitado, use  _-ItemHoldPeriod unlimited_.
  
## <a name="more-information"></a>Más información

- **How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created. 
    
- **¿Qué sucede cuando expira la duración de retención?** Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Si no se ha especificado ninguna duración para la retención colocada en el buzón inactivo, los elementos de la carpeta elementos recuperables nunca se purgan (a menos que se cambie la duración de retención para el buzón inactivo). 
    
- **¿Se sigue procesando una directiva de retención de Exchange en buzones inactivos?** Si una directiva de retención de Exchange (la característica de administración de registros de mensajería, o MRM, en Exchange Online) se aplicó a un buzón de correo cuando se inactivo, las directivas de eliminación (que son etiquetas de retención configuradas con una acción de retención de **eliminación** ) seguirán procesándose en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación se mueven a la carpeta Elementos recuperables cuando expira el período de retención. Esos elementos luego se purgan del buzón inactivo cuando expira la duración de retención de un elemento. 
    
    Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies. 
    
- **To check the new hold duration, run one of the following commands.** The first command is for Litigation Hold; the second is for In-Place Hold. 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```powershell
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **Al igual que los buzones habituales, el Asistente para carpeta administrada (MFA) también procesa buzones inactivos.** En Exchange Online, el MFA procesa los buzones aproximadamente una vez cada siete días. Después de cambiar la duración de retención para un buzón inactivo, puede usar el cmdlet **Start-ManagedFolderAssistant** para empezar a procesar inmediatamente la nueva duración de retención para el buzón inactivo. Ejecute el comando siguiente. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Si se colocan muchas retenciones en un buzón inactivo, no se mostrarán todos los GUID de retención.** Puede ejecutar el siguiente comando para mostrar los GUID de todas las suspensiones (excepto las suspensiones por juicio) que se colocan en un buzón inactivo. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
