---
title: Eliminar un buzón inactivo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Cuando ya no necesite conservar el contenido de un buzón inactivo de Microsoft 365, puede eliminar de forma permanente el buzón inactivo.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817899"
---
# <a name="delete-an-inactive-mailbox"></a>Eliminar un buzón inactivo

Un buzón inactivo se usa para conservar el correo electrónico de un antiguo empleado después de que este se va de la organización. Cuando ya no necesita conservar el contenido de un buzón inactivo, puede quitar su retención para eliminarlo de forma permanente. Además, es posible que varias retenciones se coloquen en un buzón inactivo. Por ejemplo, un buzón inactivo puede colocarse en retención de litigios y en una o varias retenciones locales. Además, se puede aplicar una directiva de retención (creada en el centro de seguridad y cumplimiento en Office 365 o Microsoft 365) al buzón inactivo. Debe quitar todas las directivas de retención y retención de un buzón inactivo para eliminarlo. Después de quitar las directivas de retención y retención, el buzón inactivo se marca para su eliminación y se elimina de forma permanente después de su procesamiento.
  
> [!IMPORTANT]
> A medida que seguimos invirtiendo en diferentes formas de conservar el contenido de los buzones, estamos anunciando la retirada de conservaciones locales en el centro de administración de Exchange. Esto significa que debe usar las retenciones por juicio y las directivas de retención para crear un buzón inactivo. A partir del 1 de julio de 2020, no podrá crear nuevas retenciones locales en Exchange Online. Pero todavía podrá cambiar la duración de retención de una conservación local colocada en un buzón inactivo. Sin embargo, a partir del 1 de octubre de 2020, no podrá cambiar la duración de retención. Solo se podrá eliminar un buzón inactivo si se quita la retención local. Los buzones inactivos existentes que se encuentran en conservación local se conservarán hasta que se quite la retención. Para obtener más información acerca de la retirada de suspensiones locales, consulte [jubilación de las herramientas de eDiscovery heredadas](legacy-ediscovery-retirement.md).
  
Consulte la sección [Más información](#more-information) para ver una descripción de lo que sucede una vez que se quitan las retenciones de un buzón inactivo.
  
## <a name="before-you-delete-an-inactive-mailbox"></a>Antes de eliminar un buzón inactivo

- Debe usar Exchange Online PowerShell para quitar una retención por juicio de un buzón inactivo. No puede usar el Centro de administración de Exchange (EAC). Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554). Puede usar Exchange Online PowerShell o el EAC para quitar una retención local de un buzón inactivo. 
    
- Puede copiar el contenido de un buzón inactivo a otro buzón antes de quitar la retención y eliminar un buzón inactivo. Para obtener más información, consulte [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).
    
- Si quita la Directiva de retención o retención de un buzón inactivo y el período de retención de buzón eliminado temporalmente el buzón ha expirado, el buzón se eliminará permanentemente. Una vez eliminado, no se puede recuperar. Antes de quitar la retención, asegúrese de que ya no necesita el contenido del buzón. Si desea volver a activar un buzón inactivo, puede recuperarlo. Para obtener más información, consulte [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
    
- Para obtener más información acerca de los buzones inactivos, consulte [buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>Paso 1: identificar las retenciones en un buzón inactivo

Como se indicó anteriormente, la retención por juicio, la conservación local o la Directiva de retención pueden colocarse en un buzón inactivo. El primer paso es identificar las retenciones de un buzón inactivo.
  
Ejecute el siguiente comando para mostrar la información de la retención de todos los buzones inactivos en su organización.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla. 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> Si muchas retenciones locales se colocan en un buzón inactivo, no se mostrarán todos los GUID de retenciones locales. Puede ejecutar el siguiente comando para mostrar todos los GUID de conservación local:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>Paso 2: Quitar una retención de un buzón inactivo

After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox. 
  
### <a name="remove-a-litigation-hold"></a>Quitar una retención de litigios

As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox. 
  
### <a name="remove-in-place-holds"></a>Quitar retenciones locales

 Hay dos maneras de quitar una retención local de un buzón inactivo: 
  
- **Eliminar el objeto de retención local** Si el buzón inactivo que quiere eliminar de forma permanente es el único buzón de origen de una conservación local, simplemente puede eliminar el objeto de retención local. 
    
    > [!NOTE]
    > You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message. 
  
- **Quitar el buzón inactivo como buzón de origen de una retención local** Si quiere conservar otros buzones de origen para una retención local, puede quitar el buzón inactivo de la lista de buzones de origen y mantener el objeto de retención local. 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>Usar el EAC para eliminar una retención local

1. If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Seleccione la conservación local que desea eliminar y, a continuación, haga clic en **Editar** ![ icono Editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.
    
5. On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).
    
6. En la advertencia, haga clic en **Sí** para eliminar la retención local. 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Usar Exchange Online PowerShell para eliminar una conservación local

1. Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. Deshabilite la retención en la retención local.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. Elimine la retención local.
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Use el EAC para quitar un buzón inactivo de una retención local.

1. If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. Seleccione la retención local que está colocada en el buzón inactivo y, a continuación, haga clic en **Editar** ![ icono de edición ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.
    
5. En la lista de buzones de origen, haga clic en el nombre del buzón inactivo que quiere quitar y después haga clic en **Quitar**![Icono de quitar](../media/adf01106-cc79-475c-8673-065371c1897b.gif).
    
6. Click **Save** to save the change. A message is displayed saying the operation was successfully completed. 
    
7. Repita los pasos 1 a 6 para quitar otras retenciones locales colocadas en el buzón inactivo.
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Usar Exchange Online PowerShell para quitar un buzón inactivo de una conservación local

Si la retención local contiene un gran número de buzones de origen, es posible que el buzón local no aparezca en la página **Orígenes** en el EAC. Hasta 3.000 buzones se muestran en la página **Orígenes** cuando edita una retención local. Si un buzón inactivo no aparece en la lista de la página **orígenes** , puede usar Exchange Online PowerShell para quitarlo de la conservación local. 
  
1. Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. Compruebe que el buzón inactivo aparezca como un buzón de origen para la retención local. 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **Nota:** La propiedad *sources* de la retención local identifica los buzones de origen por sus propiedades *legacyExchangeDN* . Como esta propiedad identifica exclusivamente los buzones inactivos, el uso de la propiedad *Sources* de la retención local ayuda a impedir que se elimine el buzón equivocado. También ayuda a evitar problemas si dos buzones tienen el mismo alias o dirección SMTP. 
   
3. Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step. 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    Por ejemplo, el siguiente comando quita el buzón inactivo para Pilar Pinilla.
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. Compruebe que el buzón inactivo se quita de la lista de buzones de origen en la variable.
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. Modifique la retención local con la lista actualizada de buzones de origen, que no incluye el buzón inactivo.
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. Compruebe que el buzón inactivo se quita de la lista de buzones de origen para la retención local.
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>Más información

- **An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered. 
    
- **¿Qué ocurre después de quitar la retención en un buzón inactivo?** El buzón de correo se considera como otros buzones eliminados temporalmente y se marca para eliminación permanente una vez que expire el período de retención de 30 días del buzón eliminado temporalmente. Este período de retención empieza en la fecha en que el buzón se volvió inactivo por primera vez. Esta fecha se conoce como la fecha de eliminación temporal, que es la fecha en que se eliminó la cuenta de usuario correspondiente o cuando se eliminó el buzón de Exchange Online con el cmdlet **Remove-Mailbox** . La fecha de eliminación temporal no es la fecha en que se quita la retención. 
    
- **Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed. 
    
- **¿Cómo afecta a los buzones inactivos el período de retención de buzones eliminados temporalmente?** Si la fecha de eliminación temporal para un buzón inactivo es más de 30 días antes de la fecha en que se ha quitado la retención, el buzón se marca para su eliminación permanente. Pero si un buzón inactivo tiene una fecha de eliminación temporal en los últimos 30 días y se quita la retención, es posible recuperar el buzón hasta que expire el período de retención de buzones eliminados temporalmente. Para obtener más información, consulte [Delete or restore User mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835). Una vez que expire el período de retención de buzones eliminados temporalmente, debe seguir los procedimientos para recuperar un buzón inactivo. Para obtener más información, consulte [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).
    
- **¿Cómo mostrar información sobre un buzón inactivo después de quitar la retención?** Una vez que se quita una retención y el buzón inactivo se revierte a un buzón eliminado temporalmente, no se devolverá mediante el parámetro *InactiveMailboxOnly* con el cmdlet **Get-Mailbox** . Pero puede mostrar información sobre el buzón mediante el comando **Get-Mailbox -SoftDeletedMailbox**. Por ejemplo: 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  En el ejemplo anterior, la propiedad *WhenSoftDeleted* identifica la fecha de eliminación temporal, que en este ejemplo es el 30 de octubre de 2014. Si este buzón eliminado temporalmente era un buzón inactivo para el que se quitó la retención, se eliminará permanentemente 30 días después del valor de la propiedad *WhenSoftDeleted* . En este caso, el buzón se elimina permanentemente después del 30 de noviembre de 2014.

