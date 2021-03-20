---
title: Actualizar listas de distribución a grupos de Microsoft 365 en Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Obtenga información sobre cómo actualizar una o varias listas de distribución a grupos de Microsoft 365 en Outlook y cómo usar PowerShell para actualizar varias listas de distribución simultáneamente.
ms.openlocfilehash: 7fd6090e00e9099feb93685a276b5e207bd05419
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915007"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="04e2b-103">Actualizar listas de distribución a grupos de Microsoft 365 en Outlook</span><span class="sxs-lookup"><span data-stu-id="04e2b-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="04e2b-104">Puede actualizar listas de distribución a Grupos de Microsoft 365 con Outlook.</span><span class="sxs-lookup"><span data-stu-id="04e2b-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="04e2b-105">Esta es una excelente manera de proporcionar a las listas de distribución de su organización todas las características y funcionalidades de Grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04e2b-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="04e2b-106">Por qué debería actualizar sus listas de distribución a grupos de Outlook</span><span class="sxs-lookup"><span data-stu-id="04e2b-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="04e2b-107">Puede actualizar las DLs una a la vez o varias al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="04e2b-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="04e2b-108">Actualizar una o varias listas de distribución a grupos de Microsoft 365 en Outlook</span><span class="sxs-lookup"><span data-stu-id="04e2b-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="04e2b-109">Debe ser administrador global o administrador de Exchange para actualizar una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="04e2b-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="04e2b-110">Para actualizar a Grupos de Microsoft 365, un grupo de distribución debe tener un propietario con un buzón.</span><span class="sxs-lookup"><span data-stu-id="04e2b-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span>

1. <span data-ttu-id="04e2b-111">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="04e2b-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="04e2b-112">En el Centro de administración de Exchange, vaya **a Grupos de** \> **destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="04e2b-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="04e2b-113">Verá un aviso que indica que tiene listas de distribución (también denominadas grupos de **distribución)** que son aptas para actualizarse a Grupos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="04e2b-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="04e2b-114">![Seleccione el botón Introducción](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="04e2b-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="04e2b-115">Seleccione una o más listas de distribución (también denominadas **grupos de distribución)** en la **página grupos.**</span><span class="sxs-lookup"><span data-stu-id="04e2b-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="04e2b-116">![Seleccionar un grupo de distribución](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="04e2b-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="04e2b-117">Seleccione el icono de actualización.</span><span class="sxs-lookup"><span data-stu-id="04e2b-117">Select the upgrade icon.</span></span><br/>![Actualizar al icono Grupos de Microsoft 365](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="04e2b-119">En el cuadro de diálogo información, seleccione **Sí** para confirmar la actualización.</span><span class="sxs-lookup"><span data-stu-id="04e2b-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="04e2b-120">El proceso comienza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="04e2b-120">The process begins immediately.</span></span> <span data-ttu-id="04e2b-121">Según el tamaño y el número de direcciones URL que actualice, el proceso puede tardar minutos u horas.</span><span class="sxs-lookup"><span data-stu-id="04e2b-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="04e2b-122">Si la lista de distribución no se puede actualizar, aparece un cuadro de diálogo que lo dice.</span><span class="sxs-lookup"><span data-stu-id="04e2b-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="04e2b-123">Vea [¿Qué listas de distribución no se pueden actualizar?](#which-distribution-lists-cant-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="04e2b-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="04e2b-124">Si va a actualizar varias listas de distribución, use la lista desplegable para filtrar qué listas de distribución se han actualizado.</span><span class="sxs-lookup"><span data-stu-id="04e2b-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="04e2b-125">Si la lista no está completa, espere un tiempo más y, a continuación, seleccione **Actualizar** para ver lo que se ha actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="04e2b-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="04e2b-126">No hay ningún aviso que le indique cuándo se ha completado el proceso de actualización para todas las direcciones URL que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="04e2b-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="04e2b-127">Para averiguarlo, vea lo que aparece en **Disponible para actualización** o Direcciones DLL **actualizadas.**</span><span class="sxs-lookup"><span data-stu-id="04e2b-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="04e2b-128">Si seleccionó una DL para la actualización, pero aún aparece en la página como Disponible para actualizar, no se pudo actualizar.</span><span class="sxs-lookup"><span data-stu-id="04e2b-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="04e2b-129">Consulte [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="04e2b-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="04e2b-130">Si estás recibiendo los mensajes de correo electrónico de resumen de grupos, es posible que observes en la parte inferior que a veces te permitirá actualizar las listas de distribución elegibles de las que seas propietario.</span><span class="sxs-lookup"><span data-stu-id="04e2b-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="04e2b-131">Vea [Tener una conversación en grupo en Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) para obtener más información acerca de los correos electrónicos de resumen.</span><span class="sxs-lookup"><span data-stu-id="04e2b-131">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="04e2b-132">Qué hacer si la actualización no funciona</span><span class="sxs-lookup"><span data-stu-id="04e2b-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="04e2b-133">Las listas de distribución que no se pueden actualizar permanecen sin cambios.</span><span class="sxs-lookup"><span data-stu-id="04e2b-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="04e2b-134">Si una o más listas **de** distribución elegibles no se pueden actualizar, abra un [vale de soporte](../contact-support-for-business-products.md)técnico .</span><span class="sxs-lookup"><span data-stu-id="04e2b-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="04e2b-135">El problema tendrá que escalarse al equipo de ingeniería de grupos para que puedan averiguar el problema.</span><span class="sxs-lookup"><span data-stu-id="04e2b-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="04e2b-136">Es posible que la lista de distribución no se haya actualizado debido a una interrupción del servicio, pero es bastante poco probable.</span><span class="sxs-lookup"><span data-stu-id="04e2b-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span></span> <span data-ttu-id="04e2b-137">Si lo desea, espere un tiempo y vuelva a intentar actualizar la DL.</span><span class="sxs-lookup"><span data-stu-id="04e2b-137">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="04e2b-138">Cómo usar PowerShell para actualizar varias listas de distribución al mismo tiempo</span><span class="sxs-lookup"><span data-stu-id="04e2b-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="04e2b-139">Si tienes experiencia en el uso de PowerShell, es posible que quieras ir a esta ruta en lugar de usar la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="04e2b-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="04e2b-140">Tenemos un conjunto de cmdlets que le ayudarán a actualizar listas de distribución.</span><span class="sxs-lookup"><span data-stu-id="04e2b-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="04e2b-141">Véalo a continuación.</span><span class="sxs-lookup"><span data-stu-id="04e2b-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="04e2b-142">Actualizar una sola DL</span><span class="sxs-lookup"><span data-stu-id="04e2b-142">Upgrade a single DL</span></span>

<span data-ttu-id="04e2b-143">Para actualizar una sola DL, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="04e2b-143">To upgrade a single DL run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

<span data-ttu-id="04e2b-144">Por ejemplo, si desea actualizar un DLs con direcciones SMTP dl1@contoso.com, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="04e2b-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> <span data-ttu-id="04e2b-145">También puede actualizar una única lista de distribución a un grupo de Microsoft 365 con el cmdlet de PowerShell [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup)</span><span class="sxs-lookup"><span data-stu-id="04e2b-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="04e2b-146">Actualizar varias direcciones URL en un lote</span><span class="sxs-lookup"><span data-stu-id="04e2b-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="04e2b-147">También puede pasar varias direcciones URL como un lote y actualizarlas juntas:</span><span class="sxs-lookup"><span data-stu-id="04e2b-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="04e2b-148">Por ejemplo, si desea actualizar cinco direcciones URL con dirección SMTP y `dl1@contoso.com` , y , ejecute el siguiente `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` comando:</span><span class="sxs-lookup"><span data-stu-id="04e2b-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="04e2b-149">Actualizar todas las DLs elegibles</span><span class="sxs-lookup"><span data-stu-id="04e2b-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="04e2b-150">Hay dos formas de actualizar todas las direcciones URL elegibles.</span><span class="sxs-lookup"><span data-stu-id="04e2b-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="04e2b-151">El cmdlet Upgrade-DistributionGroup no recibe datos de la canalización, por lo que es necesario usar el operador "foreach-object" para {} ejecutarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="04e2b-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="04e2b-152">Obtener las direcciones URL elegibles en el inquilino y actualizarlas mediante el comando de actualización:</span><span class="sxs-lookup"><span data-stu-id="04e2b-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="04e2b-153">Obtener la lista de todas las direcciones DLL y actualizar solo las direcciones URL elegibles:</span><span class="sxs-lookup"><span data-stu-id="04e2b-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="04e2b-154">Preguntas frecuentes sobre cómo actualizar listas de distribución a grupos de Microsoft 365 en Outlook</span><span class="sxs-lookup"><span data-stu-id="04e2b-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="04e2b-155">¿Qué listas de distribución no se pueden actualizar?</span><span class="sxs-lookup"><span data-stu-id="04e2b-155">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="04e2b-156">Solo puede actualizar listas de distribución sencillas y no anidadas administradas en la nube.</span><span class="sxs-lookup"><span data-stu-id="04e2b-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="04e2b-157">En la tabla siguiente se enumeran las listas de distribución **que no** se pueden actualizar.</span><span class="sxs-lookup"><span data-stu-id="04e2b-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="04e2b-158">**Propiedad**</span><span class="sxs-lookup"><span data-stu-id="04e2b-158">**Property**</span></span>|<span data-ttu-id="04e2b-159">**¿Elegible?**</span><span class="sxs-lookup"><span data-stu-id="04e2b-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="04e2b-160">Lista de distribución administrada local.</span><span class="sxs-lookup"><span data-stu-id="04e2b-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="04e2b-161">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-161">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-162">Listas de distribución anidadas.</span><span class="sxs-lookup"><span data-stu-id="04e2b-162">Nested distribution lists.</span></span> <span data-ttu-id="04e2b-163">La lista de distribución tiene grupos secundarios o es miembro de otro grupo.</span><span class="sxs-lookup"><span data-stu-id="04e2b-163">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="04e2b-164">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-164">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-165">Listas de distribución con **miembros RecipientTypeDetails distintos** de **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="04e2b-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="04e2b-166">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-166">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-167">Lista de distribución con más de 100 propietarios</span><span class="sxs-lookup"><span data-stu-id="04e2b-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="04e2b-168">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-168">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-169">Lista de distribución que solo tiene miembros pero ningún propietario</span><span class="sxs-lookup"><span data-stu-id="04e2b-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="04e2b-170">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-170">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-171">Lista de distribución con alias que contiene caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="04e2b-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="04e2b-172">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-172">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-173">Si la lista de distribución está configurada para ser una dirección de reenvío para buzón compartido</span><span class="sxs-lookup"><span data-stu-id="04e2b-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="04e2b-174">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-174">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-175">Si dl forma parte de la **restricción del remitente** en otro DL.</span><span class="sxs-lookup"><span data-stu-id="04e2b-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="04e2b-176">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-176">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-177">Grupos de seguridad</span><span class="sxs-lookup"><span data-stu-id="04e2b-177">Security groups</span></span>  <br/> |<span data-ttu-id="04e2b-178">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-178">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-179">Listas de distribución dinámica</span><span class="sxs-lookup"><span data-stu-id="04e2b-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="04e2b-180">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-180">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-181">Listas de distribución que se convirtieron en **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="04e2b-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="04e2b-182">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-182">No</span></span>  <br/> |
|<span data-ttu-id="04e2b-183">Listas de distribución **donde MemberJoinRestriction** y/o **MemberDepartRestriction** está **Cerrado**</span><span class="sxs-lookup"><span data-stu-id="04e2b-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="04e2b-184">No</span><span class="sxs-lookup"><span data-stu-id="04e2b-184">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="04e2b-185">Comprobar qué direcciones URL son aptas para la actualización</span><span class="sxs-lookup"><span data-stu-id="04e2b-185">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="04e2b-186">Si desea comprobar si un archivo DL es apto o no, puede ejecutar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="04e2b-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="04e2b-187">Si desea comprobar qué direcciones DLL son aptas para la actualización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="04e2b-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="04e2b-188">¿Quién puede ejecutar los scripts de actualización?</span><span class="sxs-lookup"><span data-stu-id="04e2b-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="04e2b-189">Personas con derechos de administrador global o de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="04e2b-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="04e2b-190">¿Por qué la tarjeta de contacto sigue mostrando una lista de distribución?</span><span class="sxs-lookup"><span data-stu-id="04e2b-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="04e2b-191">¿Qué debo hacer para evitar que una lista de distribución actualizada se muestre en mi lista de sugerencias automáticas?</span><span class="sxs-lookup"><span data-stu-id="04e2b-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="04e2b-192">Para Outlook: cuando alguien intente enviar un correo electrónico en Outlook escribiendo el nombre del grupo de Microsoft 365 después de la migración, el destinatario se resolverá como la lista de distribución en lugar del grupo.</span><span class="sxs-lookup"><span data-stu-id="04e2b-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="04e2b-193">La tarjeta de contacto del destinatario será la tarjeta de contacto de listas de distribución.</span><span class="sxs-lookup"><span data-stu-id="04e2b-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="04e2b-194">Esto se debe a la caché de destinatarios o a la memoria caché de nombres de nick en Outlook.</span><span class="sxs-lookup"><span data-stu-id="04e2b-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="04e2b-195">El correo electrónico se enviará correctamente al grupo, pero puede causar confusión al remitente.</span><span class="sxs-lookup"><span data-stu-id="04e2b-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="04e2b-196">Puede realizar los pasos descritos en este tema, Información sobre la lista [Autocompletar](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) de Outlook para restablecer la memoria caché, que solucionará este problema.</span><span class="sxs-lookup"><span data-stu-id="04e2b-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="04e2b-197">Para Outlook en la web: en el caso de Outlook en la web, el destinatario de la lista de distribución seguirá estando en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="04e2b-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="04e2b-198">Puede seguir los pasos descritos en [Quitar](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) el nombre sugerido o la dirección de correo electrónico de la lista de autocompletar para actualizar la memoria caché para ver la tarjeta de contacto del grupo.</span><span class="sxs-lookup"><span data-stu-id="04e2b-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="04e2b-199">¿Los nuevos miembros del grupo reciben un correo electrónico de bienvenida en su bandeja de entrada?</span><span class="sxs-lookup"><span data-stu-id="04e2b-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="04e2b-200">No.</span><span class="sxs-lookup"><span data-stu-id="04e2b-200">No.</span></span> <span data-ttu-id="04e2b-201">La configuración para habilitar los mensajes de bienvenida se establece en false de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="04e2b-201">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="04e2b-202">Esta configuración afecta tanto a los miembros de grupo existentes como a los nuevos que pueden unirse una vez completada la migración.</span><span class="sxs-lookup"><span data-stu-id="04e2b-202">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="04e2b-203">Si el propietario del grupo permite más adelante a los usuarios invitados, los usuarios invitados no recibirán un correo electrónico de bienvenida en su bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="04e2b-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="04e2b-204">Los miembros invitados pueden seguir trabajando con el grupo.</span><span class="sxs-lookup"><span data-stu-id="04e2b-204">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="04e2b-205">¿Qué ocurre si uno o algunos de los DLs no se actualizan?</span><span class="sxs-lookup"><span data-stu-id="04e2b-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="04e2b-206">Hay algunos casos en los que, aunque DL es apto pero no se pudo actualizar.</span><span class="sxs-lookup"><span data-stu-id="04e2b-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="04e2b-207">La DL no se actualiza y permanece como un ARCHIVO DL.</span><span class="sxs-lookup"><span data-stu-id="04e2b-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="04e2b-208">Donde el administrador **ha** aplicado la directiva de direcciones de correo electrónico de grupo para los grupos de una organización e intentan actualizar las direcciones DLL que no cumplen los criterios, la DL no se actualiza</span><span class="sxs-lookup"><span data-stu-id="04e2b-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="04e2b-209">Las DLs **con MemberJoinRestriction** o **MemberDepartRestriction** establecidas en **Closed**, no se pudieron actualizar</span><span class="sxs-lookup"><span data-stu-id="04e2b-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="04e2b-210">¿Qué sucede con la DL si se produce un error en la actualización desde EAC?</span><span class="sxs-lookup"><span data-stu-id="04e2b-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="04e2b-211">La actualización solo se realizará cuando se envía la llamada al servidor.</span><span class="sxs-lookup"><span data-stu-id="04e2b-211">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="04e2b-212">Si se produce un error en la actualización, las direcciones DLL estarán intactas.</span><span class="sxs-lookup"><span data-stu-id="04e2b-212">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="04e2b-213">Funcionarán como antes.</span><span class="sxs-lookup"><span data-stu-id="04e2b-213">They will work like they used to.</span></span>