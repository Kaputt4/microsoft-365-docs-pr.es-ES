---
title: Establecer la configuración global para la configuración de vínculos seguros en defender para Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo ver y configurar las opciones globales (la lista "bloquear las siguientes direcciones URL" y la protección de las aplicaciones de Office 365) para obtener vínculos seguros en Microsoft defender para Office 365.
ms.openlocfilehash: 2793985e6289b26baad268925cbf9c5e9a89dce9
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572434"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="458fd-103">Establecer la configuración global para vínculos seguros en Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="458fd-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="458fd-104">Este artículo está destinado a los clientes empresariales que tienen [Microsoft defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="458fd-104">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="458fd-105">Si es un usuario doméstico que busca información sobre Safelinks en Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="458fd-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="458fd-106">Vínculos seguros es una característica de [Microsoft defender para Office 365](office-365-atp.md) que proporciona análisis de URL de los mensajes de correo electrónico entrantes en el flujo de correo y la hora de la comprobación de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="458fd-106">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="458fd-107">Para obtener más información, vea [vínculos a prueba de errores en Microsoft defender para Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="458fd-107">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="458fd-108">La configuración de vínculos más seguros se configura en directivas de vínculos a prueba de errores.</span><span class="sxs-lookup"><span data-stu-id="458fd-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="458fd-109">Para obtener instrucciones, consulte [configurar directivas de vínculos seguros en Microsoft defender para Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="458fd-109">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="458fd-110">Sin embargo, vínculos seguros también usa la configuración global que se aplica a todos los usuarios incluidos en las directivas de vínculos seguros activos.</span><span class="sxs-lookup"><span data-stu-id="458fd-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="458fd-111">Este área de configuración global:</span><span class="sxs-lookup"><span data-stu-id="458fd-111">These global settings area:</span></span>

- <span data-ttu-id="458fd-112">La lista **bloquear las siguientes direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="458fd-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="458fd-113">Para obtener más información, consulte [la lista "bloquear las siguientes direcciones URL" para vínculos seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="458fd-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="458fd-114">Protección de vínculos seguros para aplicaciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="458fd-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="458fd-115">Para obtener más información, vea [configuración de vínculos seguros para aplicaciones de Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="458fd-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="458fd-116">Puede establecer la configuración global de vínculos seguros en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para las organizaciones de Microsoft 365 con buzones de correo en Exchange Online; independiente de EOP para organizaciones sin buzones de Exchange Online, pero con Microsoft defender para Office 365 para las suscripciones complementarias).</span><span class="sxs-lookup"><span data-stu-id="458fd-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="458fd-117">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="458fd-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="458fd-118">Las características que proporciona la configuración global para vínculos seguros solo se aplican a los usuarios que se incluyen en las directivas de vínculos seguros activos.</span><span class="sxs-lookup"><span data-stu-id="458fd-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="458fd-119">No hay una directiva de vínculos a prueba de errores integrada o predeterminada, por lo que debe crear al menos una directiva de vínculos seguros para que esta configuración global esté activa.</span><span class="sxs-lookup"><span data-stu-id="458fd-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="458fd-120">Para obtener instrucciones, consulte [configurar directivas de vínculos seguros en Microsoft defender para Office 365](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="458fd-120">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="458fd-121">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="458fd-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="458fd-122">Para ir directamente a la página de **vínculos seguros** , use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="458fd-122">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="458fd-123">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="458fd-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="458fd-124">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="458fd-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="458fd-125">Debe tener asignados permisos en el centro de seguridad & cumplimiento antes de poder llevar a cabo los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="458fd-125">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="458fd-126">Para establecer la configuración global de vínculos seguros, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="458fd-126">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="458fd-127">Para tener acceso de solo lectura a la configuración global de vínculos seguros, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="458fd-127">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="458fd-128">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="458fd-128">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="458fd-129">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="458fd-129">**Notes**:</span></span>

  - <span data-ttu-id="458fd-130">La adición de usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="458fd-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="458fd-131">Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="458fd-131">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="458fd-132">El grupo de roles administración de la **organización de solo vista** de [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="458fd-132">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="458fd-133">Para conocer los valores recomendados para la configuración global de vínculos seguros, consulte [configuración de vínculos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span><span class="sxs-lookup"><span data-stu-id="458fd-133">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="458fd-134">Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="458fd-134">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="458fd-135">[Las nuevas características se agregan continuamente a Microsoft defender para Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="458fd-135">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="458fd-136">A medida que se agreguen nuevas características, es posible que deba realizar ajustes en las directivas de vínculos a prueba de errores existentes.</span><span class="sxs-lookup"><span data-stu-id="458fd-136">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="458fd-137">Configurar la lista "bloquear las siguientes direcciones URL" en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="458fd-137">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="458fd-138">La lista **bloquear las siguientes direcciones URL** identifica los vínculos que deben bloquearse siempre mediante la detección de vínculos seguros en las aplicaciones compatibles.</span><span class="sxs-lookup"><span data-stu-id="458fd-138">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="458fd-139">Para obtener más información, consulte [la lista "bloquear las siguientes direcciones URL" para vínculos seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="458fd-139">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="458fd-140">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links** y, a continuación, haga clic en **configuración global**.</span><span class="sxs-lookup"><span data-stu-id="458fd-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="458fd-141">En la **Directiva de vínculos seguros de la organización** que aparece, vaya al cuadro **bloquear las siguientes direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="458fd-141">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="458fd-142">Configure una o más entradas como se describe en [la sintaxis de entrada de la lista "bloquear las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="458fd-142">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="458fd-143">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="458fd-143">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="458fd-144">Configurar la lista "bloquear las siguientes direcciones URL" en PowerShell</span><span class="sxs-lookup"><span data-stu-id="458fd-144">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="458fd-145">Para obtener información detallada sobre la sintaxis de la entrada, consulte [entry Syntax para la lista "bloquear las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="458fd-145">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="458fd-146">Puede usar el cmdlet **Get-AtpPolicyForO365** para ver las entradas existentes en la propiedad _BlockURLs_ .</span><span class="sxs-lookup"><span data-stu-id="458fd-146">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="458fd-147">Para agregar valores que van a reemplazar las entradas existentes, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="458fd-147">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="458fd-148">En este ejemplo se agregan las siguientes entradas a la lista:</span><span class="sxs-lookup"><span data-stu-id="458fd-148">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="458fd-149">Bloquee el dominio, los subdominios y las rutas de fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="458fd-149">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="458fd-150">Bloquear la investigación del subdominio, pero no el dominio principal u otros subdominios de tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="458fd-150">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="458fd-151">Para agregar o quitar valores sin que ello afecte a las entradas existentes, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="458fd-151">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="458fd-152">En este ejemplo se agrega una nueva entrada para adatum.com y se quita la entrada de fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="458fd-152">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="458fd-153">Configurar la protección de vínculos seguros para las aplicaciones de Office 365 en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="458fd-153">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="458fd-154">La protección de vínculos seguros para las aplicaciones de Office 365 se aplica a los documentos de aplicaciones Web, móviles y de escritorio de Office compatibles.</span><span class="sxs-lookup"><span data-stu-id="458fd-154">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="458fd-155">Para obtener más información, vea [configuración de vínculos seguros para aplicaciones de Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="458fd-155">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="458fd-156">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links** y, a continuación, haga clic en **configuración global**.</span><span class="sxs-lookup"><span data-stu-id="458fd-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="458fd-157">En la **Directiva de vínculos a prueba de errores de la organización** hacia fuera que aparece, configure las siguientes opciones en la sección **configuración que se aplica a contenido, excepto correo electrónico** :</span><span class="sxs-lookup"><span data-stu-id="458fd-157">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="458fd-158">**Aplicaciones de office 365**: Compruebe que el botón de alternancia sea el derecho para habilitar vínculos seguros para las aplicaciones de Office 365 compatibles: ![ activar o desactivar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="458fd-158">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="458fd-159">**No realizar seguimiento cuando los usuarios hacen clic en vínculos seguros**: mueva el botón de alternancia a la izquierda para realizar un seguimiento de los clics de usuario relacionados con direcciones URL bloqueadas en aplicaciones de Office 365 compatibles: desactivar ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="458fd-159">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="458fd-160">**No permita que los usuarios hagan clic en los vínculos seguros a la dirección URL original**: Compruebe que el botón de alternancia es hacia la derecha para impedir que los usuarios hagan clic a través de la URL bloqueada original en aplicaciones admitidas de Office 365: ![ activar o desactivar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="458fd-160">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="458fd-161">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="458fd-161">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="458fd-162">Configurar la protección de vínculos seguros para las aplicaciones de Office 365 en PowerShell</span><span class="sxs-lookup"><span data-stu-id="458fd-162">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="458fd-163">Si prefiere usar PowerShell para configurar la protección de vínculos seguros para las aplicaciones de Office 365, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="458fd-163">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="458fd-164">En este ejemplo se configura la siguiente configuración para la protección de vínculos seguros en las aplicaciones de Office 365:</span><span class="sxs-lookup"><span data-stu-id="458fd-164">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="458fd-165">Vínculos seguros para las aplicaciones de Office 365 está activado (no se usa el parámetro _EnableSafeLinksForO365Clients_ y el valor predeterminado es $true).</span><span class="sxs-lookup"><span data-stu-id="458fd-165">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="458fd-166">Se realiza un seguimiento de los clics de usuario relacionados con las direcciones URL bloqueadas en las aplicaciones de Office 365 compatibles.</span><span class="sxs-lookup"><span data-stu-id="458fd-166">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="458fd-167">Los usuarios no pueden hacer clic a través de la dirección URL bloqueada original en las aplicaciones de Office 365 compatibles (no se usa el parámetro _AllowClickThrough_ y el valor predeterminado es $false).</span><span class="sxs-lookup"><span data-stu-id="458fd-167">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="458fd-168">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="458fd-168">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="458fd-169">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="458fd-169">How do you know these procedures worked?</span></span>

<span data-ttu-id="458fd-170">Para comprobar que ha configurado correctamente la configuración global para vínculos seguros (la lista **bloquear las siguientes direcciones URL** y la configuración de protección de aplicaciones de Office 365), siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="458fd-170">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="458fd-171">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**, haga clic en **configuración global** y Compruebe la configuración de la volar hacia fuera que aparece.</span><span class="sxs-lookup"><span data-stu-id="458fd-171">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="458fd-172">En PowerShell de Exchange Online PowerShell o Exchange Online Protection, ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="458fd-172">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="458fd-173">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="458fd-173">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
