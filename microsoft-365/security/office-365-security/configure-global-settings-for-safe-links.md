---
title: Configuración global de la configuración de vínculos seguros en Defender para Office 365
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
description: Los administradores pueden aprender a ver y configurar las opciones globales (la lista "Bloquear las siguientes direcciones URL" y la protección para aplicaciones de Office 365) para Vínculos seguros en Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 885fe6a06cce054bea6d6f20c24c5c1f2a159c07
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165732"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e4e0d-103">Configuración global de vínculos seguros en Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e4e0d-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e4e0d-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="e4e0d-104">**Applies to**</span></span>
- [<span data-ttu-id="e4e0d-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e4e0d-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="e4e0d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4e0d-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="e4e0d-107">Este artículo está destinado a los clientes empresariales que tienen [Microsoft Defender para Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="e4e0d-108">Si es un usuario principal que busca información sobre safelinks en Outlook, consulte [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="e4e0d-109">Vínculos seguros es una característica de Microsoft Defender para [Office 365](office-365-atp.md) que proporciona el análisis de direcciones URL de los mensajes de correo electrónico entrantes en el flujo de correo y el tiempo de comprobación de clics de direcciones URL y vínculos en mensajes de correo electrónico y en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="e4e0d-110">Para obtener más información, vea [Vínculos seguros en Microsoft Defender para Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="e4e0d-111">La mayoría de las opciones de vínculos seguros se configuran en las directivas de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="e4e0d-112">Para obtener instrucciones, [vea Configurar directivas de vínculos seguros en Microsoft Defender para Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="e4e0d-113">Sin embargo, Vínculos seguros también usa la configuración global que se aplica a todos los usuarios incluidos en cualquier directiva de vínculos seguros activa.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="e4e0d-114">Este área de configuración global:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-114">These global settings area:</span></span>

- <span data-ttu-id="e4e0d-115">La **lista Bloquear las siguientes direcciones** URL.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="e4e0d-116">Para obtener más información, vea [la lista "Bloquear las siguientes direcciones URL" para vínculos seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-116">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="e4e0d-117">Protección de vínculos seguros para aplicaciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="e4e0d-118">Para obtener más información, vea [La configuración de vínculos seguros para aplicaciones de Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-118">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="e4e0d-119">Puede configurar las opciones globales de vínculos seguros en el Centro de seguridad y cumplimiento de & o en PowerShell (Exchange Online PowerShell para organizaciones elegibles de Microsoft 365 con buzones en Exchange Online; EOP PowerShell independiente para organizaciones sin buzones de Exchange Online, pero con Suscripciones de complemento de Microsoft Defender para Office 365).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e4e0d-120">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="e4e0d-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e4e0d-121">Las características proporcionadas por la configuración global de vínculos seguros solo se aplican a los usuarios que se incluyen en las directivas de vínculos seguros activas.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="e4e0d-122">No hay ninguna directiva de vínculos seguros integrada o predeterminada, por lo que debe crear al menos una directiva de vínculos seguros para que esta configuración global esté activa.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="e4e0d-123">Para obtener instrucciones, [vea Configurar directivas de vínculos seguros en Microsoft Defender para Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="e4e0d-124">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e4e0d-125">Para ir directamente a la **página Vínculos seguros,** use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="e4e0d-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="e4e0d-126">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e4e0d-127">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e4e0d-128">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e4e0d-129">Para configurar las opciones globales de Vínculos seguros,  debe ser miembro de los grupos de roles Administración de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e4e0d-130">Para obtener acceso de solo lectura a la configuración global de Vínculos seguros, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e4e0d-131">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="e4e0d-132">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-132">**Notes**:</span></span>

  - <span data-ttu-id="e4e0d-133">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e4e0d-134">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="e4e0d-135">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e4e0d-136">Para obtener los valores recomendados para la configuración global de Vínculos seguros, vea [La configuración de vínculos seguros.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="e4e0d-137">Espere hasta 30 minutos para que se aplique una directiva nueva o actualizada.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="e4e0d-138">[Las nuevas características se agregan continuamente a Microsoft Defender para Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="e4e0d-139">A medida que se agregan nuevas características, es posible que deba realizar ajustes en las directivas de vínculos seguros existentes.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="e4e0d-140">Configurar la lista "Bloquear las siguientes direcciones URL" en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e4e0d-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="e4e0d-141">La **lista Bloquear las siguientes direcciones URL** identifica los vínculos que siempre deben bloquearse mediante el examen de vínculos seguros en las aplicaciones compatibles.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="e4e0d-142">Para obtener más información, [vea la lista "Bloquear las siguientes direcciones URL" para Vínculos seguros.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-142">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="e4e0d-143">En el Centro de & cumplimiento,  vaya a Vínculos seguros de ATP de directiva de administración de amenazas y, a continuación, haga clic \>  \> en **Configuración global.**</span><span class="sxs-lookup"><span data-stu-id="e4e0d-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="e4e0d-144">En la **directiva de vínculos seguros de su organización** que aparece, vaya al cuadro Bloquear las siguientes **direcciones** URL.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="e4e0d-145">Configure una o más entradas como se describe en la sintaxis Entry para la lista ["Bloquear las siguientes direcciones URL".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="e4e0d-146">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="e4e0d-147">Configurar la lista "Bloquear las siguientes direcciones URL" en PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4e0d-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="e4e0d-148">Para obtener más información acerca de la sintaxis de entrada, vea La sintaxis [de entrada para la lista "Bloquear las siguientes direcciones URL".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="e4e0d-149">Puede usar el cmdlet **Get-AtpPolicyForO365** para ver las entradas existentes en la _propiedad BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="e4e0d-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="e4e0d-150">Para agregar valores que reemplacen las entradas existentes, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="e4e0d-151">En este ejemplo se agregan las siguientes entradas a la lista:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="e4e0d-152">Bloquee el dominio, los subdominios y las rutas de acceso fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="e4e0d-153">Bloquee la investigación de subdominios, pero no el dominio primario u otros subdominios de tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="e4e0d-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="e4e0d-154">Para agregar o quitar valores sin que ello afecte a otras entradas existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="e4e0d-155">En este ejemplo se agrega una nueva entrada adatum.com y se quita la entrada para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="e4e0d-156">Configurar la protección de vínculos seguros para aplicaciones de Office 365 en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e4e0d-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="e4e0d-157">La protección de vínculos seguros para aplicaciones de Office 365 se aplica a documentos en aplicaciones de escritorio, móviles y web de Office compatibles.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="e4e0d-158">Para obtener más información, vea [La configuración de vínculos seguros para aplicaciones de Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-158">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="e4e0d-159">En el Centro de & cumplimiento,  vaya a Vínculos seguros de ATP de directiva de administración de amenazas y, a continuación, haga clic \>  \> en **Configuración global.**</span><span class="sxs-lookup"><span data-stu-id="e4e0d-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="e4e0d-160">En la **directiva de vínculos seguros** de su organización que aparece, configure las siguientes opciones en la sección Configuración que se aplican al contenido excepto al **correo** electrónico:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="e4e0d-161">**Aplicaciones de Office 365:** compruebe que el botón de alternancia está a la derecha para habilitar vínculos seguros para las aplicaciones de Office 365 compatibles: ![ activar. ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="e4e0d-162">**No realice un seguimiento** de cuándo los usuarios hacen clic en Vínculos seguros: mueva el botón de alternancia a la izquierda para realizar un seguimiento de los clics del usuario relacionados con las direcciones URL bloqueadas en las aplicaciones compatibles de Office 365: ![ ](../../media/scc-toggle-off.png) Desactivar.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="e4e0d-163">No permitir que los usuarios hagan clic a través de Vínculos seguros a la dirección **URL original:** Compruebe que el botón de alternancia está a la derecha para evitar que los usuarios hagan clic en la dirección URL bloqueada original en las aplicaciones compatibles de Office 365: Activar. ![ ](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="e4e0d-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="e4e0d-164">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="e4e0d-165">Configurar la protección de vínculos seguros para aplicaciones de Office 365 en PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4e0d-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="e4e0d-166">Si prefiere usar PowerShell para configurar la protección de vínculos seguros para aplicaciones de Office 365, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="e4e0d-167">En este ejemplo se configuran las siguientes opciones para la protección de vínculos seguros en las aplicaciones de Office 365:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="e4e0d-168">Vínculos seguros para aplicaciones de Office 365 está activado (no estamos usando el parámetro _EnableSafeLinksForO365Clients_ y el valor predeterminado es $true).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="e4e0d-169">Se realiza un seguimiento de los clics del usuario relacionados con las direcciones URL bloqueadas en las aplicaciones compatibles de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4e0d-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="e4e0d-170">Los usuarios no pueden hacer clic en la dirección URL bloqueada original en aplicaciones compatibles de Office 365 (no estamos usando el parámetro _AllowClickThrough_ y el valor predeterminado es $false).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="e4e0d-171">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e4e0d-172">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="e4e0d-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="e4e0d-173">Para comprobar que ha configurado correctamente la configuración global de Vínculos seguros (la lista Bloquear las siguientes direcciones **URL** y la configuración de protección de aplicaciones de Office 365), siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="e4e0d-174">En el Centro de & cumplimiento,  vaya a Vínculos seguros de ATP de directiva de administración de amenazas, haga clic en Configuración global y compruebe la configuración en el control emergente \>  \> que aparece. </span><span class="sxs-lookup"><span data-stu-id="e4e0d-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="e4e0d-175">En Exchange Online PowerShell o Exchange Online Protection PowerShell, ejecute el siguiente comando y compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="e4e0d-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="e4e0d-176">Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="e4e0d-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
