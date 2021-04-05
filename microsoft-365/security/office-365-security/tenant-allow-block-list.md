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
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587592"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-103">Administrar la lista de permitidos o bloqueados del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="8e213-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8e213-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="8e213-104">**Applies to**</span></span>
- [<span data-ttu-id="8e213-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8e213-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8e213-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8e213-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8e213-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e213-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="8e213-108">No puede configurar elementos **permitidos** en la lista de inquilinos permitidos o bloqueados en este momento.</span><span class="sxs-lookup"><span data-stu-id="8e213-108">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="8e213-109">En organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="8e213-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="8e213-110">Por ejemplo, un mensaje bueno puede marcarse como malo (un falso positivo) o un mensaje malo se puede permitir a través (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="8e213-110">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="8e213-111">La lista de inquilinos permitidos o bloqueados en el Centro de seguridad & cumplimiento le ofrece una forma de invalidar manualmente los veredictos de filtrado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e213-111">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="8e213-112">La lista de inquilinos permitidos o bloqueados se usa durante el flujo de correo y en el momento de los clics del usuario.</span><span class="sxs-lookup"><span data-stu-id="8e213-112">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="8e213-113">Puede especificar direcciones URL o archivos para bloquearlos siempre.</span><span class="sxs-lookup"><span data-stu-id="8e213-113">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="8e213-114">En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="8e213-114">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8e213-115">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="8e213-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8e213-116">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8e213-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8e213-117">Para ir directamente a la página **Lista de inquilinos permitidos o bloqueados,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="8e213-117">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="8e213-118">Los archivos se especifican mediante el valor hash SHA256 del archivo.</span><span class="sxs-lookup"><span data-stu-id="8e213-118">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="8e213-119">Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="8e213-119">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="8e213-120">Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="8e213-120">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="8e213-121">No se admiten valores de hash perceptual (pHash).</span><span class="sxs-lookup"><span data-stu-id="8e213-121">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="8e213-122">Los valores de dirección URL disponibles se describen en la sintaxis url de la sección Lista de [inquilinos permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="8e213-122">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="8e213-123">La lista de inquilinos permitidos o bloqueados permite un máximo de 500 entradas para direcciones URL y 500 entradas para hashes de archivo.</span><span class="sxs-lookup"><span data-stu-id="8e213-123">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="8e213-124">El número máximo de caracteres para cada entrada es:</span><span class="sxs-lookup"><span data-stu-id="8e213-124">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="8e213-125">Hashes de archivo = 64</span><span class="sxs-lookup"><span data-stu-id="8e213-125">File hashes = 64</span></span>
  - <span data-ttu-id="8e213-126">URL = 250</span><span class="sxs-lookup"><span data-stu-id="8e213-126">URL = 250</span></span>

- <span data-ttu-id="8e213-127">Una entrada debe estar activa en 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="8e213-127">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="8e213-128">De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="8e213-128">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="8e213-129">Puede especificar una fecha o establecerla para que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="8e213-129">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="8e213-130">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8e213-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8e213-131">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="8e213-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8e213-132">Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="8e213-132">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="8e213-133">Para agregar y quitar valores de la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="8e213-133">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="8e213-134">Para obtener acceso de solo lectura a la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="8e213-134">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="8e213-135">Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="8e213-135">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="8e213-136">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e213-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="8e213-137">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8e213-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="8e213-138">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="8e213-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-139">Usar el Centro de seguridad & cumplimiento para crear entradas de dirección URL en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-139">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8e213-140">Para obtener más información acerca de la sintaxis de las entradas de dirección URL, vea la sintaxis de dirección URL de la sección Lista de [permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados del espacio empresarial más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="8e213-140">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="8e213-141">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="8e213-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8e213-142">En la **página Lista de inquilinos permitidos o** bloqueados, compruebe que la pestaña **Direcciones** URL está seleccionada y, a continuación, haga clic en **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="8e213-142">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="8e213-143">En el **menú desplegable Bloquear direcciones URL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8e213-143">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8e213-144">**Agregar direcciones URL para bloquear:** escriba una dirección URL por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="8e213-144">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="8e213-145">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8e213-145">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8e213-146">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="8e213-146">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="8e213-147">o</span><span class="sxs-lookup"><span data-stu-id="8e213-147">or</span></span>

     - <span data-ttu-id="8e213-148">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="8e213-148">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="8e213-150">.</span><span class="sxs-lookup"><span data-stu-id="8e213-150">.</span></span>

   - <span data-ttu-id="8e213-151">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="8e213-151">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="8e213-152">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8e213-152">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-153">Usar el Centro de & seguridad para crear entradas de archivo en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-153">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8e213-154">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="8e213-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8e213-155">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la **pestaña** Archivos y, a continuación, haga clic en **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="8e213-155">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="8e213-156">En el menú desplegable **Agregar archivos** para bloquear que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8e213-156">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8e213-157">**Agregar hash de archivo:** escriba un valor hash SHA256 por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="8e213-157">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="8e213-158">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8e213-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8e213-159">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="8e213-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="8e213-160">o</span><span class="sxs-lookup"><span data-stu-id="8e213-160">or</span></span>

     - <span data-ttu-id="8e213-161">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="8e213-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="8e213-163">.</span><span class="sxs-lookup"><span data-stu-id="8e213-163">.</span></span>

   - <span data-ttu-id="8e213-164">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="8e213-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="8e213-165">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="8e213-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-166">Usar el Centro de seguridad & cumplimiento para ver entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-166">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8e213-167">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="8e213-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8e213-168">Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.</span><span class="sxs-lookup"><span data-stu-id="8e213-168">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="8e213-169">Haga clic en los siguientes encabezados de columna para ordenar en orden ascendente o descendente:</span><span class="sxs-lookup"><span data-stu-id="8e213-169">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="8e213-170">**Valor:** la dirección URL o el hash del archivo.</span><span class="sxs-lookup"><span data-stu-id="8e213-170">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="8e213-171">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="8e213-171">**Last updated date**</span></span>
- <span data-ttu-id="8e213-172">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="8e213-172">**Expiration date**</span></span>
- <span data-ttu-id="8e213-173">**Nota**</span><span class="sxs-lookup"><span data-stu-id="8e213-173">**Note**</span></span>

<span data-ttu-id="8e213-174">Haga **clic en** Buscar, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico.</span><span class="sxs-lookup"><span data-stu-id="8e213-174">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="8e213-175">Cuando haya terminado, haga clic en **Borrar búsqueda** Borrar icono ![ de ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e213-175">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="8e213-176">Haga clic **en Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="8e213-176">Click **Filter**.</span></span> <span data-ttu-id="8e213-177">En el **menú** desplegable Filtro que aparece, configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8e213-177">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="8e213-178">**Never expire**: Select off: ![ Toggle off or ](../../media/scc-toggle-off.png) on: Toggle on ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="8e213-178">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="8e213-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="8e213-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="8e213-180">**Fecha de expiración:** seleccione una fecha de inicio (**From**), una fecha de finalización (**Para**) o ambas.</span><span class="sxs-lookup"><span data-stu-id="8e213-180">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="8e213-181">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="8e213-181">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="8e213-182">Para borrar los filtros existentes, haga clic **en Filtrar** y, en el **menú** desplegable Filtro que aparece, haga clic en **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="8e213-182">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-183">Usar el Centro de seguridad & cumplimiento para modificar entradas de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-183">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8e213-184">No puede modificar los valores de archivo o url bloqueados existentes dentro de una entrada.</span><span class="sxs-lookup"><span data-stu-id="8e213-184">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="8e213-185">Para modificar estos valores, debe eliminar y volver a crear la entrada.</span><span class="sxs-lookup"><span data-stu-id="8e213-185">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="8e213-186">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="8e213-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8e213-187">Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.</span><span class="sxs-lookup"><span data-stu-id="8e213-187">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="8e213-188">Seleccione la entrada de bloque que desea modificar y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="8e213-188">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="8e213-189">En el menú desplegable que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8e213-189">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8e213-190">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8e213-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="8e213-191">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de la entrada. </span><span class="sxs-lookup"><span data-stu-id="8e213-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="8e213-192">o</span><span class="sxs-lookup"><span data-stu-id="8e213-192">or</span></span>

     - <span data-ttu-id="8e213-193">Mueva el botón de alternancia a la derecha para configurar la entrada para que no expire nunca:</span><span class="sxs-lookup"><span data-stu-id="8e213-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="8e213-195">.</span><span class="sxs-lookup"><span data-stu-id="8e213-195">.</span></span>

   - <span data-ttu-id="8e213-196">**Nota opcional:** escriba texto descriptivo para la entrada.</span><span class="sxs-lookup"><span data-stu-id="8e213-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="8e213-197">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8e213-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-198">Usar el Centro de seguridad & cumplimiento para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-198">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="8e213-199">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="8e213-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="8e213-200">Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.</span><span class="sxs-lookup"><span data-stu-id="8e213-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="8e213-201">Seleccione la entrada de bloque que desea quitar y, a continuación, haga clic **en Eliminar** icono ![ Eliminar ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="8e213-201">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="8e213-202">En el cuadro de diálogo de advertencia que aparece, haga clic **en Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="8e213-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-203">Usar PowerShell de Exchange Online o PowerShell EOP independiente para configurar la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-204">Usar PowerShell para agregar entradas de bloque a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-204">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="8e213-205">Para agregar entradas de bloque en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8e213-205">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="8e213-206">En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8e213-206">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="8e213-207">Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="8e213-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="8e213-208">En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="8e213-208">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="8e213-209">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8e213-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-210">Usar PowerShell para ver entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-210">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8e213-211">Para ver entradas en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8e213-211">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="8e213-212">En este ejemplo se devuelven todas las direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="8e213-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="8e213-213">En este ejemplo se devuelve información sobre el valor hash de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="8e213-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="8e213-214">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8e213-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-215">Usar PowerShell para modificar entradas de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-215">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="8e213-216">No puede modificar los valores de dirección URL o archivo existentes dentro de una entrada de bloque.</span><span class="sxs-lookup"><span data-stu-id="8e213-216">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="8e213-217">Para modificar estos valores, debe eliminar y volver a crear la entrada.</span><span class="sxs-lookup"><span data-stu-id="8e213-217">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="8e213-218">Para modificar las entradas de bloque en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8e213-218">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="8e213-219">En este ejemplo se cambia la fecha de expiración de la entrada de bloque especificada.</span><span class="sxs-lookup"><span data-stu-id="8e213-219">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="8e213-220">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8e213-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-221">Usar PowerShell para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-221">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="8e213-222">Para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="8e213-222">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="8e213-223">En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de inquilinos permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="8e213-223">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="8e213-224">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="8e213-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="8e213-225">Sintaxis de dirección URL para la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="8e213-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="8e213-226">Las direcciones IP4v e IPv6 están permitidas, pero los puertos TCP/UDP no.</span><span class="sxs-lookup"><span data-stu-id="8e213-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="8e213-227">No se permiten extensiones de nombre de archivo (por ejemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="8e213-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="8e213-228">Unicode no es compatible, pero Punycode lo es.</span><span class="sxs-lookup"><span data-stu-id="8e213-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="8e213-229">Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="8e213-229">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="8e213-230">El nombre de host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="8e213-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="8e213-231">Hay al menos un carácter a la izquierda del punto.</span><span class="sxs-lookup"><span data-stu-id="8e213-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="8e213-232">Hay al menos dos caracteres a la derecha del punto.</span><span class="sxs-lookup"><span data-stu-id="8e213-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="8e213-233">Por ejemplo, `t.co` se permite; `.com` o no `contoso.` se permite.</span><span class="sxs-lookup"><span data-stu-id="8e213-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="8e213-234">Las subpaths no están implícitas.</span><span class="sxs-lookup"><span data-stu-id="8e213-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="8e213-235">Por ejemplo, `contoso.com` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="8e213-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="8e213-236">Los caracteres comodín (\*) se permiten en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="8e213-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="8e213-237">Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.</span><span class="sxs-lookup"><span data-stu-id="8e213-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="8e213-238">Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="8e213-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="8e213-239">Un comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8e213-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="8e213-240">Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o no `contoso.com/ab*` se permite.</span><span class="sxs-lookup"><span data-stu-id="8e213-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="8e213-241">Todas las subpaths no están implícitas por un comodín derecho.</span><span class="sxs-lookup"><span data-stu-id="8e213-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="8e213-242">Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="8e213-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="8e213-243">`*.com*` no es válido (no es un dominio resolvible y el comodín derecho no sigue una barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="8e213-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="8e213-244">Los caracteres comodín no están permitidos en las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="8e213-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="8e213-245">El carácter tilde (~) está disponible en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="8e213-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="8e213-246">Una tilde izquierda implica un dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="8e213-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="8e213-247">Por `~contoso.com` ejemplo, incluye `contoso.com` y `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="8e213-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="8e213-248">Se producirá un error en las entradas de dirección URL que contienen protocolos (por ejemplo, , o ) porque las entradas de dirección URL se `http://` aplican a todos los `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="8e213-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="8e213-249">No se admite ni se requiere un nombre de usuario o contraseña.</span><span class="sxs-lookup"><span data-stu-id="8e213-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="8e213-250">Las comillas (' o ") son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="8e213-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="8e213-251">Una dirección URL debe incluir todas las redirecciones siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="8e213-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="8e213-252">Escenarios de entrada de dirección URL</span><span class="sxs-lookup"><span data-stu-id="8e213-252">URL entry scenarios</span></span>

<span data-ttu-id="8e213-253">Las entradas de dirección URL válidas y sus resultados se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="8e213-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="8e213-254">Escenario: sin caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="8e213-254">Scenario: No wildcards</span></span>

<span data-ttu-id="8e213-255">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8e213-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="8e213-256">**Permitir coincidencia**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="8e213-257">**Permitir que no coincida**:</span><span class="sxs-lookup"><span data-stu-id="8e213-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="8e213-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-258">abc-contoso.com</span></span>
  - <span data-ttu-id="8e213-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8e213-259">contoso.com/a</span></span>
  - <span data-ttu-id="8e213-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="8e213-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="8e213-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8e213-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-263">www.contoso.com</span></span>
  - <span data-ttu-id="8e213-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-264">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="8e213-265">**Bloquear coincidencia**:</span><span class="sxs-lookup"><span data-stu-id="8e213-265">**Block match**:</span></span>

  - <span data-ttu-id="8e213-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-266">contoso.com</span></span>
  - <span data-ttu-id="8e213-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8e213-267">contoso.com/a</span></span>
  - <span data-ttu-id="8e213-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="8e213-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="8e213-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="8e213-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-271">www.contoso.com</span></span>
  - <span data-ttu-id="8e213-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="8e213-273">**Bloque no coincidente:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="8e213-274">Escenario: comodín izquierdo (subdominio)</span><span class="sxs-lookup"><span data-stu-id="8e213-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="8e213-275">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8e213-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="8e213-276">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="8e213-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8e213-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-277">www.contoso.com</span></span>
  - <span data-ttu-id="8e213-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8e213-279">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="8e213-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8e213-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-280">123contoso.com</span></span>
  - <span data-ttu-id="8e213-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-281">contoso.com</span></span>
  - <span data-ttu-id="8e213-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="8e213-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8e213-283">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="8e213-284">Escenario: comodín derecho en la parte superior de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="8e213-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="8e213-285">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="8e213-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="8e213-286">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="8e213-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8e213-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="8e213-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="8e213-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8e213-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8e213-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="8e213-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="8e213-290">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="8e213-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8e213-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-291">contoso.com</span></span>
  - <span data-ttu-id="8e213-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8e213-292">contoso.com/a</span></span>
  - <span data-ttu-id="8e213-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-293">www.contoso.com</span></span>
  - <span data-ttu-id="8e213-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-294">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="8e213-295">Escenario: tilde izquierda</span><span class="sxs-lookup"><span data-stu-id="8e213-295">Scenario: Left tilde</span></span>

<span data-ttu-id="8e213-296">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="8e213-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="8e213-297">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="8e213-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8e213-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-298">contoso.com</span></span>
  - <span data-ttu-id="8e213-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-299">www.contoso.com</span></span>
  - <span data-ttu-id="8e213-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8e213-301">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="8e213-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8e213-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-302">123contoso.com</span></span>
  - <span data-ttu-id="8e213-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8e213-303">contoso.com/abc</span></span>
  - <span data-ttu-id="8e213-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="8e213-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="8e213-305">Escenario: sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="8e213-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="8e213-306">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8e213-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="8e213-307">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="8e213-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8e213-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8e213-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="8e213-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8e213-309">contoso.com/a</span></span>
  - <span data-ttu-id="8e213-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8e213-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8e213-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8e213-311">contoso.com/ab</span></span>
  - <span data-ttu-id="8e213-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8e213-312">contoso.com/b</span></span>
  - <span data-ttu-id="8e213-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8e213-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8e213-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8e213-314">contoso.com/ba</span></span>

- <span data-ttu-id="8e213-315">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="8e213-316">Escenario: subdominio comodín izquierdo y sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="8e213-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="8e213-317">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="8e213-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="8e213-318">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="8e213-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8e213-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="8e213-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="8e213-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="8e213-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="8e213-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8e213-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="8e213-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="8e213-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="8e213-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="8e213-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="8e213-324">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8e213-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="8e213-325">Escenario: tilde izquierda y derecha</span><span class="sxs-lookup"><span data-stu-id="8e213-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="8e213-326">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="8e213-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="8e213-327">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="8e213-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8e213-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-328">contoso.com</span></span>
  - <span data-ttu-id="8e213-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="8e213-329">contoso.com/a</span></span>
  - <span data-ttu-id="8e213-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-330">www.contoso.com</span></span>
  - <span data-ttu-id="8e213-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="8e213-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="8e213-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="8e213-333">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="8e213-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8e213-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-334">123contoso.com</span></span>
  - <span data-ttu-id="8e213-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="8e213-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="8e213-336">Escenario: dirección IP</span><span class="sxs-lookup"><span data-stu-id="8e213-336">Scenario: IP address</span></span>

<span data-ttu-id="8e213-337">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="8e213-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="8e213-338">**Permitir coincidencia** y **Bloquear coincidencia**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="8e213-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="8e213-339">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="8e213-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="8e213-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8e213-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="8e213-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="8e213-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="8e213-342">Dirección IP con comodín derecho</span><span class="sxs-lookup"><span data-stu-id="8e213-342">IP address with right wildcard</span></span>

<span data-ttu-id="8e213-343">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="8e213-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="8e213-344">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="8e213-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="8e213-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="8e213-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="8e213-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="8e213-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="8e213-347">Ejemplos de entradas no válidas</span><span class="sxs-lookup"><span data-stu-id="8e213-347">Examples of invalid entries</span></span>

<span data-ttu-id="8e213-348">Las siguientes entradas no son válidas:</span><span class="sxs-lookup"><span data-stu-id="8e213-348">The following entries are invalid:</span></span>

- <span data-ttu-id="8e213-349">**Faltan valores de dominio o no son válidos:**</span><span class="sxs-lookup"><span data-stu-id="8e213-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="8e213-350">contoso</span><span class="sxs-lookup"><span data-stu-id="8e213-350">contoso</span></span>
  - <span data-ttu-id="8e213-351">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="8e213-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="8e213-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="8e213-352">\*.com</span></span>
  - <span data-ttu-id="8e213-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="8e213-353">\*.pdf</span></span>

- <span data-ttu-id="8e213-354">**Comodín en el texto o sin caracteres de espaciado:**</span><span class="sxs-lookup"><span data-stu-id="8e213-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="8e213-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e213-355">\*contoso.com</span></span>
  - <span data-ttu-id="8e213-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="8e213-356">contoso.com\*</span></span>
  - <span data-ttu-id="8e213-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="8e213-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="8e213-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="8e213-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="8e213-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="8e213-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="8e213-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="8e213-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="8e213-361">**Direcciones IP con puertos**:</span><span class="sxs-lookup"><span data-stu-id="8e213-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="8e213-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="8e213-362">contoso.com:443</span></span>
  - <span data-ttu-id="8e213-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="8e213-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="8e213-364">**Caracteres comodín no descriptivos:**</span><span class="sxs-lookup"><span data-stu-id="8e213-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="8e213-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="8e213-365">\*.\*</span></span>

- <span data-ttu-id="8e213-366">**Caracteres comodín intermedios**:</span><span class="sxs-lookup"><span data-stu-id="8e213-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="8e213-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="8e213-367">conto\*so.com</span></span>
  - <span data-ttu-id="8e213-368">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="8e213-368">conto~so.com</span></span>

- <span data-ttu-id="8e213-369">**Caracteres comodín dobles**</span><span class="sxs-lookup"><span data-stu-id="8e213-369">**Double wildcards**</span></span>

  - <span data-ttu-id="8e213-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="8e213-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="8e213-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="8e213-371">contoso.com/\*/\*</span></span>
