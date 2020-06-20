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
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="f8d15-103">Eliminar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="f8d15-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="f8d15-104">Un buzón inactivo se usa para conservar el correo electrónico de un antiguo empleado después de que este se va de la organización.</span><span class="sxs-lookup"><span data-stu-id="f8d15-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="f8d15-105">Cuando ya no necesita conservar el contenido de un buzón inactivo, puede quitar su retención para eliminarlo de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="f8d15-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="f8d15-106">Además, es posible que varias retenciones se coloquen en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="f8d15-107">Por ejemplo, un buzón inactivo puede colocarse en retención de litigios y en una o varias retenciones locales.</span><span class="sxs-lookup"><span data-stu-id="f8d15-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="f8d15-108">Además, se puede aplicar una directiva de retención (creada en el centro de seguridad y cumplimiento en Office 365 o Microsoft 365) al buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="f8d15-109">Debe quitar todas las directivas de retención y retención de un buzón inactivo para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="f8d15-110">Después de quitar las directivas de retención y retención, el buzón inactivo se marca para su eliminación y se elimina de forma permanente después de su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="f8d15-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f8d15-111">A medida que seguimos invirtiendo en diferentes formas de conservar el contenido de los buzones, estamos anunciando la retirada de conservaciones locales en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="f8d15-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="f8d15-112">Esto significa que debe usar las retenciones por juicio y las directivas de retención para crear un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="f8d15-113">A partir del 1 de julio de 2020, no podrá crear nuevas retenciones locales en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f8d15-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="f8d15-114">Pero todavía podrá cambiar la duración de retención de una conservación local colocada en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="f8d15-115">Sin embargo, a partir del 1 de octubre de 2020, no podrá cambiar la duración de retención.</span><span class="sxs-lookup"><span data-stu-id="f8d15-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="f8d15-116">Solo se podrá eliminar un buzón inactivo si se quita la retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="f8d15-117">Los buzones inactivos existentes que se encuentran en conservación local se conservarán hasta que se quite la retención.</span><span class="sxs-lookup"><span data-stu-id="f8d15-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="f8d15-118">Para obtener más información acerca de la retirada de suspensiones locales, consulte [jubilación de las herramientas de eDiscovery heredadas](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="f8d15-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="f8d15-119">Consulte la sección [Más información](#more-information) para ver una descripción de lo que sucede una vez que se quitan las retenciones de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="f8d15-120">Antes de eliminar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="f8d15-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="f8d15-121">Debe usar Exchange Online PowerShell para quitar una retención por juicio de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="f8d15-122">No puede usar el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="f8d15-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="f8d15-123">Para obtener instrucciones paso a paso, consulte [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="f8d15-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="f8d15-124">Puede usar Exchange Online PowerShell o el EAC para quitar una retención local de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-124">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="f8d15-125">Puede copiar el contenido de un buzón inactivo a otro buzón antes de quitar la retención y eliminar un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-125">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="f8d15-126">Para obtener más información, consulte [restaurar un buzón inactivo en Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="f8d15-126">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f8d15-127">Si quita la Directiva de retención o retención de un buzón inactivo y el período de retención de buzón eliminado temporalmente el buzón ha expirado, el buzón se eliminará permanentemente.</span><span class="sxs-lookup"><span data-stu-id="f8d15-127">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="f8d15-128">Una vez eliminado, no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="f8d15-128">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="f8d15-129">Antes de quitar la retención, asegúrese de que ya no necesita el contenido del buzón.</span><span class="sxs-lookup"><span data-stu-id="f8d15-129">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="f8d15-130">Si desea volver a activar un buzón inactivo, puede recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-130">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="f8d15-131">Para obtener más información, consulte [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="f8d15-131">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f8d15-132">Para obtener más información acerca de los buzones inactivos, consulte [buzones inactivos en Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f8d15-132">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="f8d15-133">Paso 1: identificar las retenciones en un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="f8d15-133">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="f8d15-134">Como se indicó anteriormente, la retención por juicio, la conservación local o la Directiva de retención pueden colocarse en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-134">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="f8d15-135">El primer paso es identificar las retenciones de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-135">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="f8d15-136">Ejecute el siguiente comando para mostrar la información de la retención de todos los buzones inactivos en su organización.</span><span class="sxs-lookup"><span data-stu-id="f8d15-136">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="f8d15-137">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span><span class="sxs-lookup"><span data-stu-id="f8d15-137">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="f8d15-138">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span><span class="sxs-lookup"><span data-stu-id="f8d15-138">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="f8d15-139">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="f8d15-139">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
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
> <span data-ttu-id="f8d15-140">Si muchas retenciones locales se colocan en un buzón inactivo, no se mostrarán todos los GUID de retenciones locales.</span><span class="sxs-lookup"><span data-stu-id="f8d15-140">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="f8d15-141">Puede ejecutar el siguiente comando para mostrar todos los GUID de conservación local:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="f8d15-141">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="f8d15-142">Paso 2: Quitar una retención de un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="f8d15-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="f8d15-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span><span class="sxs-lookup"><span data-stu-id="f8d15-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="f8d15-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="f8d15-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="f8d15-145">Quitar una retención de litigios</span><span class="sxs-lookup"><span data-stu-id="f8d15-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="f8d15-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="f8d15-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="f8d15-147">You can't use the EAC.</span><span class="sxs-lookup"><span data-stu-id="f8d15-147">You can't use the EAC.</span></span> <span data-ttu-id="f8d15-148">Run the following command to remove a Litigation Hold.</span><span class="sxs-lookup"><span data-stu-id="f8d15-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="f8d15-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span><span class="sxs-lookup"><span data-stu-id="f8d15-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="f8d15-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span><span class="sxs-lookup"><span data-stu-id="f8d15-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="f8d15-151">Quitar retenciones locales</span><span class="sxs-lookup"><span data-stu-id="f8d15-151">Remove In-Place Holds</span></span>

 <span data-ttu-id="f8d15-152">Hay dos maneras de quitar una retención local de un buzón inactivo:</span><span class="sxs-lookup"><span data-stu-id="f8d15-152">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="f8d15-153">**Eliminar el objeto de retención local** Si el buzón inactivo que quiere eliminar de forma permanente es el único buzón de origen de una conservación local, simplemente puede eliminar el objeto de retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-153">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f8d15-154">You have to disable the hold before you can delete an In-Place Hold object.</span><span class="sxs-lookup"><span data-stu-id="f8d15-154">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="f8d15-155">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span><span class="sxs-lookup"><span data-stu-id="f8d15-155">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="f8d15-156">**Quitar el buzón inactivo como buzón de origen de una retención local** Si quiere conservar otros buzones de origen para una retención local, puede quitar el buzón inactivo de la lista de buzones de origen y mantener el objeto de retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-156">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="f8d15-157">Usar el EAC para eliminar una retención local</span><span class="sxs-lookup"><span data-stu-id="f8d15-157">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="f8d15-158">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span><span class="sxs-lookup"><span data-stu-id="f8d15-158">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="f8d15-159">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span><span class="sxs-lookup"><span data-stu-id="f8d15-159">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="f8d15-160">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="f8d15-160">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="f8d15-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="f8d15-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="f8d15-162">Seleccione la conservación local que desea eliminar y, a continuación, haga clic en **Editar** ![ icono Editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="f8d15-162">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="f8d15-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="f8d15-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="f8d15-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="f8d15-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="f8d15-165">En la advertencia, haga clic en **Sí** para eliminar la retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-165">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="f8d15-166">Usar Exchange Online PowerShell para eliminar una conservación local</span><span class="sxs-lookup"><span data-stu-id="f8d15-166">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="f8d15-167">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span><span class="sxs-lookup"><span data-stu-id="f8d15-167">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="f8d15-168">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="f8d15-168">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="f8d15-169">Deshabilite la retención en la retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-169">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="f8d15-170">Elimine la retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-170">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="f8d15-171">Use el EAC para quitar un buzón inactivo de una retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-171">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="f8d15-172">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span><span class="sxs-lookup"><span data-stu-id="f8d15-172">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="f8d15-173">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span><span class="sxs-lookup"><span data-stu-id="f8d15-173">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="f8d15-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="f8d15-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="f8d15-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="f8d15-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="f8d15-176">Seleccione la retención local que está colocada en el buzón inactivo y, a continuación, haga clic en **Editar** ![ icono de edición ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="f8d15-176">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="f8d15-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span><span class="sxs-lookup"><span data-stu-id="f8d15-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="f8d15-178">En la lista de buzones de origen, haga clic en el nombre del buzón inactivo que quiere quitar y después haga clic en **Quitar**![Icono de quitar](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span><span class="sxs-lookup"><span data-stu-id="f8d15-178">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="f8d15-179">Click **Save** to save the change.</span><span class="sxs-lookup"><span data-stu-id="f8d15-179">Click **Save** to save the change.</span></span> <span data-ttu-id="f8d15-180">A message is displayed saying the operation was successfully completed.</span><span class="sxs-lookup"><span data-stu-id="f8d15-180">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="f8d15-181">Repita los pasos 1 a 6 para quitar otras retenciones locales colocadas en el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-181">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="f8d15-182">Usar Exchange Online PowerShell para quitar un buzón inactivo de una conservación local</span><span class="sxs-lookup"><span data-stu-id="f8d15-182">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="f8d15-183">Si la retención local contiene un gran número de buzones de origen, es posible que el buzón local no aparezca en la página **Orígenes** en el EAC.</span><span class="sxs-lookup"><span data-stu-id="f8d15-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="f8d15-184">Hasta 3.000 buzones se muestran en la página **Orígenes** cuando edita una retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="f8d15-185">Si un buzón inactivo no aparece en la lista de la página **orígenes** , puede usar Exchange Online PowerShell para quitarlo de la conservación local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="f8d15-186">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="f8d15-186">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="f8d15-187">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="f8d15-187">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="f8d15-188">Compruebe que el buzón inactivo aparezca como un buzón de origen para la retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-188">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="f8d15-189">**Nota:** La propiedad *sources* de la retención local identifica los buzones de origen por sus propiedades *legacyExchangeDN* .</span><span class="sxs-lookup"><span data-stu-id="f8d15-189">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="f8d15-190">Como esta propiedad identifica exclusivamente los buzones inactivos, el uso de la propiedad *Sources* de la retención local ayuda a impedir que se elimine el buzón equivocado.</span><span class="sxs-lookup"><span data-stu-id="f8d15-190">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="f8d15-191">También ayuda a evitar problemas si dos buzones tienen el mismo alias o dirección SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8d15-191">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="f8d15-192">Remove the inactive mailbox from the list of source mailboxes in the variable.</span><span class="sxs-lookup"><span data-stu-id="f8d15-192">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="f8d15-193">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span><span class="sxs-lookup"><span data-stu-id="f8d15-193">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="f8d15-194">Por ejemplo, el siguiente comando quita el buzón inactivo para Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="f8d15-194">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="f8d15-195">Compruebe que el buzón inactivo se quita de la lista de buzones de origen en la variable.</span><span class="sxs-lookup"><span data-stu-id="f8d15-195">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="f8d15-196">Modifique la retención local con la lista actualizada de buzones de origen, que no incluye el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-196">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="f8d15-197">Compruebe que el buzón inactivo se quita de la lista de buzones de origen para la retención local.</span><span class="sxs-lookup"><span data-stu-id="f8d15-197">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="f8d15-198">Más información</span><span class="sxs-lookup"><span data-stu-id="f8d15-198">More information</span></span>

- <span data-ttu-id="f8d15-199">**An inactive mailbox is a type of soft-deleted mailbox.**</span><span class="sxs-lookup"><span data-stu-id="f8d15-199">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="f8d15-200">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span><span class="sxs-lookup"><span data-stu-id="f8d15-200">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="f8d15-201">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span><span class="sxs-lookup"><span data-stu-id="f8d15-201">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="f8d15-202">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span><span class="sxs-lookup"><span data-stu-id="f8d15-202">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="f8d15-203">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span><span class="sxs-lookup"><span data-stu-id="f8d15-203">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="f8d15-204">**¿Qué ocurre después de quitar la retención en un buzón inactivo?**</span><span class="sxs-lookup"><span data-stu-id="f8d15-204">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="f8d15-205">El buzón de correo se considera como otros buzones eliminados temporalmente y se marca para eliminación permanente una vez que expire el período de retención de 30 días del buzón eliminado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="f8d15-205">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="f8d15-206">Este período de retención empieza en la fecha en que el buzón se volvió inactivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f8d15-206">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="f8d15-207">Esta fecha se conoce como la fecha de eliminación temporal, que es la fecha en que se eliminó la cuenta de usuario correspondiente o cuando se eliminó el buzón de Exchange Online con el cmdlet **Remove-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="f8d15-207">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="f8d15-208">La fecha de eliminación temporal no es la fecha en que se quita la retención.</span><span class="sxs-lookup"><span data-stu-id="f8d15-208">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="f8d15-209">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span><span class="sxs-lookup"><span data-stu-id="f8d15-209">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="f8d15-210">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span><span class="sxs-lookup"><span data-stu-id="f8d15-210">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="f8d15-211">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span><span class="sxs-lookup"><span data-stu-id="f8d15-211">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="f8d15-212">**¿Cómo afecta a los buzones inactivos el período de retención de buzones eliminados temporalmente?**</span><span class="sxs-lookup"><span data-stu-id="f8d15-212">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="f8d15-213">Si la fecha de eliminación temporal para un buzón inactivo es más de 30 días antes de la fecha en que se ha quitado la retención, el buzón se marca para su eliminación permanente.</span><span class="sxs-lookup"><span data-stu-id="f8d15-213">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="f8d15-214">Pero si un buzón inactivo tiene una fecha de eliminación temporal en los últimos 30 días y se quita la retención, es posible recuperar el buzón hasta que expire el período de retención de buzones eliminados temporalmente.</span><span class="sxs-lookup"><span data-stu-id="f8d15-214">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="f8d15-215">Para obtener más información, consulte [Delete or restore User mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span><span class="sxs-lookup"><span data-stu-id="f8d15-215">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="f8d15-216">Una vez que expire el período de retención de buzones eliminados temporalmente, debe seguir los procedimientos para recuperar un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="f8d15-216">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="f8d15-217">Para obtener más información, consulte [recuperar un buzón inactivo en Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="f8d15-217">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f8d15-218">**¿Cómo mostrar información sobre un buzón inactivo después de quitar la retención?**</span><span class="sxs-lookup"><span data-stu-id="f8d15-218">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="f8d15-219">Una vez que se quita una retención y el buzón inactivo se revierte a un buzón eliminado temporalmente, no se devolverá mediante el parámetro *InactiveMailboxOnly* con el cmdlet **Get-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="f8d15-219">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="f8d15-220">Pero puede mostrar información sobre el buzón mediante el comando **Get-Mailbox -SoftDeletedMailbox**.</span><span class="sxs-lookup"><span data-stu-id="f8d15-220">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="f8d15-221">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f8d15-221">For example:</span></span> 
    
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

  <span data-ttu-id="f8d15-222">En el ejemplo anterior, la propiedad *WhenSoftDeleted* identifica la fecha de eliminación temporal, que en este ejemplo es el 30 de octubre de 2014.</span><span class="sxs-lookup"><span data-stu-id="f8d15-222">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="f8d15-223">Si este buzón eliminado temporalmente era un buzón inactivo para el que se quitó la retención, se eliminará permanentemente 30 días después del valor de la propiedad *WhenSoftDeleted* .</span><span class="sxs-lookup"><span data-stu-id="f8d15-223">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="f8d15-224">En este caso, el buzón se elimina permanentemente después del 30 de noviembre de 2014.</span><span class="sxs-lookup"><span data-stu-id="f8d15-224">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

