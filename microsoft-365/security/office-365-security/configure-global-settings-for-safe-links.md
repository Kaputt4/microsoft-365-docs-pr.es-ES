---
title: Establecer la configuración global para la configuración de vínculos seguros en Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo ver y configurar las opciones globales (la lista "bloquear las siguientes direcciones URL" y la protección de las aplicaciones de Office 365) para vínculos seguros en Office 365 protección contra amenazas avanzada (ATP).
ms.openlocfilehash: 6ca18bfb555419a8f4a61b55715f328ed7da5e88
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328566"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a><span data-ttu-id="3657b-103">Establecer la configuración global para vínculos seguros en Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="3657b-103">Configure global settings for Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="3657b-104">Este artículo está destinado a los clientes empresariales que tienen la [Protección contra amenazas avanzada de Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="3657b-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="3657b-105">Si es un usuario doméstico que busca información sobre Safelinks en Outlook, consulte [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="3657b-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="3657b-106">Vínculos seguros es una característica de la [protección contra amenazas avanzada (ATP) de Office 365](office-365-atp.md) que proporciona análisis de URL de los mensajes de correo electrónico entrantes en el flujo de correo y la hora de la comprobación de direcciones URL y vínculos en los mensajes de correo electrónico y en otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="3657b-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="3657b-107">Para obtener más información, vea [vínculos seguros en Office 365 ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="3657b-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="3657b-108">La configuración de vínculos más seguros se configura en directivas de vínculos a prueba de errores.</span><span class="sxs-lookup"><span data-stu-id="3657b-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="3657b-109">Para obtener instrucciones, consulte [configurar directivas de vínculos seguros en Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3657b-109">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="3657b-110">Sin embargo, vínculos seguros también usa la configuración global que se aplica a todos los usuarios incluidos en las directivas de vínculos seguros activos.</span><span class="sxs-lookup"><span data-stu-id="3657b-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="3657b-111">Este área de configuración global:</span><span class="sxs-lookup"><span data-stu-id="3657b-111">These global settings area:</span></span>

- <span data-ttu-id="3657b-112">La lista **bloquear las siguientes direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="3657b-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="3657b-113">Para obtener más información, consulte [la lista "bloquear las siguientes direcciones URL" para vínculos seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="3657b-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="3657b-114">Protección de vínculos seguros para aplicaciones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="3657b-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="3657b-115">Para obtener más información, vea [configuración de vínculos seguros para aplicaciones de Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="3657b-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="3657b-116">Puede establecer la configuración de vínculos seguros globales en el centro de seguridad & cumplimiento o en PowerShell (Exchange Online PowerShell para las organizaciones de Microsoft 365 con buzones de correo en Exchange Online; independiente de EOP para las organizaciones sin buzones de Exchange Online, pero con las suscripciones complementarias de ATP de Office 365).</span><span class="sxs-lookup"><span data-stu-id="3657b-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3657b-117">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="3657b-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3657b-118">Las características que proporciona la configuración global para vínculos seguros solo se aplican a los usuarios que se incluyen en las directivas de vínculos seguros activos.</span><span class="sxs-lookup"><span data-stu-id="3657b-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="3657b-119">No hay una directiva de vínculos a prueba de errores integrada o predeterminada, por lo que debe crear al menos una directiva de vínculos seguros para que esta configuración global esté activa.</span><span class="sxs-lookup"><span data-stu-id="3657b-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="3657b-120">Para obtener instrucciones, consulte [configurar directivas de vínculos seguros en Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3657b-120">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="3657b-121">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3657b-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3657b-122">Para ir directamente a la página de **vínculos seguros de ATP** , use <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="3657b-122">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="3657b-123">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3657b-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3657b-124">Para conectarse a EOP PowerShell independiente, consulte [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell) (Conexión a Exchange Online Protection PowerShell).</span><span class="sxs-lookup"><span data-stu-id="3657b-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3657b-125">Para ver y configurar las opciones globales de vínculos seguros, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="3657b-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="3657b-126">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3657b-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="3657b-127">**Administración** de la organización en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3657b-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="3657b-128">Para conocer los valores recomendados para la configuración global de vínculos seguros, consulte [configuración de vínculos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span><span class="sxs-lookup"><span data-stu-id="3657b-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="3657b-129">Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="3657b-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="3657b-130">[Las nuevas características se agregan continuamente a ATP](office-365-atp.md#new-features-in-office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="3657b-130">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="3657b-131">A medida que se agreguen nuevas características, es posible que deba realizar ajustes en las directivas de vínculos a prueba de errores existentes.</span><span class="sxs-lookup"><span data-stu-id="3657b-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="3657b-132">Configurar la lista "bloquear las siguientes direcciones URL" en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3657b-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="3657b-133">La lista **bloquear las siguientes direcciones URL** identifica los vínculos que deben bloquearse siempre mediante la detección de vínculos seguros en las aplicaciones compatibles.</span><span class="sxs-lookup"><span data-stu-id="3657b-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="3657b-134">Para obtener más información, consulte [la lista "bloquear las siguientes direcciones URL" para vínculos seguros](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="3657b-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="3657b-135">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**y, a continuación, haga clic en **configuración global**.</span><span class="sxs-lookup"><span data-stu-id="3657b-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="3657b-136">En la **Directiva de vínculos seguros de la organización** que aparece, vaya al cuadro **bloquear las siguientes direcciones URL** .</span><span class="sxs-lookup"><span data-stu-id="3657b-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="3657b-137">Configure una o más entradas como se describe en [la sintaxis de entrada de la lista "bloquear las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="3657b-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="3657b-138">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3657b-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="3657b-139">Configurar la lista "bloquear las siguientes direcciones URL" en PowerShell</span><span class="sxs-lookup"><span data-stu-id="3657b-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="3657b-140">Para obtener información detallada sobre la sintaxis de la entrada, consulte [entry Syntax para la lista "bloquear las siguientes direcciones URL"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="3657b-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="3657b-141">Puede usar el cmdlet **Get-AtpPolicyForO365** para ver las entradas existentes en la propiedad _BlockURLs_ .</span><span class="sxs-lookup"><span data-stu-id="3657b-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="3657b-142">Para agregar valores que van a reemplazar las entradas existentes, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3657b-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="3657b-143">En este ejemplo se agregan las siguientes entradas a la lista:</span><span class="sxs-lookup"><span data-stu-id="3657b-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="3657b-144">Bloquee el dominio, los subdominios y las rutas de fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="3657b-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="3657b-145">Bloquear la investigación del subdominio, pero no el dominio principal u otros subdominios de tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="3657b-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="3657b-146">Para agregar o quitar valores sin que ello afecte a las entradas existentes, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="3657b-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="3657b-147">En este ejemplo se agrega una nueva entrada para adatum.com y se quita la entrada de fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="3657b-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="3657b-148">Configurar la protección de vínculos seguros para las aplicaciones de Office 365 en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3657b-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="3657b-149">La protección de vínculos seguros para las aplicaciones de Office 365 se aplica a los documentos de aplicaciones Web, móviles y de escritorio de Office compatibles.</span><span class="sxs-lookup"><span data-stu-id="3657b-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="3657b-150">Para obtener más información, vea [configuración de vínculos seguros para aplicaciones de Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="3657b-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="3657b-151">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**y, a continuación, haga clic en **configuración global**.</span><span class="sxs-lookup"><span data-stu-id="3657b-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="3657b-152">En la **Directiva de vínculos a prueba de errores de la organización** hacia fuera que aparece, configure las siguientes opciones en la sección **configuración que se aplica a contenido, excepto correo electrónico** :</span><span class="sxs-lookup"><span data-stu-id="3657b-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="3657b-153">**Aplicaciones de office 365**: Compruebe que el botón de alternancia sea el derecho para habilitar vínculos seguros para las aplicaciones de Office 365 compatibles: ![ activar o desactivar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="3657b-153">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="3657b-154">**No realizar seguimiento cuando los usuarios hacen clic en vínculos seguros**: mueva el botón de alternancia a la izquierda para realizar un seguimiento de los clics de usuario relacionados con direcciones URL bloqueadas en aplicaciones de Office 365 compatibles: desactivar ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="3657b-154">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="3657b-155">**No permita que los usuarios hagan clic en los vínculos seguros a la dirección URL original**: Compruebe que el botón de alternancia es hacia la derecha para impedir que los usuarios hagan clic a través de la URL bloqueada original en aplicaciones admitidas de Office 365: ![ activar o desactivar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="3657b-155">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="3657b-156">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3657b-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="3657b-157">Configurar la protección de vínculos seguros para las aplicaciones de Office 365 en PowerShell</span><span class="sxs-lookup"><span data-stu-id="3657b-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="3657b-158">Si prefiere usar PowerShell para configurar la protección de vínculos seguros para las aplicaciones de Office 365, use la siguiente sintaxis en Exchange Online PowerShell o Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3657b-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="3657b-159">En este ejemplo se configura la siguiente configuración para la protección de vínculos seguros en las aplicaciones de Office 365:</span><span class="sxs-lookup"><span data-stu-id="3657b-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="3657b-160">Vínculos seguros para las aplicaciones de Office 365 está activado (no se usa el parámetro _EnableSafeLinksForO365Clients_ y el valor predeterminado es $true).</span><span class="sxs-lookup"><span data-stu-id="3657b-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="3657b-161">Se realiza un seguimiento de los clics de usuario relacionados con las direcciones URL bloqueadas en las aplicaciones de Office 365 compatibles.</span><span class="sxs-lookup"><span data-stu-id="3657b-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="3657b-162">Los usuarios no pueden hacer clic a través de la dirección URL bloqueada original en las aplicaciones de Office 365 compatibles (no se usa el parámetro _AllowClickThrough_ y el valor predeterminado es $false).</span><span class="sxs-lookup"><span data-stu-id="3657b-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="3657b-163">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="3657b-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3657b-164">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="3657b-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="3657b-165">Para comprobar que ha configurado correctamente la configuración global para vínculos seguros (la lista **bloquear las siguientes direcciones URL** y la configuración de protección de aplicaciones de Office 365), siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="3657b-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="3657b-166">En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP Safe links**, haga clic en **configuración global**y Compruebe la configuración de la volar hacia fuera que aparece.</span><span class="sxs-lookup"><span data-stu-id="3657b-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="3657b-167">En PowerShell de Exchange Online PowerShell o Exchange Online Protection, ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="3657b-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="3657b-168">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="3657b-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
