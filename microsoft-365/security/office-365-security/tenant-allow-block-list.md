---
title: Administrar los archivos y las direcciones URL permitidas y bloqueadas en la lista de permitidos/bloqueados del espacio empresarial
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Los administradores pueden obtener información sobre cómo configurar las entradas de archivos y direcciones URL en la lista de permitidos y bloqueados del centro de seguridad & cumplimiento.
ms.openlocfilehash: 742a44c7ed63c8a3037e2ada295c94f89afa9c93
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726813"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-103">Administrar direcciones URL y archivos en la lista de permitidos/bloqueados del espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="88f79-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="88f79-104">Las características descritas en este tema están en versión preliminar, están sujetas a cambios y no están disponibles en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="88f79-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="88f79-105">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, es posible que no esté de acuerdo con el veredicto de filtrado de EOP.</span><span class="sxs-lookup"><span data-stu-id="88f79-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="88f79-106">Por ejemplo, un buen mensaje puede marcarse como incorrecto (un falso positivo) o puede que se permita el acceso a un mensaje incorrecto (un falso negativo).</span><span class="sxs-lookup"><span data-stu-id="88f79-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="88f79-107">La lista de permitidos y bloqueados del centro de cumplimiento de & de seguridad ofrece una forma de reemplazar manualmente los veredictos de filtrado de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="88f79-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="88f79-108">La lista de permitidos/bloqueados del inquilino se usa durante el flujo de correo y en el momento en que el usuario hace clic.</span><span class="sxs-lookup"><span data-stu-id="88f79-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="88f79-109">Puede especificar las direcciones URL y los archivos que desea permitir o bloquear en la lista de permitidos/bloqueados del inquilino.</span><span class="sxs-lookup"><span data-stu-id="88f79-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="88f79-110">En este tema se describe cómo configurar entradas en la lista de permitidos/bloqueados del centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para Microsoft 365 organizaciones con buzones en Exchange Online; PowerShell de EOP independiente para las organizaciones sin buzones de correo de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="88f79-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="88f79-111">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="88f79-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="88f79-112">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="88f79-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="88f79-113">Para ir directamente a la página de la **lista de permitidos/bloqueados de inquilino** , use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="88f79-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="88f79-114">Los archivos se especifican mediante el valor hash SHA256 del archivo.</span><span class="sxs-lookup"><span data-stu-id="88f79-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="88f79-115">Para buscar el valor hash SHA256 de un archivo en Windows, ejecute el siguiente comando en un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="88f79-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="88f79-116">Un valor de ejemplo es `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="88f79-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="88f79-117">No se permiten los valores de hash perceptual (pHash).</span><span class="sxs-lookup"><span data-stu-id="88f79-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="88f79-118">Los valores de dirección URL disponibles se describen en la sintaxis de la [dirección URL de la sección lista de permitidos/bloqueados de inquilino](#url-syntax-for-the-tenant-allowblock-list) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="88f79-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="88f79-119">La lista de permitidos/bloqueados de inquilino permite un máximo de 500 entradas para las direcciones URL y 500 entradas para los hash de archivo.</span><span class="sxs-lookup"><span data-stu-id="88f79-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="88f79-120">Una entrada debe estar activa en 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="88f79-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="88f79-121">Las entradas de bloque tienen prioridad sobre las entradas de permitir.</span><span class="sxs-lookup"><span data-stu-id="88f79-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="88f79-122">De forma predeterminada, las entradas de la lista de permitidos y bloqueados de inquilino expirarán transcurridos 30 días.</span><span class="sxs-lookup"><span data-stu-id="88f79-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="88f79-123">Puede especificar una fecha o configurarlas para que no expiren nunca.</span><span class="sxs-lookup"><span data-stu-id="88f79-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="88f79-124">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="88f79-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="88f79-125">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="88f79-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="88f79-126">Debe tener permisos asignados para poder realizar los procedimientos de este tema:</span><span class="sxs-lookup"><span data-stu-id="88f79-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="88f79-127">Para agregar y quitar valores de la lista de permitidos/bloqueados de inquilino, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="88f79-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="88f79-128">**Administración** de la organización o **Administrador de seguridad** en el [centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="88f79-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="88f79-129">Administración de la administración de la **organización** o administración de la **higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="88f79-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="88f79-130">Para obtener acceso de solo lectura a la lista de permitidos/bloqueados del inquilino, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="88f79-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="88f79-131">**Lector de seguridad** en el [centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="88f79-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="88f79-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="88f79-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-133">Usar el centro de seguridad & cumplimiento para crear entradas de dirección URL en la lista de permitidos/bloqueados de espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="88f79-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="88f79-134">Para obtener información detallada sobre la sintaxis de las entradas de dirección URL, vea la [Sintaxis de la dirección URL de la sección lista de permitidos/bloqueados de inquilino](#url-syntax-for-the-tenant-allowblock-list) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="88f79-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="88f79-135">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="88f79-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="88f79-136">En la página **lista de permitidos/bloqueados del inquilino** , compruebe que la ficha **direcciones URL** está seleccionada y, a continuación, haga clic en **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="88f79-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="88f79-137">En el control flotante **Agregar nuevas direcciones URL** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="88f79-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="88f79-138">**Agregar direcciones URL con caracteres comodín**: escriba una dirección URL por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="88f79-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="88f79-139">**Bloquear o permitir**: Seleccione si desea **permitir** o **bloquear** las direcciones URL especificadas.</span><span class="sxs-lookup"><span data-stu-id="88f79-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="88f79-140">No **expira nunca**: siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="88f79-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="88f79-141">Compruebe que la opción está desactivada (desactivar ![ ](../../media/scc-toggle-off.png) ) y use el cuadro **expira en** para especificar la fecha de caducidad de las entradas.</span><span class="sxs-lookup"><span data-stu-id="88f79-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="88f79-142">o</span><span class="sxs-lookup"><span data-stu-id="88f79-142">or</span></span>

     - <span data-ttu-id="88f79-143">Mueva el botón de alternancia a la derecha para configurar las entradas para que no expiren nunca:</span><span class="sxs-lookup"><span data-stu-id="88f79-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="88f79-145">.</span><span class="sxs-lookup"><span data-stu-id="88f79-145">.</span></span>

   - <span data-ttu-id="88f79-146">**Opcional Nota**: escriba un texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="88f79-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="88f79-147">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="88f79-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-148">Usar el centro de seguridad & cumplimiento para crear entradas de archivo en la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="88f79-149">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="88f79-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="88f79-150">En la página **lista de permitidos/bloqueados de inquilino** , seleccione la pestaña **archivos** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="88f79-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="88f79-151">En el control flotante **agregar nuevos archivos** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="88f79-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="88f79-152">**Agregar hash de archivo**: Introduzca un valor hash SHA256 por línea, hasta un máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="88f79-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="88f79-153">**Bloquear o permitir**: Seleccione si desea **permitir** o **bloquear** los archivos especificados.</span><span class="sxs-lookup"><span data-stu-id="88f79-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="88f79-154">No **expira nunca**: siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="88f79-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="88f79-155">Compruebe que la opción está desactivada (desactivar ![ ](../../media/scc-toggle-off.png) ) y use el cuadro **expira en** para especificar la fecha de caducidad de las entradas.</span><span class="sxs-lookup"><span data-stu-id="88f79-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="88f79-156">o</span><span class="sxs-lookup"><span data-stu-id="88f79-156">or</span></span>

     - <span data-ttu-id="88f79-157">Mueva el botón de alternancia a la derecha para configurar las entradas para que no expiren nunca:</span><span class="sxs-lookup"><span data-stu-id="88f79-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="88f79-159">.</span><span class="sxs-lookup"><span data-stu-id="88f79-159">.</span></span>

   - <span data-ttu-id="88f79-160">**Opcional Nota**: escriba un texto descriptivo para las entradas.</span><span class="sxs-lookup"><span data-stu-id="88f79-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="88f79-161">Cuando haya terminado, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="88f79-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-162">Usar el centro de seguridad & cumplimiento para ver las entradas de archivos y direcciones URL en la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="88f79-163">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="88f79-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="88f79-164">Seleccione la ficha **URL** o la pestaña **archivos** .</span><span class="sxs-lookup"><span data-stu-id="88f79-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="88f79-165">Haga clic en los siguientes encabezados de columna para ordenar en orden ascendente o descendente:</span><span class="sxs-lookup"><span data-stu-id="88f79-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="88f79-166">**Value**: la dirección URL o el hash de archivo.</span><span class="sxs-lookup"><span data-stu-id="88f79-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="88f79-167">**Acción**: **bloquear** o **permitir**.</span><span class="sxs-lookup"><span data-stu-id="88f79-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="88f79-168">**Fecha de la última actualización**</span><span class="sxs-lookup"><span data-stu-id="88f79-168">**Last updated date**</span></span>
- <span data-ttu-id="88f79-169">**Fecha de expiración**</span><span class="sxs-lookup"><span data-stu-id="88f79-169">**Expiration date**</span></span>
- <span data-ttu-id="88f79-170">**Nota**</span><span class="sxs-lookup"><span data-stu-id="88f79-170">**Note**</span></span>

<span data-ttu-id="88f79-171">Haga clic en **agrupar** para agrupar las entradas por **acción** (**bloquear** o **permitir**) o en **ninguna**.</span><span class="sxs-lookup"><span data-stu-id="88f79-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="88f79-172">Haga clic en **Buscar**, escriba todo o parte de una dirección URL o un valor de archivo y, a continuación, presione Entrar para buscar un valor específico.</span><span class="sxs-lookup"><span data-stu-id="88f79-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="88f79-173">Cuando haya terminado, haga clic en **Clear Search** ![ Clear Search Icon ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="88f79-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="88f79-174">Haga clic en **filtro**.</span><span class="sxs-lookup"><span data-stu-id="88f79-174">Click **Filter**.</span></span> <span data-ttu-id="88f79-175">En el control flotante de **filtro** que aparece, configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="88f79-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="88f79-176">**Acción**: seleccione **permitir**, **bloquear** o ambos.</span><span class="sxs-lookup"><span data-stu-id="88f79-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="88f79-177">**Nunca expire**: seleccione Desactivado (desactivado ![ ](../../media/scc-toggle-off.png) ) o activado ( ![ alternar en ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="88f79-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="88f79-178">**Última actualización**: Seleccione una fecha de inicio (desde), una fecha**de**finalización (**hasta**) o ambas.</span><span class="sxs-lookup"><span data-stu-id="88f79-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="88f79-179">**Fecha de expiración**: Seleccione una fecha**de**Inicio (desde), una fecha de finalización (**hasta**) o ambas.</span><span class="sxs-lookup"><span data-stu-id="88f79-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="88f79-180">Cuando haya terminado, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="88f79-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="88f79-181">Para borrar los filtros existentes, haga clic en **filtrar**y, en el control flotante de **filtro** que aparece, haga clic en **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="88f79-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-182">Usar el centro de seguridad & cumplimiento para modificar las entradas de archivo y la dirección URL en la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="88f79-183">No puede modificar el valor de la dirección URL o del archivo en sí.</span><span class="sxs-lookup"><span data-stu-id="88f79-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="88f79-184">En su lugar, debe eliminar la entrada y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="88f79-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="88f79-185">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="88f79-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="88f79-186">Seleccione la ficha **URL** o la pestaña **archivos** .</span><span class="sxs-lookup"><span data-stu-id="88f79-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="88f79-187">Seleccione la entrada que desea modificar y, a continuación, haga clic en **Editar** ![ icono Editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="88f79-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="88f79-188">En el control flotante que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="88f79-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="88f79-189">**Bloquear o permitir**: seleccione **permitir** o **bloquear**.</span><span class="sxs-lookup"><span data-stu-id="88f79-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="88f79-190">No **expira nunca**: siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="88f79-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="88f79-191">Compruebe que la opción está desactivada (desactivar ![ ](../../media/scc-toggle-off.png) ) y use el cuadro **expira en** para especificar la fecha de caducidad de la entrada.</span><span class="sxs-lookup"><span data-stu-id="88f79-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="88f79-192">o</span><span class="sxs-lookup"><span data-stu-id="88f79-192">or</span></span>

     - <span data-ttu-id="88f79-193">Mueva el botón de alternancia a la derecha para configurar que la entrada nunca expire:</span><span class="sxs-lookup"><span data-stu-id="88f79-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Habilitar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="88f79-195">.</span><span class="sxs-lookup"><span data-stu-id="88f79-195">.</span></span>

   - <span data-ttu-id="88f79-196">**Opcional Nota**: escriba un texto descriptivo para la entrada.</span><span class="sxs-lookup"><span data-stu-id="88f79-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="88f79-197">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="88f79-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-198">Usar el centro de seguridad & cumplimiento para quitar las entradas de archivo y de dirección URL de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="88f79-199">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** para \> **Policy** \> **las listas de permitidos y bloqueados del inquilino**.</span><span class="sxs-lookup"><span data-stu-id="88f79-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="88f79-200">Seleccione la ficha **URL** o la pestaña **archivos** .</span><span class="sxs-lookup"><span data-stu-id="88f79-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="88f79-201">Seleccione la entrada que desee quitar y, a continuación, haga clic en **eliminar** ![ icono de eliminación ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="88f79-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="88f79-202">En el cuadro de diálogo de advertencia que aparece, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="88f79-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-203">Usar Exchange Online PowerShell o PowerShell independiente de EOP para configurar la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-204">Usar PowerShell para agregar entradas de archivos y direcciones URL en la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="88f79-205">Para agregar la dirección URL y las entradas de archivo en la lista de permitidos/bloqueados del inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="88f79-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="88f79-206">En este ejemplo se agrega una entrada de bloque de dirección URL para contoso.com y todos los subdominios (por ejemplo, contoso.com, www.contoso.com y xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="88f79-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="88f79-207">Como no se usaron los parámetros ExpirationDate o noexpiration, la entrada expira después de 30 días.</span><span class="sxs-lookup"><span data-stu-id="88f79-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="88f79-208">En este ejemplo se agrega una entrada de permiso de archivo para los archivos especificados que nunca expiran.</span><span class="sxs-lookup"><span data-stu-id="88f79-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="88f79-209">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="88f79-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-210">Usar PowerShell para ver las entradas de archivos y direcciones URL en la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="88f79-211">Para ver las entradas de la dirección URL y los archivos en la lista de permitidos/bloqueados del inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="88f79-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="88f79-212">En este ejemplo se devuelven todas las direcciones URL bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="88f79-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="88f79-213">En este ejemplo se devuelve información sobre el valor hash del archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="88f79-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="88f79-214">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="88f79-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-215">Usar PowerShell para modificar entradas de archivos y direcciones URL en la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="88f79-216">No puede modificar el valor de la dirección URL o del archivo en sí.</span><span class="sxs-lookup"><span data-stu-id="88f79-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="88f79-217">En su lugar, debe eliminar la entrada y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="88f79-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="88f79-218">Para modificar las entradas de la dirección URL y los archivos en la lista de permitidos/bloqueados del inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="88f79-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="88f79-219">En este ejemplo se cambia la fecha de caducidad de la entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="88f79-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="88f79-220">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="88f79-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-221">Usar PowerShell para quitar entradas de archivos y direcciones URL de la lista de permitidos y bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="88f79-222">Para quitar las entradas de direcciones URL y archivos de la lista de permitidos/bloqueados del inquilino, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="88f79-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="88f79-223">En este ejemplo se quita la entrada de la dirección URL especificada de la lista de permitidos/bloqueados del inquilino.</span><span class="sxs-lookup"><span data-stu-id="88f79-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="88f79-224">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="88f79-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="88f79-225">Sintaxis de dirección URL para la lista de permitidos/bloqueados del inquilino</span><span class="sxs-lookup"><span data-stu-id="88f79-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="88f79-226">Se permiten las direcciones IP4v e IPv6, pero los puertos TCP/UDP no.</span><span class="sxs-lookup"><span data-stu-id="88f79-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="88f79-227">No se permiten las extensiones de nombre de archivo (por ejemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="88f79-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="88f79-228">No se admite Unicode, pero Punycode es.</span><span class="sxs-lookup"><span data-stu-id="88f79-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="88f79-229">Los nombres de host se permiten si todas las instrucciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="88f79-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="88f79-230">El nombre de host contiene un punto.</span><span class="sxs-lookup"><span data-stu-id="88f79-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="88f79-231">Hay al menos un carácter a la izquierda del punto.</span><span class="sxs-lookup"><span data-stu-id="88f79-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="88f79-232">Hay al menos dos caracteres a la derecha del punto.</span><span class="sxs-lookup"><span data-stu-id="88f79-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="88f79-233">Por ejemplo, `t.co` está permitido; `.com` o `contoso.` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="88f79-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="88f79-234">Los subtrazados no son implícitos.</span><span class="sxs-lookup"><span data-stu-id="88f79-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="88f79-235">Por ejemplo, `contoso.com` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="88f79-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="88f79-236">Los caracteres comodín (\*) están permitidos en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="88f79-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="88f79-237">Un comodín izquierdo debe ir seguido de un punto para especificar un subdominio.</span><span class="sxs-lookup"><span data-stu-id="88f79-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="88f79-238">Por ejemplo, `*.contoso.com` está permitido; `*contoso.com` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="88f79-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="88f79-239">Un comodín derecho debe ir seguido de una barra diagonal (/) para especificar una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="88f79-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="88f79-240">Por ejemplo, `contoso.com/*` está permitido; `contoso.com*` o `contoso.com/ab*` no está permitido.</span><span class="sxs-lookup"><span data-stu-id="88f79-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="88f79-241">Un comodín derecho no implica todos los subtrazados.</span><span class="sxs-lookup"><span data-stu-id="88f79-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="88f79-242">Por ejemplo, `contoso.com/*` no incluye `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="88f79-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="88f79-243">`*.com*`no es válido (no es un dominio que se pueda resolver y el comodín derecho no sigue una barra diagonal).</span><span class="sxs-lookup"><span data-stu-id="88f79-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="88f79-244">No se permiten caracteres comodín en direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="88f79-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="88f79-245">El carácter tilde (~) está disponible en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="88f79-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="88f79-246">Una tilde izquierda implica un dominio y todos los subdominios.</span><span class="sxs-lookup"><span data-stu-id="88f79-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="88f79-247">Por ejemplo `~contoso.com` `contoso.com` , incluye y `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="88f79-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="88f79-248">Las entradas de dirección URL que contienen protocolos (por ejemplo,, `http://` `https://` o) producirán `ftp://` un error porque las entradas de dirección URL se aplican a todos los protocolos.</span><span class="sxs-lookup"><span data-stu-id="88f79-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="88f79-249">No se admite ni es necesario un nombre de usuario ni una contraseña.</span><span class="sxs-lookup"><span data-stu-id="88f79-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="88f79-250">Las comillas (' o ") son caracteres no válidos.</span><span class="sxs-lookup"><span data-stu-id="88f79-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="88f79-251">Una dirección URL debe incluir todas las redirecciones siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="88f79-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="88f79-252">Escenarios de entrada de direcciones URL</span><span class="sxs-lookup"><span data-stu-id="88f79-252">URL entry scenarios</span></span>

<span data-ttu-id="88f79-253">En las siguientes secciones se describen las entradas de dirección URL válidas y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="88f79-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="88f79-254">Escenario: sin caracteres comodín</span><span class="sxs-lookup"><span data-stu-id="88f79-254">Scenario: No wildcards</span></span>

<span data-ttu-id="88f79-255">**Entrada**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="88f79-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="88f79-256">**Permitir coincidencia**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="88f79-257">**Permitir sin coincidencia**:</span><span class="sxs-lookup"><span data-stu-id="88f79-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="88f79-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-258">abc-contoso.com</span></span>
  - <span data-ttu-id="88f79-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="88f79-259">contoso.com/a</span></span>
  - <span data-ttu-id="88f79-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="88f79-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="88f79-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="88f79-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-263">www.contoso.com</span></span>
  - <span data-ttu-id="88f79-264">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="88f79-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="88f79-265">**Coincidencia de bloque**:</span><span class="sxs-lookup"><span data-stu-id="88f79-265">**Block match**:</span></span>

  - <span data-ttu-id="88f79-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-266">contoso.com</span></span>
  - <span data-ttu-id="88f79-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="88f79-267">contoso.com/a</span></span>
  - <span data-ttu-id="88f79-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="88f79-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="88f79-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="88f79-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-271">www.contoso.com</span></span>
  - <span data-ttu-id="88f79-272">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="88f79-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="88f79-273">**Bloque no coincidente**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="88f79-274">Escenario: comodín izquierdo (subdominio)</span><span class="sxs-lookup"><span data-stu-id="88f79-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="88f79-275">**Entrada**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="88f79-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="88f79-276">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="88f79-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="88f79-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-277">www.contoso.com</span></span>
  - <span data-ttu-id="88f79-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="88f79-279">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="88f79-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="88f79-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-280">123contoso.com</span></span>
  - <span data-ttu-id="88f79-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-281">contoso.com</span></span>
  - <span data-ttu-id="88f79-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="88f79-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="88f79-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="88f79-284">Escenario: comodín derecho en la parte superior de la ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="88f79-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="88f79-285">**Entrada**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="88f79-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="88f79-286">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="88f79-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="88f79-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="88f79-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="88f79-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="88f79-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="88f79-289">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="88f79-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="88f79-290">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="88f79-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="88f79-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-291">contoso.com</span></span>
  - <span data-ttu-id="88f79-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="88f79-292">contoso.com/a</span></span>
  - <span data-ttu-id="88f79-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-293">www.contoso.com</span></span>
  - <span data-ttu-id="88f79-294">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="88f79-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="88f79-295">Escenario: tilde izquierda</span><span class="sxs-lookup"><span data-stu-id="88f79-295">Scenario: Left tilde</span></span>

<span data-ttu-id="88f79-296">**Entrada**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="88f79-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="88f79-297">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="88f79-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="88f79-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-298">contoso.com</span></span>
  - <span data-ttu-id="88f79-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-299">www.contoso.com</span></span>
  - <span data-ttu-id="88f79-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="88f79-301">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="88f79-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="88f79-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-302">123contoso.com</span></span>
  - <span data-ttu-id="88f79-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="88f79-303">contoso.com/abc</span></span>
  - <span data-ttu-id="88f79-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="88f79-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="88f79-305">Escenario: sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="88f79-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="88f79-306">**Entrada**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="88f79-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="88f79-307">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="88f79-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="88f79-308">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="88f79-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="88f79-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="88f79-309">contoso.com/a</span></span>
  - <span data-ttu-id="88f79-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="88f79-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="88f79-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="88f79-311">contoso.com/ab</span></span>
  - <span data-ttu-id="88f79-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="88f79-312">contoso.com/b</span></span>
  - <span data-ttu-id="88f79-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="88f79-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="88f79-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="88f79-314">contoso.com/ba</span></span>

- <span data-ttu-id="88f79-315">**Permitir no coincidentes** y **no coincidentes**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="88f79-316">Escenario: subdominio comodín izquierdo y sufijo comodín derecho</span><span class="sxs-lookup"><span data-stu-id="88f79-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="88f79-317">**Entrada**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="88f79-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="88f79-318">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="88f79-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="88f79-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="88f79-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="88f79-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="88f79-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="88f79-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="88f79-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="88f79-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="88f79-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="88f79-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="88f79-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="88f79-324">**Permitir no coincidentes** y **no coincidentes**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="88f79-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="88f79-325">Escenario: tilde izquierda y derecha</span><span class="sxs-lookup"><span data-stu-id="88f79-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="88f79-326">**Entrada**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="88f79-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="88f79-327">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="88f79-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="88f79-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-328">contoso.com</span></span>
  - <span data-ttu-id="88f79-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="88f79-329">contoso.com/a</span></span>
  - <span data-ttu-id="88f79-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-330">www.contoso.com</span></span>
  - <span data-ttu-id="88f79-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="88f79-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="88f79-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="88f79-333">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="88f79-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="88f79-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-334">123contoso.com</span></span>
  - <span data-ttu-id="88f79-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="88f79-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="88f79-336">Escenario: dirección IP</span><span class="sxs-lookup"><span data-stu-id="88f79-336">Scenario: IP address</span></span>

<span data-ttu-id="88f79-337">**Entrada**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="88f79-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="88f79-338">**Permitir** coincidencia de coincidencia y **bloqueo**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="88f79-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="88f79-339">**Permitir no coincidentes** y **no coincidentes**:</span><span class="sxs-lookup"><span data-stu-id="88f79-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="88f79-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="88f79-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="88f79-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="88f79-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="88f79-342">Dirección IP con comodín derecho</span><span class="sxs-lookup"><span data-stu-id="88f79-342">IP address with right wildcard</span></span>

<span data-ttu-id="88f79-343">**Entrada**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="88f79-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="88f79-344">**Permitir** coincidencia de coincidencia y **bloqueo**:</span><span class="sxs-lookup"><span data-stu-id="88f79-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="88f79-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="88f79-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="88f79-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="88f79-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="88f79-347">Ejemplos de entradas no válidas</span><span class="sxs-lookup"><span data-stu-id="88f79-347">Examples of invalid entries</span></span>

<span data-ttu-id="88f79-348">Las siguientes entradas no son válidas:</span><span class="sxs-lookup"><span data-stu-id="88f79-348">The following entries are invalid:</span></span>

- <span data-ttu-id="88f79-349">**Faltan valores de dominio o no son válidos**:</span><span class="sxs-lookup"><span data-stu-id="88f79-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="88f79-350">contoso</span><span class="sxs-lookup"><span data-stu-id="88f79-350">contoso</span></span>
  - <span data-ttu-id="88f79-351">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="88f79-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="88f79-352">\*. com</span><span class="sxs-lookup"><span data-stu-id="88f79-352">\*.com</span></span>
  - <span data-ttu-id="88f79-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="88f79-353">\*.pdf</span></span>

- <span data-ttu-id="88f79-354">**Comodín en texto o sin caracteres de espaciado**:</span><span class="sxs-lookup"><span data-stu-id="88f79-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="88f79-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="88f79-355">\*contoso.com</span></span>
  - <span data-ttu-id="88f79-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="88f79-356">contoso.com\*</span></span>
  - <span data-ttu-id="88f79-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="88f79-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="88f79-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="88f79-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="88f79-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="88f79-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="88f79-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="88f79-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="88f79-361">**Direcciones IP con puertos**:</span><span class="sxs-lookup"><span data-stu-id="88f79-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="88f79-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="88f79-362">contoso.com:443</span></span>
  - <span data-ttu-id="88f79-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="88f79-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="88f79-364">**Caracteres comodín no descriptivos**:</span><span class="sxs-lookup"><span data-stu-id="88f79-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="88f79-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="88f79-365">\*.\*</span></span>

- <span data-ttu-id="88f79-366">**Caracteres comodín del segundo nombre**:</span><span class="sxs-lookup"><span data-stu-id="88f79-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="88f79-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="88f79-367">conto\*so.com</span></span>
  - <span data-ttu-id="88f79-368">conto ~ so. com</span><span class="sxs-lookup"><span data-stu-id="88f79-368">conto~so.com</span></span>

- <span data-ttu-id="88f79-369">**Caracteres comodín dobles**</span><span class="sxs-lookup"><span data-stu-id="88f79-369">**Double wildcards**</span></span>

  - <span data-ttu-id="88f79-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="88f79-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="88f79-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="88f79-371">contoso.com/\*/\*</span></span>
