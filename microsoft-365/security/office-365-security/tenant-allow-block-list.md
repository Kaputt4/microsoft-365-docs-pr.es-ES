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
ms.openlocfilehash: 12139708fc5cde133819713fd7185435e594a1a9
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809184"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-103">Administrar la lista de permitidos o bloqueados del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="510ae-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="510ae-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="510ae-104">**Applies to**</span></span>
- [<span data-ttu-id="510ae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="510ae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="510ae-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="510ae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="510ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="510ae-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="510ae-108">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="510ae-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="510ae-109">Si su organización no tiene las características de suplantación de identidad como se describe en este artículo, vea la experiencia de administración de suplantación de identidad anterior en [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="510ae-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="510ae-110">No puede configurar la dirección URL o **los** elementos de archivo permitidos en la lista de inquilinos permitidos o bloqueados en este momento.</span><span class="sxs-lookup"><span data-stu-id="510ae-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="510ae-111">En Microsoft 365 organizaciones con buzones de correo en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="510ae-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="510ae-112">Por ejemplo, un mensaje bueno puede marcarse como malo (un falso positivo) o un mensaje malo se puede permitir a través (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="510ae-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="510ae-113">La lista de inquilinos permitidos o bloqueados en el Centro de seguridad & cumplimiento le ofrece una forma de invalidar manualmente los Microsoft 365 de filtrado.</span><span class="sxs-lookup"><span data-stu-id="510ae-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="510ae-114">La lista de inquilinos permitidos o bloqueados se usa durante el flujo de correo y en el momento de los clics del usuario.</span><span class="sxs-lookup"><span data-stu-id="510ae-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="510ae-115">Puede especificar los siguientes tipos de invalidaciones:</span><span class="sxs-lookup"><span data-stu-id="510ae-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="510ae-116">Direcciones URL que se bloquearán.</span><span class="sxs-lookup"><span data-stu-id="510ae-116">URLs to block.</span></span>
- <span data-ttu-id="510ae-117">Archivos que se va a bloquear.</span><span class="sxs-lookup"><span data-stu-id="510ae-117">Files to block.</span></span>
- <span data-ttu-id="510ae-118">Remitentes suplantados para permitir o bloquear.</span><span class="sxs-lookup"><span data-stu-id="510ae-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="510ae-119">Si invalida el veredicto permitir o bloquear en la información de inteligencia suplantada, el remitente  suplantado se convierte en una entrada manual de permitir o bloquear que solo aparece en la pestaña Suplantación de identidad de la lista de permitidos o bloqueados del inquilino. [](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="510ae-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="510ae-120">También puede crear entradas de permitir o bloquear manualmente para remitentes suplantados aquí antes de que los detecte la inteligencia de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="510ae-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="510ae-121">En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="510ae-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="510ae-122">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="510ae-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="510ae-123">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="510ae-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="510ae-124">Para ir directamente a la página **Lista de inquilinos permitidos o bloqueados,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="510ae-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="510ae-125">Los archivos se especifican mediante el valor hash SHA256 del archivo.</span><span class="sxs-lookup"><span data-stu-id="510ae-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="510ae-126">Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="510ae-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="510ae-127">Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="510ae-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="510ae-128">No se admiten valores de hash perceptual (pHash).</span><span class="sxs-lookup"><span data-stu-id="510ae-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="510ae-129">Los valores de dirección URL disponibles se describen en la sintaxis url de la sección Lista de [inquilinos permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="510ae-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="510ae-130">La lista de inquilinos permitidos o bloqueados permite un máximo de 500 entradas para direcciones URL y 500 entradas para hashes de archivo.</span><span class="sxs-lookup"><span data-stu-id="510ae-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="510ae-131">El número máximo de caracteres para cada entrada es:</span><span class="sxs-lookup"><span data-stu-id="510ae-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="510ae-132">Hashes de archivo = 64</span><span class="sxs-lookup"><span data-stu-id="510ae-132">File hashes = 64</span></span>
  - <span data-ttu-id="510ae-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="510ae-133">URL = 250</span></span>

- <span data-ttu-id="510ae-134">Una entrada debe estar activa en 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="510ae-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="510ae-135">De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="510ae-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="510ae-136">Puede especificar una fecha o establecerla para que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="510ae-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="510ae-137">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="510ae-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="510ae-138">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="510ae-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="510ae-139">Debe tener permisos asignados en Exchange Online antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="510ae-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="510ae-140">**Direcciones URL y archivos:**</span><span class="sxs-lookup"><span data-stu-id="510ae-140">**URLs and files**:</span></span>
    - <span data-ttu-id="510ae-141">Para agregar y quitar valores de la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="510ae-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="510ae-142">Para obtener acceso de solo lectura a la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="510ae-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="510ae-143">**Suplantación:** una de las siguientes combinaciones:</span><span class="sxs-lookup"><span data-stu-id="510ae-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="510ae-144">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="510ae-144">**Organization Management**</span></span>
    - <span data-ttu-id="510ae-145">**Administrador de seguridad** <u>y</u> **Configuración de solo vista** o Administración de la organización de solo **vista**.</span><span class="sxs-lookup"><span data-stu-id="510ae-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="510ae-146">Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="510ae-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="510ae-147">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="510ae-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="510ae-148">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="510ae-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="510ae-149">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="510ae-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-150">Usar el Centro de seguridad & cumplimiento para crear entradas de dirección URL de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="510ae-151">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="510ae-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="510ae-152">En la **página Lista de inquilinos permitidos o** bloqueados, compruebe que la pestaña **Direcciones** URL está seleccionada y, a continuación, haga clic en **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="510ae-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="510ae-153">En el **menú desplegable Bloquear direcciones URL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="510ae-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="510ae-154">**Agregar direcciones URL para bloquear:** escriba una dirección URL por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="510ae-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="510ae-155">Para obtener más información acerca de la sintaxis de las entradas de dirección URL, vea la sintaxis de dirección URL de la sección Lista de [permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados del espacio empresarial más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="510ae-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="510ae-156">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="510ae-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="510ae-157">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="510ae-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="510ae-158">o</span><span class="sxs-lookup"><span data-stu-id="510ae-158">or</span></span>

     - <span data-ttu-id="510ae-159">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="510ae-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="510ae-161">.</span><span class="sxs-lookup"><span data-stu-id="510ae-161">.</span></span>

   - <span data-ttu-id="510ae-162">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="510ae-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="510ae-163">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="510ae-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-164">Usar el Centro de seguridad & cumplimiento para crear entradas de archivo de bloqueo en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="510ae-165">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="510ae-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="510ae-166">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la **pestaña** Archivos y, a continuación, haga clic en **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="510ae-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="510ae-167">En el menú desplegable **Agregar archivos** para bloquear que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="510ae-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="510ae-168">**Agregar hash de archivo:** escriba un valor hash SHA256 por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="510ae-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="510ae-169">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="510ae-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="510ae-170">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Expira en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="510ae-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="510ae-171">o</span><span class="sxs-lookup"><span data-stu-id="510ae-171">or</span></span>

     - <span data-ttu-id="510ae-172">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="510ae-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="510ae-174">.</span><span class="sxs-lookup"><span data-stu-id="510ae-174">.</span></span>

   - <span data-ttu-id="510ae-175">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="510ae-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="510ae-176">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="510ae-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-177">Usar el Centro de seguridad & cumplimiento para crear entradas de remitente suplantadas de identidad o de bloqueo en la lista de permitidos o bloqueados de inquilinos</span><span class="sxs-lookup"><span data-stu-id="510ae-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-178">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="510ae-178">**Notes**:</span></span>

- <span data-ttu-id="510ae-179">Solo se _permite o_ bloquea  específicamente la combinación del usuario suplantado y la infraestructura de envío definida en el par de dominio.</span><span class="sxs-lookup"><span data-stu-id="510ae-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="510ae-180">Al configurar una entrada de permitir o bloquear para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la información de inteligencia suplantación.</span><span class="sxs-lookup"><span data-stu-id="510ae-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="510ae-181">Las entradas de remitentes suplantados nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="510ae-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="510ae-182">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="510ae-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="510ae-183">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la pestaña **Suplantación** y, a continuación, haga clic **en Agregar**.</span><span class="sxs-lookup"><span data-stu-id="510ae-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="510ae-184">En el **menú desplegable Agregar nuevos pares de** dominio que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="510ae-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="510ae-185">**Agregar nuevos pares de dominio con caracteres comodín:** escriba un par de dominio por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="510ae-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="510ae-186">Para obtener más información acerca de la sintaxis de las entradas de remitente suplantadas, vea la sintaxis del par de dominios para las entradas de remitente suplantadas en la sección Lista de [permitidos/bloqueados](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) del espacio empresarial más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="510ae-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="510ae-187">**Tipo de suplantación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="510ae-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="510ae-188">**Interno:** el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="510ae-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="510ae-189">**Externo:** el remitente suplantado está en un dominio externo.</span><span class="sxs-lookup"><span data-stu-id="510ae-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="510ae-190">**Acción:** seleccione **Permitir** o **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="510ae-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="510ae-191">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="510ae-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-192">Usar el Centro de seguridad & cumplimiento para ver entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="510ae-193">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="510ae-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="510ae-194">Seleccione la pestaña que desee.</span><span class="sxs-lookup"><span data-stu-id="510ae-194">Select the tab you want.</span></span> <span data-ttu-id="510ae-195">Las columnas disponibles dependen de la pestaña seleccionada:</span><span class="sxs-lookup"><span data-stu-id="510ae-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="510ae-196">**DIRECCIONES URL:**</span><span class="sxs-lookup"><span data-stu-id="510ae-196">**URLs**:</span></span>
     - <span data-ttu-id="510ae-197">**Value**: La dirección URL.</span><span class="sxs-lookup"><span data-stu-id="510ae-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="510ae-198">**Action**: El valor **Block**.</span><span class="sxs-lookup"><span data-stu-id="510ae-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="510ae-199">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="510ae-199">**Last updated date**</span></span>
     - <span data-ttu-id="510ae-200">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="510ae-200">**Expiration date**</span></span>
     - <span data-ttu-id="510ae-201">**Nota**</span><span class="sxs-lookup"><span data-stu-id="510ae-201">**Note**</span></span>

   - <span data-ttu-id="510ae-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="510ae-202">**Files**</span></span>
     - <span data-ttu-id="510ae-203">**Valor:** hash de archivo.</span><span class="sxs-lookup"><span data-stu-id="510ae-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="510ae-204">**Action**: El valor **Block**.</span><span class="sxs-lookup"><span data-stu-id="510ae-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="510ae-205">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="510ae-205">**Last updated date**</span></span>
     - <span data-ttu-id="510ae-206">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="510ae-206">**Expiration date**</span></span>
     - <span data-ttu-id="510ae-207">**Nota**</span><span class="sxs-lookup"><span data-stu-id="510ae-207">**Note**</span></span>

   - <span data-ttu-id="510ae-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="510ae-208">**Spoofing**</span></span>
     - <span data-ttu-id="510ae-209">**Usuario suplantado**</span><span class="sxs-lookup"><span data-stu-id="510ae-209">**Spoofed user**</span></span>
     - <span data-ttu-id="510ae-210">**Infraestructura de envío**</span><span class="sxs-lookup"><span data-stu-id="510ae-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="510ae-211">**Tipo de suplantación:** el **valor Interno** o **Externo**.</span><span class="sxs-lookup"><span data-stu-id="510ae-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="510ae-212">**Action:** el valor **Block** o **Allow**.</span><span class="sxs-lookup"><span data-stu-id="510ae-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="510ae-213">Puede hacer clic en un encabezado de columna para ordenar en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="510ae-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="510ae-214">Puede hacer clic **en Grupo** para agrupar los resultados.</span><span class="sxs-lookup"><span data-stu-id="510ae-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="510ae-215">Los valores disponibles dependen de la pestaña seleccionada:</span><span class="sxs-lookup"><span data-stu-id="510ae-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="510ae-216">**DIRECCIONES URL:** puede agrupar los resultados por **Acción**.</span><span class="sxs-lookup"><span data-stu-id="510ae-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="510ae-217">**Archivos:** puede agrupar los resultados por **Acción**.</span><span class="sxs-lookup"><span data-stu-id="510ae-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="510ae-218">**Dominios de remitente para la omisión de BCL:** **el** grupo no está disponible en esta pestaña.</span><span class="sxs-lookup"><span data-stu-id="510ae-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="510ae-219">**Suplantación:** puede agrupar los resultados por **tipo Action** o **Spoof**.</span><span class="sxs-lookup"><span data-stu-id="510ae-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="510ae-220">Haga **clic en** Buscar, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico.</span><span class="sxs-lookup"><span data-stu-id="510ae-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="510ae-221">Cuando haya terminado, haga clic en **Borrar búsqueda** Borrar icono ![ de ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) búsqueda.</span><span class="sxs-lookup"><span data-stu-id="510ae-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="510ae-222">Haga **clic en** Filtrar para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="510ae-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="510ae-223">Los valores que están disponibles en **el** control desplegable Filtro que aparece dependen de la pestaña seleccionada:</span><span class="sxs-lookup"><span data-stu-id="510ae-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="510ae-224">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="510ae-224">**URLs**</span></span>
     - <span data-ttu-id="510ae-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="510ae-225">**Action**</span></span>
     - <span data-ttu-id="510ae-226">**No expirar nunca**</span><span class="sxs-lookup"><span data-stu-id="510ae-226">**Never expire**</span></span>
     - <span data-ttu-id="510ae-227">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="510ae-227">**Last updated date**</span></span>
     - <span data-ttu-id="510ae-228">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="510ae-228">**Expiration date**</span></span>

   - <span data-ttu-id="510ae-229">**Files**</span><span class="sxs-lookup"><span data-stu-id="510ae-229">**Files**</span></span>
     - <span data-ttu-id="510ae-230">**Action**</span><span class="sxs-lookup"><span data-stu-id="510ae-230">**Action**</span></span>
     - <span data-ttu-id="510ae-231">**No expirar nunca**</span><span class="sxs-lookup"><span data-stu-id="510ae-231">**Never expire**</span></span>
     - <span data-ttu-id="510ae-232">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="510ae-232">**Last updated date**</span></span>
     - <span data-ttu-id="510ae-233">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="510ae-233">**Expiration date**</span></span>

   - <span data-ttu-id="510ae-234">**Dominios de remitente para la omisión de BCL**</span><span class="sxs-lookup"><span data-stu-id="510ae-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="510ae-235">**No expirar nunca**</span><span class="sxs-lookup"><span data-stu-id="510ae-235">**Never expire**</span></span>
     - <span data-ttu-id="510ae-236">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="510ae-236">**Last updated date**</span></span>
     - <span data-ttu-id="510ae-237">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="510ae-237">**Expiration date**</span></span>

   - <span data-ttu-id="510ae-238">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="510ae-238">**Spoofing**</span></span>
     - <span data-ttu-id="510ae-239">**Action**</span><span class="sxs-lookup"><span data-stu-id="510ae-239">**Action**</span></span>
     - <span data-ttu-id="510ae-240">**Tipo de suplantación**</span><span class="sxs-lookup"><span data-stu-id="510ae-240">**Spoof type**</span></span>

   <span data-ttu-id="510ae-241">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="510ae-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="510ae-242">Para borrar los filtros existentes, haga clic **en Filtrar** y, en el **menú** desplegable Filtro que aparece, haga clic en **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="510ae-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-243">Usar el Centro de seguridad & cumplimiento para modificar las entradas de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="510ae-244">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="510ae-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="510ae-245">Seleccione la pestaña que contiene el tipo de entrada que desea modificar:</span><span class="sxs-lookup"><span data-stu-id="510ae-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="510ae-246">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="510ae-246">**URLs**</span></span>
   - <span data-ttu-id="510ae-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="510ae-247">**Files**</span></span>
   - <span data-ttu-id="510ae-248">**Dominios de remitente para la omisión de BCL**</span><span class="sxs-lookup"><span data-stu-id="510ae-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="510ae-249">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="510ae-249">**Spoofing**</span></span>

3. <span data-ttu-id="510ae-250">Seleccione la entrada que desea modificar y, a continuación, haga clic **en Editar** icono ![ Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="510ae-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="510ae-251">Los valores que puede modificar en el control desplegable que aparece dependen de la pestaña seleccionada en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="510ae-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="510ae-252">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="510ae-252">**URLs**</span></span>
     - <span data-ttu-id="510ae-253">**No expire nunca** ni la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="510ae-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="510ae-254">**Nota opcional**</span><span class="sxs-lookup"><span data-stu-id="510ae-254">**Optional note**</span></span>

   - <span data-ttu-id="510ae-255">**Files**</span><span class="sxs-lookup"><span data-stu-id="510ae-255">**Files**</span></span>
     - <span data-ttu-id="510ae-256">**No expire nunca** ni la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="510ae-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="510ae-257">**Nota opcional**</span><span class="sxs-lookup"><span data-stu-id="510ae-257">**Optional note**</span></span>

   - <span data-ttu-id="510ae-258">**Dominios de remitente para la omisión de BCL**</span><span class="sxs-lookup"><span data-stu-id="510ae-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="510ae-259">**No expire nunca** ni la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="510ae-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="510ae-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="510ae-260">**Spoofing**</span></span>
     - <span data-ttu-id="510ae-261">**Acción:** puede cambiar el valor a **Permitir** o **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="510ae-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="510ae-262">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="510ae-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-263">Usar el Centro de & seguridad para quitar entradas de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="510ae-264">En el Centro de seguridad & cumplimiento, vaya a **Administración** de amenazas Directivas \>  \> **permitir/bloquear listas de inquilinos.**</span><span class="sxs-lookup"><span data-stu-id="510ae-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="510ae-265">Seleccione la pestaña que contiene el tipo de entrada que desea quitar:</span><span class="sxs-lookup"><span data-stu-id="510ae-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="510ae-266">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="510ae-266">**URLs**</span></span>
   - <span data-ttu-id="510ae-267">**Files**</span><span class="sxs-lookup"><span data-stu-id="510ae-267">**Files**</span></span>
   - <span data-ttu-id="510ae-268">**Dominios de remitente para la omisión de BCL**</span><span class="sxs-lookup"><span data-stu-id="510ae-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="510ae-269">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="510ae-269">**Spoofing**</span></span>

3. <span data-ttu-id="510ae-270">Seleccione la entrada que desea quitar y, a continuación, haga clic **en Eliminar** icono ![ Eliminar ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="510ae-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="510ae-271">En el cuadro de diálogo de advertencia que aparece, haga clic **en Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="510ae-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-272">Use Exchange Online PowerShell o PowerShell de EOP independiente para configurar la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-273">Usar PowerShell para agregar entradas de dirección URL o archivo de bloque a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-274">Para agregar entradas de dirección URL o archivo de bloque en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="510ae-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="510ae-275">En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="510ae-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="510ae-276">En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="510ae-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="510ae-277">Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="510ae-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="510ae-278">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="510ae-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-279">Usar PowerShell para agregar entradas de remitente suplantadas de identidad o bloquear a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-280">Para agregar entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="510ae-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="510ae-281">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="510ae-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-282">Usar PowerShell para ver entradas de direcciones URL o archivos bloqueados en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-283">Para ver entradas de direcciones URL o archivos bloqueados en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="510ae-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="510ae-284">En este ejemplo se devuelve información sobre el valor hash de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="510ae-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="510ae-285">En este ejemplo se devuelven todas las direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="510ae-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="510ae-286">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="510ae-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-287">Usar PowerShell para ver o bloquear entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-288">Para ver entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="510ae-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="510ae-289">En este ejemplo se devuelven todas las entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="510ae-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="510ae-290">En este ejemplo se devuelven todas las entradas de remitente suplantadas que son internas.</span><span class="sxs-lookup"><span data-stu-id="510ae-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="510ae-291">En este ejemplo se devuelven todas las entradas de remitente suplantadas bloqueadas que son externas.</span><span class="sxs-lookup"><span data-stu-id="510ae-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="510ae-292">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="510ae-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-293">Usar PowerShell para modificar entradas de direcciones URL y archivos de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-294">Para modificar entradas de archivos de bloque y direcciones URL en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="510ae-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="510ae-295">En este ejemplo se cambia la fecha de expiración de la entrada de dirección URL de bloque especificada.</span><span class="sxs-lookup"><span data-stu-id="510ae-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="510ae-296">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="510ae-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-297">Usar PowerShell para modificar entradas de remitente suplantadas o de permitir en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-298">Para modificar permitir o bloquear entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="510ae-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="510ae-299">En este ejemplo se cambia la entrada de remitente suplantada de permitir a bloquear.</span><span class="sxs-lookup"><span data-stu-id="510ae-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="510ae-300">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="510ae-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-301">Usar PowerShell para quitar direcciones URL o entradas de archivo de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-302">Para quitar entradas de archivos y direcciones URL de la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="510ae-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="510ae-303">En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de inquilinos permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="510ae-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="510ae-304">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="510ae-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-305">Usar PowerShell para quitar o bloquear entradas de remitente suplantados de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-306">Para quitar entradas de remitente de suplantación de identidad de la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="510ae-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="510ae-307">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="510ae-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-308">Sintaxis de dirección URL para la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="510ae-309">Las direcciones IP4v e IPv6 están permitidas, pero los puertos TCP/UDP no.</span><span class="sxs-lookup"><span data-stu-id="510ae-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="510ae-310">No se permiten extensiones de nombre de archivo (por ejemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="510ae-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="510ae-311">Unicode no es compatible, pero Punycode lo es.</span><span class="sxs-lookup"><span data-stu-id="510ae-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="510ae-312">Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="510ae-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="510ae-313">El nombre de host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="510ae-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="510ae-314">Hay al menos un carácter a la izquierda del punto.</span><span class="sxs-lookup"><span data-stu-id="510ae-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="510ae-315">Hay al menos dos caracteres a la derecha del punto.</span><span class="sxs-lookup"><span data-stu-id="510ae-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="510ae-316">Por ejemplo, `t.co` se permite; `.com` o no `contoso.` se permite.</span><span class="sxs-lookup"><span data-stu-id="510ae-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="510ae-317">Las subpaths no están implícitas.</span><span class="sxs-lookup"><span data-stu-id="510ae-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="510ae-318">Por ejemplo, `contoso.com` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="510ae-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="510ae-319">Los caracteres comodín (\*) se permiten en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="510ae-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="510ae-320">Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.</span><span class="sxs-lookup"><span data-stu-id="510ae-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="510ae-321">Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="510ae-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="510ae-322">Un comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="510ae-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="510ae-323">Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o no `contoso.com/ab*` se permite.</span><span class="sxs-lookup"><span data-stu-id="510ae-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="510ae-324">Todas las subpaths no están implícitas por un comodín derecho.</span><span class="sxs-lookup"><span data-stu-id="510ae-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="510ae-325">Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="510ae-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="510ae-326">`*.com*` no es válido (no es un dominio resolvible y el comodín derecho no sigue una barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="510ae-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="510ae-327">Los caracteres comodín no están permitidos en las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="510ae-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="510ae-328">El carácter tilde (~) está disponible en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="510ae-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="510ae-329">Una tilde izquierda implica un dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="510ae-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="510ae-330">Por `~contoso.com` ejemplo, incluye `contoso.com` y `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="510ae-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="510ae-331">Se producirá un error en las entradas de dirección URL que contienen protocolos (por ejemplo, , o ) porque las entradas de dirección URL se `http://` aplican a todos los `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="510ae-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="510ae-332">No se admite ni se requiere un nombre de usuario o contraseña.</span><span class="sxs-lookup"><span data-stu-id="510ae-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="510ae-333">Las comillas (' o ") son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="510ae-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="510ae-334">Una dirección URL debe incluir todas las redirecciones siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="510ae-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="510ae-335">Escenarios de entrada de dirección URL</span><span class="sxs-lookup"><span data-stu-id="510ae-335">URL entry scenarios</span></span>

<span data-ttu-id="510ae-336">Las entradas de dirección URL válidas y sus resultados se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="510ae-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="510ae-337">Escenario: sin caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="510ae-337">Scenario: No wildcards</span></span>

<span data-ttu-id="510ae-338">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="510ae-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="510ae-339">**Permitir coincidencia**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="510ae-340">**Permitir que no coincida**:</span><span class="sxs-lookup"><span data-stu-id="510ae-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="510ae-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-341">abc-contoso.com</span></span>
  - <span data-ttu-id="510ae-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="510ae-342">contoso.com/a</span></span>
  - <span data-ttu-id="510ae-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="510ae-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="510ae-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="510ae-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-346">www.contoso.com</span></span>
  - <span data-ttu-id="510ae-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="510ae-348">**Bloquear coincidencia**:</span><span class="sxs-lookup"><span data-stu-id="510ae-348">**Block match**:</span></span>

  - <span data-ttu-id="510ae-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-349">contoso.com</span></span>
  - <span data-ttu-id="510ae-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="510ae-350">contoso.com/a</span></span>
  - <span data-ttu-id="510ae-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="510ae-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="510ae-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="510ae-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-354">www.contoso.com</span></span>
  - <span data-ttu-id="510ae-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="510ae-356">**Bloque no coincidente:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="510ae-357">Escenario: comodín izquierdo (subdominio)</span><span class="sxs-lookup"><span data-stu-id="510ae-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="510ae-358">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="510ae-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="510ae-359">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="510ae-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="510ae-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-360">www.contoso.com</span></span>
  - <span data-ttu-id="510ae-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="510ae-362">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="510ae-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="510ae-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-363">123contoso.com</span></span>
  - <span data-ttu-id="510ae-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-364">contoso.com</span></span>
  - <span data-ttu-id="510ae-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="510ae-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="510ae-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="510ae-367">Escenario: comodín derecho en la parte superior de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="510ae-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="510ae-368">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="510ae-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="510ae-369">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="510ae-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="510ae-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="510ae-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="510ae-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="510ae-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="510ae-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="510ae-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="510ae-373">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="510ae-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="510ae-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-374">contoso.com</span></span>
  - <span data-ttu-id="510ae-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="510ae-375">contoso.com/a</span></span>
  - <span data-ttu-id="510ae-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-376">www.contoso.com</span></span>
  - <span data-ttu-id="510ae-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="510ae-378">Escenario: tilde izquierda</span><span class="sxs-lookup"><span data-stu-id="510ae-378">Scenario: Left tilde</span></span>

<span data-ttu-id="510ae-379">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="510ae-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="510ae-380">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="510ae-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="510ae-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-381">contoso.com</span></span>
  - <span data-ttu-id="510ae-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-382">www.contoso.com</span></span>
  - <span data-ttu-id="510ae-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="510ae-384">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="510ae-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="510ae-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-385">123contoso.com</span></span>
  - <span data-ttu-id="510ae-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="510ae-386">contoso.com/abc</span></span>
  - <span data-ttu-id="510ae-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="510ae-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="510ae-388">Escenario: sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="510ae-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="510ae-389">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="510ae-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="510ae-390">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="510ae-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="510ae-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="510ae-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="510ae-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="510ae-392">contoso.com/a</span></span>
  - <span data-ttu-id="510ae-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="510ae-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="510ae-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="510ae-394">contoso.com/ab</span></span>
  - <span data-ttu-id="510ae-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="510ae-395">contoso.com/b</span></span>
  - <span data-ttu-id="510ae-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="510ae-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="510ae-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="510ae-397">contoso.com/ba</span></span>

- <span data-ttu-id="510ae-398">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="510ae-399">Escenario: subdominio comodín izquierdo y sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="510ae-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="510ae-400">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="510ae-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="510ae-401">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="510ae-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="510ae-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="510ae-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="510ae-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="510ae-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="510ae-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="510ae-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="510ae-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="510ae-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="510ae-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="510ae-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="510ae-407">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="510ae-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="510ae-408">Escenario: tilde izquierda y derecha</span><span class="sxs-lookup"><span data-stu-id="510ae-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="510ae-409">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="510ae-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="510ae-410">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="510ae-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="510ae-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-411">contoso.com</span></span>
  - <span data-ttu-id="510ae-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="510ae-412">contoso.com/a</span></span>
  - <span data-ttu-id="510ae-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-413">www.contoso.com</span></span>
  - <span data-ttu-id="510ae-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="510ae-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="510ae-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="510ae-416">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="510ae-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="510ae-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-417">123contoso.com</span></span>
  - <span data-ttu-id="510ae-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="510ae-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="510ae-419">Escenario: dirección IP</span><span class="sxs-lookup"><span data-stu-id="510ae-419">Scenario: IP address</span></span>

<span data-ttu-id="510ae-420">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="510ae-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="510ae-421">**Permitir coincidencia** y **Bloquear coincidencia**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="510ae-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="510ae-422">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="510ae-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="510ae-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="510ae-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="510ae-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="510ae-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="510ae-425">Dirección IP con comodín derecho</span><span class="sxs-lookup"><span data-stu-id="510ae-425">IP address with right wildcard</span></span>

<span data-ttu-id="510ae-426">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="510ae-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="510ae-427">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="510ae-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="510ae-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="510ae-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="510ae-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="510ae-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="510ae-430">Ejemplos de entradas no válidas</span><span class="sxs-lookup"><span data-stu-id="510ae-430">Examples of invalid entries</span></span>

<span data-ttu-id="510ae-431">Las siguientes entradas no son válidas:</span><span class="sxs-lookup"><span data-stu-id="510ae-431">The following entries are invalid:</span></span>

- <span data-ttu-id="510ae-432">**Faltan valores de dominio o no son válidos:**</span><span class="sxs-lookup"><span data-stu-id="510ae-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="510ae-433">contoso</span><span class="sxs-lookup"><span data-stu-id="510ae-433">contoso</span></span>
  - <span data-ttu-id="510ae-434">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="510ae-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="510ae-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="510ae-435">\*.com</span></span>
  - <span data-ttu-id="510ae-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="510ae-436">\*.pdf</span></span>

- <span data-ttu-id="510ae-437">**Comodín en el texto o sin caracteres de espaciado:**</span><span class="sxs-lookup"><span data-stu-id="510ae-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="510ae-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="510ae-438">\*contoso.com</span></span>
  - <span data-ttu-id="510ae-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="510ae-439">contoso.com\*</span></span>
  - <span data-ttu-id="510ae-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="510ae-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="510ae-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="510ae-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="510ae-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="510ae-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="510ae-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="510ae-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="510ae-444">**Direcciones IP con puertos**:</span><span class="sxs-lookup"><span data-stu-id="510ae-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="510ae-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="510ae-445">contoso.com:443</span></span>
  - <span data-ttu-id="510ae-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="510ae-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="510ae-447">**Caracteres comodín no descriptivos:**</span><span class="sxs-lookup"><span data-stu-id="510ae-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="510ae-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="510ae-448">\*.\*</span></span>

- <span data-ttu-id="510ae-449">**Caracteres comodín intermedios**:</span><span class="sxs-lookup"><span data-stu-id="510ae-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="510ae-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="510ae-450">conto\*so.com</span></span>
  - <span data-ttu-id="510ae-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="510ae-451">conto~so.com</span></span>

- <span data-ttu-id="510ae-452">**Caracteres comodín dobles**</span><span class="sxs-lookup"><span data-stu-id="510ae-452">**Double wildcards**</span></span>

  - <span data-ttu-id="510ae-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="510ae-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="510ae-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="510ae-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="510ae-455">Sintaxis de par de dominio para entradas de remitente suplantadas en la lista de inquilinos permitidos/bloqueados</span><span class="sxs-lookup"><span data-stu-id="510ae-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="510ae-456">Un par de dominio para un remitente suplantado en la lista de inquilinos permitidos o bloqueados usa la siguiente sintaxis: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="510ae-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="510ae-457">**Usuario suplantado:** este valor implica la dirección de correo electrónico del usuario  suplantado que se muestra en el cuadro De de los clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="510ae-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="510ae-458">Esta dirección también se conoce como `5322.From` la dirección.</span><span class="sxs-lookup"><span data-stu-id="510ae-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="510ae-459">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="510ae-459">Valid values include:</span></span>
  - <span data-ttu-id="510ae-460">Una dirección de correo electrónico individual (por ejemplo, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="510ae-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="510ae-461">Un dominio de correo electrónico (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="510ae-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="510ae-462">El carácter comodín (por ejemplo, \* ).</span><span class="sxs-lookup"><span data-stu-id="510ae-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="510ae-463">**Infraestructura de** envío: este valor indica el origen de los mensajes del usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="510ae-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="510ae-464">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="510ae-464">Valid values include:</span></span>
  - <span data-ttu-id="510ae-465">El dominio encontrado en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen (por ejemplo, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="510ae-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="510ae-466">Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="510ae-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="510ae-467">Estos son algunos ejemplos de pares de dominio válidos para identificar remitentes suplantados:</span><span class="sxs-lookup"><span data-stu-id="510ae-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="510ae-468">El número máximo de entradas de remitente suplantadas es 1000.</span><span class="sxs-lookup"><span data-stu-id="510ae-468">The maximum number of spoofed sender entries is 1000.</span></span> 

<span data-ttu-id="510ae-469">Agregar un par de dominio solo permite o bloquea *la* combinación del usuario suplantado *y la* infraestructura de envío.</span><span class="sxs-lookup"><span data-stu-id="510ae-469">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="510ae-470">No permite el correo electrónico del usuario suplantado de ningún origen, ni permite el correo electrónico del origen de la infraestructura de envío para ningún usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="510ae-470">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="510ae-471">Por ejemplo, agrega una entrada allow para el siguiente par de dominio:</span><span class="sxs-lookup"><span data-stu-id="510ae-471">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="510ae-472">**Dominio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="510ae-472">**Domain**: gmail.com</span></span>
- <span data-ttu-id="510ae-473">**Infraestructura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="510ae-473">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="510ae-474">Solo los mensajes de ese dominio *y* el par de infraestructura de envío pueden suplantación.</span><span class="sxs-lookup"><span data-stu-id="510ae-474">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="510ae-475">Otros remitentes que intentan suplantar gmail.com no están permitidos.</span><span class="sxs-lookup"><span data-stu-id="510ae-475">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="510ae-476">Los mensajes de remitentes de otros dominios que se originaron tms.mx.com se comprueban mediante la inteligencia de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="510ae-476">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
