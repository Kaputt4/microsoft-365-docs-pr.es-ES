---
title: Administrar sus permitidos y bloques en la lista de inquilinos permitidos/bloqueados
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar los permisos y los bloques en la lista de inquilinos permitidos o bloqueados en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 960fbf26b610485fb46c935b04aedcc593b85752
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407255"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-103">Administrar la lista de permitidos o bloqueados del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="fef14-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fef14-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="fef14-104">**Applies to**</span></span>
- [<span data-ttu-id="fef14-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fef14-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fef14-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="fef14-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="fef14-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fef14-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="fef14-108">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="fef14-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="fef14-109">No puede configurar elementos **permitidos** en la lista de inquilinos permitidos o bloqueados en este momento.</span><span class="sxs-lookup"><span data-stu-id="fef14-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="fef14-110">En organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="fef14-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="fef14-111">Por ejemplo, un mensaje bueno puede marcarse como malo (un falso positivo) o un mensaje malo se puede permitir a través (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="fef14-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="fef14-112">La lista de inquilinos permitidos o bloqueados en el Centro de seguridad & cumplimiento le ofrece una forma de invalidar manualmente los veredictos de filtrado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fef14-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="fef14-113">La lista de inquilinos permitidos o bloqueados se usa durante el flujo de correo y en el momento de los clics del usuario.</span><span class="sxs-lookup"><span data-stu-id="fef14-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="fef14-114">Puede especificar direcciones URL o archivos para bloquearlos siempre.</span><span class="sxs-lookup"><span data-stu-id="fef14-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="fef14-115">En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="fef14-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fef14-116">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="fef14-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fef14-117">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="fef14-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fef14-118">Para ir directamente a la página **Lista de inquilinos permitidos o bloqueados,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="fef14-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="fef14-119">Los archivos se especifican mediante el valor hash SHA256 del archivo.</span><span class="sxs-lookup"><span data-stu-id="fef14-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="fef14-120">Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="fef14-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="fef14-121">Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="fef14-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="fef14-122">No se admiten valores de hash perceptual (pHash).</span><span class="sxs-lookup"><span data-stu-id="fef14-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="fef14-123">Los valores de dirección URL disponibles se describen en la sintaxis url de la sección Lista de [inquilinos permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="fef14-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="fef14-124">La lista de inquilinos permitidos o bloqueados permite un máximo de 500 entradas para direcciones URL y 500 entradas para hashes de archivo.</span><span class="sxs-lookup"><span data-stu-id="fef14-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="fef14-125">Una entrada debe estar activa en 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="fef14-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="fef14-126">De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="fef14-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="fef14-127">Puede especificar una fecha o establecerla para que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="fef14-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="fef14-128">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="fef14-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fef14-129">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="fef14-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fef14-130">Debe tener asignados permisos en **Exchange Online** para poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="fef14-130">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="fef14-131">Para agregar y quitar valores de la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="fef14-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="fef14-132">Para obtener acceso de solo lectura a la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="fef14-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="fef14-133">Para obtener más información, consulte los [permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="fef14-133">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="fef14-134">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="fef14-134">**Notes**:</span></span>

  - <span data-ttu-id="fef14-135">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos y permisos necesarios para _otras_ características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fef14-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="fef14-136">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fef14-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="fef14-137">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="fef14-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-138">Usar el Centro de seguridad & cumplimiento para crear entradas de dirección URL en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fef14-139">Para obtener más información acerca de la sintaxis de las entradas de dirección URL, vea la sintaxis de dirección URL de la sección Lista de [permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados del espacio empresarial más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="fef14-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="fef14-140">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="fef14-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fef14-141">En la **página Lista de inquilinos permitidos o** bloqueados, compruebe que la pestaña **Direcciones** URL está seleccionada y, a continuación, haga clic en **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="fef14-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="fef14-142">En el **menú desplegable Bloquear direcciones URL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fef14-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fef14-143">**Agregar direcciones URL para bloquear:** escriba una dirección URL por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="fef14-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="fef14-144">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="fef14-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="fef14-145">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="fef14-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="fef14-146">o</span><span class="sxs-lookup"><span data-stu-id="fef14-146">or</span></span>

     - <span data-ttu-id="fef14-147">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="fef14-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="fef14-149">.</span><span class="sxs-lookup"><span data-stu-id="fef14-149">.</span></span>

   - <span data-ttu-id="fef14-150">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="fef14-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="fef14-151">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fef14-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-152">Usar el Centro de & seguridad para crear entradas de archivo en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="fef14-153">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="fef14-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fef14-154">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la **pestaña** Archivos y, a continuación, haga clic en **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="fef14-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="fef14-155">En el menú desplegable **Agregar archivos** para bloquear que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fef14-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fef14-156">**Agregar hash de archivo:** escriba un valor hash SHA256 por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="fef14-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="fef14-157">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="fef14-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="fef14-158">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="fef14-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="fef14-159">o</span><span class="sxs-lookup"><span data-stu-id="fef14-159">or</span></span>

     - <span data-ttu-id="fef14-160">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="fef14-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="fef14-162">.</span><span class="sxs-lookup"><span data-stu-id="fef14-162">.</span></span>

   - <span data-ttu-id="fef14-163">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="fef14-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="fef14-164">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fef14-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-165">Usar el Centro de seguridad & cumplimiento para ver entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="fef14-166">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="fef14-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fef14-167">Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.</span><span class="sxs-lookup"><span data-stu-id="fef14-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="fef14-168">Haga clic en los siguientes encabezados de columna para ordenar en orden ascendente o descendente:</span><span class="sxs-lookup"><span data-stu-id="fef14-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="fef14-169">**Valor:** la dirección URL o el hash del archivo.</span><span class="sxs-lookup"><span data-stu-id="fef14-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="fef14-170">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="fef14-170">**Last updated date**</span></span>
- <span data-ttu-id="fef14-171">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="fef14-171">**Expiration date**</span></span>
- <span data-ttu-id="fef14-172">**Nota**</span><span class="sxs-lookup"><span data-stu-id="fef14-172">**Note**</span></span>

<span data-ttu-id="fef14-173">Haga **clic en** Buscar, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico.</span><span class="sxs-lookup"><span data-stu-id="fef14-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="fef14-174">Cuando haya terminado, haga clic en **Borrar búsqueda** Borrar icono ![ de ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fef14-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="fef14-175">Haga clic **en Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="fef14-175">Click **Filter**.</span></span> <span data-ttu-id="fef14-176">En el **menú** desplegable Filtro que aparece, configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fef14-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="fef14-177">**Never expire**: Select off: ![ Toggle off or ](../../media/scc-toggle-off.png) on: Toggle on ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="fef14-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="fef14-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="fef14-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="fef14-179">**Fecha de expiración:** seleccione una fecha de inicio (**From**), una fecha de finalización (**Para**) o ambas.</span><span class="sxs-lookup"><span data-stu-id="fef14-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="fef14-180">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="fef14-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="fef14-181">Para borrar los filtros existentes, haga clic **en Filtrar** y, en el **menú** desplegable Filtro que aparece, haga clic en **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="fef14-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-182">Usar el Centro de seguridad & cumplimiento para modificar entradas de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fef14-183">No puede modificar los valores de archivo o url bloqueados existentes dentro de una entrada.</span><span class="sxs-lookup"><span data-stu-id="fef14-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="fef14-184">Para modificar estos valores, debe eliminar y volver a crear la entrada.</span><span class="sxs-lookup"><span data-stu-id="fef14-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="fef14-185">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="fef14-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fef14-186">Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.</span><span class="sxs-lookup"><span data-stu-id="fef14-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="fef14-187">Seleccione la entrada de bloque que desea modificar y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="fef14-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="fef14-188">En el menú desplegable que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="fef14-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fef14-189">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="fef14-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="fef14-190">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de la entrada. </span><span class="sxs-lookup"><span data-stu-id="fef14-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="fef14-191">o</span><span class="sxs-lookup"><span data-stu-id="fef14-191">or</span></span>

     - <span data-ttu-id="fef14-192">Mueva el botón de alternancia a la derecha para configurar la entrada para que no expire nunca:</span><span class="sxs-lookup"><span data-stu-id="fef14-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="fef14-194">.</span><span class="sxs-lookup"><span data-stu-id="fef14-194">.</span></span>

   - <span data-ttu-id="fef14-195">**Nota opcional:** escriba texto descriptivo para la entrada.</span><span class="sxs-lookup"><span data-stu-id="fef14-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="fef14-196">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fef14-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-197">Usar el Centro de seguridad & cumplimiento para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="fef14-198">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="fef14-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="fef14-199">Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.</span><span class="sxs-lookup"><span data-stu-id="fef14-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="fef14-200">Seleccione la entrada de bloque que desea quitar y, a continuación, haga clic **en Eliminar** icono ![ Eliminar ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="fef14-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="fef14-201">En el cuadro de diálogo de advertencia que aparece, haga clic **en Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="fef14-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-202">Usar PowerShell de Exchange Online o PowerShell EOP independiente para configurar la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-203">Usar PowerShell para agregar entradas de bloque a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="fef14-204">Para agregar entradas de bloque en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="fef14-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="fef14-205">En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="fef14-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="fef14-206">Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="fef14-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="fef14-207">En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="fef14-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="fef14-208">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="fef14-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-209">Usar PowerShell para ver entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fef14-210">Para ver entradas en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="fef14-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="fef14-211">En este ejemplo se devuelven todas las direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="fef14-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="fef14-212">En este ejemplo se devuelve información sobre el valor hash de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="fef14-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="fef14-213">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="fef14-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-214">Usar PowerShell para modificar entradas de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="fef14-215">No puede modificar los valores de dirección URL o archivo existentes dentro de una entrada de bloque.</span><span class="sxs-lookup"><span data-stu-id="fef14-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="fef14-216">Para modificar estos valores, debe eliminar y volver a crear la entrada.</span><span class="sxs-lookup"><span data-stu-id="fef14-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="fef14-217">Para modificar las entradas de bloque en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="fef14-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="fef14-218">En este ejemplo se cambia la fecha de expiración de la entrada de bloque especificada.</span><span class="sxs-lookup"><span data-stu-id="fef14-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="fef14-219">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="fef14-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-220">Usar PowerShell para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="fef14-221">Para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="fef14-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="fef14-222">En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de inquilinos permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="fef14-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="fef14-223">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="fef14-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="fef14-224">Sintaxis de dirección URL para la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="fef14-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="fef14-225">Las direcciones IP4v e IPv6 están permitidas, pero los puertos TCP/UDP no.</span><span class="sxs-lookup"><span data-stu-id="fef14-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="fef14-226">No se permiten extensiones de nombre de archivo (por ejemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="fef14-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="fef14-227">Unicode no es compatible, pero Punycode lo es.</span><span class="sxs-lookup"><span data-stu-id="fef14-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="fef14-228">Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="fef14-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="fef14-229">El nombre de host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="fef14-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="fef14-230">Hay al menos un carácter a la izquierda del punto.</span><span class="sxs-lookup"><span data-stu-id="fef14-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="fef14-231">Hay al menos dos caracteres a la derecha del punto.</span><span class="sxs-lookup"><span data-stu-id="fef14-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="fef14-232">Por ejemplo, `t.co` se permite; `.com` o no `contoso.` se permite.</span><span class="sxs-lookup"><span data-stu-id="fef14-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="fef14-233">Las subpaths no están implícitas.</span><span class="sxs-lookup"><span data-stu-id="fef14-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="fef14-234">Por ejemplo, `contoso.com` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="fef14-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="fef14-235">Los caracteres comodín (\*) se permiten en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="fef14-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="fef14-236">Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.</span><span class="sxs-lookup"><span data-stu-id="fef14-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="fef14-237">Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="fef14-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="fef14-238">Un comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="fef14-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="fef14-239">Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o no `contoso.com/ab*` se permite.</span><span class="sxs-lookup"><span data-stu-id="fef14-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="fef14-240">Todas las subpaths no están implícitas por un comodín derecho.</span><span class="sxs-lookup"><span data-stu-id="fef14-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="fef14-241">Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="fef14-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="fef14-242">`*.com*` no es válido (no es un dominio resolvible y el comodín derecho no sigue una barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="fef14-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="fef14-243">Los caracteres comodín no están permitidos en las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="fef14-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="fef14-244">El carácter tilde (~) está disponible en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="fef14-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="fef14-245">Una tilde izquierda implica un dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="fef14-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="fef14-246">Por `~contoso.com` ejemplo, incluye `contoso.com` y `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="fef14-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="fef14-247">Se producirá un error en las entradas de dirección URL que contienen protocolos (por ejemplo, , o ) porque las entradas de dirección URL se `http://` aplican a todos los `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="fef14-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="fef14-248">No se admite ni se requiere un nombre de usuario o contraseña.</span><span class="sxs-lookup"><span data-stu-id="fef14-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="fef14-249">Las comillas (' o ") son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="fef14-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="fef14-250">Una dirección URL debe incluir todas las redirecciones siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="fef14-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="fef14-251">Escenarios de entrada de dirección URL</span><span class="sxs-lookup"><span data-stu-id="fef14-251">URL entry scenarios</span></span>

<span data-ttu-id="fef14-252">Las entradas de dirección URL válidas y sus resultados se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="fef14-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="fef14-253">Escenario: sin caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="fef14-253">Scenario: No wildcards</span></span>

<span data-ttu-id="fef14-254">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="fef14-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="fef14-255">**Permitir coincidencia**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="fef14-256">**Permitir que no coincida**:</span><span class="sxs-lookup"><span data-stu-id="fef14-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="fef14-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-257">abc-contoso.com</span></span>
  - <span data-ttu-id="fef14-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fef14-258">contoso.com/a</span></span>
  - <span data-ttu-id="fef14-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="fef14-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="fef14-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="fef14-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-262">www.contoso.com</span></span>
  - <span data-ttu-id="fef14-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="fef14-264">**Bloquear coincidencia**:</span><span class="sxs-lookup"><span data-stu-id="fef14-264">**Block match**:</span></span>

  - <span data-ttu-id="fef14-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-265">contoso.com</span></span>
  - <span data-ttu-id="fef14-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fef14-266">contoso.com/a</span></span>
  - <span data-ttu-id="fef14-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="fef14-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="fef14-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="fef14-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-270">www.contoso.com</span></span>
  - <span data-ttu-id="fef14-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="fef14-272">**Bloque no coincidente:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="fef14-273">Escenario: comodín izquierdo (subdominio)</span><span class="sxs-lookup"><span data-stu-id="fef14-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="fef14-274">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="fef14-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="fef14-275">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="fef14-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fef14-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-276">www.contoso.com</span></span>
  - <span data-ttu-id="fef14-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="fef14-278">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="fef14-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fef14-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-279">123contoso.com</span></span>
  - <span data-ttu-id="fef14-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-280">contoso.com</span></span>
  - <span data-ttu-id="fef14-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="fef14-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="fef14-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="fef14-283">Escenario: comodín derecho en la parte superior de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="fef14-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="fef14-284">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="fef14-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="fef14-285">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="fef14-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fef14-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="fef14-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="fef14-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="fef14-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="fef14-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="fef14-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="fef14-289">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="fef14-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fef14-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-290">contoso.com</span></span>
  - <span data-ttu-id="fef14-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fef14-291">contoso.com/a</span></span>
  - <span data-ttu-id="fef14-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-292">www.contoso.com</span></span>
  - <span data-ttu-id="fef14-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="fef14-294">Escenario: tilde izquierda</span><span class="sxs-lookup"><span data-stu-id="fef14-294">Scenario: Left tilde</span></span>

<span data-ttu-id="fef14-295">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="fef14-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="fef14-296">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="fef14-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fef14-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-297">contoso.com</span></span>
  - <span data-ttu-id="fef14-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-298">www.contoso.com</span></span>
  - <span data-ttu-id="fef14-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="fef14-300">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="fef14-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fef14-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-301">123contoso.com</span></span>
  - <span data-ttu-id="fef14-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="fef14-302">contoso.com/abc</span></span>
  - <span data-ttu-id="fef14-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="fef14-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="fef14-304">Escenario: sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="fef14-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="fef14-305">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="fef14-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="fef14-306">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="fef14-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fef14-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fef14-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="fef14-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fef14-308">contoso.com/a</span></span>
  - <span data-ttu-id="fef14-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="fef14-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="fef14-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="fef14-310">contoso.com/ab</span></span>
  - <span data-ttu-id="fef14-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="fef14-311">contoso.com/b</span></span>
  - <span data-ttu-id="fef14-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="fef14-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="fef14-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="fef14-313">contoso.com/ba</span></span>

- <span data-ttu-id="fef14-314">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="fef14-315">Escenario: subdominio comodín izquierdo y sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="fef14-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="fef14-316">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="fef14-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="fef14-317">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="fef14-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fef14-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="fef14-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="fef14-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="fef14-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="fef14-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fef14-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="fef14-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="fef14-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="fef14-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="fef14-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="fef14-323">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="fef14-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="fef14-324">Escenario: tilde izquierda y derecha</span><span class="sxs-lookup"><span data-stu-id="fef14-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="fef14-325">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="fef14-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="fef14-326">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="fef14-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fef14-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-327">contoso.com</span></span>
  - <span data-ttu-id="fef14-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="fef14-328">contoso.com/a</span></span>
  - <span data-ttu-id="fef14-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-329">www.contoso.com</span></span>
  - <span data-ttu-id="fef14-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="fef14-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="fef14-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="fef14-332">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="fef14-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fef14-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-333">123contoso.com</span></span>
  - <span data-ttu-id="fef14-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="fef14-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="fef14-335">Escenario: dirección IP</span><span class="sxs-lookup"><span data-stu-id="fef14-335">Scenario: IP address</span></span>

<span data-ttu-id="fef14-336">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="fef14-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="fef14-337">**Permitir coincidencia** y **Bloquear coincidencia**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="fef14-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="fef14-338">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="fef14-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="fef14-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="fef14-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="fef14-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="fef14-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="fef14-341">Dirección IP con comodín derecho</span><span class="sxs-lookup"><span data-stu-id="fef14-341">IP address with right wildcard</span></span>

<span data-ttu-id="fef14-342">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="fef14-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="fef14-343">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="fef14-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="fef14-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="fef14-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="fef14-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="fef14-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="fef14-346">Ejemplos de entradas no válidas</span><span class="sxs-lookup"><span data-stu-id="fef14-346">Examples of invalid entries</span></span>

<span data-ttu-id="fef14-347">Las siguientes entradas no son válidas:</span><span class="sxs-lookup"><span data-stu-id="fef14-347">The following entries are invalid:</span></span>

- <span data-ttu-id="fef14-348">**Faltan valores de dominio o no son válidos:**</span><span class="sxs-lookup"><span data-stu-id="fef14-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="fef14-349">contoso</span><span class="sxs-lookup"><span data-stu-id="fef14-349">contoso</span></span>
  - <span data-ttu-id="fef14-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="fef14-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="fef14-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="fef14-351">\*.com</span></span>
  - <span data-ttu-id="fef14-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="fef14-352">\*.pdf</span></span>

- <span data-ttu-id="fef14-353">**Comodín en el texto o sin caracteres de espaciado:**</span><span class="sxs-lookup"><span data-stu-id="fef14-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="fef14-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="fef14-354">\*contoso.com</span></span>
  - <span data-ttu-id="fef14-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="fef14-355">contoso.com\*</span></span>
  - <span data-ttu-id="fef14-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="fef14-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="fef14-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="fef14-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="fef14-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="fef14-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="fef14-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="fef14-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="fef14-360">**Direcciones IP con puertos**:</span><span class="sxs-lookup"><span data-stu-id="fef14-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="fef14-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="fef14-361">contoso.com:443</span></span>
  - <span data-ttu-id="fef14-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="fef14-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="fef14-363">**Caracteres comodín no descriptivos:**</span><span class="sxs-lookup"><span data-stu-id="fef14-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="fef14-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="fef14-364">\*.\*</span></span>

- <span data-ttu-id="fef14-365">**Caracteres comodín intermedios**:</span><span class="sxs-lookup"><span data-stu-id="fef14-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="fef14-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="fef14-366">conto\*so.com</span></span>
  - <span data-ttu-id="fef14-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="fef14-367">conto~so.com</span></span>

- <span data-ttu-id="fef14-368">**Caracteres comodín dobles**</span><span class="sxs-lookup"><span data-stu-id="fef14-368">**Double wildcards**</span></span>

  - <span data-ttu-id="fef14-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="fef14-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="fef14-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="fef14-370">contoso.com/\*/\*</span></span>
