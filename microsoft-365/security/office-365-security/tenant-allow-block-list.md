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
ms.openlocfilehash: 20e460f4e93f7b87faaead8b87ba561224e38938
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515213"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-103">Administrar la lista de permitidos o bloqueados del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="c063e-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c063e-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="c063e-104">**Applies to**</span></span>
- [<span data-ttu-id="c063e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c063e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c063e-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c063e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c063e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c063e-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="c063e-108">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="c063e-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="c063e-109">No puede configurar elementos **permitidos** en la lista de inquilinos permitidos o bloqueados en este momento.</span><span class="sxs-lookup"><span data-stu-id="c063e-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="c063e-110">En organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="c063e-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="c063e-111">Por ejemplo, un mensaje bueno puede marcarse como malo (un falso positivo) o un mensaje malo se puede permitir a través (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="c063e-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="c063e-112">La lista de inquilinos permitidos o bloqueados en el Centro de seguridad & cumplimiento le ofrece una forma de invalidar manualmente los veredictos de filtrado de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c063e-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="c063e-113">La lista de inquilinos permitidos o bloqueados se usa durante el flujo de correo y en el momento de los clics del usuario.</span><span class="sxs-lookup"><span data-stu-id="c063e-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="c063e-114">Puede especificar direcciones URL o archivos para bloquearlos siempre.</span><span class="sxs-lookup"><span data-stu-id="c063e-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="c063e-115">En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="c063e-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c063e-116">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="c063e-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c063e-117">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c063e-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c063e-118">Para ir directamente a la página **Lista de inquilinos permitidos o bloqueados,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="c063e-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="c063e-119">Los archivos se especifican mediante el valor hash SHA256 del archivo.</span><span class="sxs-lookup"><span data-stu-id="c063e-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="c063e-120">Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="c063e-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="c063e-121">Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="c063e-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="c063e-122">No se admiten valores de hash perceptual (pHash).</span><span class="sxs-lookup"><span data-stu-id="c063e-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="c063e-123">Los valores de dirección URL disponibles se describen en la sintaxis url de la sección Lista de [inquilinos permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c063e-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="c063e-124">La lista de inquilinos permitidos o bloqueados permite un máximo de 500 entradas para direcciones URL y 500 entradas para hashes de archivo.</span><span class="sxs-lookup"><span data-stu-id="c063e-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="c063e-125">El número máximo de caracteres para cada entrada es:</span><span class="sxs-lookup"><span data-stu-id="c063e-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="c063e-126">Hashes de archivo = 64</span><span class="sxs-lookup"><span data-stu-id="c063e-126">File hashes = 64</span></span>
  - <span data-ttu-id="c063e-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="c063e-127">URL = 250</span></span>

- <span data-ttu-id="c063e-128">Una entrada debe estar activa en 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="c063e-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="c063e-129">De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="c063e-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="c063e-130">Puede especificar una fecha o establecerla para que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="c063e-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="c063e-131">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c063e-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c063e-132">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="c063e-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c063e-133">Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="c063e-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c063e-134">Para agregar y quitar valores de la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="c063e-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="c063e-135">Para obtener acceso de solo lectura a la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="c063e-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c063e-136">Para obtener más información, vea los [permisos en Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="c063e-136">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="c063e-137">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c063e-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c063e-138">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c063e-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="c063e-139">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="c063e-139">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-140">Usar el Centro de seguridad & cumplimiento para crear entradas de dirección URL en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c063e-141">Para obtener más información acerca de la sintaxis de las entradas de dirección URL, vea la sintaxis de dirección URL de la sección Lista de [permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados del espacio empresarial más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c063e-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="c063e-142">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="c063e-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c063e-143">En la **página Lista de inquilinos permitidos o** bloqueados, compruebe que la pestaña **Direcciones** URL está seleccionada y, a continuación, haga clic en **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="c063e-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="c063e-144">En el **menú desplegable Bloquear direcciones URL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c063e-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c063e-145">**Agregar direcciones URL para bloquear:** escriba una dirección URL por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="c063e-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c063e-146">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="c063e-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c063e-147">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="c063e-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="c063e-148">o</span><span class="sxs-lookup"><span data-stu-id="c063e-148">or</span></span>

     - <span data-ttu-id="c063e-149">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="c063e-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="c063e-151">.</span><span class="sxs-lookup"><span data-stu-id="c063e-151">.</span></span>

   - <span data-ttu-id="c063e-152">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="c063e-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c063e-153">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c063e-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-154">Usar el Centro de & seguridad para crear entradas de archivo en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c063e-155">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="c063e-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c063e-156">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la **pestaña** Archivos y, a continuación, haga clic en **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="c063e-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="c063e-157">En el menú desplegable **Agregar archivos** para bloquear que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c063e-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c063e-158">**Agregar hash de archivo:** escriba un valor hash SHA256 por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="c063e-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c063e-159">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="c063e-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c063e-160">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="c063e-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c063e-161">o</span><span class="sxs-lookup"><span data-stu-id="c063e-161">or</span></span>

     - <span data-ttu-id="c063e-162">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="c063e-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="c063e-164">.</span><span class="sxs-lookup"><span data-stu-id="c063e-164">.</span></span>

   - <span data-ttu-id="c063e-165">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="c063e-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c063e-166">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c063e-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-167">Usar el Centro de seguridad & cumplimiento para ver entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c063e-168">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="c063e-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c063e-169">Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.</span><span class="sxs-lookup"><span data-stu-id="c063e-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="c063e-170">Haga clic en los siguientes encabezados de columna para ordenar en orden ascendente o descendente:</span><span class="sxs-lookup"><span data-stu-id="c063e-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="c063e-171">**Valor:** la dirección URL o el hash del archivo.</span><span class="sxs-lookup"><span data-stu-id="c063e-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="c063e-172">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="c063e-172">**Last updated date**</span></span>
- <span data-ttu-id="c063e-173">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="c063e-173">**Expiration date**</span></span>
- <span data-ttu-id="c063e-174">**Nota**</span><span class="sxs-lookup"><span data-stu-id="c063e-174">**Note**</span></span>

<span data-ttu-id="c063e-175">Haga **clic en** Buscar, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico.</span><span class="sxs-lookup"><span data-stu-id="c063e-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="c063e-176">Cuando haya terminado, haga clic en **Borrar búsqueda** Borrar icono ![ de ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c063e-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="c063e-177">Haga clic **en Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="c063e-177">Click **Filter**.</span></span> <span data-ttu-id="c063e-178">En el **menú** desplegable Filtro que aparece, configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c063e-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="c063e-179">**Never expire**: Select off: ![ Toggle off or ](../../media/scc-toggle-off.png) on: Toggle on ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="c063e-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="c063e-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="c063e-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="c063e-181">**Fecha de expiración:** seleccione una fecha de inicio (**From**), una fecha de finalización (**Para**) o ambas.</span><span class="sxs-lookup"><span data-stu-id="c063e-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="c063e-182">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c063e-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="c063e-183">Para borrar los filtros existentes, haga clic **en Filtrar** y, en el **menú** desplegable Filtro que aparece, haga clic en **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c063e-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-184">Usar el Centro de seguridad & cumplimiento para modificar entradas de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c063e-185">No puede modificar los valores de archivo o url bloqueados existentes dentro de una entrada.</span><span class="sxs-lookup"><span data-stu-id="c063e-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="c063e-186">Para modificar estos valores, debe eliminar y volver a crear la entrada.</span><span class="sxs-lookup"><span data-stu-id="c063e-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="c063e-187">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="c063e-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c063e-188">Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.</span><span class="sxs-lookup"><span data-stu-id="c063e-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c063e-189">Seleccione la entrada de bloque que desea modificar y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="c063e-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="c063e-190">En el menú desplegable que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c063e-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c063e-191">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="c063e-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c063e-192">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de la entrada. </span><span class="sxs-lookup"><span data-stu-id="c063e-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="c063e-193">o</span><span class="sxs-lookup"><span data-stu-id="c063e-193">or</span></span>

     - <span data-ttu-id="c063e-194">Mueva el botón de alternancia a la derecha para configurar la entrada para que no expire nunca:</span><span class="sxs-lookup"><span data-stu-id="c063e-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="c063e-196">.</span><span class="sxs-lookup"><span data-stu-id="c063e-196">.</span></span>

   - <span data-ttu-id="c063e-197">**Nota opcional:** escriba texto descriptivo para la entrada.</span><span class="sxs-lookup"><span data-stu-id="c063e-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="c063e-198">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="c063e-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-199">Usar el Centro de seguridad & cumplimiento para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c063e-200">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="c063e-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c063e-201">Seleccione la **pestaña Direcciones URL** o la **pestaña** Archivos.</span><span class="sxs-lookup"><span data-stu-id="c063e-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c063e-202">Seleccione la entrada de bloque que desea quitar y, a continuación, haga clic **en Eliminar** icono ![ Eliminar ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="c063e-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="c063e-203">En el cuadro de diálogo de advertencia que aparece, haga clic **en Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c063e-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-204">Usar PowerShell de Exchange Online o PowerShell EOP independiente para configurar la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-205">Usar PowerShell para agregar entradas de bloque a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="c063e-206">Para agregar entradas de bloque en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="c063e-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c063e-207">En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c063e-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="c063e-208">Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="c063e-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="c063e-209">En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="c063e-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="c063e-210">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c063e-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-211">Usar PowerShell para ver entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c063e-212">Para ver entradas en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="c063e-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="c063e-213">En este ejemplo se devuelven todas las direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="c063e-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="c063e-214">En este ejemplo se devuelve información sobre el valor hash de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c063e-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="c063e-215">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c063e-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-216">Usar PowerShell para modificar entradas de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c063e-217">No puede modificar los valores de dirección URL o archivo existentes dentro de una entrada de bloque.</span><span class="sxs-lookup"><span data-stu-id="c063e-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="c063e-218">Para modificar estos valores, debe eliminar y volver a crear la entrada.</span><span class="sxs-lookup"><span data-stu-id="c063e-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="c063e-219">Para modificar las entradas de bloque en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="c063e-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c063e-220">En este ejemplo se cambia la fecha de expiración de la entrada de bloque especificada.</span><span class="sxs-lookup"><span data-stu-id="c063e-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="c063e-221">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c063e-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-222">Usar PowerShell para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="c063e-223">Para quitar entradas de bloque de la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="c063e-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="c063e-224">En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de inquilinos permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="c063e-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="c063e-225">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c063e-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="c063e-226">Sintaxis de dirección URL para la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="c063e-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="c063e-227">Las direcciones IP4v e IPv6 están permitidas, pero los puertos TCP/UDP no.</span><span class="sxs-lookup"><span data-stu-id="c063e-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="c063e-228">No se permiten extensiones de nombre de archivo (por ejemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="c063e-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="c063e-229">Unicode no es compatible, pero Punycode lo es.</span><span class="sxs-lookup"><span data-stu-id="c063e-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="c063e-230">Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="c063e-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="c063e-231">El nombre de host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="c063e-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="c063e-232">Hay al menos un carácter a la izquierda del punto.</span><span class="sxs-lookup"><span data-stu-id="c063e-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="c063e-233">Hay al menos dos caracteres a la derecha del punto.</span><span class="sxs-lookup"><span data-stu-id="c063e-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="c063e-234">Por ejemplo, `t.co` se permite; `.com` o no `contoso.` se permite.</span><span class="sxs-lookup"><span data-stu-id="c063e-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="c063e-235">Las subpaths no están implícitas.</span><span class="sxs-lookup"><span data-stu-id="c063e-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="c063e-236">Por ejemplo, `contoso.com` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c063e-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="c063e-237">Los caracteres comodín (\*) se permiten en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="c063e-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="c063e-238">Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.</span><span class="sxs-lookup"><span data-stu-id="c063e-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="c063e-239">Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="c063e-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="c063e-240">Un comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c063e-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="c063e-241">Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o no `contoso.com/ab*` se permite.</span><span class="sxs-lookup"><span data-stu-id="c063e-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="c063e-242">Todas las subpaths no están implícitas por un comodín derecho.</span><span class="sxs-lookup"><span data-stu-id="c063e-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="c063e-243">Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c063e-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="c063e-244">`*.com*` no es válido (no es un dominio resolvible y el comodín derecho no sigue una barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="c063e-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="c063e-245">Los caracteres comodín no están permitidos en las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="c063e-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="c063e-246">El carácter tilde (~) está disponible en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="c063e-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="c063e-247">Una tilde izquierda implica un dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="c063e-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="c063e-248">Por `~contoso.com` ejemplo, incluye `contoso.com` y `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="c063e-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="c063e-249">Se producirá un error en las entradas de dirección URL que contienen protocolos (por ejemplo, , o ) porque las entradas de dirección URL se `http://` aplican a todos los `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="c063e-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="c063e-250">No se admite ni se requiere un nombre de usuario o contraseña.</span><span class="sxs-lookup"><span data-stu-id="c063e-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="c063e-251">Las comillas (' o ") son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="c063e-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="c063e-252">Una dirección URL debe incluir todas las redirecciones siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="c063e-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="c063e-253">Escenarios de entrada de dirección URL</span><span class="sxs-lookup"><span data-stu-id="c063e-253">URL entry scenarios</span></span>

<span data-ttu-id="c063e-254">Las entradas de dirección URL válidas y sus resultados se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="c063e-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="c063e-255">Escenario: sin caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="c063e-255">Scenario: No wildcards</span></span>

<span data-ttu-id="c063e-256">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c063e-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="c063e-257">**Permitir coincidencia**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="c063e-258">**Permitir que no coincida**:</span><span class="sxs-lookup"><span data-stu-id="c063e-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="c063e-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-259">abc-contoso.com</span></span>
  - <span data-ttu-id="c063e-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c063e-260">contoso.com/a</span></span>
  - <span data-ttu-id="c063e-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="c063e-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="c063e-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c063e-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-264">www.contoso.com</span></span>
  - <span data-ttu-id="c063e-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c063e-266">**Bloquear coincidencia**:</span><span class="sxs-lookup"><span data-stu-id="c063e-266">**Block match**:</span></span>

  - <span data-ttu-id="c063e-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-267">contoso.com</span></span>
  - <span data-ttu-id="c063e-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c063e-268">contoso.com/a</span></span>
  - <span data-ttu-id="c063e-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="c063e-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="c063e-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c063e-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-272">www.contoso.com</span></span>
  - <span data-ttu-id="c063e-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c063e-274">**Bloque no coincidente:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="c063e-275">Escenario: comodín izquierdo (subdominio)</span><span class="sxs-lookup"><span data-stu-id="c063e-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="c063e-276">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c063e-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="c063e-277">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="c063e-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c063e-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-278">www.contoso.com</span></span>
  - <span data-ttu-id="c063e-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c063e-280">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="c063e-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c063e-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-281">123contoso.com</span></span>
  - <span data-ttu-id="c063e-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-282">contoso.com</span></span>
  - <span data-ttu-id="c063e-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="c063e-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c063e-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="c063e-285">Escenario: comodín derecho en la parte superior de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="c063e-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="c063e-286">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="c063e-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="c063e-287">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="c063e-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c063e-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="c063e-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="c063e-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c063e-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c063e-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="c063e-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="c063e-291">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="c063e-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c063e-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-292">contoso.com</span></span>
  - <span data-ttu-id="c063e-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c063e-293">contoso.com/a</span></span>
  - <span data-ttu-id="c063e-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-294">www.contoso.com</span></span>
  - <span data-ttu-id="c063e-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="c063e-296">Escenario: tilde izquierda</span><span class="sxs-lookup"><span data-stu-id="c063e-296">Scenario: Left tilde</span></span>

<span data-ttu-id="c063e-297">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c063e-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="c063e-298">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="c063e-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c063e-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-299">contoso.com</span></span>
  - <span data-ttu-id="c063e-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-300">www.contoso.com</span></span>
  - <span data-ttu-id="c063e-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c063e-302">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="c063e-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c063e-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-303">123contoso.com</span></span>
  - <span data-ttu-id="c063e-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c063e-304">contoso.com/abc</span></span>
  - <span data-ttu-id="c063e-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c063e-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="c063e-306">Escenario: sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="c063e-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="c063e-307">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c063e-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="c063e-308">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="c063e-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c063e-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c063e-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="c063e-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c063e-310">contoso.com/a</span></span>
  - <span data-ttu-id="c063e-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c063e-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c063e-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c063e-312">contoso.com/ab</span></span>
  - <span data-ttu-id="c063e-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c063e-313">contoso.com/b</span></span>
  - <span data-ttu-id="c063e-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c063e-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c063e-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c063e-315">contoso.com/ba</span></span>

- <span data-ttu-id="c063e-316">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="c063e-317">Escenario: subdominio comodín izquierdo y sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="c063e-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="c063e-318">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c063e-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="c063e-319">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="c063e-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c063e-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c063e-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="c063e-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c063e-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c063e-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c063e-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="c063e-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c063e-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c063e-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c063e-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="c063e-325">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c063e-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="c063e-326">Escenario: tilde izquierda y derecha</span><span class="sxs-lookup"><span data-stu-id="c063e-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="c063e-327">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="c063e-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="c063e-328">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="c063e-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c063e-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-329">contoso.com</span></span>
  - <span data-ttu-id="c063e-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c063e-330">contoso.com/a</span></span>
  - <span data-ttu-id="c063e-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-331">www.contoso.com</span></span>
  - <span data-ttu-id="c063e-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c063e-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="c063e-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c063e-334">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="c063e-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c063e-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-335">123contoso.com</span></span>
  - <span data-ttu-id="c063e-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="c063e-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="c063e-337">Escenario: dirección IP</span><span class="sxs-lookup"><span data-stu-id="c063e-337">Scenario: IP address</span></span>

<span data-ttu-id="c063e-338">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="c063e-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="c063e-339">**Permitir coincidencia** y **Bloquear coincidencia**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c063e-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="c063e-340">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="c063e-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c063e-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c063e-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="c063e-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c063e-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="c063e-343">Dirección IP con comodín derecho</span><span class="sxs-lookup"><span data-stu-id="c063e-343">IP address with right wildcard</span></span>

<span data-ttu-id="c063e-344">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="c063e-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="c063e-345">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="c063e-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c063e-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="c063e-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="c063e-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="c063e-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="c063e-348">Ejemplos de entradas no válidas</span><span class="sxs-lookup"><span data-stu-id="c063e-348">Examples of invalid entries</span></span>

<span data-ttu-id="c063e-349">Las siguientes entradas no son válidas:</span><span class="sxs-lookup"><span data-stu-id="c063e-349">The following entries are invalid:</span></span>

- <span data-ttu-id="c063e-350">**Faltan valores de dominio o no son válidos:**</span><span class="sxs-lookup"><span data-stu-id="c063e-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="c063e-351">contoso</span><span class="sxs-lookup"><span data-stu-id="c063e-351">contoso</span></span>
  - <span data-ttu-id="c063e-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="c063e-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="c063e-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="c063e-353">\*.com</span></span>
  - <span data-ttu-id="c063e-354">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="c063e-354">\*.pdf</span></span>

- <span data-ttu-id="c063e-355">**Comodín en el texto o sin caracteres de espaciado:**</span><span class="sxs-lookup"><span data-stu-id="c063e-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="c063e-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="c063e-356">\*contoso.com</span></span>
  - <span data-ttu-id="c063e-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="c063e-357">contoso.com\*</span></span>
  - <span data-ttu-id="c063e-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c063e-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="c063e-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="c063e-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="c063e-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="c063e-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="c063e-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="c063e-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="c063e-362">**Direcciones IP con puertos**:</span><span class="sxs-lookup"><span data-stu-id="c063e-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="c063e-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="c063e-363">contoso.com:443</span></span>
  - <span data-ttu-id="c063e-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="c063e-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="c063e-365">**Caracteres comodín no descriptivos:**</span><span class="sxs-lookup"><span data-stu-id="c063e-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="c063e-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="c063e-366">\*.\*</span></span>

- <span data-ttu-id="c063e-367">**Caracteres comodín intermedios**:</span><span class="sxs-lookup"><span data-stu-id="c063e-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="c063e-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="c063e-368">conto\*so.com</span></span>
  - <span data-ttu-id="c063e-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="c063e-369">conto~so.com</span></span>

- <span data-ttu-id="c063e-370">**Caracteres comodín dobles**</span><span class="sxs-lookup"><span data-stu-id="c063e-370">**Double wildcards**</span></span>

  - <span data-ttu-id="c063e-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="c063e-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="c063e-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="c063e-372">contoso.com/\*/\*</span></span>
