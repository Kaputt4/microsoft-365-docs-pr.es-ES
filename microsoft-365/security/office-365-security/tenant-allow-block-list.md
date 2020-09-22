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
ms.openlocfilehash: eb9dcc5b239aae1366a0a2e0eebd68b3f0082e6b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202344"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="51196-103">Administrar direcciones URL en la lista de permitidos y bloqueados del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="51196-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="51196-104">Las características descritas en este tema están en versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="51196-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="51196-105">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="51196-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="51196-106">Por ejemplo, un buen mensaje puede marcarse como incorrecto (un falso positivo) o puede que se permita el acceso a un mensaje incorrecto (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="51196-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="51196-107">La lista de permitidos y bloqueados del centro de cumplimiento de & de seguridad ofrece una forma de reemplazar manualmente los veredictos de filtrado de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="51196-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="51196-108">La lista de permitidos/bloqueados del inquilino se usa durante el flujo de correo y en el momento en que el usuario hace clic.</span><span class="sxs-lookup"><span data-stu-id="51196-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="51196-109">Puede especificar las direcciones URL que desea permitir o bloquear en la lista de permitidos/bloqueados del inquilino.</span><span class="sxs-lookup"><span data-stu-id="51196-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="51196-110">En este tema se describe cómo configurar entradas en la lista de permitidos/bloqueados del centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; PowerShell de EOP independiente para las organizaciones sin buzones de correo de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="51196-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="51196-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="51196-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="51196-112">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="51196-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="51196-113">Para ir directamente a la página de la **lista de permitidos/bloqueados de inquilino** , use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="51196-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="51196-114">Los valores de dirección URL disponibles se describen en la sintaxis de la [dirección URL de la sección lista de permitidos/bloqueados de inquilino](#url-syntax-for-the-tenant-allowblock-list) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="51196-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="51196-115">La lista de permitidos/bloqueados de inquilino permite un máximo de 500 entradas para las direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="51196-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="51196-116">Una entrada debe estar activa en 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="51196-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="51196-117">Las entradas de bloque tienen prioridad sobre las entradas de permitir.</span><span class="sxs-lookup"><span data-stu-id="51196-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="51196-118">De forma predeterminada, las entradas de la lista de permitidos y bloqueados de inquilino expirarán transcurridos 30 días.</span><span class="sxs-lookup"><span data-stu-id="51196-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="51196-119">Puede especificar una fecha o configurarlas para que no expiren nunca.</span><span class="sxs-lookup"><span data-stu-id="51196-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="51196-120">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="51196-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="51196-121">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="51196-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="51196-122">Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:</span><span class="sxs-lookup"><span data-stu-id="51196-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="51196-123">Para agregar y quitar valores de la lista de permitidos/bloqueados de inquilino, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="51196-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="51196-124">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="51196-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="51196-125">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="51196-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="51196-126">Para obtener acceso de solo lectura a la lista de permitidos/bloqueados del inquilino, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="51196-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="51196-127">**Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="51196-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="51196-128">**Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="51196-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="51196-129">Usar el centro de seguridad & cumplimiento para crear entradas de dirección URL en la lista de permitidos/bloqueados de espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="51196-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="51196-130">Para obtener información detallada sobre la sintaxis de las entradas de dirección URL, vea la [Sintaxis de la dirección URL de la sección lista de permitidos/bloqueados de inquilino](#url-syntax-for-the-tenant-allowblock-list) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="51196-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="51196-131">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="51196-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="51196-132">En la página **lista de permitidos/bloqueados del inquilino** , compruebe que la ficha **direcciones URL** está seleccionada y, a continuación, haga clic en **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="51196-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="51196-133">En el control flotante **Agregar nuevas direcciones URL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="51196-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="51196-134">**Agregar direcciones URL con caracteres comodín**: escriba una dirección URL por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="51196-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="51196-135">**Bloquear o permitir**: Seleccione si desea **permitir** o **bloquear** las direcciones URL especificadas.</span><span class="sxs-lookup"><span data-stu-id="51196-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="51196-136">No **expira nunca**: siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51196-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="51196-137">Compruebe que la opción está desactivada (desactivar ![ ](../../media/scc-toggle-off.png) ) y use el cuadro **expira en** para especificar la fecha de caducidad de las entradas.</span><span class="sxs-lookup"><span data-stu-id="51196-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="51196-138">o</span><span class="sxs-lookup"><span data-stu-id="51196-138">or</span></span>

     - <span data-ttu-id="51196-139">Mueva el botón de alternancia a la derecha para configurar las entradas para que no expiren nunca:</span><span class="sxs-lookup"><span data-stu-id="51196-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="51196-141">.</span><span class="sxs-lookup"><span data-stu-id="51196-141">.</span></span>

   - <span data-ttu-id="51196-142">**Opcional Nota**: escriba un texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="51196-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="51196-143">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="51196-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="51196-144">Usar el centro de seguridad & cumplimiento para ver las entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="51196-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="51196-145">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="51196-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="51196-146">Seleccione la ficha **direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="51196-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="51196-147">Haga clic en los siguientes encabezados de columna para ordenar en orden ascendente o descendente:</span><span class="sxs-lookup"><span data-stu-id="51196-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="51196-148">**Valor**</span><span class="sxs-lookup"><span data-stu-id="51196-148">**Value**</span></span>
- <span data-ttu-id="51196-149">**Acción**: **bloquear** o **permitir**.</span><span class="sxs-lookup"><span data-stu-id="51196-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="51196-150">**Fecha de la última actualización**</span><span class="sxs-lookup"><span data-stu-id="51196-150">**Last updated date**</span></span>
- <span data-ttu-id="51196-151">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="51196-151">**Expiration date**</span></span>
- <span data-ttu-id="51196-152">**Nota**</span><span class="sxs-lookup"><span data-stu-id="51196-152">**Note**</span></span>

<span data-ttu-id="51196-153">Haga clic en **agrupar** para agrupar las entradas por **acción** (**bloquear** o **permitir**) o en **ninguna**.</span><span class="sxs-lookup"><span data-stu-id="51196-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="51196-154">Haga clic en **Buscar**, escriba todo o parte de un valor y, a continuación, presione Entrar para buscar un valor específico.</span><span class="sxs-lookup"><span data-stu-id="51196-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="51196-155">Cuando haya terminado, haga clic en **Clear Search** ![ Clear Search Icon ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="51196-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="51196-156">Haga clic en **filtro**.</span><span class="sxs-lookup"><span data-stu-id="51196-156">Click **Filter**.</span></span> <span data-ttu-id="51196-157">En el control flotante de **filtro** que aparece, configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="51196-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="51196-158">**Acción**: seleccione **permitir**, **bloquear** o ambos.</span><span class="sxs-lookup"><span data-stu-id="51196-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="51196-159">**Nunca expire**: seleccione Desactivado (desactivado ![ ](../../media/scc-toggle-off.png) ) o activado ( ![ alternar en ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="51196-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="51196-160">**Última actualización**: Seleccione una fecha de inicio (desde), una fecha**de**finalización (**hasta**) o ambas.</span><span class="sxs-lookup"><span data-stu-id="51196-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="51196-161">**Fecha de expiración**: Seleccione una fecha**de**Inicio (desde), una fecha de finalización (**hasta**) o ambas.</span><span class="sxs-lookup"><span data-stu-id="51196-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="51196-162">Cuando haya terminado, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="51196-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="51196-163">Para borrar los filtros existentes, haga clic en **filtrar**y, en el control flotante de **filtro** que aparece, haga clic en **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="51196-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="51196-164">Usar el centro de seguridad & cumplimiento para modificar las entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="51196-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="51196-165">El valor de la dirección URL no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="51196-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="51196-166">En su lugar, debe eliminar la entrada y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="51196-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="51196-167">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="51196-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="51196-168">Seleccione la ficha **direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="51196-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="51196-169">Seleccione la entrada que desea modificar y, a continuación, haga clic en **Editar** ![ icono Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="51196-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="51196-170">En el control flotante que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="51196-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="51196-171">**Bloquear o permitir**: seleccione **permitir** o **bloquear**.</span><span class="sxs-lookup"><span data-stu-id="51196-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="51196-172">No **expira nunca**: siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="51196-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="51196-173">Compruebe que la opción está desactivada (desactivar ![ ](../../media/scc-toggle-off.png) ) y use el cuadro **expira en** para especificar la fecha de caducidad de la entrada.</span><span class="sxs-lookup"><span data-stu-id="51196-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="51196-174">o</span><span class="sxs-lookup"><span data-stu-id="51196-174">or</span></span>

     - <span data-ttu-id="51196-175">Mueva el botón de alternancia a la derecha para configurar que la entrada nunca expire:</span><span class="sxs-lookup"><span data-stu-id="51196-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="51196-177">.</span><span class="sxs-lookup"><span data-stu-id="51196-177">.</span></span>

   - <span data-ttu-id="51196-178">**Opcional Nota**: escriba un texto descriptivo para la entrada.</span><span class="sxs-lookup"><span data-stu-id="51196-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="51196-179">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51196-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="51196-180">Usar el centro de seguridad & cumplimiento para quitar entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="51196-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="51196-181">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="51196-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="51196-182">Seleccione la ficha **direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="51196-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="51196-183">Seleccione la entrada que desee quitar y, a continuación, haga clic en **eliminar** ![ icono de eliminación ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="51196-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="51196-184">En el cuadro de diálogo de advertencia que aparece, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="51196-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="51196-185">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="51196-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="51196-186">Usar PowerShell para agregar entradas en la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="51196-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="51196-187">Para agregar entradas a la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="51196-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="51196-188">En este ejemplo se agrega una entrada de bloque de dirección URL para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="51196-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="51196-189">Como no se usaron los parámetros ExpirationDate o noexpiration, la entrada expira después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="51196-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="51196-190">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="51196-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="51196-191">Usar PowerShell para ver las entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="51196-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="51196-192">Para ver las entradas de la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="51196-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="51196-193">En este ejemplo se devuelven todas las direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="51196-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="51196-194">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="51196-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="51196-195">Usar PowerShell para modificar entradas en la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="51196-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="51196-196">El valor de la dirección URL no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="51196-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="51196-197">En su lugar, debe eliminar la entrada y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="51196-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="51196-198">Para modificar las entradas de la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="51196-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="51196-199">En este ejemplo se cambia la fecha de caducidad de la entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="51196-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="51196-200">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="51196-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="51196-201">Usar PowerShell para quitar entradas de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="51196-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="51196-202">Para quitar entradas de la lista de permitidos/bloqueados de inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="51196-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="51196-203">En este ejemplo se quita la entrada de la dirección URL especificada de la lista de permitidos/bloqueados del inquilino.</span><span class="sxs-lookup"><span data-stu-id="51196-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="51196-204">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="51196-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="51196-205">Sintaxis de dirección URL para la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="51196-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="51196-206">Se permiten las direcciones IP4v e IPv6, pero los puertos TCP/UDP no.</span><span class="sxs-lookup"><span data-stu-id="51196-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="51196-207">No se permiten las extensiones de nombre de archivo (por ejemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="51196-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="51196-208">No se admite Unicode, pero Punycode es.</span><span class="sxs-lookup"><span data-stu-id="51196-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="51196-209">Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="51196-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="51196-210">El nombre de host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="51196-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="51196-211">Hay al menos un carácter a la izquierda del punto.</span><span class="sxs-lookup"><span data-stu-id="51196-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="51196-212">Hay al menos dos caracteres a la derecha del punto.</span><span class="sxs-lookup"><span data-stu-id="51196-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="51196-213">Por ejemplo, `t.co` está permitido; `.com` o `contoso.` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="51196-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="51196-214">Los subtrazados no son implícitos.</span><span class="sxs-lookup"><span data-stu-id="51196-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="51196-215">Por ejemplo, `contoso.com` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="51196-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="51196-216">Los caracteres comodín (\*) están permitidos en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="51196-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="51196-217">Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.</span><span class="sxs-lookup"><span data-stu-id="51196-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="51196-218">Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="51196-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="51196-219">Un comodín derecho debe ir seguido de una barra diagonal (/) para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="51196-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="51196-220">Por ejemplo, `contoso.com/*` está permitido; `contoso.com*` o `contoso.com/ab*` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="51196-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="51196-221">Un comodín derecho no implica todos los subtrazados.</span><span class="sxs-lookup"><span data-stu-id="51196-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="51196-222">Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="51196-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="51196-223">`*.com*` no es válido (no es un dominio que se pueda resolver y el comodín derecho no sigue una barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="51196-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="51196-224">No se permiten caracteres comodín en direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="51196-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="51196-225">El carácter tilde (~) está disponible en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="51196-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="51196-226">Una tilde izquierda implica un dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="51196-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="51196-227">Por ejemplo `~contoso.com` `contoso.com` , incluye y `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="51196-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="51196-228">Las entradas de dirección URL que contienen protocolos (por ejemplo,, `http://` `https://` o) producirán `ftp://` un error porque las entradas de dirección URL se aplican a todos los protocolos.</span><span class="sxs-lookup"><span data-stu-id="51196-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="51196-229">No se admite ni es necesario un nombre de usuario ni una contraseña.</span><span class="sxs-lookup"><span data-stu-id="51196-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="51196-230">Las comillas (' o ") son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="51196-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="51196-231">Una dirección URL debe incluir todas las redirecciones siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="51196-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="51196-232">Escenarios de entrada de direcciones URL</span><span class="sxs-lookup"><span data-stu-id="51196-232">URL entry scenarios</span></span>

<span data-ttu-id="51196-233">En las siguientes secciones se describen las entradas de dirección URL válidas y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="51196-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="51196-234">Escenario: sin caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="51196-234">Scenario: No wildcards</span></span>

<span data-ttu-id="51196-235">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="51196-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="51196-236">**Permitir coincidencia**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="51196-237">**Permitir sin coincidencia**:</span><span class="sxs-lookup"><span data-stu-id="51196-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="51196-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-238">abc-contoso.com</span></span>
  - <span data-ttu-id="51196-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="51196-239">contoso.com/a</span></span>
  - <span data-ttu-id="51196-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="51196-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="51196-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="51196-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-243">www.contoso.com</span></span>
  - <span data-ttu-id="51196-244">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="51196-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="51196-245">**Coincidencia de bloque**:</span><span class="sxs-lookup"><span data-stu-id="51196-245">**Block match**:</span></span>

  - <span data-ttu-id="51196-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-246">contoso.com</span></span>
  - <span data-ttu-id="51196-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="51196-247">contoso.com/a</span></span>
  - <span data-ttu-id="51196-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="51196-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="51196-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="51196-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-251">www.contoso.com</span></span>
  - <span data-ttu-id="51196-252">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="51196-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="51196-253">**Bloque no coincidente**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="51196-254">Escenario: comodín izquierdo (subdominio)</span><span class="sxs-lookup"><span data-stu-id="51196-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="51196-255">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="51196-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="51196-256">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="51196-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="51196-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-257">www.contoso.com</span></span>
  - <span data-ttu-id="51196-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="51196-259">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="51196-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="51196-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-260">123contoso.com</span></span>
  - <span data-ttu-id="51196-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-261">contoso.com</span></span>
  - <span data-ttu-id="51196-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="51196-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="51196-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="51196-264">Escenario: comodín derecho en la parte superior de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="51196-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="51196-265">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="51196-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="51196-266">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="51196-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="51196-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="51196-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="51196-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="51196-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="51196-269">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="51196-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="51196-270">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="51196-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="51196-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-271">contoso.com</span></span>
  - <span data-ttu-id="51196-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="51196-272">contoso.com/a</span></span>
  - <span data-ttu-id="51196-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-273">www.contoso.com</span></span>
  - <span data-ttu-id="51196-274">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="51196-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="51196-275">Escenario: tilde izquierda</span><span class="sxs-lookup"><span data-stu-id="51196-275">Scenario: Left tilde</span></span>

<span data-ttu-id="51196-276">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="51196-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="51196-277">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="51196-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="51196-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-278">contoso.com</span></span>
  - <span data-ttu-id="51196-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-279">www.contoso.com</span></span>
  - <span data-ttu-id="51196-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="51196-281">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="51196-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="51196-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-282">123contoso.com</span></span>
  - <span data-ttu-id="51196-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="51196-283">contoso.com/abc</span></span>
  - <span data-ttu-id="51196-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="51196-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="51196-285">Escenario: sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="51196-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="51196-286">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="51196-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="51196-287">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="51196-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="51196-288">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="51196-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="51196-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="51196-289">contoso.com/a</span></span>
  - <span data-ttu-id="51196-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="51196-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="51196-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="51196-291">contoso.com/ab</span></span>
  - <span data-ttu-id="51196-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="51196-292">contoso.com/b</span></span>
  - <span data-ttu-id="51196-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="51196-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="51196-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="51196-294">contoso.com/ba</span></span>

- <span data-ttu-id="51196-295">**Permitir no coincidentes** y **no coincidentes**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="51196-296">Escenario: subdominio comodín izquierdo y sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="51196-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="51196-297">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="51196-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="51196-298">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="51196-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="51196-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="51196-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="51196-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="51196-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="51196-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="51196-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="51196-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="51196-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="51196-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="51196-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="51196-304">**Permitir no coincidentes** y **no coincidentes**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="51196-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="51196-305">Escenario: tilde izquierda y derecha</span><span class="sxs-lookup"><span data-stu-id="51196-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="51196-306">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="51196-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="51196-307">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="51196-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="51196-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-308">contoso.com</span></span>
  - <span data-ttu-id="51196-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="51196-309">contoso.com/a</span></span>
  - <span data-ttu-id="51196-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-310">www.contoso.com</span></span>
  - <span data-ttu-id="51196-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="51196-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="51196-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="51196-313">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="51196-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="51196-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-314">123contoso.com</span></span>
  - <span data-ttu-id="51196-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="51196-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="51196-316">Escenario: dirección IP</span><span class="sxs-lookup"><span data-stu-id="51196-316">Scenario: IP address</span></span>

<span data-ttu-id="51196-317">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="51196-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="51196-318">**Permitir** coincidencia de coincidencia y **bloqueo**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="51196-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="51196-319">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="51196-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="51196-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="51196-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="51196-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="51196-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="51196-322">Dirección IP con comodín derecho</span><span class="sxs-lookup"><span data-stu-id="51196-322">IP address with right wildcard</span></span>

<span data-ttu-id="51196-323">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="51196-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="51196-324">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="51196-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="51196-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="51196-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="51196-326">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="51196-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="51196-327">Ejemplos de entradas no válidas</span><span class="sxs-lookup"><span data-stu-id="51196-327">Examples of invalid entries</span></span>

<span data-ttu-id="51196-328">Las siguientes entradas no son válidas:</span><span class="sxs-lookup"><span data-stu-id="51196-328">The following entries are invalid:</span></span>

- <span data-ttu-id="51196-329">**Faltan valores de dominio o no son válidos**:</span><span class="sxs-lookup"><span data-stu-id="51196-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="51196-330">contoso</span><span class="sxs-lookup"><span data-stu-id="51196-330">contoso</span></span>
  - <span data-ttu-id="51196-331">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="51196-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="51196-332">\*. com</span><span class="sxs-lookup"><span data-stu-id="51196-332">\*.com</span></span>
  - <span data-ttu-id="51196-333">\*. pdf</span><span class="sxs-lookup"><span data-stu-id="51196-333">\*.pdf</span></span>

- <span data-ttu-id="51196-334">**Comodín en texto o sin caracteres de espaciado**:</span><span class="sxs-lookup"><span data-stu-id="51196-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="51196-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="51196-335">\*contoso.com</span></span>
  - <span data-ttu-id="51196-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="51196-336">contoso.com\*</span></span>
  - <span data-ttu-id="51196-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="51196-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="51196-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="51196-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="51196-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="51196-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="51196-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="51196-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="51196-341">**Direcciones IP con puertos**:</span><span class="sxs-lookup"><span data-stu-id="51196-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="51196-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="51196-342">contoso.com:443</span></span>
  - <span data-ttu-id="51196-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="51196-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="51196-344">**Caracteres comodín no descriptivos**:</span><span class="sxs-lookup"><span data-stu-id="51196-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="51196-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="51196-345">\*.\*</span></span>

- <span data-ttu-id="51196-346">**Caracteres comodín del segundo nombre**:</span><span class="sxs-lookup"><span data-stu-id="51196-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="51196-347">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="51196-347">conto\*so.com</span></span>
  - <span data-ttu-id="51196-348">conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="51196-348">conto~so.com</span></span>

- <span data-ttu-id="51196-349">**Caracteres comodín dobles**</span><span class="sxs-lookup"><span data-stu-id="51196-349">**Double wildcards**</span></span>

  - <span data-ttu-id="51196-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="51196-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="51196-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="51196-351">contoso.com/\*/\*</span></span>
