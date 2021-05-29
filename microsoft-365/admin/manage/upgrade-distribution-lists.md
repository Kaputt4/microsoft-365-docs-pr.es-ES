---
title: Actualizar listas de distribución a Microsoft 365 grupos en Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Obtenga información sobre cómo actualizar una o varias listas de distribución Microsoft 365 grupos en Outlook y cómo usar PowerShell para actualizar varias listas de distribución simultáneamente.
ms.openlocfilehash: d4686e7f2ec305194130b60fbacab24c9cf7f4e9
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698945"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="395ce-103">Actualizar listas de distribución a Microsoft 365 grupos en Outlook</span><span class="sxs-lookup"><span data-stu-id="395ce-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="395ce-104">Puede actualizar listas de distribución a grupos Microsoft 365 en Outlook.</span><span class="sxs-lookup"><span data-stu-id="395ce-104">You can upgrade distribution lists to Microsoft 365 Groups in Outlook.</span></span> <span data-ttu-id="395ce-105">Esta es una excelente manera de proporcionar a las listas de distribución de su organización todas las características y funcionalidades de Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="395ce-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="395ce-106">Por qué debería actualizar sus listas de distribución a grupos de Outlook</span><span class="sxs-lookup"><span data-stu-id="395ce-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="395ce-107">Puede actualizar las DLs una a la vez o varias al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="395ce-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="395ce-108">Actualizar uno o varios grupos de listas de distribución a Microsoft 365 grupos en Outlook</span><span class="sxs-lookup"><span data-stu-id="395ce-108">Upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="395ce-109">Debe ser un administrador global o un administrador Exchange para actualizar un grupo de listas de distribución.</span><span class="sxs-lookup"><span data-stu-id="395ce-109">You must be a global admin or Exchange admin to upgrade a distribution list group.</span></span> <span data-ttu-id="395ce-110">Para actualizar a Microsoft 365, el grupo de lista de distribución debe tener un propietario con un buzón.</span><span class="sxs-lookup"><span data-stu-id="395ce-110">To upgrade to Microsoft 365 Groups, the distribution list group must have an owner with a mailbox.</span></span>

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="395ce-111">Use el nuevo EAC para actualizar uno o varios grupos de listas de distribución a Microsoft 365 grupos de Outlook</span><span class="sxs-lookup"><span data-stu-id="395ce-111">Use the new EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="395ce-112">Vaya al nuevo centro [Exchange de administración](https://admin.exchange.microsoft.com)y vaya a Grupos **de** \> **destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="395ce-112">Go to the new [Exchange admin center](https://admin.exchange.microsoft.com), and navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="395ce-113">Seleccione el grupo de lista de distribución (también denominado grupo de **distribución)** que desea actualizar a Microsoft 365 en la **página** Grupos.</span><span class="sxs-lookup"><span data-stu-id="395ce-113">Select the distribution list group (also called a **distribution group**) that you want to upgrade to Microsoft 365 group from the **Groups** page.</span></span>

3. <span data-ttu-id="395ce-114">Seleccione el **grupo de distribución Actualizar** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="395ce-114">Select the **Upgrade distribution group** from the tool bar.</span></span>

4. <span data-ttu-id="395ce-115">En el cuadro de diálogo **¿Listo para actualizar?**, haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="395ce-115">In the dialog box **Ready to upgrade?**, click **Upgrade**.</span></span> <span data-ttu-id="395ce-116">El proceso comienza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="395ce-116">The process begins immediately.</span></span> <span data-ttu-id="395ce-117">Según el tamaño y el número de grupos de listas de distribución que actualice, el proceso puede tardar minutos u horas.</span><span class="sxs-lookup"><span data-stu-id="395ce-117">Depending on the size and number of distribution list groups you're upgrading, the process can take minutes or hours.</span></span>

> [!NOTE]
> <span data-ttu-id="395ce-118">Un banner en la parte superior indica la actualización, por ejemplo, los grupos de distribución *se han actualizado. Los cambios tardarán 5 minutos. Filtrar por Microsoft 365 para ver los grupos de distrrución actualizados*.</span><span class="sxs-lookup"><span data-stu-id="395ce-118">A banner at the top indicates the upgrade, for example, *Distribution group(s) has been upgraded. It will take 5 minutes to reflect the changes. Filter by Microsoft 365 groups to see the upgraded distrubtion groups(s)*.</span></span>

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="395ce-119">Use el EAC clásico para actualizar uno o varios grupos de listas de distribución a Microsoft 365 grupos de Outlook</span><span class="sxs-lookup"><span data-stu-id="395ce-119">Use the Classic EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="395ce-120">Vaya al Centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administración Exchange clásico.</a></span><span class="sxs-lookup"><span data-stu-id="395ce-120">Go to the Classic <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="395ce-121">En el Centro Exchange administración, vaya a **Grupos de** \> **destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="395ce-121">In the Classic Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="395ce-122">Verá un aviso que indica que tiene listas de distribución (también denominadas grupos de **distribución)** que son aptas para actualizarse a Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="395ce-122">You'll see a notice indicating you have distribution lists (also called **distribution groups**) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="395ce-123">![Seleccione el botón Introducción](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="395ce-123">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="395ce-124">Seleccione una o más listas de distribución (también denominadas **grupos de distribución)** en la **página grupos.**</span><span class="sxs-lookup"><span data-stu-id="395ce-124">Select one or more distribution lists (also called a **distribution group**) from the **groups** page.</span></span><br/><span data-ttu-id="395ce-125">![Seleccionar un grupo de distribución](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="395ce-125">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="395ce-126">Seleccione el icono de actualización.</span><span class="sxs-lookup"><span data-stu-id="395ce-126">Select the upgrade icon.</span></span><br/>![Actualizar a Microsoft 365 de grupos](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="395ce-128">En el cuadro de diálogo información, seleccione **Sí** para confirmar la actualización.</span><span class="sxs-lookup"><span data-stu-id="395ce-128">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="395ce-129">El proceso comienza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="395ce-129">The process begins immediately.</span></span> <span data-ttu-id="395ce-130">Según el tamaño y el número de direcciones URL que actualice, el proceso puede tardar minutos u horas.</span><span class="sxs-lookup"><span data-stu-id="395ce-130">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="395ce-131">Si la lista de distribución no se puede actualizar, aparece un cuadro de diálogo que lo dice.</span><span class="sxs-lookup"><span data-stu-id="395ce-131">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="395ce-132">Vea [¿Qué listas de distribución no se pueden actualizar?](#which-distribution-lists-cant-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="395ce-132">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="395ce-133">Si va a actualizar varias listas de distribución, use la lista desplegable para filtrar qué listas de distribución se han actualizado.</span><span class="sxs-lookup"><span data-stu-id="395ce-133">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="395ce-134">Si la lista no está completa, espere un tiempo más y, a continuación, seleccione **Actualizar** para ver lo que se ha actualizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="395ce-134">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="395ce-135">No hay ningún aviso que le indique cuándo se ha completado el proceso de actualización para todas las direcciones URL que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="395ce-135">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="395ce-136">Para averiguarlo, vea lo que aparece en **Disponible para actualización** o Direcciones DLL **actualizadas.**</span><span class="sxs-lookup"><span data-stu-id="395ce-136">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="395ce-137">Si seleccionó un archivo DL para la actualización, pero aún aparece en la página como Disponible para actualizar, no se pudo actualizar.</span><span class="sxs-lookup"><span data-stu-id="395ce-137">If you selected a DL for upgrade, but it's still appeared on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="395ce-138">Consulte [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="395ce-138">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="395ce-139">Si estás recibiendo los mensajes de correo electrónico de resumen de grupos, es posible que observes en la parte inferior que a veces te permitirá actualizar las listas de distribución elegibles de las que seas propietario.</span><span class="sxs-lookup"><span data-stu-id="395ce-139">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="395ce-140">Consulta [Tener una conversación en grupo en Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) para obtener más información acerca de los correos electrónicos de resumen.</span><span class="sxs-lookup"><span data-stu-id="395ce-140">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="395ce-141">Qué hacer si la actualización no funciona</span><span class="sxs-lookup"><span data-stu-id="395ce-141">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="395ce-142">Las listas de distribución que no se pueden actualizar permanecen sin cambios.</span><span class="sxs-lookup"><span data-stu-id="395ce-142">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="395ce-143">Si una o más listas **de** distribución elegibles no se pueden actualizar, abra un [vale de soporte](../../business-video/get-help-support.md)técnico .</span><span class="sxs-lookup"><span data-stu-id="395ce-143">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../../business-video/get-help-support.md).</span></span> <span data-ttu-id="395ce-144">El problema tendrá que escalarse al equipo de ingeniería de grupos para que puedan averiguar el problema.</span><span class="sxs-lookup"><span data-stu-id="395ce-144">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="395ce-145">Es posible que la lista de distribución no se haya actualizado debido a una interrupción del servicio, pero es poco probable.</span><span class="sxs-lookup"><span data-stu-id="395ce-145">It's possible that the distribution list didn't get upgraded because of a service outage, but unlikely.</span></span> <span data-ttu-id="395ce-146">Si lo desea, espere un tiempo y vuelva a intentar actualizar la DL.</span><span class="sxs-lookup"><span data-stu-id="395ce-146">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="395ce-147">Cómo usar PowerShell para actualizar varias listas de distribución al mismo tiempo</span><span class="sxs-lookup"><span data-stu-id="395ce-147">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="395ce-148">Si tienes experiencia en el uso de PowerShell, es posible que quieras ir a esta ruta en lugar de usar la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="395ce-148">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="395ce-149">Tenemos un conjunto de cmdlets que le ayudarán a actualizar listas de distribución.</span><span class="sxs-lookup"><span data-stu-id="395ce-149">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="395ce-150">Véalo a continuación.</span><span class="sxs-lookup"><span data-stu-id="395ce-150">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="395ce-151">Actualizar una sola DL</span><span class="sxs-lookup"><span data-stu-id="395ce-151">Upgrade a single DL</span></span>

<span data-ttu-id="395ce-152">Para actualizar una sola DL, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="395ce-152">To upgrade a single DL, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

<span data-ttu-id="395ce-153">Por ejemplo, si desea actualizar un archivo DL con una dirección SMTP dl1@contoso.com, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="395ce-153">For example, if you want to upgrade a DL with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> <span data-ttu-id="395ce-154">También puede actualizar una lista de distribución única a un grupo Microsoft 365 con el cmdlet de PowerShell [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup)</span><span class="sxs-lookup"><span data-stu-id="395ce-154">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="395ce-155">Actualizar varias direcciones URL en un lote</span><span class="sxs-lookup"><span data-stu-id="395ce-155">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="395ce-156">También puede pasar varias direcciones URL como un lote y actualizarlas juntas:</span><span class="sxs-lookup"><span data-stu-id="395ce-156">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

<span data-ttu-id="395ce-157">Por ejemplo, si desea actualizar cinco direcciones URL con dirección SMTP y `dl1@contoso.com` , y , ejecute el siguiente `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` comando:</span><span class="sxs-lookup"><span data-stu-id="395ce-157">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="395ce-158">Actualizar todas las DLs elegibles</span><span class="sxs-lookup"><span data-stu-id="395ce-158">Upgrade all eligible DLs</span></span>

<span data-ttu-id="395ce-159">Hay dos formas de actualizar todas las direcciones URL elegibles.</span><span class="sxs-lookup"><span data-stu-id="395ce-159">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="395ce-160">El cmdlet Upgrade-DistributionGroup no recibe datos de la canalización, por lo que es necesario usar el operador "foreach-object" para {} ejecutarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="395ce-160">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="395ce-161">Obtener las direcciones URL elegibles en el inquilino y actualizarlas mediante el comando de actualización:</span><span class="sxs-lookup"><span data-stu-id="395ce-161">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="395ce-162">Obtener la lista de todas las direcciones DLL y actualizar solo las direcciones URL elegibles:</span><span class="sxs-lookup"><span data-stu-id="395ce-162">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="395ce-163">Preguntas frecuentes sobre cómo actualizar listas de distribución Microsoft 365 grupos en Outlook</span><span class="sxs-lookup"><span data-stu-id="395ce-163">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="395ce-164">¿Qué listas de distribución no se pueden actualizar?</span><span class="sxs-lookup"><span data-stu-id="395ce-164">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="395ce-165">Solo puede actualizar listas de distribución sencillas y no anidadas administradas en la nube.</span><span class="sxs-lookup"><span data-stu-id="395ce-165">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="395ce-166">En la tabla siguiente se enumeran las listas de distribución **que no** se pueden actualizar.</span><span class="sxs-lookup"><span data-stu-id="395ce-166">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="395ce-167">**Property**</span><span class="sxs-lookup"><span data-stu-id="395ce-167">**Property**</span></span>|<span data-ttu-id="395ce-168">**¿Elegible?**</span><span class="sxs-lookup"><span data-stu-id="395ce-168">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="395ce-169">Lista de distribución administrada local.</span><span class="sxs-lookup"><span data-stu-id="395ce-169">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="395ce-170">No</span><span class="sxs-lookup"><span data-stu-id="395ce-170">No</span></span>  <br/> |
|<span data-ttu-id="395ce-171">Listas de distribución anidadas.</span><span class="sxs-lookup"><span data-stu-id="395ce-171">Nested distribution lists.</span></span> <span data-ttu-id="395ce-172">La lista de distribución tiene grupos secundarios o es miembro de otro grupo.</span><span class="sxs-lookup"><span data-stu-id="395ce-172">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="395ce-173">No</span><span class="sxs-lookup"><span data-stu-id="395ce-173">No</span></span>  <br/> |
|<span data-ttu-id="395ce-174">Listas de distribución con **miembros RecipientTypeDetails distintos** de **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="395ce-174">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="395ce-175">No</span><span class="sxs-lookup"><span data-stu-id="395ce-175">No</span></span>  <br/> |
|<span data-ttu-id="395ce-176">Lista de distribución con más de 100 propietarios</span><span class="sxs-lookup"><span data-stu-id="395ce-176">Distribution list that has more than 100 owners</span></span>  <br/> |<span data-ttu-id="395ce-177">No</span><span class="sxs-lookup"><span data-stu-id="395ce-177">No</span></span>  <br/> |
|<span data-ttu-id="395ce-178">Lista de distribución que solo tiene miembros pero ningún propietario</span><span class="sxs-lookup"><span data-stu-id="395ce-178">Distribution list that only has members but no owner</span></span>  <br/> |<span data-ttu-id="395ce-179">No</span><span class="sxs-lookup"><span data-stu-id="395ce-179">No</span></span>  <br/> |
|<span data-ttu-id="395ce-180">Lista de distribución con alias que contiene caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="395ce-180">Distribution list that has alias containing special characters</span></span>  <br/> |<span data-ttu-id="395ce-181">No</span><span class="sxs-lookup"><span data-stu-id="395ce-181">No</span></span>  <br/> |
|<span data-ttu-id="395ce-182">Si la lista de distribución está configurada para ser una dirección de reenvío para buzón compartido</span><span class="sxs-lookup"><span data-stu-id="395ce-182">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="395ce-183">No</span><span class="sxs-lookup"><span data-stu-id="395ce-183">No</span></span>  <br/> |
|<span data-ttu-id="395ce-184">Si dl forma parte de la **restricción del remitente** en otro DL.</span><span class="sxs-lookup"><span data-stu-id="395ce-184">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="395ce-185">No</span><span class="sxs-lookup"><span data-stu-id="395ce-185">No</span></span>  <br/> |
|<span data-ttu-id="395ce-186">Grupos de seguridad</span><span class="sxs-lookup"><span data-stu-id="395ce-186">Security groups</span></span>  <br/> |<span data-ttu-id="395ce-187">No</span><span class="sxs-lookup"><span data-stu-id="395ce-187">No</span></span>  <br/> |
|<span data-ttu-id="395ce-188">Listas de distribución dinámica</span><span class="sxs-lookup"><span data-stu-id="395ce-188">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="395ce-189">No</span><span class="sxs-lookup"><span data-stu-id="395ce-189">No</span></span>  <br/> |
|<span data-ttu-id="395ce-190">Listas de distribución que se convirtieron en **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="395ce-190">Distribution lists that were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="395ce-191">No</span><span class="sxs-lookup"><span data-stu-id="395ce-191">No</span></span>  <br/> |
|<span data-ttu-id="395ce-192">Listas de distribución **donde MemberJoinRestriction** y/o **MemberDepartRestriction** está **Cerrado**</span><span class="sxs-lookup"><span data-stu-id="395ce-192">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="395ce-193">No</span><span class="sxs-lookup"><span data-stu-id="395ce-193">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="395ce-194">Comprobar qué direcciones URL son aptas para la actualización</span><span class="sxs-lookup"><span data-stu-id="395ce-194">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="395ce-195">Si desea comprobar si un archivo DL es apto o no, puede ejecutar el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="395ce-195">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="395ce-196">Si desea comprobar qué direcciones DLL son aptas para la actualización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="395ce-196">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="395ce-197">Quién Puede ejecutar los scripts de actualización?</span><span class="sxs-lookup"><span data-stu-id="395ce-197">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="395ce-198">Personas con derechos de administrador global Exchange administrador.</span><span class="sxs-lookup"><span data-stu-id="395ce-198">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="395ce-199">¿Por qué la tarjeta de contacto sigue mostrando una lista de distribución?</span><span class="sxs-lookup"><span data-stu-id="395ce-199">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="395ce-200">¿Qué debo hacer para evitar que una lista de distribución actualizada se muestre en mi lista de sugerencias automáticas?</span><span class="sxs-lookup"><span data-stu-id="395ce-200">What should I do to prevent an upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="395ce-201">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span><span class="sxs-lookup"><span data-stu-id="395ce-201">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="395ce-202">La tarjeta de contacto del destinatario será la tarjeta de contacto de listas de distribución.</span><span class="sxs-lookup"><span data-stu-id="395ce-202">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="395ce-203">Esto se debe a la caché de destinatarios o a la caché de nombres de nick en Outlook.</span><span class="sxs-lookup"><span data-stu-id="395ce-203">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="395ce-204">El correo electrónico se enviará correctamente al grupo, pero puede causar confusión al remitente.</span><span class="sxs-lookup"><span data-stu-id="395ce-204">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="395ce-205">Puede realizar los pasos de este artículo, Información sobre la lista Outlook [Autocompletar](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) para restablecer la memoria caché, lo que solucionará este problema.</span><span class="sxs-lookup"><span data-stu-id="395ce-205">You can perform the steps in this article, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="395ce-206">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span><span class="sxs-lookup"><span data-stu-id="395ce-206">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="395ce-207">Puede seguir los pasos descritos en [Quitar](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) el nombre sugerido o la dirección de correo electrónico de la lista de autocompletar para actualizar la memoria caché para ver la tarjeta de contacto del grupo.</span><span class="sxs-lookup"><span data-stu-id="395ce-207">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="395ce-208">¿Los nuevos miembros del grupo reciben un correo electrónico de bienvenida en su bandeja de entrada?</span><span class="sxs-lookup"><span data-stu-id="395ce-208">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="395ce-209">No.</span><span class="sxs-lookup"><span data-stu-id="395ce-209">No.</span></span> <span data-ttu-id="395ce-210">La configuración para habilitar los mensajes de bienvenida se establece en false de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="395ce-210">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="395ce-211">Esta configuración afecta tanto a los miembros de grupo existentes como a los nuevos que pueden unirse una vez completada la migración.</span><span class="sxs-lookup"><span data-stu-id="395ce-211">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="395ce-212">Si el propietario del grupo permite más adelante a los usuarios invitados, los usuarios invitados no recibirán un correo electrónico de bienvenida en su bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="395ce-212">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="395ce-213">Los miembros invitados pueden seguir trabajando con el grupo.</span><span class="sxs-lookup"><span data-stu-id="395ce-213">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="395ce-214">¿Qué ocurre si uno o algunos de los DLs no se actualizan?</span><span class="sxs-lookup"><span data-stu-id="395ce-214">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="395ce-215">Hay algunos casos en los que, aunque DL es apto pero no se pudo actualizar.</span><span class="sxs-lookup"><span data-stu-id="395ce-215">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="395ce-216">La DL no se actualiza y permanece como un ARCHIVO DL.</span><span class="sxs-lookup"><span data-stu-id="395ce-216">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="395ce-217">Cuando el administrador **ha** aplicado la directiva de direcciones de correo electrónico de grupo para los grupos de una organización y tratan de actualizar direcciones DLL que no cumplen los criterios, la DL no se actualiza</span><span class="sxs-lookup"><span data-stu-id="395ce-217">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs that doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="395ce-218">Las DLs **con MemberJoinRestriction** o **MemberDepartRestriction** establecidas en **Closed**, no se pudieron actualizar</span><span class="sxs-lookup"><span data-stu-id="395ce-218">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="395ce-219">¿Qué sucede con la DL si se produce un error en la actualización desde EAC?</span><span class="sxs-lookup"><span data-stu-id="395ce-219">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="395ce-220">La actualización solo se realizará cuando se envía la llamada al servidor.</span><span class="sxs-lookup"><span data-stu-id="395ce-220">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="395ce-221">Si se produce un error en la actualización, las direcciones DLL estarán intactas.</span><span class="sxs-lookup"><span data-stu-id="395ce-221">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="395ce-222">Funcionarán como antes.</span><span class="sxs-lookup"><span data-stu-id="395ce-222">They will work like they used to.</span></span>

## <a name="related-content"></a><span data-ttu-id="395ce-223">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="395ce-223">Related content</span></span>

<span data-ttu-id="395ce-224">[Comparar grupos](../create-groups/compare-groups.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="395ce-224">[Compare groups](../create-groups/compare-groups.md) (article)</span></span>\
<span data-ttu-id="395ce-225">[Explicar los Microsoft 365 a los usuarios](../create-groups/explain-groups-knowledge-worker.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="395ce-225">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
[<span data-ttu-id="395ce-226">Agregar o quitar miembros de Microsoft 365 grupos mediante el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="395ce-226">Add or remove members from Microsoft 365 groups using the admin center</span></span>](../create-groups/add-or-remove-members-from-groups.md)
