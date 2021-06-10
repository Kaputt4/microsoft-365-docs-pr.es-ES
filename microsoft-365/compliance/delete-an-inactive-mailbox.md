---
title: Eliminar un buzón inactivo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
description: Cuando ya no necesite conservar el contenido de un buzón Microsoft 365 inactivo, puede eliminar permanentemente el buzón inactivo.
ms.openlocfilehash: 077a71bfdd82721e0992e5d14073aa037b7cfd1b
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100829"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="ba477-103">Eliminar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="ba477-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="ba477-104">Un buzón inactivo se usa para conservar el correo electrónico de un antiguo empleado después de salir de la organización.</span><span class="sxs-lookup"><span data-stu-id="ba477-104">An inactive mailbox is used to preserve a former employee's email after they leave your organization.</span></span> <span data-ttu-id="ba477-105">Cuando ya no necesita conservar el contenido de un buzón inactivo, puede quitar su retención para eliminarlo de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="ba477-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="ba477-106">Además, es posible que varias retenciones se coloquen en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="ba477-107">Por ejemplo, un buzón inactivo puede colocarse en retención de litigios y en una o varias retenciones locales.</span><span class="sxs-lookup"><span data-stu-id="ba477-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="ba477-108">Además, se puede aplicar una directiva de retención (creada en el centro de seguridad y cumplimiento en Office 365 o Microsoft 365) al buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="ba477-109">Debe quitar todas las directivas de retención y retención de un buzón inactivo para eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="ba477-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="ba477-110">Después de quitar las directivas de retención y retención, el buzón inactivo se marca para su eliminación y se elimina permanentemente después de procesarlo.</span><span class="sxs-lookup"><span data-stu-id="ba477-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ba477-111">A medida que seguimos invirtiendo de diferentes maneras para conservar el contenido del buzón, estamos anunciando la retirada de las In-Place en el centro Exchange administración.</span><span class="sxs-lookup"><span data-stu-id="ba477-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="ba477-112">Esto significa que debe usar las directivas de retención y retención por juicio para crear un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="ba477-113">A partir del 1 de julio de 2020 no podrá crear nuevas retenciones In-Place en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ba477-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="ba477-114">Pero aún podrá cambiar la duración de retención de una retención In-Place en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="ba477-115">Sin embargo, a partir del 1 de octubre de 2020, no podrá cambiar la duración de la retención.</span><span class="sxs-lookup"><span data-stu-id="ba477-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="ba477-116">Solo podrá eliminar un buzón inactivo quitando la In-Place espera.</span><span class="sxs-lookup"><span data-stu-id="ba477-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="ba477-117">Los buzones inactivos existentes que están en In-Place conservación se conservarán hasta que se quite la retención.</span><span class="sxs-lookup"><span data-stu-id="ba477-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="ba477-118">Para obtener más información acerca de la retirada de In-Place, vea [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="ba477-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="ba477-119">Consulte la sección [Más información](#more-information) para ver una descripción de lo que sucede una vez que se quitan las retenciones de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="ba477-120">Antes de eliminar un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="ba477-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="ba477-121">Debe usar powershell Exchange Online para quitar una retención por juicio de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="ba477-122">No puede usar el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="ba477-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="ba477-123">Para obtener instrucciones, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ba477-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="ba477-124">Puede copiar el contenido de un buzón inactivo a otro buzón antes de quitar la retención y eliminar un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="ba477-125">Para obtener más información, [vea Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ba477-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="ba477-126">Si quita la directiva de retención o retención de un buzón inactivo y el período de retención del buzón eliminado temporalmente para el buzón ha expirado, el buzón se eliminará permanentemente.</span><span class="sxs-lookup"><span data-stu-id="ba477-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="ba477-127">Una vez eliminado, no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="ba477-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="ba477-128">Antes de quitar la retención, asegúrese de que ya no necesita el contenido del buzón.</span><span class="sxs-lookup"><span data-stu-id="ba477-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="ba477-129">Si desea reactivar un buzón inactivo, puede recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="ba477-129">If you want to reactivate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="ba477-130">Para obtener más información, [vea Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ba477-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="ba477-131">Para obtener más información acerca de los buzones inactivos, vea [Buzones](inactive-mailboxes-in-office-365.md)inactivos en Office 365 .</span><span class="sxs-lookup"><span data-stu-id="ba477-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="ba477-132">Paso 1: identificar las retenciones en un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="ba477-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="ba477-133">Como se ha indicado anteriormente, una directiva de retención por juicio, In-Place suspensión o retención podría colocarse en un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="ba477-134">El primer paso es identificar las retenciones de un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="ba477-135">Ejecute el siguiente comando para mostrar la información de la retención de todos los buzones inactivos en su organización.</span><span class="sxs-lookup"><span data-stu-id="ba477-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="ba477-136">El valor de **True** para la propiedad **LitigationHoldEnabled** indica que el buzón inactivo está en retención por juicio.</span><span class="sxs-lookup"><span data-stu-id="ba477-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="ba477-137">Si una conservación local se coloca en un buzón inactivo, el GUID de la retención se muestra como el valor de la propiedad **InPlaceHolds**.</span><span class="sxs-lookup"><span data-stu-id="ba477-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="ba477-138">Por ejemplo, los siguientes resultados de dos buzones inactivos muestran que se coloca una retención por juicio en Ann Beebe y que una directiva de retención y retención de In-Place se coloca en Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="ba477-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="ba477-139">Si se colocan muchas In-Place o directivas de retención en un buzón inactivo, no se mostrarán todos los GUID de retención In-Place suspensión.</span><span class="sxs-lookup"><span data-stu-id="ba477-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="ba477-140">Puede ejecutar el siguiente comando para mostrar todos los GUID de la propiedad InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="ba477-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="ba477-141">Para obtener más información acerca de cómo identificar las retenciones, vea [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ba477-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="ba477-142">Paso 2: Quitar una retención de un buzón inactivo</span><span class="sxs-lookup"><span data-stu-id="ba477-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="ba477-p109">Tras identificar el tipo de retención que está colocada en el buzón inactivo (y si hay varias retenciones), el siguiente paso es quitar las retenciones del buzón. Como se mencionó anteriormente, tiene que quitar todas las retenciones para eliminar de forma permanente un buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-p109">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="ba477-145">Quitar una retención de litigios</span><span class="sxs-lookup"><span data-stu-id="ba477-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="ba477-p110">Como se mencionó anteriormente, tiene que usar Windows PowerShell para quitar una retención de litigios de un buzón inactivo. No puede usar el EAC. Ejecute el siguiente comando para quitar una retención de litigios.</span><span class="sxs-lookup"><span data-stu-id="ba477-p110">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="ba477-p111">La mejor manera de identificar un buzón inactivo es usando el valor Nombre distintivo o GUID de Exchange. El uso de uno de estos valores ayuda a impedir que se especifique accidentalmente el buzón equivocado.</span><span class="sxs-lookup"><span data-stu-id="ba477-p111">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="ba477-151">Quitar un buzón inactivo de una directiva de retención</span><span class="sxs-lookup"><span data-stu-id="ba477-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="ba477-152">El procedimiento para quitar un buzón inactivo de una directiva de retención Microsoft 365 depende de si la directiva de retención asignada al buzón inactivo es explícita o de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="ba477-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="ba477-153">en el tipo de directiva de retención asignada al buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="ba477-154">Directivas de retención de toda la organización asignadas a todos los buzones de la organización.</span><span class="sxs-lookup"><span data-stu-id="ba477-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="ba477-155">Use el cmdlet **Get-OrganizationConfig** en Exchange Online PowerShell para obtener información sobre las directivas de retención de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="ba477-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="ba477-156">Directivas de retención de ubicación específicas asignadas a buzones específicos.</span><span class="sxs-lookup"><span data-stu-id="ba477-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="ba477-157">Se trata de directivas que se asignan a las ubicaciones de contenido de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="ba477-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="ba477-158">Use el cmdlet **Get-Mailbox -Include QueMailbox** en Exchange Online PowerShell para obtener información sobre las directivas de retención asignadas a buzones inactivos específicos.</span><span class="sxs-lookup"><span data-stu-id="ba477-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="ba477-159">Quitar un buzón inactivo de una directiva de retención en toda la organización</span><span class="sxs-lookup"><span data-stu-id="ba477-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="ba477-160">Ejecute el siguiente comando en Exchange Online PowerShell para excluir un buzón inactivo de una directiva de retención en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="ba477-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="ba477-161">Para obtener más información sobre cómo identificar las directivas de retención de toda la organización aplicadas a un buzón inactivo y obtener el GUID de una directiva de retención, vea la sección "Get-OrganizationConfig" en [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span><span class="sxs-lookup"><span data-stu-id="ba477-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="ba477-162">Como alternativa, puede ejecutar el siguiente comando para quitar el buzón inactivo de todas las directivas de toda la organización:</span><span class="sxs-lookup"><span data-stu-id="ba477-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="ba477-163">Quitar un buzón inactivo de una directiva de retención de ubicación específica</span><span class="sxs-lookup"><span data-stu-id="ba477-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="ba477-164">Ejecute el siguiente comando en [PowerShell & Centro](/powershell/exchange/connect-to-scc-powershell) de seguridad y cumplimiento para quitar un buzón inactivo de una directiva de retención explícita.</span><span class="sxs-lookup"><span data-stu-id="ba477-164">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="ba477-165">Para obtener más información acerca de cómo identificar directivas de retención de ubicación específicas aplicadas a un buzón inactivo y obtener el GUID de una directiva de retención, vea la sección "Get-Mailbox" en [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ba477-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="ba477-166">Quitar retenciones locales</span><span class="sxs-lookup"><span data-stu-id="ba477-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="ba477-167">Hay dos maneras de quitar una retención local de un buzón inactivo:</span><span class="sxs-lookup"><span data-stu-id="ba477-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="ba477-168">**Elimine el In-Place hold**.</span><span class="sxs-lookup"><span data-stu-id="ba477-168">**Delete the In-Place Hold object**.</span></span> <span data-ttu-id="ba477-169">Si el buzón inactivo que desea eliminar permanentemente es el único buzón de origen para una retención de In-Place, solo puede eliminar el In-Place hold.</span><span class="sxs-lookup"><span data-stu-id="ba477-169">If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="ba477-p116">Tiene que deshabilitar la retención antes de poder eliminar un objeto de retención local. Si intenta eliminar un objeto de retención local que tiene habilitada la retención, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ba477-p116">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="ba477-172">**Quite el buzón inactivo como buzón de origen de una In-Place hold**.</span><span class="sxs-lookup"><span data-stu-id="ba477-172">**Remove the inactive mailbox as a source mailbox of an In-Place Hold**.</span></span> <span data-ttu-id="ba477-173">Si quiere conservar otros buzones de origen para una retención local, puede quitar el buzón inactivo de la lista de buzones de origen y mantener el objeto de retención local.</span><span class="sxs-lookup"><span data-stu-id="ba477-173">If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="ba477-174">Eliminar una retención In-Place espera</span><span class="sxs-lookup"><span data-stu-id="ba477-174">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="ba477-p118">Cree una variable que contenga las propiedades de la retención local que quiera eliminar. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ba477-p118">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="ba477-177">Deshabilite la retención en la retención local.</span><span class="sxs-lookup"><span data-stu-id="ba477-177">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="ba477-178">Elimine la retención local.</span><span class="sxs-lookup"><span data-stu-id="ba477-178">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="ba477-179">Quitar un buzón inactivo de una In-Place retención</span><span class="sxs-lookup"><span data-stu-id="ba477-179">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="ba477-180">Si la retención local contiene un gran número de buzones de origen, es posible que el buzón local no aparezca en la página **Orígenes** en el EAC.</span><span class="sxs-lookup"><span data-stu-id="ba477-180">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="ba477-181">Hasta 3.000 buzones se muestran en la página **Orígenes** cuando edita una retención local.</span><span class="sxs-lookup"><span data-stu-id="ba477-181">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="ba477-182">Si un buzón inactivo no aparece  en la página Orígenes, puede usar Exchange Online PowerShell para quitarlo de la In-Place espera.</span><span class="sxs-lookup"><span data-stu-id="ba477-182">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="ba477-p120">Cree una variable que contenga las propiedades de la retención local colocada en el buzón inactivo. Use el GUID de retención local que obtuvo en [Paso 1: Identificar las retenciones en un buzón inactivo](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ba477-p120">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="ba477-185">Compruebe que el buzón inactivo aparezca como un buzón de origen para la retención local.</span><span class="sxs-lookup"><span data-stu-id="ba477-185">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="ba477-p121">La propiedad *Sources* de la retención local identifica los buzones de origen por sus propiedades *LegacyExchangeDN*. Como esta propiedad identifica exclusivamente los buzones inactivos, el uso de la propiedad *Sources* de la retención local ayuda a impedir que se elimine el buzón equivocado. También ayuda a evitar problemas si dos buzones tienen el mismo alias o dirección SMTP.</span><span class="sxs-lookup"><span data-stu-id="ba477-p121">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="ba477-p122">Quite el buzón inactivo de la lista de buzones de origen en la variable. Asegúrese de usar la propiedad **LegacyExchangeDN** del buzón inactivo devuelto por el comando en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="ba477-p122">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="ba477-191">Por ejemplo, el siguiente comando quita el buzón inactivo para Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="ba477-191">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="ba477-192">Compruebe que el buzón inactivo se quita de la lista de buzones de origen en la variable.</span><span class="sxs-lookup"><span data-stu-id="ba477-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="ba477-193">Modifique la retención local con la lista actualizada de buzones de origen, que no incluye el buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="ba477-194">Compruebe que el buzón inactivo se quita de la lista de buzones de origen para la retención local.</span><span class="sxs-lookup"><span data-stu-id="ba477-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="ba477-195">Más información</span><span class="sxs-lookup"><span data-stu-id="ba477-195">More information</span></span>

- <span data-ttu-id="ba477-196">**Un buzón inactivo es un tipo de buzón eliminado temporalmente.**</span><span class="sxs-lookup"><span data-stu-id="ba477-196">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="ba477-197">En Exchange Online, un buzón eliminado temporalmente es un buzón que se ha eliminado, pero se pueden recuperar en un período de retención específico.</span><span class="sxs-lookup"><span data-stu-id="ba477-197">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="ba477-198">Un buzón inactivo anteriormente estará disponible como buzón eliminado temporalmente en Exchange Online durante 183 días.</span><span class="sxs-lookup"><span data-stu-id="ba477-198">A previously inactive mailbox will be available as a soft-deleted mailbox in Exchange Online for 183 days.</span></span> <span data-ttu-id="ba477-199">Esto significa que el buzón se puede recuperar dentro de los 183 días siguientes a la eliminación temporal.</span><span class="sxs-lookup"><span data-stu-id="ba477-199">This means that the mailbox can be recovered within 183 days of being soft-deleted.</span></span> <span data-ttu-id="ba477-200">Después de 183 días, un buzón eliminado temporalmente se marca para su eliminación permanente y no se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="ba477-200">After 183 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="ba477-201">**¿Qué ocurre después de quitar la retención en un buzón inactivo?**</span><span class="sxs-lookup"><span data-stu-id="ba477-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="ba477-202">El buzón se trata como otros buzones eliminados temporalmente y se marca para su eliminación permanente después de que expire el período de retención de buzones eliminado temporalmente de 183 días.</span><span class="sxs-lookup"><span data-stu-id="ba477-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 183-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="ba477-203">Este período de retención empieza en la fecha en que el buzón se volvió inactivo por primera vez.</span><span class="sxs-lookup"><span data-stu-id="ba477-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="ba477-204">Esta fecha se conoce como la fecha de eliminación temporal, que es la fecha en que se eliminó la cuenta de usuario correspondiente o cuando se eliminó el buzón de Exchange Online con el cmdlet **Remove-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="ba477-204">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="ba477-205">La fecha de eliminación temporal no es la fecha en que se quita la retención.</span><span class="sxs-lookup"><span data-stu-id="ba477-205">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="ba477-206">**¿Un buzón inactivo se elimina de forma permanente inmediatamente después de quitar la retención?**</span><span class="sxs-lookup"><span data-stu-id="ba477-206">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="ba477-207">Un buzón inactivo anteriormente estará disponible en el estado eliminado temporalmente durante 183 días.</span><span class="sxs-lookup"><span data-stu-id="ba477-207">A formerly inactive mailbox will be available in the soft-deleted state for 183 days.</span></span> <span data-ttu-id="ba477-208">Después de 183 días, el buzón se marcará para su eliminación permanente.</span><span class="sxs-lookup"><span data-stu-id="ba477-208">After 183 days the mailbox will be marked for permanent deletion.</span></span>

- <span data-ttu-id="ba477-209">**¿Cómo mostrar información sobre un buzón inactivo después de quitar la retención?**</span><span class="sxs-lookup"><span data-stu-id="ba477-209">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="ba477-210">Después de quitar una retención y de que el buzón inactivo vuelva a un buzón eliminado temporalmente, no se devolverá mediante el parámetro *InactiveMailboxOnly* con el cmdlet **Get-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="ba477-210">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="ba477-211">Pero puede mostrar información sobre el buzón mediante el comando **Get-Mailbox -SoftDeletedMailbox**.</span><span class="sxs-lookup"><span data-stu-id="ba477-211">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="ba477-212">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ba477-212">For example:</span></span>

  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox,WasInactiveMailbox,InactiveMailboxRetireTime
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 6/16/2020 1:19:04 AM
  IsInactiveMailbox      : False
  WasInactiveMailbox     : True
  InactiveMailboxRetireTime : 9/30/2020 11:16:23 PM
  ```

  <span data-ttu-id="ba477-213">En el ejemplo anterior, la propiedad *WhenSoftDeleted* identifica la fecha de eliminación temporal, que en este ejemplo es el 16 de junio de 2020.</span><span class="sxs-lookup"><span data-stu-id="ba477-213">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is June 16, 2020.</span></span> <span data-ttu-id="ba477-214">La *propiedad Was ElMailbox* aparece como porque anteriormente era un `True` buzón inactivo.</span><span class="sxs-lookup"><span data-stu-id="ba477-214">The *WasInactiveMailbox* property is listed as `True` because it was previously an inactive mailbox.</span></span> <span data-ttu-id="ba477-215">El buzón se eliminará permanentemente 183 días después del 30 de septiembre de 2020.</span><span class="sxs-lookup"><span data-stu-id="ba477-215">The mailbox will be permanently deleted 183 days after September 30, 2020.</span></span>

