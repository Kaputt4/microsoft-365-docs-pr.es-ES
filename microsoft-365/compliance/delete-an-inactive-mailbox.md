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
description: Cuando ya no necesite conservar el contenido de un buzón inactivo de Microsoft 365, puede eliminar permanentemente el buzón inactivo.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817899"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="9a246-103">Eliminar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="9a246-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="9a246-104">Un buzón inactivo se usa para conservar el correo electrónico de un antiguo empleado después de que este se va de la organización.</span><span class="sxs-lookup"><span data-stu-id="9a246-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="9a246-105">Cuando ya no necesita conservar el contenido de un buzón inactivo, puede quitar su retención para eliminarlo de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="9a246-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="9a246-106">Además, es posible que varias retenciones se coloquen en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="9a246-107">Por ejemplo, un buzón inactivo puede colocarse en retención de litigios y en una o varias retenciones locales.</span><span class="sxs-lookup"><span data-stu-id="9a246-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="9a246-108">Además, se puede aplicar una directiva de retención (creada en el Centro de seguridad y cumplimiento en Office 365 o Microsoft 365) al buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="9a246-109">Debe quitar todas las retenciones y directivas de retención de un buzón inactivo para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="9a246-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="9a246-110">Después de quitar las retenciones y las directivas de retención, el buzón inactivo se marca para su eliminación y se elimina permanentemente después de que se procese.</span><span class="sxs-lookup"><span data-stu-id="9a246-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9a246-111">A medida que seguimos invirtiendo en diferentes formas de conservar el contenido del buzón, anunciamos la retirada de In-Place retenciones en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="9a246-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="9a246-112">Esto significa que debe usar las retenciones por juicio y las directivas de retención para crear un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="9a246-113">A partir del 1 de julio de 2020 no podrá crear nuevas retenciones de In-Place en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9a246-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="9a246-114">Sin embargo, podrá cambiar la duración de retención de una retención In-Place en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="9a246-115">Sin embargo, a partir del 1 de octubre de 2020, no podrá cambiar la duración de retención.</span><span class="sxs-lookup"><span data-stu-id="9a246-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="9a246-116">Solo podrá eliminar un buzón inactivo quitando la retención In-Place correo.</span><span class="sxs-lookup"><span data-stu-id="9a246-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="9a246-117">Los buzones inactivos existentes que están In-Place conservación local se conservarán hasta que se quite la retención.</span><span class="sxs-lookup"><span data-stu-id="9a246-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="9a246-118">Para obtener más información acerca de la retirada de In-Place de documentos electrónicos, vea Retirada de herramientas de exhibición de [documentos electrónicos heredadas.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="9a246-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="9a246-119">Consulte la sección [Más información](#more-information) para ver una descripción de lo que sucede una vez que se quitan las retenciones de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="9a246-120">Antes de eliminar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="9a246-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="9a246-121">Debe usar Exchange Online PowerShell para quitar una retención por juicio de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="9a246-122">No puede usar el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="9a246-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="9a246-123">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="9a246-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="9a246-124">Puede usar Exchange Online PowerShell o el EAC para quitar una retención In-Place de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-124">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="9a246-125">Puede copiar el contenido de un buzón inactivo a otro buzón antes de quitar la retención y eliminar un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-125">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="9a246-126">Para obtener más información, [vea Restaurar un buzón inactivo en Office 365.](restore-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="9a246-126">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="9a246-127">Si quita la directiva de retención o retención de un buzón inactivo y el período de retención del buzón eliminado temporalmente para el buzón ha expirado, el buzón se eliminará permanentemente.</span><span class="sxs-lookup"><span data-stu-id="9a246-127">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="9a246-128">Una vez eliminado, no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="9a246-128">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="9a246-129">Antes de quitar la retención, asegúrese de que ya no necesita el contenido del buzón.</span><span class="sxs-lookup"><span data-stu-id="9a246-129">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="9a246-130">Si desea volver a activar un buzón inactivo, puede recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="9a246-130">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="9a246-131">Para obtener más información, [consulte Recuperar un buzón inactivo en Office 365.](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="9a246-131">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="9a246-132">Para obtener más información acerca de los buzones inactivos, vea [Buzones inactivos en Office 365.](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="9a246-132">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="9a246-133">Paso 1: identificar las retenciones en un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="9a246-133">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="9a246-134">Como se indicó anteriormente, una retención por juicio, In-Place retención local o una directiva de retención podría colocarse en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-134">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="9a246-135">El primer paso es identificar las retenciones de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-135">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="9a246-136">Ejecute el siguiente comando para mostrar la información de la retención de todos los buzones inactivos en su organización.</span><span class="sxs-lookup"><span data-stu-id="9a246-136">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="9a246-p107">El valor de **True** para la propiedad **LitigationHoldEnabled** indica que el buzón inactivo está en retención por juicio. Si una retención local se coloca en un buzón inactivo, el GUID de la retención se muestra como el valor de la propiedad **InPlaceHolds**. Por ejemplo, los siguientes resultados para dos buzones inactivos muestran que una retención por juicio se coloca en Ann Beebe y dos retenciones locales se colocan en Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="9a246-p107">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
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
> <span data-ttu-id="9a246-140">Si muchas retenciones locales se colocan en un buzón inactivo, no se mostrarán todos los GUID de retenciones locales.</span><span class="sxs-lookup"><span data-stu-id="9a246-140">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="9a246-141">Puede ejecutar el siguiente comando para mostrar todos los GUID In-Place hold:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="9a246-141">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="9a246-142">Paso 2: Quitar una retención de un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="9a246-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="9a246-p109">Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es quitar las retenciones del buzón. Como se mencionó anteriormente, tiene que quitar todas las retenciones para eliminar de forma permanente un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-p109">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="9a246-145">Quitar una retención de litigios</span><span class="sxs-lookup"><span data-stu-id="9a246-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="9a246-p110">Como se mencionó anteriormente, tiene que usar Windows PowerShell para quitar una retención de litigios de un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para quitar una retención de litigios.</span><span class="sxs-lookup"><span data-stu-id="9a246-p110">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="9a246-p111">La mejor manera de identificar un buzón inactivo es usando el valor Nombre distintivo o GUID de Exchange. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado.</span><span class="sxs-lookup"><span data-stu-id="9a246-p111">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="9a246-151">Quitar retenciones locales</span><span class="sxs-lookup"><span data-stu-id="9a246-151">Remove In-Place Holds</span></span>

 <span data-ttu-id="9a246-152">Hay dos maneras de quitar una retención local de un buzón inactivo:</span><span class="sxs-lookup"><span data-stu-id="9a246-152">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="9a246-153">**Eliminar el objeto In-Place hold** Si el buzón inactivo que desea eliminar permanentemente es el único buzón de origen de una retención In-Place, simplemente puede eliminar el objeto In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="9a246-153">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9a246-p112">Tiene que deshabilitar la retención antes de poder eliminar un objeto de retención local. Si intenta eliminar un objeto de retención local que tiene habilitada la retención, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="9a246-p112">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="9a246-156">**Quitar el buzón inactivo como buzón de origen de una retención local** Si quiere conservar otros buzones de origen para una retención local, puede quitar el buzón inactivo de la lista de buzones de origen y mantener el objeto de retención local.</span><span class="sxs-lookup"><span data-stu-id="9a246-156">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="9a246-157">Usar el EAC para eliminar una retención local</span><span class="sxs-lookup"><span data-stu-id="9a246-157">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="9a246-p113">Si conoce el nombre de la retención local que quiere eliminar, puede ir al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local que se coloca en el buzón inactivo que quiere eliminar de forma permanente. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9a246-p113">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="9a246-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="9a246-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="9a246-162">Seleccione la In-Place que desea eliminar y, a continuación, haga clic **en el icono** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) Editar.</span><span class="sxs-lookup"><span data-stu-id="9a246-162">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="9a246-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="9a246-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="9a246-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="9a246-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="9a246-165">En la advertencia, haga clic en **Sí** para eliminar la retención local.</span><span class="sxs-lookup"><span data-stu-id="9a246-165">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="9a246-166">Usar Exchange Online PowerShell para eliminar una In-Place retención</span><span class="sxs-lookup"><span data-stu-id="9a246-166">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="9a246-p114">Cree una variable que contenga las propiedades de la retención local que quiera eliminar. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9a246-p114">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="9a246-169">Deshabilite la retención en la retención local.</span><span class="sxs-lookup"><span data-stu-id="9a246-169">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="9a246-170">Elimine la retención local.</span><span class="sxs-lookup"><span data-stu-id="9a246-170">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="9a246-171">Use el EAC para quitar un buzón inactivo de una retención local.</span><span class="sxs-lookup"><span data-stu-id="9a246-171">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="9a246-p115">Si conoce el nombre de la retención local que está colocada en el buzón inactivo, puede ir al siguiente paso. De lo contrario, ejecute el siguiente comando para obtener el nombre de la retención local colocada en el buzón. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9a246-p115">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="9a246-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="9a246-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="9a246-176">Seleccione la In-Place que se coloca en el buzón inactivo y, a continuación, haga clic **en el icono** Editar ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) edición.</span><span class="sxs-lookup"><span data-stu-id="9a246-176">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="9a246-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span><span class="sxs-lookup"><span data-stu-id="9a246-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="9a246-178">En la lista de buzones de origen, haga clic en el nombre del buzón inactivo que quiere quitar y después haga clic en **Quitar**![Icono de quitar](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span><span class="sxs-lookup"><span data-stu-id="9a246-178">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="9a246-p116">Haga clic en **Guardar** para guardar el cambio. Se muestra un mensaje que indica que la operación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9a246-p116">Click **Save** to save the change. A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="9a246-181">Repita los pasos 1 a 6 para quitar otras retenciones locales colocadas en el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-181">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="9a246-182">Usar Exchange Online PowerShell para quitar un buzón inactivo de una retención In-Place local</span><span class="sxs-lookup"><span data-stu-id="9a246-182">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="9a246-183">Si la retención local contiene un gran número de buzones de origen, es posible que el buzón local no aparezca en la página **Orígenes** en el EAC.</span><span class="sxs-lookup"><span data-stu-id="9a246-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="9a246-184">Hasta 3.000 buzones se muestran en la página **Orígenes** cuando edita una retención local.</span><span class="sxs-lookup"><span data-stu-id="9a246-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="9a246-185">Si un buzón inactivo no aparece  en la página Orígenes, puede usar Exchange Online PowerShell para quitarlo de la In-Place retención.</span><span class="sxs-lookup"><span data-stu-id="9a246-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="9a246-p118">Cree una variable que contenga las propiedades de la retención local colocada en el buzón inactivo. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9a246-p118">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="9a246-188">Compruebe que el buzón inactivo aparezca como un buzón de origen para la retención local.</span><span class="sxs-lookup"><span data-stu-id="9a246-188">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="9a246-189">**Nota:** La *propiedad Sources* de la In-Place local identifica los buzones de origen por sus propiedades *LegacyExchangeDN.*</span><span class="sxs-lookup"><span data-stu-id="9a246-189">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="9a246-190">Como esta propiedad identifica exclusivamente los buzones inactivos, el uso de la propiedad *Sources* de la retención local ayuda a impedir que se elimine el buzón equivocado.</span><span class="sxs-lookup"><span data-stu-id="9a246-190">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="9a246-191">También ayuda a evitar problemas si dos buzones tienen el mismo alias o dirección SMTP.</span><span class="sxs-lookup"><span data-stu-id="9a246-191">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="9a246-p120">Quite el buzón inactivo de la lista de buzones de origen en la variable. Asegúrese de usar la propiedad **LegacyExchangeDN** del buzón inactivo devuelto por el comando en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="9a246-p120">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="9a246-194">Por ejemplo, el siguiente comando quita el buzón inactivo para Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="9a246-194">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="9a246-195">Compruebe que el buzón inactivo se quita de la lista de buzones de origen en la variable.</span><span class="sxs-lookup"><span data-stu-id="9a246-195">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="9a246-196">Modifique la retención local con la lista actualizada de buzones de origen, que no incluye el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-196">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="9a246-197">Compruebe que el buzón inactivo se quita de la lista de buzones de origen para la retención local.</span><span class="sxs-lookup"><span data-stu-id="9a246-197">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="9a246-198">Más información</span><span class="sxs-lookup"><span data-stu-id="9a246-198">More information</span></span>

- <span data-ttu-id="9a246-p121">**Un buzón inactivo es un tipo de buzón eliminado temporalmente.** En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se pueden recuperar en un período de retención específico. El período de retención del buzón eliminado temporalmente en Exchange Online es de 30 días. Esto significa que el buzón se puede recuperar en un plazo de 30 días después de eliminarse temporalmente. Después de 30 días, un buzón eliminado temporalmente se marca para su eliminación permanente y no puede recuperarse.</span><span class="sxs-lookup"><span data-stu-id="9a246-p121">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="9a246-204">**¿Qué ocurre después de quitar la retención en un buzón inactivo?**</span><span class="sxs-lookup"><span data-stu-id="9a246-204">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="9a246-205">El buzón de correo se considera como otros buzones eliminados temporalmente y se marca para eliminación permanente una vez que expire el período de retención de 30 días del buzón eliminado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="9a246-205">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="9a246-206">Este período de retención empieza en la fecha en que el buzón se volvió inactivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="9a246-206">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="9a246-207">Esta fecha se conoce como la fecha de eliminación temporal, que es la fecha en que se eliminó la cuenta de usuario correspondiente o cuando se eliminó el buzón de Exchange Online con el cmdlet **Remove-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="9a246-207">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="9a246-208">La fecha de eliminación temporal no es la fecha en que se quita la retención.</span><span class="sxs-lookup"><span data-stu-id="9a246-208">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="9a246-p123">**¿Un buzón inactivo se elimina de forma permanente inmediatamente después de quitar la retención?** Si la fecha de eliminación temporal para un buzón inactivo supera 30 días, el buzón no se eliminará permanentemente en cuanto se quite la retención. El buzón se marcará para su eliminación permanente y se eliminará la próxima vez que se procese.</span><span class="sxs-lookup"><span data-stu-id="9a246-p123">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="9a246-212">**¿Cómo afecta a los buzones inactivos el período de retención de buzones eliminados temporalmente?**</span><span class="sxs-lookup"><span data-stu-id="9a246-212">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="9a246-213">Si la fecha de eliminación temporal para un buzón inactivo es más de 30 días antes de la fecha en que se ha quitado la retención, el buzón se marca para su eliminación permanente.</span><span class="sxs-lookup"><span data-stu-id="9a246-213">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="9a246-214">Pero si un buzón inactivo tiene una fecha de eliminación temporal en los últimos 30 días y se quita la retención, es posible recuperar el buzón hasta que expire el período de retención de buzones eliminados temporalmente.</span><span class="sxs-lookup"><span data-stu-id="9a246-214">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="9a246-215">Para obtener más información, [consulte Eliminar o restaurar buzones de usuario en Exchange Online.](https://go.microsoft.com/fwlink/?linkid=856835)</span><span class="sxs-lookup"><span data-stu-id="9a246-215">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="9a246-216">Una vez que expire el período de retención de buzones eliminados temporalmente, debe seguir los procedimientos para recuperar un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="9a246-216">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="9a246-217">Para obtener más información, [consulte Recuperar un buzón inactivo en Office 365.](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="9a246-217">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="9a246-218">**¿Cómo mostrar información sobre un buzón inactivo después de quitar la retención?**</span><span class="sxs-lookup"><span data-stu-id="9a246-218">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="9a246-219">Después de quitar una retención y de revertir el buzón inactivo a un buzón eliminado temporalmente, no se devolverá mediante el parámetro *InactiveMailboxOnly* con el cmdlet **Get-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="9a246-219">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="9a246-220">Pero puede mostrar información sobre el buzón mediante el comando **Get-Mailbox -SoftDeletedMailbox**.</span><span class="sxs-lookup"><span data-stu-id="9a246-220">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="9a246-221">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9a246-221">For example:</span></span> 
    
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

  <span data-ttu-id="9a246-222">En el ejemplo anterior, la propiedad *WhenSoftDeleted* identifica la fecha de eliminación temporal, que en este ejemplo es el 30 de octubre de 2014.</span><span class="sxs-lookup"><span data-stu-id="9a246-222">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="9a246-223">Si este buzón eliminado temporalmente era anteriormente un buzón inactivo para el que se quitó la retención, se eliminará permanentemente 30 días después del valor de la propiedad *WhenSoftDeleted.*</span><span class="sxs-lookup"><span data-stu-id="9a246-223">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="9a246-224">En este caso, el buzón se elimina permanentemente después del 30 de noviembre de 2014.</span><span class="sxs-lookup"><span data-stu-id="9a246-224">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

