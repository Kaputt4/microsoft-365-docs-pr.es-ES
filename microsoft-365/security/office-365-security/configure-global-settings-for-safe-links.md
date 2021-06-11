---
title: Configurar la configuración global para Caja fuerte de vínculos en Defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a ver y configurar la configuración global (la lista "Bloquear las siguientes direcciones URL" y la protección para aplicaciones de Office 365) para Caja fuerte Vínculos en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b1bcdaf92412b17b231e3f4849bae8aab72f292
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878537"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1facf-103">Configurar la configuración global para Caja fuerte vínculos en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1facf-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1facf-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="1facf-104">**Applies to**</span></span>
- [<span data-ttu-id="1facf-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1facf-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1facf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1facf-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="1facf-107">Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1facf-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="1facf-108">Si es un usuario principal que busca información sobre safelinks en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="1facf-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="1facf-109">Caja fuerte Vínculos es una característica de [Microsoft Defender](defender-for-office-365.md) para Office 365 que proporciona el examen de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el tiempo de comprobación de clics de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="1facf-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="1facf-110">Para obtener más información, [vea Caja fuerte Links in Microsoft Defender for Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="1facf-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="1facf-111">Puede configurar la mayoría de Caja fuerte de vínculos en Caja fuerte de vínculos.</span><span class="sxs-lookup"><span data-stu-id="1facf-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="1facf-112">Para obtener instrucciones, vea [Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1facf-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="1facf-113">Sin embargo, Caja fuerte links también usa la siguiente configuración global que se configura fuera de las directivas de vínculos de Caja fuerte:</span><span class="sxs-lookup"><span data-stu-id="1facf-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="1facf-114">La **lista Bloquear las siguientes direcciones** URL.</span><span class="sxs-lookup"><span data-stu-id="1facf-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="1facf-115">Esta configuración se aplica a todos los usuarios incluidos en las directivas de vínculos Caja fuerte activas.</span><span class="sxs-lookup"><span data-stu-id="1facf-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="1facf-116">Para obtener más información, vea ["Bloquear las siguientes direcciones URL" para](safe-links.md#block-the-following-urls-list-for-safe-links) obtener Caja fuerte vínculos</span><span class="sxs-lookup"><span data-stu-id="1facf-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="1facf-117">Caja fuerte Vincula la protección para Office 365 aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1facf-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="1facf-118">Esta configuración se aplica a todos los usuarios de la organización con licencia para Defender para Office 365, independientemente de si los usuarios se incluyen en directivas de vínculos de Caja fuerte activas o no.</span><span class="sxs-lookup"><span data-stu-id="1facf-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="1facf-119">Para obtener más información, [consulta Caja fuerte configuración de vínculos para Office 365 aplicaciones](safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="1facf-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="1facf-120">Puede configurar la configuración global de vínculos de Caja fuerte en el portal de Microsoft 365 Defender o en PowerShell (powershell de Exchange Online para organizaciones Microsoft 365 elegibles con buzones en Exchange Online; PowerShell EOP independiente para organizaciones sin buzones de Exchange Online, pero con Microsoft Defender para suscripciones de complemento Office 365).</span><span class="sxs-lookup"><span data-stu-id="1facf-120">You can configure the global Safe Links settings in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1facf-121">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="1facf-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1facf-122">No hay ninguna directiva de vínculos Caja fuerte integrada o predeterminada, por lo que debe crear al  menos una directiva de vínculos de Caja fuerte para que la lista Bloquear las siguientes direcciones URL esté activa.</span><span class="sxs-lookup"><span data-stu-id="1facf-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="1facf-123">Para obtener instrucciones, vea [Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1facf-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="1facf-124">Abra el portal Microsoft 365 Defender en <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="1facf-124">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="1facf-125">Para ir directamente a la **página Caja fuerte vínculos,** use <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="1facf-125">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="1facf-126">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1facf-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1facf-127">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="1facf-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1facf-128">Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="1facf-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1facf-129">Para configurar la configuración global de Caja fuerte, debe ser miembro  de los grupos de roles Administración de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="1facf-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="1facf-130">Para obtener acceso de solo lectura a la configuración global de Caja fuerte links, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="1facf-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="1facf-131">Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="1facf-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="1facf-132">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="1facf-132">**Notes**:</span></span>

  - <span data-ttu-id="1facf-133">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1facf-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1facf-134">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="1facf-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="1facf-135">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="1facf-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="1facf-136">Para obtener los valores recomendados para la configuración global de Caja fuerte vínculos, vea [Caja fuerte configuración de vínculos](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span><span class="sxs-lookup"><span data-stu-id="1facf-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="1facf-137">Permitir hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="1facf-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="1facf-138">[Las nuevas características se agregan continuamente a Microsoft Defender para Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="1facf-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="1facf-139">A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos de Caja fuerte existentes.</span><span class="sxs-lookup"><span data-stu-id="1facf-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="1facf-140">Configurar la lista "Bloquear las siguientes direcciones URL" en el portal de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1facf-140">Configure the "Block the following URLs" list in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="1facf-141">La **lista Bloquear las siguientes direcciones URL** identifica los vínculos que siempre deben bloquearse mediante el examen de vínculos Caja fuerte en aplicaciones compatibles.</span><span class="sxs-lookup"><span data-stu-id="1facf-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="1facf-142">Para obtener más información, vea ["Bloquear las siguientes direcciones URL" para obtener Caja fuerte vínculos](safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="1facf-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="1facf-143">En el portal Microsoft 365 Defender, vaya a Email **& Collaboration** Policies \> **& Rules** Threat \> **policies** \> **section** \> **Caja fuerte Links**.</span><span class="sxs-lookup"><span data-stu-id="1facf-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="1facf-144">En la **página Caja fuerte,** haga clic en **Configuración global**.</span><span class="sxs-lookup"><span data-stu-id="1facf-144">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="1facf-145">En el **Caja fuerte de vínculos** de la organización que aparece, vaya al cuadro **Bloquear las siguientes direcciones URL.**</span><span class="sxs-lookup"><span data-stu-id="1facf-145">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="1facf-146">Configure una o más entradas como se describe en Sintaxis Entry para la lista ["Bloquear las siguientes direcciones URL".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="1facf-146">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="1facf-147">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1facf-147">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="1facf-148">Configurar la lista "Bloquear las siguientes direcciones URL" en PowerShell</span><span class="sxs-lookup"><span data-stu-id="1facf-148">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="1facf-149">Para obtener más información acerca de la sintaxis de entrada, vea [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="1facf-149">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="1facf-150">Puede usar el cmdlet **Get-AtpPolicyForO365** para ver las entradas existentes en la _propiedad BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="1facf-150">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="1facf-151">Para agregar valores que reemplacen las entradas existentes, use la siguiente sintaxis Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1facf-151">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="1facf-152">En este ejemplo se agregan las siguientes entradas a la lista:</span><span class="sxs-lookup"><span data-stu-id="1facf-152">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="1facf-153">Bloquee el dominio, los subdominios y las rutas de acceso fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1facf-153">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="1facf-154">Bloquee la investigación de subdominios, pero no el dominio primario u otros subdominios de tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="1facf-154">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="1facf-155">Para agregar o quitar valores sin afectar a otras entradas existentes, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="1facf-155">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="1facf-156">En este ejemplo se agrega una nueva entrada para adatum.com y se quita la entrada para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="1facf-156">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="1facf-157">Configurar Caja fuerte de vínculos para Office 365 aplicaciones en el portal de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1facf-157">Configure Safe Links protection for Office 365 apps in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="1facf-158">Caja fuerte La protección de vínculos Office 365 aplicaciones se aplica a documentos en aplicaciones Office de escritorio, móviles y web compatibles.</span><span class="sxs-lookup"><span data-stu-id="1facf-158">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="1facf-159">Para obtener más información, [consulta Caja fuerte configuración de vínculos para Office 365 aplicaciones](safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="1facf-159">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="1facf-160">En el portal Microsoft 365 Defender, vaya a Email **& Collaboration** Policies \> **& Rules** Threat \> **policies** \> **section** \> **Caja fuerte Links**.</span><span class="sxs-lookup"><span data-stu-id="1facf-160">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="1facf-161">En la **página Caja fuerte,** haga clic en **Configuración global**.</span><span class="sxs-lookup"><span data-stu-id="1facf-161">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="1facf-162">En la **directiva Caja fuerte vínculos** de la organización que aparece, configure las siguientes opciones en la sección Configuración que se aplican al contenido de las **aplicaciones** Office 365 compatibles:</span><span class="sxs-lookup"><span data-stu-id="1facf-162">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content in supported Office 365 apps** section:</span></span>

   - <span data-ttu-id="1facf-163">**Usar Caja fuerte en Office 365** aplicaciones: compruebe que la alternancia está a la derecha para habilitar Caja fuerte vínculos para aplicaciones Office 365 compatibles: ![ Activar ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="1facf-163">**Use Safe Links in Office 365 apps**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="1facf-164">No realizar un seguimiento cuando los usuarios hacen clic en vínculos protegidos en aplicaciones de **Office 365:** mueva el botón de alternancia a la izquierda para realizar un seguimiento de los clics de usuario relacionados con las direcciones URL bloqueadas en las aplicaciones Office 365 compatibles: Desactivar ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="1facf-164">**Do not track when users click protected links in Office 365 apps**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="1facf-165">No permitir que los usuarios hagan clic en la dirección URL original de las aplicaciones de **Office 365:** compruebe que la alternancia está a la derecha para impedir que los usuarios hagan clic en la dirección URL bloqueada original en las aplicaciones de Office 365 compatibles: Activar ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="1facf-165">**Do not let users click through to the original URL in Office 365 apps**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="1facf-166">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1facf-166">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="1facf-167">Configurar Caja fuerte de vínculos para Office 365 aplicaciones en PowerShell</span><span class="sxs-lookup"><span data-stu-id="1facf-167">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="1facf-168">Si prefiere usar PowerShell para configurar la protección de vínculos de Caja fuerte para aplicaciones de Office 365, use la sintaxis siguiente en Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1facf-168">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="1facf-169">En este ejemplo se configuran las siguientes opciones para la protección Caja fuerte vínculos en Office 365 aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="1facf-169">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="1facf-170">Caja fuerte Los vínculos Office 365 aplicaciones están activados (no estamos usando el parámetro _EnableSafeLinksForO365Clients_ y el valor predeterminado es $true).</span><span class="sxs-lookup"><span data-stu-id="1facf-170">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="1facf-171">Se realiza un seguimiento de los clics de usuario relacionados con las direcciones URL bloqueadas Office 365 aplicaciones admitidas.</span><span class="sxs-lookup"><span data-stu-id="1facf-171">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="1facf-172">Los usuarios no pueden hacer clic en la dirección URL bloqueada original en aplicaciones Office 365 compatibles (no estamos usando el parámetro _AllowClickThrough_ y el valor predeterminado es $false).</span><span class="sxs-lookup"><span data-stu-id="1facf-172">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="1facf-173">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="1facf-173">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1facf-174">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="1facf-174">How do you know these procedures worked?</span></span>

<span data-ttu-id="1facf-175">Para comprobar que ha configurado correctamente la configuración global de los vínculos de Caja fuerte (la lista Bloquear las siguientes direcciones **URL** y la configuración de protección de aplicaciones de Office 365), siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1facf-175">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="1facf-176">En el portal de Microsoft 365 Defender, vaya a Email **& Collaboration** Policies & \> **Rules** Threat policies section Caja fuerte Links click Global settings y verify the settings in the fly out \>  \>  \>  \> that appears. </span><span class="sxs-lookup"><span data-stu-id="1facf-176">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Safe Links** \> click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="1facf-177">En Exchange Online PowerShell o Exchange Online Protection PowerShell, ejecute el siguiente comando y compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="1facf-177">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="1facf-178">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="1facf-178">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
