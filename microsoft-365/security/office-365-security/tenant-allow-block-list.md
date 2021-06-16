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
ms.openlocfilehash: 67c3badb86f1cfb9bf644cc202ed67e3163a6772
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933160"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-103">Administrar la lista de permitidos o bloqueados del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="5433b-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5433b-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="5433b-104">**Applies to**</span></span>
- [<span data-ttu-id="5433b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5433b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5433b-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5433b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5433b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5433b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="5433b-108">Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="5433b-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="5433b-109">Si su organización no tiene las características de suplantación de identidad como se describe en este artículo, vea la experiencia de administración de suplantación de identidad anterior en [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="5433b-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="5433b-110">No puede configurar la dirección URL o **los** elementos de archivo permitidos en la lista de inquilinos permitidos o bloqueados en este momento.</span><span class="sxs-lookup"><span data-stu-id="5433b-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="5433b-111">En Microsoft 365 organizaciones con buzones de correo en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="5433b-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="5433b-112">Por ejemplo, un mensaje bueno puede marcarse como malo (un falso positivo) o un mensaje malo se puede permitir a través (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="5433b-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="5433b-113">La lista de inquilinos permitidos o bloqueados en el portal de Microsoft 365 Defender le ofrece una forma de invalidar manualmente los Microsoft 365 de filtrado.</span><span class="sxs-lookup"><span data-stu-id="5433b-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="5433b-114">La lista de inquilinos permitidos o bloqueados se usa durante el flujo de correo y en el momento de los clics del usuario.</span><span class="sxs-lookup"><span data-stu-id="5433b-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="5433b-115">Puede especificar los siguientes tipos de invalidaciones:</span><span class="sxs-lookup"><span data-stu-id="5433b-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="5433b-116">Direcciones URL que se bloquearán.</span><span class="sxs-lookup"><span data-stu-id="5433b-116">URLs to block.</span></span>
- <span data-ttu-id="5433b-117">Archivos que se va a bloquear.</span><span class="sxs-lookup"><span data-stu-id="5433b-117">Files to block.</span></span>
- <span data-ttu-id="5433b-118">Remitentes suplantados para permitir o bloquear.</span><span class="sxs-lookup"><span data-stu-id="5433b-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="5433b-119">Si invalida el veredicto permitir o bloquear en la información de inteligencia suplantada, el remitente  suplantado se convierte en una entrada manual de permitir o bloquear que solo aparece en la pestaña Suplantación de identidad de la lista de permitidos o bloqueados del inquilino. [](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="5433b-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="5433b-120">También puede crear entradas de permitir o bloquear manualmente para remitentes suplantados aquí antes de que los detecte la inteligencia de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5433b-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="5433b-121">En este artículo se describe cómo configurar entradas en la lista de inquilinos permitidos o bloqueados en el portal de Microsoft 365 Defender o en PowerShell (Exchange Online PowerShell para organizaciones de Microsoft 365 con buzones en Exchange Online; PowerShell de EOP independiente para organizaciones sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="5433b-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5433b-122">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="5433b-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5433b-123">Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="5433b-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="5433b-124">Para ir directamente a la página **Listas de inquilinos permitidos o** bloqueados, use <https://security.microsoft.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="5433b-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="5433b-125">Los archivos se especifican mediante el valor hash SHA256 del archivo.</span><span class="sxs-lookup"><span data-stu-id="5433b-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="5433b-126">Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="5433b-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="5433b-127">Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="5433b-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="5433b-128">No se admiten valores de hash perceptual (pHash).</span><span class="sxs-lookup"><span data-stu-id="5433b-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="5433b-129">Los valores de dirección URL disponibles se describen en la sintaxis url de la sección Lista de [inquilinos permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5433b-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="5433b-130">La lista de inquilinos permitidos o bloqueados permite un máximo de 500 entradas para direcciones URL y 500 entradas para hashes de archivo.</span><span class="sxs-lookup"><span data-stu-id="5433b-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="5433b-131">El número máximo de caracteres para cada entrada es:</span><span class="sxs-lookup"><span data-stu-id="5433b-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="5433b-132">Hashes de archivo = 64</span><span class="sxs-lookup"><span data-stu-id="5433b-132">File hashes = 64</span></span>
  - <span data-ttu-id="5433b-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="5433b-133">URL = 250</span></span>

- <span data-ttu-id="5433b-134">Una entrada debe estar activa en 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="5433b-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="5433b-135">De forma predeterminada, las entradas de la lista de inquilinos permitidos o bloqueados expirarán después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="5433b-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="5433b-136">Puede especificar una fecha o establecerla para que no expire nunca.</span><span class="sxs-lookup"><span data-stu-id="5433b-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="5433b-137">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5433b-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5433b-138">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="5433b-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5433b-139">Debe tener permisos asignados en Exchange Online antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="5433b-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="5433b-140">**Direcciones URL y archivos:**</span><span class="sxs-lookup"><span data-stu-id="5433b-140">**URLs and files**:</span></span>
    - <span data-ttu-id="5433b-141">Para agregar y quitar valores de la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="5433b-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="5433b-142">Para obtener acceso de solo lectura a la lista de inquilinos permitidos o bloqueados, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="5433b-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="5433b-143">**Suplantación:** una de las siguientes combinaciones:</span><span class="sxs-lookup"><span data-stu-id="5433b-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="5433b-144">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="5433b-144">**Organization Management**</span></span>
    - <span data-ttu-id="5433b-145">**Administrador de seguridad** <u>y</u> **Configuración de solo vista** o Administración de la organización de solo **vista**.</span><span class="sxs-lookup"><span data-stu-id="5433b-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="5433b-146">Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="5433b-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="5433b-147">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5433b-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5433b-148">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5433b-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="5433b-149">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="5433b-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-150">Usar el portal Microsoft 365 Defender para crear entradas de dirección URL de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5433b-151">En el portal Microsoft 365 Defender, vaya a **Directivas &** de reglas de amenazas Sección Reglas de directivas de amenazas. \>  \>  \> </span><span class="sxs-lookup"><span data-stu-id="5433b-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5433b-152">En la **página Lista de inquilinos permitidos o** bloqueados, compruebe que la pestaña **Direcciones** URL está seleccionada y, a continuación, haga clic en Bloquear ![ icono ](../../media/m365-cc-sc-create-icon.png) **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="5433b-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="5433b-153">En el **menú desplegable Bloquear direcciones URL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5433b-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="5433b-154">**Agregar direcciones URL con caracteres comodín:** escriba una dirección URL por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="5433b-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="5433b-155">Para obtener más información acerca de la sintaxis de las entradas de dirección URL, vea la sintaxis de dirección URL de la sección Lista de [permitidos o](#url-syntax-for-the-tenant-allowblock-list) bloqueados del espacio empresarial más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5433b-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="5433b-156">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5433b-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="5433b-157">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Quitar en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="5433b-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="5433b-158">o</span><span class="sxs-lookup"><span data-stu-id="5433b-158">or</span></span>

     - <span data-ttu-id="5433b-159">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="5433b-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="5433b-161">.</span><span class="sxs-lookup"><span data-stu-id="5433b-161">.</span></span>
   - <span data-ttu-id="5433b-162">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="5433b-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="5433b-163">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5433b-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-164">Usar el portal Microsoft 365 Defender para crear entradas de archivo de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5433b-165">En el portal Microsoft 365 Defender, vaya a **Directivas &** de reglas de amenazas Sección Reglas de directivas de amenazas. \>  \>  \> </span><span class="sxs-lookup"><span data-stu-id="5433b-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5433b-166">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la **pestaña** Archivos y, a continuación, haga clic en Bloquear ![ icono ](../../media/m365-cc-sc-create-icon.png) **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="5433b-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="5433b-167">En el menú desplegable **Bloquear** archivos que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5433b-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="5433b-168">**Agregar hash de archivo:** escriba un valor hash SHA256 por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="5433b-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="5433b-169">**Nunca expire:** realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="5433b-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="5433b-170">Compruebe que la configuración está desactivada ( Desactivar ) y use el cuadro Quitar en para especificar la fecha ![ ](../../media/scc-toggle-off.png) de expiración de las entradas. </span><span class="sxs-lookup"><span data-stu-id="5433b-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="5433b-171">o</span><span class="sxs-lookup"><span data-stu-id="5433b-171">or</span></span>

     - <span data-ttu-id="5433b-172">Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren:</span><span class="sxs-lookup"><span data-stu-id="5433b-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/scc-toggle-on.png)<span data-ttu-id="5433b-174">.</span><span class="sxs-lookup"><span data-stu-id="5433b-174">.</span></span>
   - <span data-ttu-id="5433b-175">**Nota opcional:** escriba texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="5433b-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="5433b-176">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5433b-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-177">Use el portal de Microsoft 365 Defender para crear entradas de remitente suplantadas de identidad en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-178">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="5433b-178">**Notes**:</span></span>

- <span data-ttu-id="5433b-179">Solo se _permite o_ bloquea  específicamente la combinación del usuario suplantado y la infraestructura de envío definida en el par de dominio.</span><span class="sxs-lookup"><span data-stu-id="5433b-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="5433b-180">Al configurar una entrada de permitir o bloquear para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la información de inteligencia suplantación.</span><span class="sxs-lookup"><span data-stu-id="5433b-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="5433b-181">Las entradas de remitentes suplantados nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="5433b-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="5433b-182">En el portal Microsoft 365 Defender, vaya a **Directivas &** de reglas de amenazas Sección Reglas de directivas de amenazas. \>  \>  \> </span><span class="sxs-lookup"><span data-stu-id="5433b-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5433b-183">En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la pestaña **Suplantación** y, a continuación, haga clic ![ en Bloquear icono ](../../media/m365-cc-sc-create-icon.png) **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5433b-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="5433b-184">En el **menú desplegable Agregar nuevos pares de** dominio que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5433b-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="5433b-185">**Agregar nuevos pares de dominio con caracteres comodín:** escriba un par de dominio por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="5433b-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="5433b-186">Para obtener más información acerca de la sintaxis de las entradas de remitente suplantadas, vea la sintaxis del par de dominios para las entradas de remitente suplantadas en la sección Lista de [permitidos/bloqueados](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) del espacio empresarial más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5433b-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="5433b-187">**Tipo de suplantación:** seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="5433b-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="5433b-188">**Interno:** el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="5433b-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="5433b-189">**Externo:** el remitente suplantado está en un dominio externo.</span><span class="sxs-lookup"><span data-stu-id="5433b-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="5433b-190">**Acción:** seleccione **Permitir** o **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="5433b-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="5433b-191">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5433b-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-192">Usar el portal Microsoft 365 Defender para ver entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5433b-193">En el portal Microsoft 365 Defender, vaya a **Directivas &** de reglas de amenazas Sección Reglas de directivas de amenazas. \>  \>  \> </span><span class="sxs-lookup"><span data-stu-id="5433b-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5433b-194">Seleccione la pestaña que desee.</span><span class="sxs-lookup"><span data-stu-id="5433b-194">Select the tab you want.</span></span> <span data-ttu-id="5433b-195">Las columnas disponibles dependen de la pestaña seleccionada:</span><span class="sxs-lookup"><span data-stu-id="5433b-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="5433b-196">**DIRECCIONES URL:**</span><span class="sxs-lookup"><span data-stu-id="5433b-196">**URLs**:</span></span>
     - <span data-ttu-id="5433b-197">**Value**: La dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5433b-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="5433b-198">**Action**: El valor **Block**.</span><span class="sxs-lookup"><span data-stu-id="5433b-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="5433b-199">**Actualizado por última vez**</span><span class="sxs-lookup"><span data-stu-id="5433b-199">**Last updated**</span></span>
     - <span data-ttu-id="5433b-200">**Quitar en**</span><span class="sxs-lookup"><span data-stu-id="5433b-200">**Remove on**</span></span>
     - <span data-ttu-id="5433b-201">**Notas**</span><span class="sxs-lookup"><span data-stu-id="5433b-201">**Notes**</span></span>
   - <span data-ttu-id="5433b-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="5433b-202">**Files**</span></span>
     - <span data-ttu-id="5433b-203">**Valor:** hash de archivo.</span><span class="sxs-lookup"><span data-stu-id="5433b-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="5433b-204">**Action**: El valor **Block**.</span><span class="sxs-lookup"><span data-stu-id="5433b-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="5433b-205">**Actualizado por última vez**</span><span class="sxs-lookup"><span data-stu-id="5433b-205">**Last updated**</span></span>
     - <span data-ttu-id="5433b-206">**Quitar en**</span><span class="sxs-lookup"><span data-stu-id="5433b-206">**Remove on**</span></span>
     - <span data-ttu-id="5433b-207">**Notas**</span><span class="sxs-lookup"><span data-stu-id="5433b-207">**Notes**</span></span>
   - <span data-ttu-id="5433b-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="5433b-208">**Spoofing**</span></span>
     - <span data-ttu-id="5433b-209">**Usuario suplantado**</span><span class="sxs-lookup"><span data-stu-id="5433b-209">**Spoofed user**</span></span>
     - <span data-ttu-id="5433b-210">**Infraestructura de envío**</span><span class="sxs-lookup"><span data-stu-id="5433b-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="5433b-211">**Tipo de suplantación:** el **valor Interno** o **Externo**.</span><span class="sxs-lookup"><span data-stu-id="5433b-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="5433b-212">**Action:** el valor **Block** o **Allow**.</span><span class="sxs-lookup"><span data-stu-id="5433b-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="5433b-213">Puede hacer clic en un encabezado de columna para ordenar en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="5433b-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="5433b-214">Puede hacer clic **en Grupo** para agrupar los resultados.</span><span class="sxs-lookup"><span data-stu-id="5433b-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="5433b-215">Los valores disponibles dependen de la pestaña seleccionada:</span><span class="sxs-lookup"><span data-stu-id="5433b-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="5433b-216">**DIRECCIONES URL:** puede agrupar los resultados por **Acción**.</span><span class="sxs-lookup"><span data-stu-id="5433b-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="5433b-217">**Archivos:** puede agrupar los resultados por **Acción**.</span><span class="sxs-lookup"><span data-stu-id="5433b-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="5433b-218">**Suplantación:** puede agrupar los resultados por **tipo Action** o **Spoof**.</span><span class="sxs-lookup"><span data-stu-id="5433b-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="5433b-219">Haga **clic en** Buscar, escriba todo o parte de un valor y, a continuación, presione ENTRAR para buscar un valor específico.</span><span class="sxs-lookup"><span data-stu-id="5433b-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="5433b-220">Cuando haya terminado, haga clic en ![ Borrar icono de búsqueda Borrar ](../../media/m365-cc-sc-close-icon.png) **búsqueda.**</span><span class="sxs-lookup"><span data-stu-id="5433b-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="5433b-221">Haga **clic en** Filtrar para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="5433b-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="5433b-222">Los valores que están disponibles en **el** control desplegable Filtro que aparece dependen de la pestaña seleccionada:</span><span class="sxs-lookup"><span data-stu-id="5433b-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="5433b-223">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="5433b-223">**URLs**</span></span>
     - <span data-ttu-id="5433b-224">**Action**</span><span class="sxs-lookup"><span data-stu-id="5433b-224">**Action**</span></span>
     - <span data-ttu-id="5433b-225">**No expirar nunca**</span><span class="sxs-lookup"><span data-stu-id="5433b-225">**Never expire**</span></span>
     - <span data-ttu-id="5433b-226">**Fecha de última actualización**</span><span class="sxs-lookup"><span data-stu-id="5433b-226">**Last updated date**</span></span>
     - <span data-ttu-id="5433b-227">**Quitar en**</span><span class="sxs-lookup"><span data-stu-id="5433b-227">**Remove on**</span></span>
   - <span data-ttu-id="5433b-228">**Files**</span><span class="sxs-lookup"><span data-stu-id="5433b-228">**Files**</span></span>
     - <span data-ttu-id="5433b-229">**Action**</span><span class="sxs-lookup"><span data-stu-id="5433b-229">**Action**</span></span>
     - <span data-ttu-id="5433b-230">**No expirar nunca**</span><span class="sxs-lookup"><span data-stu-id="5433b-230">**Never expire**</span></span>
     - <span data-ttu-id="5433b-231">**Actualizado por última vez**</span><span class="sxs-lookup"><span data-stu-id="5433b-231">**Last updated**</span></span>
     - <span data-ttu-id="5433b-232">**Quitar en**</span><span class="sxs-lookup"><span data-stu-id="5433b-232">**Remove on**</span></span>
   - <span data-ttu-id="5433b-233">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="5433b-233">**Spoofing**</span></span>
     - <span data-ttu-id="5433b-234">**Action**</span><span class="sxs-lookup"><span data-stu-id="5433b-234">**Action**</span></span>
     - <span data-ttu-id="5433b-235">**Tipo de suplantación**</span><span class="sxs-lookup"><span data-stu-id="5433b-235">**Spoof type**</span></span>

   <span data-ttu-id="5433b-236">Cuando haya terminado, haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="5433b-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="5433b-237">Para borrar los filtros existentes, haga clic **en Filtrar** y, en el **menú** desplegable Filtro que aparece, haga clic en **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="5433b-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-238">Usar el portal Microsoft 365 Defender para modificar entradas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5433b-239">En el portal Microsoft 365 Defender, vaya a **Directivas &** de reglas de amenazas Sección Reglas de directivas de amenazas. \>  \>  \> </span><span class="sxs-lookup"><span data-stu-id="5433b-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5433b-240">Seleccione la pestaña que contiene el tipo de entrada que desea modificar:</span><span class="sxs-lookup"><span data-stu-id="5433b-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="5433b-241">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="5433b-241">**URLs**</span></span>
   - <span data-ttu-id="5433b-242">**Files**</span><span class="sxs-lookup"><span data-stu-id="5433b-242">**Files**</span></span>
   - <span data-ttu-id="5433b-243">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="5433b-243">**Spoofing**</span></span>

3. <span data-ttu-id="5433b-244">Seleccione la entrada que desea modificar y, a continuación, haga clic ![ en Editar icono ](../../media/m365-cc-sc-edit-icon.png) **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5433b-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="5433b-245">Los valores que puede modificar en el control desplegable que aparece dependen de la pestaña seleccionada en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="5433b-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="5433b-246">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="5433b-246">**URLs**</span></span>
     - <span data-ttu-id="5433b-247">**No expire nunca** ni la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="5433b-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="5433b-248">**Nota opcional**</span><span class="sxs-lookup"><span data-stu-id="5433b-248">**Optional note**</span></span>
   - <span data-ttu-id="5433b-249">**Files**</span><span class="sxs-lookup"><span data-stu-id="5433b-249">**Files**</span></span>
     - <span data-ttu-id="5433b-250">**No expire nunca** ni la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="5433b-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="5433b-251">**Nota opcional**</span><span class="sxs-lookup"><span data-stu-id="5433b-251">**Optional note**</span></span>
   - <span data-ttu-id="5433b-252">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="5433b-252">**Spoofing**</span></span>
     - <span data-ttu-id="5433b-253">**Acción:** puede cambiar el valor a **Permitir** o **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="5433b-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="5433b-254">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5433b-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-255">Usar el portal Microsoft 365 Defender para quitar entradas de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="5433b-256">En el portal Microsoft 365 Defender, vaya a **Directivas &** de reglas de amenazas Sección Reglas de directivas de amenazas. \>  \>  \> </span><span class="sxs-lookup"><span data-stu-id="5433b-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="5433b-257">Seleccione la pestaña que contiene el tipo de entrada que desea quitar:</span><span class="sxs-lookup"><span data-stu-id="5433b-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="5433b-258">**DIRECCIONES URL**</span><span class="sxs-lookup"><span data-stu-id="5433b-258">**URLs**</span></span>
   - <span data-ttu-id="5433b-259">**Files**</span><span class="sxs-lookup"><span data-stu-id="5433b-259">**Files**</span></span>
   - <span data-ttu-id="5433b-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="5433b-260">**Spoofing**</span></span>

3. <span data-ttu-id="5433b-261">Seleccione la entrada que desea quitar y, a continuación, haga clic ![ en Eliminar icono ](../../media/m365-cc-sc-delete-icon.png) **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5433b-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="5433b-262">En el cuadro de diálogo de advertencia que aparece, haga clic **en Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="5433b-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-263">Use Exchange Online PowerShell o PowerShell de EOP independiente para configurar la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-264">Usar PowerShell para agregar entradas de dirección URL o archivo de bloque a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-265">Para agregar entradas de dirección URL o archivo de bloque en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5433b-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="5433b-266">En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="5433b-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="5433b-267">En este ejemplo se agrega una entrada de dirección URL de bloque para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5433b-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="5433b-268">Dado que no usamos los parámetros ExpirationDate o NoExpiration, la entrada expira después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="5433b-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="5433b-269">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="5433b-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-270">Usar PowerShell para agregar entradas de remitente suplantadas de identidad o bloquear a la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-271">Para agregar entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5433b-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="5433b-272">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="5433b-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-273">Usar PowerShell para ver entradas de direcciones URL o archivos bloqueados en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-274">Para ver entradas de direcciones URL o archivos bloqueados en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5433b-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="5433b-275">En este ejemplo se devuelve información sobre el valor hash de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="5433b-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="5433b-276">En este ejemplo se devuelven todas las direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="5433b-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="5433b-277">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="5433b-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-278">Usar PowerShell para ver o bloquear entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-279">Para ver entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5433b-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="5433b-280">En este ejemplo se devuelven todas las entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="5433b-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="5433b-281">En este ejemplo se devuelven todas las entradas de remitente suplantadas que son internas.</span><span class="sxs-lookup"><span data-stu-id="5433b-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="5433b-282">En este ejemplo se devuelven todas las entradas de remitente suplantadas bloqueadas que son externas.</span><span class="sxs-lookup"><span data-stu-id="5433b-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="5433b-283">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="5433b-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-284">Usar PowerShell para modificar entradas de direcciones URL y archivos de bloque en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-285">Para modificar entradas de archivos de bloque y direcciones URL en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5433b-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="5433b-286">En este ejemplo se cambia la fecha de expiración de la entrada de dirección URL de bloque especificada.</span><span class="sxs-lookup"><span data-stu-id="5433b-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="5433b-287">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="5433b-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-288">Usar PowerShell para modificar entradas de remitente suplantadas o de permitir en la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-289">Para modificar permitir o bloquear entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5433b-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="5433b-290">En este ejemplo se cambia la entrada de remitente suplantada de permitir a bloquear.</span><span class="sxs-lookup"><span data-stu-id="5433b-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="5433b-291">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="5433b-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-292">Usar PowerShell para quitar direcciones URL o entradas de archivo de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-293">Para quitar entradas de archivos y direcciones URL de la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5433b-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="5433b-294">En este ejemplo se quita la entrada de dirección URL de bloque especificada de la lista de inquilinos permitidos o bloqueados.</span><span class="sxs-lookup"><span data-stu-id="5433b-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="5433b-295">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="5433b-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-296">Usar PowerShell para quitar o bloquear entradas de remitente suplantados de la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-297">Para quitar entradas de remitente de suplantación de identidad de la lista de inquilinos permitidos o bloqueados, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5433b-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="5433b-298">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="5433b-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-299">Sintaxis de dirección URL para la lista de inquilinos permitidos o bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="5433b-300">Las direcciones IP4v e IPv6 están permitidas, pero los puertos TCP/UDP no.</span><span class="sxs-lookup"><span data-stu-id="5433b-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="5433b-301">No se permiten extensiones de nombre de archivo (por ejemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="5433b-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="5433b-302">Unicode no es compatible, pero Punycode lo es.</span><span class="sxs-lookup"><span data-stu-id="5433b-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="5433b-303">Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="5433b-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="5433b-304">El nombre de host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="5433b-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="5433b-305">Hay al menos un carácter a la izquierda del punto.</span><span class="sxs-lookup"><span data-stu-id="5433b-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="5433b-306">Hay al menos dos caracteres a la derecha del punto.</span><span class="sxs-lookup"><span data-stu-id="5433b-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="5433b-307">Por ejemplo, `t.co` se permite; `.com` o no `contoso.` se permite.</span><span class="sxs-lookup"><span data-stu-id="5433b-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="5433b-308">Las subpaths no están implícitas.</span><span class="sxs-lookup"><span data-stu-id="5433b-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="5433b-309">Por ejemplo, `contoso.com` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="5433b-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="5433b-310">Los caracteres comodín (\*) se permiten en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="5433b-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="5433b-311">Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.</span><span class="sxs-lookup"><span data-stu-id="5433b-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="5433b-312">Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="5433b-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="5433b-313">Un comodín derecho debe seguir una barra diagonal (/) para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="5433b-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="5433b-314">Por ejemplo, `contoso.com/*` se permite; `contoso.com*` o no `contoso.com/ab*` se permite.</span><span class="sxs-lookup"><span data-stu-id="5433b-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="5433b-315">Todas las subpaths no están implícitas por un comodín derecho.</span><span class="sxs-lookup"><span data-stu-id="5433b-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="5433b-316">Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="5433b-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="5433b-317">`*.com*` no es válido (no es un dominio resolvible y el comodín derecho no sigue una barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="5433b-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="5433b-318">Los caracteres comodín no están permitidos en las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="5433b-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="5433b-319">El carácter tilde (~) está disponible en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="5433b-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="5433b-320">Una tilde izquierda implica un dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="5433b-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="5433b-321">Por `~contoso.com` ejemplo, incluye `contoso.com` y `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="5433b-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="5433b-322">Se producirá un error en las entradas de dirección URL que contienen protocolos (por ejemplo, , o ) porque las entradas de dirección URL se `http://` aplican a todos los `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="5433b-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="5433b-323">No se admite ni se requiere un nombre de usuario o contraseña.</span><span class="sxs-lookup"><span data-stu-id="5433b-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="5433b-324">Las comillas (' o ") son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="5433b-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="5433b-325">Una dirección URL debe incluir todas las redirecciones siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="5433b-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="5433b-326">Escenarios de entrada de dirección URL</span><span class="sxs-lookup"><span data-stu-id="5433b-326">URL entry scenarios</span></span>

<span data-ttu-id="5433b-327">Las entradas de dirección URL válidas y sus resultados se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="5433b-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="5433b-328">Escenario: sin caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="5433b-328">Scenario: No wildcards</span></span>

<span data-ttu-id="5433b-329">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="5433b-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="5433b-330">**Permitir coincidencia**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="5433b-331">**Permitir que no coincida**:</span><span class="sxs-lookup"><span data-stu-id="5433b-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="5433b-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-332">abc-contoso.com</span></span>
  - <span data-ttu-id="5433b-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5433b-333">contoso.com/a</span></span>
  - <span data-ttu-id="5433b-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="5433b-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="5433b-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="5433b-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-337">www.contoso.com</span></span>
  - <span data-ttu-id="5433b-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="5433b-339">**Bloquear coincidencia**:</span><span class="sxs-lookup"><span data-stu-id="5433b-339">**Block match**:</span></span>

  - <span data-ttu-id="5433b-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-340">contoso.com</span></span>
  - <span data-ttu-id="5433b-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5433b-341">contoso.com/a</span></span>
  - <span data-ttu-id="5433b-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="5433b-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="5433b-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="5433b-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-345">www.contoso.com</span></span>
  - <span data-ttu-id="5433b-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="5433b-347">**Bloque no coincidente:** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="5433b-348">Escenario: comodín izquierdo (subdominio)</span><span class="sxs-lookup"><span data-stu-id="5433b-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="5433b-349">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="5433b-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="5433b-350">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="5433b-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5433b-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-351">www.contoso.com</span></span>
  - <span data-ttu-id="5433b-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="5433b-353">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="5433b-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5433b-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-354">123contoso.com</span></span>
  - <span data-ttu-id="5433b-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-355">contoso.com</span></span>
  - <span data-ttu-id="5433b-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="5433b-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="5433b-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="5433b-358">Escenario: comodín derecho en la parte superior de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="5433b-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="5433b-359">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="5433b-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="5433b-360">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="5433b-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5433b-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="5433b-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="5433b-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="5433b-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="5433b-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="5433b-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="5433b-364">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="5433b-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5433b-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-365">contoso.com</span></span>
  - <span data-ttu-id="5433b-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5433b-366">contoso.com/a</span></span>
  - <span data-ttu-id="5433b-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-367">www.contoso.com</span></span>
  - <span data-ttu-id="5433b-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="5433b-369">Escenario: tilde izquierda</span><span class="sxs-lookup"><span data-stu-id="5433b-369">Scenario: Left tilde</span></span>

<span data-ttu-id="5433b-370">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="5433b-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="5433b-371">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="5433b-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5433b-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-372">contoso.com</span></span>
  - <span data-ttu-id="5433b-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-373">www.contoso.com</span></span>
  - <span data-ttu-id="5433b-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="5433b-375">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="5433b-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5433b-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-376">123contoso.com</span></span>
  - <span data-ttu-id="5433b-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="5433b-377">contoso.com/abc</span></span>
  - <span data-ttu-id="5433b-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="5433b-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="5433b-379">Escenario: sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="5433b-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="5433b-380">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="5433b-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="5433b-381">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="5433b-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5433b-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="5433b-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="5433b-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5433b-383">contoso.com/a</span></span>
  - <span data-ttu-id="5433b-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="5433b-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="5433b-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="5433b-385">contoso.com/ab</span></span>
  - <span data-ttu-id="5433b-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="5433b-386">contoso.com/b</span></span>
  - <span data-ttu-id="5433b-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="5433b-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="5433b-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="5433b-388">contoso.com/ba</span></span>

- <span data-ttu-id="5433b-389">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="5433b-390">Escenario: subdominio comodín izquierdo y sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="5433b-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="5433b-391">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="5433b-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="5433b-392">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="5433b-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5433b-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="5433b-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="5433b-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="5433b-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="5433b-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5433b-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="5433b-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="5433b-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="5433b-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="5433b-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="5433b-398">**Permitir no coincidente y** **Bloquear no coincidente:** contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="5433b-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="5433b-399">Escenario: tilde izquierda y derecha</span><span class="sxs-lookup"><span data-stu-id="5433b-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="5433b-400">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="5433b-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="5433b-401">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="5433b-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5433b-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-402">contoso.com</span></span>
  - <span data-ttu-id="5433b-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="5433b-403">contoso.com/a</span></span>
  - <span data-ttu-id="5433b-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-404">www.contoso.com</span></span>
  - <span data-ttu-id="5433b-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="5433b-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="5433b-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="5433b-407">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="5433b-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5433b-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-408">123contoso.com</span></span>
  - <span data-ttu-id="5433b-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="5433b-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="5433b-410">Escenario: dirección IP</span><span class="sxs-lookup"><span data-stu-id="5433b-410">Scenario: IP address</span></span>

<span data-ttu-id="5433b-411">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="5433b-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="5433b-412">**Permitir coincidencia** y **Bloquear coincidencia**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="5433b-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="5433b-413">**Permitir no coincidente y** **Bloquear no coincidente**:</span><span class="sxs-lookup"><span data-stu-id="5433b-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="5433b-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="5433b-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="5433b-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="5433b-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="5433b-416">Dirección IP con comodín derecho</span><span class="sxs-lookup"><span data-stu-id="5433b-416">IP address with right wildcard</span></span>

<span data-ttu-id="5433b-417">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="5433b-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="5433b-418">**Permitir coincidencia y** **Bloquear coincidencia:**</span><span class="sxs-lookup"><span data-stu-id="5433b-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="5433b-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="5433b-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="5433b-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="5433b-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="5433b-421">Ejemplos de entradas no válidas</span><span class="sxs-lookup"><span data-stu-id="5433b-421">Examples of invalid entries</span></span>

<span data-ttu-id="5433b-422">Las siguientes entradas no son válidas:</span><span class="sxs-lookup"><span data-stu-id="5433b-422">The following entries are invalid:</span></span>

- <span data-ttu-id="5433b-423">**Faltan valores de dominio o no son válidos:**</span><span class="sxs-lookup"><span data-stu-id="5433b-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="5433b-424">contoso</span><span class="sxs-lookup"><span data-stu-id="5433b-424">contoso</span></span>
  - <span data-ttu-id="5433b-425">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="5433b-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="5433b-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="5433b-426">\*.com</span></span>
  - <span data-ttu-id="5433b-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="5433b-427">\*.pdf</span></span>

- <span data-ttu-id="5433b-428">**Comodín en el texto o sin caracteres de espaciado:**</span><span class="sxs-lookup"><span data-stu-id="5433b-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="5433b-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="5433b-429">\*contoso.com</span></span>
  - <span data-ttu-id="5433b-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="5433b-430">contoso.com\*</span></span>
  - <span data-ttu-id="5433b-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="5433b-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="5433b-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="5433b-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="5433b-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="5433b-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="5433b-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="5433b-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="5433b-435">**Direcciones IP con puertos**:</span><span class="sxs-lookup"><span data-stu-id="5433b-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="5433b-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="5433b-436">contoso.com:443</span></span>
  - <span data-ttu-id="5433b-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="5433b-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="5433b-438">**Caracteres comodín no descriptivos:**</span><span class="sxs-lookup"><span data-stu-id="5433b-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="5433b-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="5433b-439">\*.\*</span></span>

- <span data-ttu-id="5433b-440">**Caracteres comodín intermedios**:</span><span class="sxs-lookup"><span data-stu-id="5433b-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="5433b-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="5433b-441">conto\*so.com</span></span>
  - <span data-ttu-id="5433b-442">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="5433b-442">conto~so.com</span></span>

- <span data-ttu-id="5433b-443">**Caracteres comodín dobles**</span><span class="sxs-lookup"><span data-stu-id="5433b-443">**Double wildcards**</span></span>

  - <span data-ttu-id="5433b-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="5433b-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="5433b-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="5433b-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="5433b-446">Sintaxis de par de dominio para entradas de remitente suplantadas en la lista de inquilinos permitidos/bloqueados</span><span class="sxs-lookup"><span data-stu-id="5433b-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="5433b-447">Un par de dominio para un remitente suplantado en la lista de inquilinos permitidos o bloqueados usa la siguiente sintaxis: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="5433b-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="5433b-448">**Usuario suplantado:** este valor implica la dirección de correo electrónico del usuario  suplantado que se muestra en el cuadro De de los clientes de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5433b-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="5433b-449">Esta dirección también se conoce como `5322.From` la dirección.</span><span class="sxs-lookup"><span data-stu-id="5433b-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="5433b-450">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="5433b-450">Valid values include:</span></span>
  - <span data-ttu-id="5433b-451">Una dirección de correo electrónico individual (por ejemplo, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5433b-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="5433b-452">Un dominio de correo electrónico (por ejemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5433b-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="5433b-453">El carácter comodín (por ejemplo, \* ).</span><span class="sxs-lookup"><span data-stu-id="5433b-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="5433b-454">**Infraestructura de** envío: este valor indica el origen de los mensajes del usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="5433b-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="5433b-455">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="5433b-455">Valid values include:</span></span>
  - <span data-ttu-id="5433b-456">El dominio encontrado en una búsqueda dns inversa (registro PTR) de la dirección IP del servidor de correo electrónico de origen (por ejemplo, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="5433b-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="5433b-457">Si la dirección IP de origen no tiene ningún registro PTR, la infraestructura de envío se identifica como \<source IP\> /24 (por ejemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="5433b-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="5433b-458">Estos son algunos ejemplos de pares de dominio válidos para identificar remitentes suplantados:</span><span class="sxs-lookup"><span data-stu-id="5433b-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="5433b-459">El número máximo de entradas de remitente suplantadas es 1000.</span><span class="sxs-lookup"><span data-stu-id="5433b-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="5433b-460">Agregar un par de dominio solo permite o bloquea *la* combinación del usuario suplantado *y la* infraestructura de envío.</span><span class="sxs-lookup"><span data-stu-id="5433b-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="5433b-461">No permite el correo electrónico del usuario suplantado de ningún origen, ni permite el correo electrónico del origen de la infraestructura de envío para ningún usuario suplantado.</span><span class="sxs-lookup"><span data-stu-id="5433b-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="5433b-462">Por ejemplo, agrega una entrada allow para el siguiente par de dominio:</span><span class="sxs-lookup"><span data-stu-id="5433b-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="5433b-463">**Dominio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="5433b-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="5433b-464">**Infraestructura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="5433b-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="5433b-465">Solo los mensajes de ese dominio *y* el par de infraestructura de envío pueden suplantación.</span><span class="sxs-lookup"><span data-stu-id="5433b-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="5433b-466">Otros remitentes que intentan suplantar gmail.com no están permitidos.</span><span class="sxs-lookup"><span data-stu-id="5433b-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="5433b-467">Los mensajes de remitentes de otros dominios que se originaron tms.mx.com se comprueban mediante la inteligencia de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5433b-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
