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
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538968"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-103">Administrar la lista de permitidos o bloqueados del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="ad759-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ad759-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="ad759-104">**Applies to**</span></span>
- [<span data-ttu-id="ad759-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ad759-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ad759-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="ad759-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ad759-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad759-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="ad759-108">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="ad759-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="ad759-109">Si su organización no tiene las características de suplantación de identidad como se describe en este artículo, vea la experiencia de administración de suplantación de identidad anterior en [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="ad759-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="ad759-110">No puede configurar la dirección URL o **los** elementos de archivo permitidos en la lista de inquilinos permitidos o bloqueados en este momento.</span><span class="sxs-lookup"><span data-stu-id="ad759-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="ad759-111">En Microsoft 365 organizaciones con buzones de correo en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="ad759-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="ad759-112">Por ejemplo, un mensaje bueno puede marcarse como malo (un falso positivo) o un mensaje malo se puede permitir a través (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="ad759-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="ad759-113">La lista de inquilinos permitidos o bloqueados en el Centro de seguridad & cumplimiento le ofrece una forma de invalidar manualmente los Microsoft 365 de filtrado.</span><span class="sxs-lookup"><span data-stu-id="ad759-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="ad759-114">La lista de inquilinos permitidos o bloqueados se usa durante el flujo de correo y en el momento de los clics del usuario.</span><span class="sxs-lookup"><span data-stu-id="ad759-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="ad759-115">Puede especificar los siguientes tipos de invalidaciones:</span><span class="sxs-lookup"><span data-stu-id="ad759-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="ad759-116">Direcciones URL que se bloquearán.</span><span class="sxs-lookup"><span data-stu-id="ad759-116">URLs to block.</span></span>
- <span data-ttu-id="ad759-117">Archivos que se va a bloquear.</span><span class="sxs-lookup"><span data-stu-id="ad759-117">Files to block.</span></span>
- <span data-ttu-id="ad759-118">Dominios de remitente de correo masivo que se permiten.</span><span class="sxs-lookup"><span data-stu-id="ad759-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="ad759-119">Para obtener más información acerca del correo masivo, el nivel de confianza en masa (BCL) y el filtrado masivo de correo mediante directivas contra correo no deseado, vea [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="ad759-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="ad759-120">Remitentes suplantados para permitir o bloquear.</span><span class="sxs-lookup"><span data-stu-id="ad759-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="ad759-121">Si invalida el veredicto permitir o bloquear en la información de inteligencia suplantada, el remitente  suplantado se convierte en una entrada manual de permitir o bloquear que solo aparece en la pestaña Suplantación de identidad de la lista de permitidos o bloqueados del inquilino. [](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="ad759-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="ad759-122">También puede crear entradas de permitir o bloquear manualmente para remitentes suplantados aquí antes de que los detecte la inteligencia de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="ad759-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="ad759-123">En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="ad759-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ad759-124">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="ad759-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ad759-125">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ad759-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ad759-126">Para ir directamente a la página **Lista de inquilinos permitidos o bloqueados,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="ad759-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="ad759-127">Los archivos se especifican mediante el valor hash SHA256 del archivo.</span><span class="sxs-lookup"><span data-stu-id="ad759-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="ad759-128">Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="ad759-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="ad759-129">Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="ad759-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="ad759-130">No se admiten valores de hash perceptual (pHash).</span><span class="sxs-lookup"><span data-stu-id="ad759-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="ad759-131">Los valores de dirección URL disponibles se describen en la sintaxis url de la sección Lista de [inquilinos permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ad759-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="ad759-132">La lista de inquilinos permitidos o bloqueados permite un máximo de 500 entradas para direcciones URL y 500 entradas para hashes de archivo.</span><span class="sxs-lookup"><span data-stu-id="ad759-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="ad759-133">El número máximo de caracteres para cada entrada es:</span><span class="sxs-lookup"><span data-stu-id="ad759-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="ad759-134">Hashes de archivo = 64</span><span class="sxs-lookup"><span data-stu-id="ad759-134">File hashes = 64</span></span>
  - <span data-ttu-id="ad759-135">URL = 250</span><span class="sxs-lookup"><span data-stu-id="ad759-135">URL = 250</span></span>

- <span data-ttu-id="ad759-136">Una entrada debe estar activa en 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="ad759-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="ad759-137">De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="ad759-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="ad759-138">Puede especificar una fecha o establecerla para que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="ad759-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="ad759-139">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ad759-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ad759-140">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ad759-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ad759-141">Debe tener permisos asignados en Exchange Online antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="ad759-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ad759-142">**Direcciones URL, archivos y permitir remitentes masivos:**</span><span class="sxs-lookup"><span data-stu-id="ad759-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="ad759-143">Para agregar y quitar valores de la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="ad759-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="ad759-144">Para obtener acceso de solo lectura a la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="ad759-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="ad759-145">**Suplantación:** una de las siguientes combinaciones:</span><span class="sxs-lookup"><span data-stu-id="ad759-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="ad759-146">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="ad759-146">**Organization Management**</span></span>
    - <span data-ttu-id="ad759-147">**Administrador de seguridad** <u>y</u> **Configuración de solo vista** o Administración de la organización de solo **vista**.</span><span class="sxs-lookup"><span data-stu-id="ad759-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="ad759-148">Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="ad759-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="ad759-149">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ad759-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ad759-150">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ad759-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="ad759-151">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="ad759-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-152">Usar el Centro de seguridad & cumplimiento para crear entradas de dirección URL de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ad759-153">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="ad759-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ad759-154">En la **página Lista de inquilinos permitidos o** bloqueados, compruebe que la pestaña **Direcciones** URL está seleccionada y, a continuación, haga clic en **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="ad759-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="ad759-155">En el **menú desplegable Bloquear direcciones URL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ad759-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ad759-156">**Agregar direcciones URL para bloquear:** escriba una dirección URL por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="ad759-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="ad759-157">Para obtener más información acerca de la sintaxis de las entradas de dirección URL, vea la sintaxis de dirección URL de la sección Lista de [permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados del espacio empresarial más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ad759-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="ad759-158">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="ad759-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ad759-159">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="ad759-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="ad759-160">o</span><span class="sxs-lookup"><span data-stu-id="ad759-160">or</span></span>

     - <span data-ttu-id="ad759-161">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="ad759-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="ad759-163">.</span><span class="sxs-lookup"><span data-stu-id="ad759-163">.</span></span>

   - <span data-ttu-id="ad759-164">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="ad759-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ad759-165">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad759-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-166">Usar el Centro de seguridad & cumplimiento para crear entradas de archivo de bloqueo en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ad759-167">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="ad759-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ad759-168">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la **pestaña** Archivos y, a continuación, haga clic en **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="ad759-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="ad759-169">En el menú desplegable **Agregar archivos** para bloquear que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ad759-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ad759-170">**Agregar hash de archivo:** escriba un valor hash SHA256 por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="ad759-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ad759-171">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="ad759-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ad759-172">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="ad759-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ad759-173">o</span><span class="sxs-lookup"><span data-stu-id="ad759-173">or</span></span>

     - <span data-ttu-id="ad759-174">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="ad759-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="ad759-176">.</span><span class="sxs-lookup"><span data-stu-id="ad759-176">.</span></span>

   - <span data-ttu-id="ad759-177">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="ad759-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="ad759-178">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad759-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-179">Usar el Centro de seguridad & cumplimiento para crear entradas de dominio de remitente de correo masivo en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ad759-180">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="ad759-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ad759-181">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la pestaña Dominios de remitente para la omisión de **BCL** y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad759-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="ad759-182">En el menú desplegable Agregar dominio de remitente para la omisión **de BCL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ad759-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ad759-183">Agregar dominios de remitente para la omisión **de BCL:** escriba un dominio de origen de correo masivo bueno por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="ad759-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="ad759-184">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="ad759-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="ad759-185">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="ad759-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="ad759-186">o</span><span class="sxs-lookup"><span data-stu-id="ad759-186">or</span></span>

     - <span data-ttu-id="ad759-187">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="ad759-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="ad759-189">.</span><span class="sxs-lookup"><span data-stu-id="ad759-189">.</span></span>

4. <span data-ttu-id="ad759-190">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad759-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-191">Usar el Centro de seguridad & cumplimiento para crear entradas de remitente suplantadas de identidad o de bloqueo en la lista de permitidos o bloqueados de inquilinos</span><span class="sxs-lookup"><span data-stu-id="ad759-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-192">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="ad759-192">**Notes**:</span></span>

- <span data-ttu-id="ad759-193">Solo se _permite o_ bloquea  específicamente la combinación del usuario suplantado y la infraestructura de envío definida en el par de dominio.</span><span class="sxs-lookup"><span data-stu-id="ad759-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="ad759-194">Al configurar una entrada de permitir o bloquear para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la información de inteligencia suplantación.</span><span class="sxs-lookup"><span data-stu-id="ad759-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="ad759-195">Las entradas de remitentes suplantados nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="ad759-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="ad759-196">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="ad759-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ad759-197">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la pestaña **Suplantación** y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad759-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="ad759-198">En el **menú desplegable Agregar nuevos pares de** dominio que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ad759-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ad759-199">**Agregar nuevos pares de dominio con caracteres comodín:** escriba un par de dominio por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="ad759-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="ad759-200">Para obtener más información acerca de la sintaxis de las entradas de remitente suplantadas, vea la sintaxis del par de dominios para las entradas de remitente suplantadas en la sección Lista de [permitidos/bloqueados](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) del espacio empresarial más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ad759-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="ad759-201">**Tipo de suplantación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ad759-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="ad759-202">**Interno:** el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="ad759-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="ad759-203">**Externo:** el remitente suplantado está en un dominio externo.</span><span class="sxs-lookup"><span data-stu-id="ad759-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="ad759-204">**Acción:** seleccione **Permitir** o **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="ad759-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="ad759-205">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ad759-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-206">Usar el Centro de seguridad & cumplimiento para ver entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ad759-207">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="ad759-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ad759-208">Seleccione la pestaña que desee.</span><span class="sxs-lookup"><span data-stu-id="ad759-208">Select the tab you want.</span></span> <span data-ttu-id="ad759-209">Las columnas disponibles dependen de la pestaña seleccionada:</span><span class="sxs-lookup"><span data-stu-id="ad759-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="ad759-210">**DIRECCIONES URL:**</span><span class="sxs-lookup"><span data-stu-id="ad759-210">**URLs**:</span></span>
     - <span data-ttu-id="ad759-211">**Value**: La dirección URL.</span><span class="sxs-lookup"><span data-stu-id="ad759-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="ad759-212">**Action**: El valor **Block**.</span><span class="sxs-lookup"><span data-stu-id="ad759-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="ad759-213">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="ad759-213">**Last updated date**</span></span>
     - <span data-ttu-id="ad759-214">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="ad759-214">**Expiration date**</span></span>
     - <span data-ttu-id="ad759-215">**Nota**</span><span class="sxs-lookup"><span data-stu-id="ad759-215">**Note**</span></span>

   - <span data-ttu-id="ad759-216">**Files**</span><span class="sxs-lookup"><span data-stu-id="ad759-216">**Files**</span></span>
     - <span data-ttu-id="ad759-217">**Valor:** hash de archivo.</span><span class="sxs-lookup"><span data-stu-id="ad759-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="ad759-218">**Action**: El valor **Block**.</span><span class="sxs-lookup"><span data-stu-id="ad759-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="ad759-219">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="ad759-219">**Last updated date**</span></span>
     - <span data-ttu-id="ad759-220">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="ad759-220">**Expiration date**</span></span>
     - <span data-ttu-id="ad759-221">**Nota**</span><span class="sxs-lookup"><span data-stu-id="ad759-221">**Note**</span></span>

   - <span data-ttu-id="ad759-222">**Dominios de remitente para la omisión de BCL**</span><span class="sxs-lookup"><span data-stu-id="ad759-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="ad759-223">**Valor:** dominio del remitente de correo masivo.</span><span class="sxs-lookup"><span data-stu-id="ad759-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="ad759-224">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="ad759-224">**Last updated date**</span></span>
     - <span data-ttu-id="ad759-225">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="ad759-225">**Expiration date**</span></span>

   - <span data-ttu-id="ad759-226">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ad759-226">**Spoofing**</span></span>
     - <span data-ttu-id="ad759-227">**Usuario suplantado**</span><span class="sxs-lookup"><span data-stu-id="ad759-227">**Spoofed user**</span></span>
     - <span data-ttu-id="ad759-228">**Infraestructura de envío**</span><span class="sxs-lookup"><span data-stu-id="ad759-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="ad759-229">**Tipo de suplantación:** el **valor Interno** o **Externo**.</span><span class="sxs-lookup"><span data-stu-id="ad759-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="ad759-230">**Action:** el valor **Block** o **Allow**.</span><span class="sxs-lookup"><span data-stu-id="ad759-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="ad759-231">Puede hacer clic en un encabezado de columna para ordenar en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="ad759-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="ad759-232">Puede hacer clic **en Grupo** para agrupar los resultados.</span><span class="sxs-lookup"><span data-stu-id="ad759-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="ad759-233">Los valores disponibles dependen de la pestaña seleccionada:</span><span class="sxs-lookup"><span data-stu-id="ad759-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="ad759-234">**DIRECCIONES URL:** puede agrupar los resultados por **Acción**.</span><span class="sxs-lookup"><span data-stu-id="ad759-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="ad759-235">**Archivos:** puede agrupar los resultados por **Acción**.</span><span class="sxs-lookup"><span data-stu-id="ad759-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="ad759-236">**Dominios de remitente para la omisión de BCL:** **el** grupo no está disponible en esta pestaña.</span><span class="sxs-lookup"><span data-stu-id="ad759-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="ad759-237">**Suplantación:** puede agrupar los resultados por **tipo Action** o **Spoof**.</span><span class="sxs-lookup"><span data-stu-id="ad759-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="ad759-238">Haga **clic en** Buscar, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico.</span><span class="sxs-lookup"><span data-stu-id="ad759-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="ad759-239">Cuando haya terminado, haga clic en **Borrar búsqueda** Borrar icono ![ de ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ad759-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="ad759-240">Haga **clic en** Filtrar para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="ad759-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="ad759-241">Los valores que están disponibles en **el** control desplegable Filtro que aparece dependen de la pestaña seleccionada:</span><span class="sxs-lookup"><span data-stu-id="ad759-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="ad759-242">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="ad759-242">**URLs**</span></span>
     - <span data-ttu-id="ad759-243">**Action**</span><span class="sxs-lookup"><span data-stu-id="ad759-243">**Action**</span></span>
     - <span data-ttu-id="ad759-244">**No expirar nunca**</span><span class="sxs-lookup"><span data-stu-id="ad759-244">**Never expire**</span></span>
     - <span data-ttu-id="ad759-245">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="ad759-245">**Last updated date**</span></span>
     - <span data-ttu-id="ad759-246">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="ad759-246">**Expiration date**</span></span>

   - <span data-ttu-id="ad759-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="ad759-247">**Files**</span></span>
     - <span data-ttu-id="ad759-248">**Action**</span><span class="sxs-lookup"><span data-stu-id="ad759-248">**Action**</span></span>
     - <span data-ttu-id="ad759-249">**No expirar nunca**</span><span class="sxs-lookup"><span data-stu-id="ad759-249">**Never expire**</span></span>
     - <span data-ttu-id="ad759-250">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="ad759-250">**Last updated date**</span></span>
     - <span data-ttu-id="ad759-251">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="ad759-251">**Expiration date**</span></span>

   - <span data-ttu-id="ad759-252">**Dominios de remitente para la omisión de BCL**</span><span class="sxs-lookup"><span data-stu-id="ad759-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="ad759-253">**No expirar nunca**</span><span class="sxs-lookup"><span data-stu-id="ad759-253">**Never expire**</span></span>
     - <span data-ttu-id="ad759-254">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="ad759-254">**Last updated date**</span></span>
     - <span data-ttu-id="ad759-255">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="ad759-255">**Expiration date**</span></span>

   - <span data-ttu-id="ad759-256">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ad759-256">**Spoofing**</span></span>
     - <span data-ttu-id="ad759-257">**Action**</span><span class="sxs-lookup"><span data-stu-id="ad759-257">**Action**</span></span>
     - <span data-ttu-id="ad759-258">**Tipo de suplantación**</span><span class="sxs-lookup"><span data-stu-id="ad759-258">**Spoof type**</span></span>

   <span data-ttu-id="ad759-259">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="ad759-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="ad759-260">Para borrar los filtros existentes, haga clic **en Filtrar** y, en el **menú** desplegable Filtro que aparece, haga clic en **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="ad759-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-261">Usar el Centro de seguridad & cumplimiento para modificar las entradas de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ad759-262">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="ad759-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ad759-263">Seleccione la pestaña que contiene el tipo de entrada que desea modificar:</span><span class="sxs-lookup"><span data-stu-id="ad759-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="ad759-264">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="ad759-264">**URLs**</span></span>
   - <span data-ttu-id="ad759-265">**Files**</span><span class="sxs-lookup"><span data-stu-id="ad759-265">**Files**</span></span>
   - <span data-ttu-id="ad759-266">**Dominios de remitente para la omisión de BCL**</span><span class="sxs-lookup"><span data-stu-id="ad759-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="ad759-267">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ad759-267">**Spoofing**</span></span>

3. <span data-ttu-id="ad759-268">Seleccione la entrada que desea modificar y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="ad759-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="ad759-269">Los valores que puede modificar en el control desplegable que aparece dependen de la pestaña seleccionada en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="ad759-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="ad759-270">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="ad759-270">**URLs**</span></span>
     - <span data-ttu-id="ad759-271">**No expire nunca** ni la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="ad759-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="ad759-272">**Nota opcional**</span><span class="sxs-lookup"><span data-stu-id="ad759-272">**Optional note**</span></span>

   - <span data-ttu-id="ad759-273">**Files**</span><span class="sxs-lookup"><span data-stu-id="ad759-273">**Files**</span></span>
     - <span data-ttu-id="ad759-274">**No expire nunca** ni la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="ad759-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="ad759-275">**Nota opcional**</span><span class="sxs-lookup"><span data-stu-id="ad759-275">**Optional note**</span></span>

   - <span data-ttu-id="ad759-276">**Dominios de remitente para la omisión de BCL**</span><span class="sxs-lookup"><span data-stu-id="ad759-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="ad759-277">**No expire nunca** ni la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="ad759-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="ad759-278">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ad759-278">**Spoofing**</span></span>
     - <span data-ttu-id="ad759-279">**Acción:** puede cambiar el valor a **Permitir** o **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="ad759-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="ad759-280">Cuando termine, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad759-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-281">Usar el Centro de & seguridad para quitar entradas de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="ad759-282">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="ad759-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="ad759-283">Seleccione la pestaña que contiene el tipo de entrada que desea quitar:</span><span class="sxs-lookup"><span data-stu-id="ad759-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="ad759-284">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="ad759-284">**URLs**</span></span>
   - <span data-ttu-id="ad759-285">**Files**</span><span class="sxs-lookup"><span data-stu-id="ad759-285">**Files**</span></span>
   - <span data-ttu-id="ad759-286">**Dominios de remitente para la omisión de BCL**</span><span class="sxs-lookup"><span data-stu-id="ad759-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="ad759-287">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="ad759-287">**Spoofing**</span></span>

3. <span data-ttu-id="ad759-288">Seleccione la entrada que desea quitar y, a continuación, haga clic **en Eliminar** icono ![ Eliminar ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="ad759-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="ad759-289">En el cuadro de diálogo de advertencia que aparece, haga clic **en Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ad759-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-290">Use Exchange Online PowerShell o PowerShell de EOP independiente para configurar la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-291">Usar PowerShell para agregar entradas de dirección URL o archivo de bloque a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-292">Para agregar entradas de dirección URL o archivo de bloque en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad759-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="ad759-293">En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="ad759-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="ad759-294">En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ad759-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="ad759-295">Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="ad759-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="ad759-296">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-297">Usar PowerShell para agregar entradas de dominio de remitente de correo masivo a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-298">Para agregar entradas de dominio de remitente de correo masivo en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad759-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="ad759-299">En este ejemplo se agrega una entrada de remitente masivo permitida para el dominio especificado que nunca expira.</span><span class="sxs-lookup"><span data-stu-id="ad759-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="ad759-300">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-301">Usar PowerShell para agregar entradas de remitente suplantadas de identidad o bloquear a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-302">Para agregar entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad759-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="ad759-303">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-304">Usar PowerShell para ver entradas de direcciones URL o archivos bloqueados en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-305">Para ver entradas de direcciones URL o archivos bloqueados en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad759-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="ad759-306">En este ejemplo se devuelve información sobre el valor hash de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="ad759-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="ad759-307">En este ejemplo se devuelven todas las direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="ad759-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="ad759-308">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-309">Usar PowerShell para ver entradas de dominio de remitente de correo masivo en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-310">Para ver permitir entradas de dominio de remitente de correo masivo en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad759-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="ad759-311">En este ejemplo se devuelven todos los dominios de remitente de correo masivo permitidos.</span><span class="sxs-lookup"><span data-stu-id="ad759-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="ad759-312">En este ejemplo se devuelve información para el dominio de remitente masivo especificado.</span><span class="sxs-lookup"><span data-stu-id="ad759-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="ad759-313">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-314">Usar PowerShell para ver o bloquear entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-315">Para ver entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad759-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="ad759-316">En este ejemplo se devuelven todas las entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="ad759-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="ad759-317">En este ejemplo se devuelven todas las entradas de remitente suplantadas que son internas.</span><span class="sxs-lookup"><span data-stu-id="ad759-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="ad759-318">En este ejemplo se devuelven todas las entradas de remitente suplantadas bloqueadas que son externas.</span><span class="sxs-lookup"><span data-stu-id="ad759-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="ad759-319">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-320">Usar PowerShell para modificar entradas de direcciones URL y archivos de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-321">Para modificar entradas de archivos de bloque y direcciones URL en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad759-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="ad759-322">En este ejemplo se cambia la fecha de expiración de la entrada de dirección URL de bloque especificada.</span><span class="sxs-lookup"><span data-stu-id="ad759-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="ad759-323">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-324">Usar PowerShell para modificar permitir entradas de dominio de remitente de correo masivo en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-325">Para modificar permitir entradas de dominio de remitente de correo masivo en la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ad759-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="ad759-326">En este ejemplo se cambia la expiración de la entrada de dominio de remitente de correo masivo especificada para que nunca expire.</span><span class="sxs-lookup"><span data-stu-id="ad759-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="ad759-327">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-328">Usar PowerShell para modificar entradas de remitente suplantadas o de permitir en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-329">Para modificar permitir o bloquear entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ad759-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="ad759-330">En este ejemplo se cambia la entrada de remitente suplantada de permitir a bloquear.</span><span class="sxs-lookup"><span data-stu-id="ad759-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="ad759-331">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-332">Usar PowerShell para quitar entradas de dominio, archivo y dominio del remitente de correo masivo de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-333">Para quitar entradas de dominio de remitente de correo masivo, bloquear entradas de archivo y bloquear entradas de dirección URL de la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ad759-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ad759-334">En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de inquilinos permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="ad759-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="ad759-335">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-336">Usar PowerShell para quitar o bloquear entradas de remitente suplantados de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-337">Para quitar entradas de remitente de suplantación de identidad de la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="ad759-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="ad759-338">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="ad759-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-339">Sintaxis de dirección URL para la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="ad759-340">Las direcciones IP4v e IPv6 están permitidas, pero los puertos TCP/UDP no.</span><span class="sxs-lookup"><span data-stu-id="ad759-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="ad759-341">No se permiten extensiones de nombre de archivo (por ejemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="ad759-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="ad759-342">Unicode no es compatible, pero Punycode lo es.</span><span class="sxs-lookup"><span data-stu-id="ad759-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="ad759-343">Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="ad759-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="ad759-344">El nombre de host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="ad759-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="ad759-345">Hay al menos un carácter a la izquierda del punto.</span><span class="sxs-lookup"><span data-stu-id="ad759-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="ad759-346">Hay al menos dos caracteres a la derecha del punto.</span><span class="sxs-lookup"><span data-stu-id="ad759-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="ad759-347">Por ejemplo, `t.co` se permite; `.com` o no `contoso.` se permite.</span><span class="sxs-lookup"><span data-stu-id="ad759-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="ad759-348">Las subpaths no están implícitas.</span><span class="sxs-lookup"><span data-stu-id="ad759-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="ad759-349">Por ejemplo, `contoso.com` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ad759-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="ad759-350">Los caracteres comodín (\*) se permiten en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="ad759-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="ad759-351">Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.</span><span class="sxs-lookup"><span data-stu-id="ad759-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="ad759-352">Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="ad759-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="ad759-353">Un comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="ad759-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="ad759-354">Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o no `contoso.com/ab*` se permite.</span><span class="sxs-lookup"><span data-stu-id="ad759-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="ad759-355">Todas las subpaths no están implícitas por un comodín derecho.</span><span class="sxs-lookup"><span data-stu-id="ad759-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="ad759-356">Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="ad759-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="ad759-357">`*.com*` no es válido (no es un dominio resolvible y el comodín derecho no sigue una barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="ad759-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="ad759-358">Los caracteres comodín no están permitidos en las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="ad759-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="ad759-359">El carácter tilde (~) está disponible en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="ad759-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="ad759-360">Una tilde izquierda implica un dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="ad759-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="ad759-361">Por `~contoso.com` ejemplo, incluye `contoso.com` y `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="ad759-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="ad759-362">Se producirá un error en las entradas de dirección URL que contienen protocolos (por ejemplo, , o ) porque las entradas de dirección URL se `http://` aplican a todos los `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="ad759-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="ad759-363">No se admite ni se requiere un nombre de usuario o contraseña.</span><span class="sxs-lookup"><span data-stu-id="ad759-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="ad759-364">Las comillas (' o ") son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="ad759-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="ad759-365">Una dirección URL debe incluir todas las redirecciones siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="ad759-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="ad759-366">Escenarios de entrada de dirección URL</span><span class="sxs-lookup"><span data-stu-id="ad759-366">URL entry scenarios</span></span>

<span data-ttu-id="ad759-367">Las entradas de dirección URL válidas y sus resultados se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="ad759-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="ad759-368">Escenario: sin caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="ad759-368">Scenario: No wildcards</span></span>

<span data-ttu-id="ad759-369">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ad759-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="ad759-370">**Permitir coincidencia**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="ad759-371">**Permitir que no coincida**:</span><span class="sxs-lookup"><span data-stu-id="ad759-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="ad759-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-372">abc-contoso.com</span></span>
  - <span data-ttu-id="ad759-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ad759-373">contoso.com/a</span></span>
  - <span data-ttu-id="ad759-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="ad759-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="ad759-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ad759-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-377">www.contoso.com</span></span>
  - <span data-ttu-id="ad759-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ad759-379">**Bloquear coincidencia**:</span><span class="sxs-lookup"><span data-stu-id="ad759-379">**Block match**:</span></span>

  - <span data-ttu-id="ad759-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-380">contoso.com</span></span>
  - <span data-ttu-id="ad759-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ad759-381">contoso.com/a</span></span>
  - <span data-ttu-id="ad759-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="ad759-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="ad759-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="ad759-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-385">www.contoso.com</span></span>
  - <span data-ttu-id="ad759-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="ad759-387">**Bloque no coincidente:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="ad759-388">Escenario: comodín izquierdo (subdominio)</span><span class="sxs-lookup"><span data-stu-id="ad759-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="ad759-389">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ad759-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="ad759-390">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="ad759-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ad759-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-391">www.contoso.com</span></span>
  - <span data-ttu-id="ad759-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ad759-393">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="ad759-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ad759-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-394">123contoso.com</span></span>
  - <span data-ttu-id="ad759-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-395">contoso.com</span></span>
  - <span data-ttu-id="ad759-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="ad759-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ad759-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="ad759-398">Escenario: comodín derecho en la parte superior de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="ad759-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="ad759-399">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="ad759-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="ad759-400">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="ad759-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ad759-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="ad759-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="ad759-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ad759-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ad759-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="ad759-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="ad759-404">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="ad759-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ad759-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-405">contoso.com</span></span>
  - <span data-ttu-id="ad759-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ad759-406">contoso.com/a</span></span>
  - <span data-ttu-id="ad759-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-407">www.contoso.com</span></span>
  - <span data-ttu-id="ad759-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="ad759-409">Escenario: tilde izquierda</span><span class="sxs-lookup"><span data-stu-id="ad759-409">Scenario: Left tilde</span></span>

<span data-ttu-id="ad759-410">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="ad759-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="ad759-411">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="ad759-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ad759-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-412">contoso.com</span></span>
  - <span data-ttu-id="ad759-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-413">www.contoso.com</span></span>
  - <span data-ttu-id="ad759-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ad759-415">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="ad759-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ad759-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-416">123contoso.com</span></span>
  - <span data-ttu-id="ad759-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ad759-417">contoso.com/abc</span></span>
  - <span data-ttu-id="ad759-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="ad759-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="ad759-419">Escenario: sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="ad759-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="ad759-420">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ad759-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="ad759-421">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="ad759-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ad759-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ad759-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="ad759-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ad759-423">contoso.com/a</span></span>
  - <span data-ttu-id="ad759-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ad759-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ad759-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ad759-425">contoso.com/ab</span></span>
  - <span data-ttu-id="ad759-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ad759-426">contoso.com/b</span></span>
  - <span data-ttu-id="ad759-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ad759-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ad759-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ad759-428">contoso.com/ba</span></span>

- <span data-ttu-id="ad759-429">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="ad759-430">Escenario: subdominio comodín izquierdo y sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="ad759-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="ad759-431">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="ad759-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="ad759-432">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="ad759-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ad759-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="ad759-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="ad759-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="ad759-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="ad759-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ad759-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="ad759-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="ad759-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="ad759-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="ad759-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="ad759-438">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ad759-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="ad759-439">Escenario: tilde izquierda y derecha</span><span class="sxs-lookup"><span data-stu-id="ad759-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="ad759-440">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="ad759-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="ad759-441">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="ad759-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ad759-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-442">contoso.com</span></span>
  - <span data-ttu-id="ad759-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="ad759-443">contoso.com/a</span></span>
  - <span data-ttu-id="ad759-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-444">www.contoso.com</span></span>
  - <span data-ttu-id="ad759-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="ad759-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="ad759-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="ad759-447">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="ad759-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ad759-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-448">123contoso.com</span></span>
  - <span data-ttu-id="ad759-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="ad759-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="ad759-450">Escenario: dirección IP</span><span class="sxs-lookup"><span data-stu-id="ad759-450">Scenario: IP address</span></span>

<span data-ttu-id="ad759-451">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="ad759-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="ad759-452">**Permitir coincidencia** y **Bloquear coincidencia**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ad759-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="ad759-453">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="ad759-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="ad759-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ad759-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="ad759-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="ad759-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="ad759-456">Dirección IP con comodín derecho</span><span class="sxs-lookup"><span data-stu-id="ad759-456">IP address with right wildcard</span></span>

<span data-ttu-id="ad759-457">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="ad759-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="ad759-458">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="ad759-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="ad759-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="ad759-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="ad759-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="ad759-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="ad759-461">Ejemplos de entradas no válidas</span><span class="sxs-lookup"><span data-stu-id="ad759-461">Examples of invalid entries</span></span>

<span data-ttu-id="ad759-462">Las siguientes entradas no son válidas:</span><span class="sxs-lookup"><span data-stu-id="ad759-462">The following entries are invalid:</span></span>

- <span data-ttu-id="ad759-463">**Faltan valores de dominio o no son válidos:**</span><span class="sxs-lookup"><span data-stu-id="ad759-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="ad759-464">contoso</span><span class="sxs-lookup"><span data-stu-id="ad759-464">contoso</span></span>
  - <span data-ttu-id="ad759-465">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="ad759-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="ad759-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="ad759-466">\*.com</span></span>
  - <span data-ttu-id="ad759-467">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="ad759-467">\*.pdf</span></span>

- <span data-ttu-id="ad759-468">**Comodín en el texto o sin caracteres de espaciado:**</span><span class="sxs-lookup"><span data-stu-id="ad759-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="ad759-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="ad759-469">\*contoso.com</span></span>
  - <span data-ttu-id="ad759-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="ad759-470">contoso.com\*</span></span>
  - <span data-ttu-id="ad759-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="ad759-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="ad759-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="ad759-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="ad759-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="ad759-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="ad759-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="ad759-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="ad759-475">**Direcciones IP con puertos**:</span><span class="sxs-lookup"><span data-stu-id="ad759-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="ad759-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="ad759-476">contoso.com:443</span></span>
  - <span data-ttu-id="ad759-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="ad759-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="ad759-478">**Caracteres comodín no descriptivos:**</span><span class="sxs-lookup"><span data-stu-id="ad759-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="ad759-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="ad759-479">\*.\*</span></span>

- <span data-ttu-id="ad759-480">**Caracteres comodín intermedios**:</span><span class="sxs-lookup"><span data-stu-id="ad759-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="ad759-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="ad759-481">conto\*so.com</span></span>
  - <span data-ttu-id="ad759-482">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="ad759-482">conto~so.com</span></span>

- <span data-ttu-id="ad759-483">**Caracteres comodín dobles**</span><span class="sxs-lookup"><span data-stu-id="ad759-483">**Double wildcards**</span></span>

  - <span data-ttu-id="ad759-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="ad759-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="ad759-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="ad759-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="ad759-486">Sintaxis de par de dominio para entradas de remitente suplantadas en la lista de inquilinos permitidos/bloqueados</span><span class="sxs-lookup"><span data-stu-id="ad759-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="ad759-487">Un par de dominio para un remitente suplantado en la lista de inquilinos permitidos o bloqueados usa la siguiente sintaxis: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="ad759-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="ad759-488">**Usuario suplantado:** este valor implica la dirección de correo electrónico del usuario  suplantado que se muestra en el cuadro De de los clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="ad759-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="ad759-489">Esta dirección también se conoce como `5322.From` la dirección.</span><span class="sxs-lookup"><span data-stu-id="ad759-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="ad759-490">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="ad759-490">Valid values include:</span></span>
  - <span data-ttu-id="ad759-491">Una dirección de correo electrónico individual (por ejemplo, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ad759-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="ad759-492">Un dominio de correo electrónico (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="ad759-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="ad759-493">El carácter comodín (por ejemplo, \* ).</span><span class="sxs-lookup"><span data-stu-id="ad759-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="ad759-494">**Infraestructura de** envío: este valor indica el origen de los mensajes del usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="ad759-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="ad759-495">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="ad759-495">Valid values include:</span></span>
  - <span data-ttu-id="ad759-496">El dominio encontrado en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen (por ejemplo, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="ad759-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="ad759-497">Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="ad759-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="ad759-498">Estos son algunos ejemplos de pares de dominio válidos para identificar remitentes suplantados:</span><span class="sxs-lookup"><span data-stu-id="ad759-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="ad759-499">Agregar un par de dominio solo permite o bloquea *la* combinación del usuario suplantado *y la* infraestructura de envío.</span><span class="sxs-lookup"><span data-stu-id="ad759-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="ad759-500">No permite el correo electrónico del usuario suplantado de ningún origen, ni permite el correo electrónico del origen de la infraestructura de envío para ningún usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="ad759-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="ad759-501">Por ejemplo, agrega una entrada allow para el siguiente par de dominio:</span><span class="sxs-lookup"><span data-stu-id="ad759-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="ad759-502">**Dominio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="ad759-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="ad759-503">**Infraestructura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="ad759-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="ad759-504">Solo los mensajes de ese dominio *y* el par de infraestructura de envío pueden suplantación.</span><span class="sxs-lookup"><span data-stu-id="ad759-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="ad759-505">Otros remitentes que intentan suplantar gmail.com no están permitidos.</span><span class="sxs-lookup"><span data-stu-id="ad759-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="ad759-506">Los mensajes de remitentes de otros dominios que se originaron tms.mx.com se comprueban mediante la inteligencia de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="ad759-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
