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
description: Después de que un buzón de Office 365 esté inactivo, cambie la duración de la retención o la directiva de retención de Office 365 asignada al buzón inactivo.
ms.openlocfilehash: 675e6eb36f762a50c3caafce07d09fda9ba9d98e
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126381"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Cambiar la duración de retención para un buzón inactivo

Un buzón inactivo se usa para conservar el correo electrónico de un antiguo empleado después de que abandone la organización. Un buzón pasa a estar inactivo cuando se coloca en el buzón una retención por juicio, una retención de In-Place, una directiva de retención de Microsoft 365 o una retención asociada a un caso de exhibición de documentos electrónicos y se elimina la cuenta de usuario correspondiente. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. La duración de retención define cuánto tiempo se retienen los elementos en la carpeta Elementos recuperables. Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Después de que un buzón esté inactivo, puede cambiar la duración de la retención o la directiva de retención de Microsoft 365 asignada al buzón inactivo.
  
> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido del buzón, anunciamos la retirada de In-Place retenciones en el Centro de administración de Exchange. Esto significa que debe usar las retenciones por juicio y las directivas de retención de Microsoft 365 para crear un buzón inactivo. A partir del 1 de abril de 2020 no podrá crear nuevas retenciones de In-Place en Exchange Online. Sin embargo, podrá cambiar la duración de retención de una retención In-Place en un buzón inactivo. Sin embargo, a partir del 1 de julio de 2020, no podrá cambiar la duración de retención. Solo podrá eliminar un buzón inactivo quitando la retención In-Place correo. Los buzones inactivos existentes que están In-Place conservación local se conservarán hasta que se quite la retención. Para obtener más información acerca de la retirada de In-Place de documentos electrónicos, vea Retirada de herramientas de exhibición de [documentos electrónicos heredadas.](legacy-ediscovery-retirement.md)
  
## <a name="connect-to-powershell"></a>Conectarse a PowerShell

- Debe usar Exchange Online PowerShell para cambiar la duración de retención de una retención por juicio en un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Pero puede usar Exchange Online PowerShell o el EAC para cambiar la duración de retención de una In-Place retención. Puede usar el Centro de seguridad y cumplimiento o powerShell del Centro de seguridad & Cumplimiento para cambiar la duración de retención de una directiva de retención de Microsoft 365.
    
- Para conectarse a PowerShell de Exchange Online o PowerShell del Centro de & cumplimiento, consulte uno de los siguientes temas:
    
  - [Conectarse a Exchange Online mediante PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [Conectarse a PowerShell del Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=799771)
    
- Las retenciones asociadas a casos de exhibición de documentos electrónicos son retenciones infinitas, lo que significa que no hay ninguna duración de retención que se pueda cambiar. Los elementos se mantienen para siempre o hasta que se quita la retención y se elimina el buzón inactivo.
    
- Para obtener más información acerca de los buzones inactivos, consulte [Buzones inactivos en Microsoft 365.](inactive-mailboxes-in-office-365.md)
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Dado que los distintos tipos de retenciones o una o más directivas de retención de Microsoft 365 pueden colocarse en un buzón inactivo, el primer paso es identificar las retenciones en un buzón inactivo.
  
Ejecute el siguiente comando en Exchange Online PowerShell para mostrar la información de retención de todos los buzones inactivos de su organización.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```

El valor de **True** para la propiedad **LitigationHoldEnabled** indica que el buzón inactivo está en retención por juicio. Si una directiva de retención de In-Place, retención de exhibición de documentos electrónicos o Microsoft 365 se coloca en un buzón inactivo, se muestra un GUID para la directiva de retención o retención como el valor de la propiedad **InPlaceHolds.** Por ejemplo, a continuación se muestran los resultados de cinco buzones inactivos. 
  
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

En la tabla siguiente se identifican los cinco tipos de retención diferentes que se usaron para hacer que cada buzón se quedara inactivo.
  
|**Buzón inactivo**|**Tipo de retención**|**Cómo identificar la retención en el buzón inactivo**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |Retención por juicio  <br/> |La  *propiedad LitigationHoldEnabled*  se establece en  `True` .  <br/> |
|Pilar Pinilla  <br/> |Retención en contexto  <br/> |La  *propiedad InPlaceHolds*  contiene el GUID de la In-Place que se coloca en el buzón inactivo. Puede saber que se trata de una retención In-Place porque el identificador no comienza con un prefijo.  <br/> Puede usar el comando de Exchange Online PowerShell para obtener información sobre la retención In-Place  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` en el buzón inactivo.  <br/> |
|Mario Necaise  <br/> |Directiva de retención de Microsoft 365 en toda la organización en el Centro de & cumplimiento  <br/> |La  *propiedad InPlaceHolds*  está vacía. Esto indica que se aplica una o varias directivas de retención de Microsoft 365 en toda la organización o (en toda Exchange) al buzón inactivo. En este caso, puede ejecutar el comando en Exchange Online PowerShell para obtener una lista de los GUID para las directivas de retención de Microsoft 365 en toda la  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` organización. El GUID de las directivas de retención de toda la organización que se aplican a los buzones de Exchange comienzan con el  `mbx` prefijo; por ejemplo,  `mbxa3056bb15562480fadb46ce523ff7b02` .  <br/> <br/>Para identificar la directiva de retención de Microsoft 365 que se aplica al buzón inactivo, ejecute el siguiente comando en PowerShell del Centro de seguridad & cumplimiento.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Alondes Olson  <br/> |Directiva de retención de Microsoft 365 en el Centro de seguridad & cumplimiento aplicado a buzones específicos  <br/> |La  *propiedad InPlaceHolds*  contiene el GUID de la directiva de retención de Microsoft 365 que se aplica al buzón inactivo. Puede saber que se trata de una directiva de retención que se aplica a buzones específicos porque el GUID comienza con el  `mbx` prefijo. Si el GUID de la directiva de retención aplicada al buzón inactivo se inició con el prefijo, indicaría que la directiva de retención se aplica a las conversaciones de  `skp` Skype Empresarial.  <br/><br/> Para identificar la directiva de retención de Microsoft 365 que se aplica al buzón inactivo, ejecute el siguiente comando en PowerShell del Centro de seguridad & cumplimiento.<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>Asegúrese de quitar el  `mbx` prefijo o cuando ejecute este  `skp` comando.  <br/> |
|Torón McMahon  <br/> |Retención de casos de exhibición de documentos electrónicos en el Centro de & cumplimiento  <br/> |La  *propiedad InPlaceHolds*  contiene el GUID de la retención de casos de eDiscovery que se coloca en el buzón inactivo. Puede saber que se trata de una retención de casos de exhibición de documentos electrónicos porque el GUID comienza con el  `UniH` prefijo.  <br/> Puede usar el cmdlet de PowerShell del Centro de seguridad & Cumplimiento para obtener información sobre el caso de eDiscovery al que está asociada la retención en el buzón  `Get-CaseHoldPolicy` inactivo. Por ejemplo, puede ejecutar el comando para mostrar el nombre de la retención de  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` casos que está en el buzón inactivo. Asegúrese de quitar el  `UniH` prefijo al ejecutar este comando.  <br/><br/> Para identificar el caso de exhibición de documentos electrónicos al que está asociada la retención en el buzón inactivo, ejecute los siguientes comandos.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **Nota:** No se recomienda usar retenciones de exhibición de documentos electrónicos para buzones inactivos. Esto se debe a que los casos de exhibición de documentos electrónicos están destinados a casos específicos y limitados por tiempo relacionados con un problema legal. En algún momento, un caso legal probablemente finalizará y las retenciones asociadas con el caso se quitarán y el caso de exhibición de documentos electrónicos se cerrará (o eliminará). De hecho, si una retención que se coloca en un buzón inactivo está asociada a un caso de exhibición de documentos electrónicos y la retención se libera o el caso de eDiscovery se cierra o elimina, el buzón inactivo se eliminará permanentemente. 

Para obtener más información acerca de las directivas de retención de Microsoft 365, vea Más información sobre las directivas de retención [y las etiquetas de retención.](retention.md)
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>Paso 2: cambiar la duración de retención para un buzón inactivo

Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es cambiar la duración para la retención. 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>Cambiar la duración de una retención por juicio.

Aquí se muestra cómo usar Exchange Online PowerShell para cambiar la duración de retención de una retención por juicio que se coloca en un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, se cambia la duración de retención a un período de tiempo ilimitado.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

El resultado es que los elementos del buzón inactivo se conservan indefinidamente o hasta que se quita la retención o se cambia la duración de retención a un valor diferente.
  
> [!TIP]
> La mejor manera de identificar un buzón inactivo es usando el valor **Distinguished Name** o **Exchange GUID**. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado. 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>Cambiar la duración de una conservación local

 Puede usar el EAC o Exchange Online PowerShell para cambiar la duración de retención de una In-Place retención. 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>Usar el EAC para cambiar la duración de retención

1. Si conoce el nombre de la conservación local que quiere cambiar, vaya al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la conservación local colocada en el buzón inactivo. Use el GUID In-Place de retención que obtuvo en el [paso 1.](#step-1-identify-the-holds-on-an-inactive-mailbox)

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Seleccione la In-Place que desea cambiar y, a continuación, seleccione **el icono Editar** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) edición.
    
4. En la página propiedades de la retención **de exhibición &amp;** de documentos electrónicos local, seleccione **Retención local.** 
    
5. Realice una de las siguientes acciones en función de la duración de retención actual:
    
    1. Seleccione **Retener indefinidamente para** retener elementos durante un período de tiempo ilimitado. 
    
    2. Seleccione Especificar el número de días que se deben retener los **elementos relativos** a su fecha de recibido para retener los elementos durante un período específico. Type the number of days that you want to hold items for. 
    
    ![Captura de pantalla del cambio de duración para una conservación local](../media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. Seleccione **Guardar**.
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Usar Exchange Online PowerShell para cambiar la duración de retención

1. Si conoce el nombre de la conservación local que quiere cambiar, vaya al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la conservación local colocada en el buzón inactivo. Use el GUID In-Place de retención que obtuvo en el [paso 1.](#step-1-identify-the-holds-on-an-inactive-mailbox)

    ```powershell
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. Ejecute el siguiente comando para cambiar la duración de retención. En este ejemplo, la duración de retención se cambia a 2.555 días (aproximadamente siete años). 
    
    ```powershell
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     Para cambiar la duración de retención a un período de tiempo ilimitado, use  _-ItemHoldPeriod unlimited_.
  
## <a name="more-information"></a>Más información

- **¿Cómo se calcula la duración de retención para un elemento en un buzón inactivo?** La duración se calcula desde la fecha original en que un elemento de buzón se recibe o se crea. 
    
- **¿Qué sucede cuando expira la duración de retención?** Cuando expira la duración de retención de un elemento en la carpeta Elementos recuperables, el elemento se elimina permanentemente (se purga) del buzón inactivo. Si no se especifica ninguna duración para la retención colocada en el buzón inactivo, los elementos de la carpeta Elementos recuperables nunca se purgan (a menos que se cambie la duración de retención del buzón inactivo). 
    
- **¿Se sigue procesando una directiva de retención de Exchange en buzones inactivos?** Si se aplicó una directiva de retención de Exchange (la característica de administración de registros de mensajería o MRM en  Exchange Online) a un buzón cuando se activó, las directivas de eliminación (que son etiquetas de retención configuradas con una acción de retención Eliminar) se seguirán procesando en el buzón inactivo. Esto significa que los elementos etiquetados con una directiva de eliminación se mueven a la carpeta Elementos recuperables cuando expira el período de retención. Esos elementos luego se purgan del buzón inactivo cuando expira la duración de retención de un elemento. 
    
    Por el contrario, se ignora cualquier directiva de archivo (que son etiquetas de retención configuradas con una acción de retención **MoveToArchive** ) que esté incluida en la directiva de retención asignada a un buzón inactivo. Eso significa que los elementos de un buzón inactivo etiquetados con una directiva de archivo permanecen en el buzón principal cuando expira el período de retención. No se mueven al buzón de archivo o a la carpeta Elementos recuperables en el buzón de archivo. Dado que un usuario no puede iniciar sesión en un buzón inactivo, no existen motivos para consumir los recursos del centro de datos para procesar las directivas de archivo. 
    
- **Para comprobar la nueva duración de retención, ejecute uno de los siguientes comandos.** El primer comando es para retención por juicio; el segundo es para conservación local. 

    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```powershell
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **Al igual que los buzones habituales, el Asistente para carpeta administrada (MFA) también procesa buzones inactivos.** En Exchange Online, la MFA procesa buzones aproximadamente una vez cada siete días. Después de cambiar la duración de retención para un buzón inactivo, puede usar el cmdlet **Start-ManagedFolderAssistant** para empezar a procesar inmediatamente la nueva duración de retención para el buzón inactivo. Ejecute el comando siguiente. 

    ```powershell
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **Si se colocan muchas retenciones en un buzón inactivo, no se mostrarán todos los GUID de retención.** Puede ejecutar el siguiente comando para mostrar los GUID de todas las retenciones (excepto las retenciones por juicio) que se colocan en un buzón inactivo. 
    
    ```powershell
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
