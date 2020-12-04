---
title: Administrar las direcciones URL permitidas y bloqueadas en la lista de permitidos/bloqueados del inquilino
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar entradas de direcciones URL en la lista de permitidos y bloqueados del centro de seguridad & cumplimiento.
ms.openlocfilehash: 1aae54ffd6026a7fc131017a10f9676d96be9b69
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572651"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-103">Administrar direcciones URL en la lista de permitidos y bloqueados del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="f0706-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="f0706-104">Las características descritas en este tema están en versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="f0706-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="f0706-105">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="f0706-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="f0706-106">Por ejemplo, un buen mensaje puede marcarse como incorrecto (un falso positivo) o puede que se permita el acceso a un mensaje incorrecto (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="f0706-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="f0706-107">La lista de permitidos y bloqueados del centro de cumplimiento de & de seguridad ofrece una forma de reemplazar manualmente los veredictos de filtrado de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f0706-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="f0706-108">La lista de permitidos/bloqueados del inquilino se usa durante el flujo de correo y en el momento en que el usuario hace clic.</span><span class="sxs-lookup"><span data-stu-id="f0706-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="f0706-109">Puede especificar las direcciones URL que desea permitir o bloquear en la lista de permitidos/bloqueados del inquilino.</span><span class="sxs-lookup"><span data-stu-id="f0706-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="f0706-110">En este tema se describe cómo configurar entradas en la lista de permitidos/bloqueados del centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; PowerShell de EOP independiente para las organizaciones sin buzones de correo de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="f0706-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f0706-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="f0706-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f0706-112">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f0706-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f0706-113">Para ir directamente a la página de la **lista de permitidos/bloqueados de inquilino** , use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="f0706-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="f0706-114">Los valores de dirección URL disponibles se describen en la sintaxis de la [dirección URL de la sección lista de permitidos/bloqueados de inquilino](#url-syntax-for-the-tenant-allowblock-list) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="f0706-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="f0706-115">La lista de permitidos/bloqueados de inquilino permite un máximo de 500 entradas para las direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="f0706-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="f0706-116">Una entrada debe estar activa en 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="f0706-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="f0706-117">Las entradas de bloque tienen prioridad sobre las entradas de permitir.</span><span class="sxs-lookup"><span data-stu-id="f0706-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="f0706-118">De forma predeterminada, las entradas de la lista de permitidos y bloqueados de inquilino expirarán transcurridos 30 días.</span><span class="sxs-lookup"><span data-stu-id="f0706-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="f0706-119">Puede especificar una fecha o configurarlas para que no expiren nunca.</span><span class="sxs-lookup"><span data-stu-id="f0706-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="f0706-120">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f0706-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f0706-121">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f0706-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f0706-122">Debe tener asignados permisos en el centro de seguridad & cumplimiento antes de poder llevar a cabo los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="f0706-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f0706-123">Para agregar y quitar valores de la lista de permitidos/bloqueados de inquilino, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="f0706-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f0706-124">Para obtener acceso de solo lectura a la lista de permitidos/bloqueados de inquilino, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="f0706-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f0706-125">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f0706-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="f0706-126">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="f0706-126">**Notes**:</span></span>

  - <span data-ttu-id="f0706-127">La adición de usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0706-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f0706-128">Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="f0706-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="f0706-129">El grupo de roles administración de la **organización de solo vista** de [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="f0706-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-130">Usar el centro de seguridad & cumplimiento para crear entradas de dirección URL en la lista de permitidos/bloqueados de espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="f0706-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f0706-131">Para obtener información detallada sobre la sintaxis de las entradas de dirección URL, vea la [Sintaxis de la dirección URL de la sección lista de permitidos/bloqueados de inquilino](#url-syntax-for-the-tenant-allowblock-list) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="f0706-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="f0706-132">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="f0706-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f0706-133">En la página **lista de permitidos/bloqueados del inquilino** , compruebe que la ficha **direcciones URL** está seleccionada y, a continuación, haga clic en **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="f0706-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="f0706-134">En el control flotante **Agregar nuevas direcciones URL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f0706-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f0706-135">**Agregar direcciones URL con caracteres comodín**: escriba una dirección URL por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="f0706-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="f0706-136">**Bloquear o permitir**: Seleccione si desea **permitir** o **bloquear** las direcciones URL especificadas.</span><span class="sxs-lookup"><span data-stu-id="f0706-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="f0706-137">No **expira nunca**: siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f0706-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f0706-138">Compruebe que la opción está desactivada (desactivar ![ ](../../media/scc-toggle-off.png) ) y use el cuadro **expira en** para especificar la fecha de caducidad de las entradas.</span><span class="sxs-lookup"><span data-stu-id="f0706-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="f0706-139">o</span><span class="sxs-lookup"><span data-stu-id="f0706-139">or</span></span>

     - <span data-ttu-id="f0706-140">Mueva el botón de alternancia a la derecha para configurar las entradas para que no expiren nunca:</span><span class="sxs-lookup"><span data-stu-id="f0706-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f0706-142">.</span><span class="sxs-lookup"><span data-stu-id="f0706-142">.</span></span>

   - <span data-ttu-id="f0706-143">**Opcional Nota**: escriba un texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="f0706-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="f0706-144">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f0706-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-145">Usar el centro de seguridad & cumplimiento para ver las entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="f0706-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f0706-146">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="f0706-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f0706-147">Seleccione la ficha **direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="f0706-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="f0706-148">Haga clic en los siguientes encabezados de columna para ordenar en orden ascendente o descendente:</span><span class="sxs-lookup"><span data-stu-id="f0706-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="f0706-149">**Valor**</span><span class="sxs-lookup"><span data-stu-id="f0706-149">**Value**</span></span>
- <span data-ttu-id="f0706-150">**Acción**: **bloquear** o **permitir**.</span><span class="sxs-lookup"><span data-stu-id="f0706-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="f0706-151">**Fecha de la última actualización**</span><span class="sxs-lookup"><span data-stu-id="f0706-151">**Last updated date**</span></span>
- <span data-ttu-id="f0706-152">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="f0706-152">**Expiration date**</span></span>
- <span data-ttu-id="f0706-153">**Nota**</span><span class="sxs-lookup"><span data-stu-id="f0706-153">**Note**</span></span>

<span data-ttu-id="f0706-154">Haga clic en **agrupar** para agrupar las entradas por **acción** (**bloquear** o **permitir**) o en **ninguna**.</span><span class="sxs-lookup"><span data-stu-id="f0706-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="f0706-155">Haga clic en **Buscar**, escriba todo o parte de un valor y, a continuación, presione Entrar para buscar un valor específico.</span><span class="sxs-lookup"><span data-stu-id="f0706-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="f0706-156">Cuando haya terminado, haga clic en **Clear Search** ![ Clear Search Icon ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="f0706-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="f0706-157">Haga clic en **filtro**.</span><span class="sxs-lookup"><span data-stu-id="f0706-157">Click **Filter**.</span></span> <span data-ttu-id="f0706-158">En el control flotante de **filtro** que aparece, configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f0706-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="f0706-159">**Acción**: seleccione **permitir**, **bloquear** o ambos.</span><span class="sxs-lookup"><span data-stu-id="f0706-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="f0706-160">**Nunca expire**: seleccione Desactivado (desactivado ![ ](../../media/scc-toggle-off.png) ) o activado ( ![ alternar en ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="f0706-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="f0706-161">**Última actualización**: Seleccione una fecha de inicio (desde), una fecha **de** finalización (**hasta**) o ambas.</span><span class="sxs-lookup"><span data-stu-id="f0706-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="f0706-162">**Fecha de expiración**: Seleccione una fecha **de** Inicio (desde), una fecha de finalización (**hasta**) o ambas.</span><span class="sxs-lookup"><span data-stu-id="f0706-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="f0706-163">Cuando haya terminado, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f0706-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="f0706-164">Para borrar los filtros existentes, haga clic en **filtrar** y, en el control flotante de **filtro** que aparece, haga clic en **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="f0706-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-165">Usar el centro de seguridad & cumplimiento para modificar las entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="f0706-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f0706-166">El valor de la dirección URL no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="f0706-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="f0706-167">En su lugar, debe eliminar la entrada y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="f0706-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="f0706-168">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="f0706-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f0706-169">Seleccione la ficha **direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="f0706-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="f0706-170">Seleccione la entrada que desea modificar y, a continuación, haga clic en **Editar** ![ icono Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="f0706-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="f0706-171">En el control flotante que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f0706-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f0706-172">**Bloquear o permitir**: seleccione **permitir** o **bloquear**.</span><span class="sxs-lookup"><span data-stu-id="f0706-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="f0706-173">No **expira nunca**: siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f0706-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="f0706-174">Compruebe que la opción está desactivada (desactivar ![ ](../../media/scc-toggle-off.png) ) y use el cuadro **expira en** para especificar la fecha de caducidad de la entrada.</span><span class="sxs-lookup"><span data-stu-id="f0706-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="f0706-175">o</span><span class="sxs-lookup"><span data-stu-id="f0706-175">or</span></span>

     - <span data-ttu-id="f0706-176">Mueva el botón de alternancia a la derecha para configurar que la entrada nunca expire:</span><span class="sxs-lookup"><span data-stu-id="f0706-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="f0706-178">.</span><span class="sxs-lookup"><span data-stu-id="f0706-178">.</span></span>

   - <span data-ttu-id="f0706-179">**Opcional Nota**: escriba un texto descriptivo para la entrada.</span><span class="sxs-lookup"><span data-stu-id="f0706-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="f0706-180">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f0706-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-181">Usar el centro de seguridad & cumplimiento para quitar entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="f0706-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="f0706-182">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="f0706-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="f0706-183">Seleccione la ficha **direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="f0706-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="f0706-184">Seleccione la entrada que desee quitar y, a continuación, haga clic en **eliminar** ![ icono de eliminación ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="f0706-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="f0706-185">En el cuadro de diálogo de advertencia que aparece, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f0706-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-186">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="f0706-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-187">Usar PowerShell para agregar entradas en la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="f0706-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f0706-188">Para agregar entradas a la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f0706-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f0706-189">En este ejemplo se agrega una entrada de bloque de dirección URL para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f0706-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="f0706-190">Como no se usaron los parámetros ExpirationDate o noexpiration, la entrada expira después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="f0706-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="f0706-191">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f0706-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-192">Usar PowerShell para ver las entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="f0706-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f0706-193">Para ver las entradas de la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f0706-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="f0706-194">En este ejemplo se devuelven todas las direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="f0706-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="f0706-195">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f0706-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-196">Usar PowerShell para modificar entradas en la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="f0706-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="f0706-197">El valor de la dirección URL no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="f0706-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="f0706-198">En su lugar, debe eliminar la entrada y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="f0706-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="f0706-199">Para modificar las entradas de la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f0706-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="f0706-200">En este ejemplo se cambia la fecha de caducidad de la entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="f0706-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="f0706-201">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f0706-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-202">Usar PowerShell para quitar entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="f0706-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="f0706-203">Para quitar entradas de la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f0706-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="f0706-204">En este ejemplo se quita la entrada de la dirección URL especificada de la lista de permitidos/bloqueados del inquilino.</span><span class="sxs-lookup"><span data-stu-id="f0706-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="f0706-205">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="f0706-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="f0706-206">Sintaxis de dirección URL para la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="f0706-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="f0706-207">Se permiten las direcciones IP4v e IPv6, pero los puertos TCP/UDP no.</span><span class="sxs-lookup"><span data-stu-id="f0706-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="f0706-208">No se permiten las extensiones de nombre de archivo (por ejemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="f0706-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="f0706-209">No se admite Unicode, pero Punycode es.</span><span class="sxs-lookup"><span data-stu-id="f0706-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="f0706-210">Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="f0706-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="f0706-211">El nombre de host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="f0706-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="f0706-212">Hay al menos un carácter a la izquierda del punto.</span><span class="sxs-lookup"><span data-stu-id="f0706-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="f0706-213">Hay al menos dos caracteres a la derecha del punto.</span><span class="sxs-lookup"><span data-stu-id="f0706-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="f0706-214">Por ejemplo, `t.co` está permitido; `.com` o `contoso.` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="f0706-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="f0706-215">Los subtrazados no son implícitos.</span><span class="sxs-lookup"><span data-stu-id="f0706-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="f0706-216">Por ejemplo, `contoso.com` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f0706-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="f0706-217">Los caracteres comodín (\*) están permitidos en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="f0706-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="f0706-218">Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.</span><span class="sxs-lookup"><span data-stu-id="f0706-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="f0706-219">Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="f0706-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="f0706-220">Un comodín derecho debe ir seguido de una barra diagonal (/) para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f0706-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="f0706-221">Por ejemplo, `contoso.com/*` está permitido; `contoso.com*` o `contoso.com/ab*` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="f0706-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="f0706-222">Un comodín derecho no implica todos los subtrazados.</span><span class="sxs-lookup"><span data-stu-id="f0706-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="f0706-223">Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="f0706-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="f0706-224">`*.com*` no es válido (no es un dominio que se pueda resolver y el comodín derecho no sigue una barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="f0706-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="f0706-225">No se permiten caracteres comodín en direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="f0706-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="f0706-226">El carácter tilde (~) está disponible en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="f0706-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="f0706-227">Una tilde izquierda implica un dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="f0706-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="f0706-228">Por ejemplo `~contoso.com` `contoso.com` , incluye y `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="f0706-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="f0706-229">Las entradas de dirección URL que contienen protocolos (por ejemplo,, `http://` `https://` o) producirán `ftp://` un error porque las entradas de dirección URL se aplican a todos los protocolos.</span><span class="sxs-lookup"><span data-stu-id="f0706-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="f0706-230">No se admite ni es necesario un nombre de usuario ni una contraseña.</span><span class="sxs-lookup"><span data-stu-id="f0706-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="f0706-231">Las comillas (' o ") son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="f0706-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="f0706-232">Una dirección URL debe incluir todas las redirecciones siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="f0706-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="f0706-233">Escenarios de entrada de direcciones URL</span><span class="sxs-lookup"><span data-stu-id="f0706-233">URL entry scenarios</span></span>

<span data-ttu-id="f0706-234">En las siguientes secciones se describen las entradas de dirección URL válidas y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="f0706-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="f0706-235">Escenario: sin caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="f0706-235">Scenario: No wildcards</span></span>

<span data-ttu-id="f0706-236">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f0706-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="f0706-237">**Permitir coincidencia**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="f0706-238">**Permitir sin coincidencia**:</span><span class="sxs-lookup"><span data-stu-id="f0706-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="f0706-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-239">abc-contoso.com</span></span>
  - <span data-ttu-id="f0706-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f0706-240">contoso.com/a</span></span>
  - <span data-ttu-id="f0706-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="f0706-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="f0706-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f0706-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-244">www.contoso.com</span></span>
  - <span data-ttu-id="f0706-245">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="f0706-245">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="f0706-246">**Coincidencia de bloque**:</span><span class="sxs-lookup"><span data-stu-id="f0706-246">**Block match**:</span></span>

  - <span data-ttu-id="f0706-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-247">contoso.com</span></span>
  - <span data-ttu-id="f0706-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f0706-248">contoso.com/a</span></span>
  - <span data-ttu-id="f0706-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="f0706-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="f0706-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="f0706-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-252">www.contoso.com</span></span>
  - <span data-ttu-id="f0706-253">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="f0706-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="f0706-254">**Bloque no coincidente**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="f0706-255">Escenario: comodín izquierdo (subdominio)</span><span class="sxs-lookup"><span data-stu-id="f0706-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="f0706-256">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f0706-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="f0706-257">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="f0706-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f0706-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-258">www.contoso.com</span></span>
  - <span data-ttu-id="f0706-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f0706-260">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="f0706-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f0706-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-261">123contoso.com</span></span>
  - <span data-ttu-id="f0706-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-262">contoso.com</span></span>
  - <span data-ttu-id="f0706-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="f0706-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f0706-264">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="f0706-265">Escenario: comodín derecho en la parte superior de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="f0706-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="f0706-266">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="f0706-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="f0706-267">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="f0706-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f0706-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="f0706-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="f0706-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f0706-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f0706-270">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="f0706-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="f0706-271">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="f0706-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f0706-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-272">contoso.com</span></span>
  - <span data-ttu-id="f0706-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f0706-273">contoso.com/a</span></span>
  - <span data-ttu-id="f0706-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-274">www.contoso.com</span></span>
  - <span data-ttu-id="f0706-275">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="f0706-275">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="f0706-276">Escenario: tilde izquierda</span><span class="sxs-lookup"><span data-stu-id="f0706-276">Scenario: Left tilde</span></span>

<span data-ttu-id="f0706-277">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="f0706-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="f0706-278">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="f0706-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f0706-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-279">contoso.com</span></span>
  - <span data-ttu-id="f0706-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-280">www.contoso.com</span></span>
  - <span data-ttu-id="f0706-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f0706-282">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="f0706-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f0706-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-283">123contoso.com</span></span>
  - <span data-ttu-id="f0706-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f0706-284">contoso.com/abc</span></span>
  - <span data-ttu-id="f0706-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="f0706-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="f0706-286">Escenario: sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="f0706-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="f0706-287">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f0706-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="f0706-288">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="f0706-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f0706-289">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="f0706-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="f0706-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f0706-290">contoso.com/a</span></span>
  - <span data-ttu-id="f0706-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f0706-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f0706-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f0706-292">contoso.com/ab</span></span>
  - <span data-ttu-id="f0706-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f0706-293">contoso.com/b</span></span>
  - <span data-ttu-id="f0706-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f0706-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f0706-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f0706-295">contoso.com/ba</span></span>

- <span data-ttu-id="f0706-296">**Permitir no coincidentes** y **no coincidentes**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="f0706-297">Escenario: subdominio comodín izquierdo y sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="f0706-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="f0706-298">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="f0706-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="f0706-299">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="f0706-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f0706-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="f0706-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="f0706-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="f0706-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="f0706-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f0706-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="f0706-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="f0706-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="f0706-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="f0706-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="f0706-305">**Permitir no coincidentes** y **no coincidentes**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f0706-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="f0706-306">Escenario: tilde izquierda y derecha</span><span class="sxs-lookup"><span data-stu-id="f0706-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="f0706-307">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="f0706-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="f0706-308">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="f0706-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f0706-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-309">contoso.com</span></span>
  - <span data-ttu-id="f0706-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="f0706-310">contoso.com/a</span></span>
  - <span data-ttu-id="f0706-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-311">www.contoso.com</span></span>
  - <span data-ttu-id="f0706-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="f0706-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="f0706-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="f0706-314">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="f0706-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f0706-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-315">123contoso.com</span></span>
  - <span data-ttu-id="f0706-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="f0706-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="f0706-317">Escenario: dirección IP</span><span class="sxs-lookup"><span data-stu-id="f0706-317">Scenario: IP address</span></span>

<span data-ttu-id="f0706-318">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="f0706-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="f0706-319">**Permitir** coincidencia de coincidencia y **bloqueo**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f0706-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="f0706-320">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="f0706-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="f0706-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f0706-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="f0706-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="f0706-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="f0706-323">Dirección IP con comodín derecho</span><span class="sxs-lookup"><span data-stu-id="f0706-323">IP address with right wildcard</span></span>

<span data-ttu-id="f0706-324">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="f0706-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="f0706-325">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="f0706-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="f0706-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="f0706-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="f0706-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="f0706-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="f0706-328">Ejemplos de entradas no válidas</span><span class="sxs-lookup"><span data-stu-id="f0706-328">Examples of invalid entries</span></span>

<span data-ttu-id="f0706-329">Las siguientes entradas no son válidas:</span><span class="sxs-lookup"><span data-stu-id="f0706-329">The following entries are invalid:</span></span>

- <span data-ttu-id="f0706-330">**Faltan valores de dominio o no son válidos**:</span><span class="sxs-lookup"><span data-stu-id="f0706-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="f0706-331">contoso</span><span class="sxs-lookup"><span data-stu-id="f0706-331">contoso</span></span>
  - <span data-ttu-id="f0706-332">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="f0706-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="f0706-333">\*. com</span><span class="sxs-lookup"><span data-stu-id="f0706-333">\*.com</span></span>
  - <span data-ttu-id="f0706-334">\*. pdf</span><span class="sxs-lookup"><span data-stu-id="f0706-334">\*.pdf</span></span>

- <span data-ttu-id="f0706-335">**Comodín en texto o sin caracteres de espaciado**:</span><span class="sxs-lookup"><span data-stu-id="f0706-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="f0706-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="f0706-336">\*contoso.com</span></span>
  - <span data-ttu-id="f0706-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="f0706-337">contoso.com\*</span></span>
  - <span data-ttu-id="f0706-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="f0706-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="f0706-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="f0706-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="f0706-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="f0706-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="f0706-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="f0706-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="f0706-342">**Direcciones IP con puertos**:</span><span class="sxs-lookup"><span data-stu-id="f0706-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="f0706-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="f0706-343">contoso.com:443</span></span>
  - <span data-ttu-id="f0706-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="f0706-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="f0706-345">**Caracteres comodín no descriptivos**:</span><span class="sxs-lookup"><span data-stu-id="f0706-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="f0706-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="f0706-346">\*.\*</span></span>

- <span data-ttu-id="f0706-347">**Caracteres comodín del segundo nombre**:</span><span class="sxs-lookup"><span data-stu-id="f0706-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="f0706-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="f0706-348">conto\*so.com</span></span>
  - <span data-ttu-id="f0706-349">conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="f0706-349">conto~so.com</span></span>

- <span data-ttu-id="f0706-350">**Caracteres comodín dobles**</span><span class="sxs-lookup"><span data-stu-id="f0706-350">**Double wildcards**</span></span>

  - <span data-ttu-id="f0706-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="f0706-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="f0706-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="f0706-352">contoso.com/\*/\*</span></span>
