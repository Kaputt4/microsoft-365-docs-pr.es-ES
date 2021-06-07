---
title: Configuración de directivas contra phishing en EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a crear, modificar y eliminar las directivas contra suplantación de identidad que están disponibles en organizaciones de Exchange Online Protection (EOP) con o sin buzones Exchange Online correo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f074596f0391e98735b07d17390cd058fd6fcafe
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793021"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="5a164-103">Configuración de directivas contra phishing en EOP</span><span class="sxs-lookup"><span data-stu-id="5a164-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5a164-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="5a164-104">**Applies to**</span></span>
- [<span data-ttu-id="5a164-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5a164-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="5a164-106">En Microsoft 365 organizaciones con buzones en organizaciones de Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de correo de Exchange Online, hay una directiva contra la suplantación de identidad predeterminada que contiene un número limitado de características contra la suplantación de identidad que están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a164-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="5a164-107">Para obtener más información, consulte [Configuración de suplantación de identidad en las directivas contra phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="5a164-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="5a164-108">Los administradores pueden ver, editar y configurar (pero no eliminar) la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a164-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="5a164-109">Para mayor granularidad, también puede crear directivas personalizadas contra la suplantación de identidad que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="5a164-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="5a164-110">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="5a164-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="5a164-111">Las organizaciones con Exchange Online buzones de correo pueden configurar directivas contra la suplantación de identidad en el centro de seguridad de Microsoft 365 o en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a164-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 security center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="5a164-112">Las organizaciones EOP independientes solo pueden usar el centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5a164-112">Standalone EOP organizations can only use the security center.</span></span>

<span data-ttu-id="5a164-113">Para obtener información sobre cómo crear y modificar las directivas contra suplantación de identidad más avanzadas que están disponibles en Microsoft Defender para Office 365, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5a164-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="5a164-114">Los elementos básicos de una directiva contra la suplantación de identidad son:</span><span class="sxs-lookup"><span data-stu-id="5a164-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="5a164-115">**La directiva contra suplantación de** identidad : especifica las protecciones de suplantación de identidad (phishing) que se habilitarán o deshabilitarán y las acciones que se aplicarán a las opciones.</span><span class="sxs-lookup"><span data-stu-id="5a164-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="5a164-116">**La regla contra suplantación de** identidad : especifica la prioridad y los filtros de destinatarios (a quién se aplica la directiva) para una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5a164-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="5a164-117">La diferencia entre estos dos elementos no es obvia al administrar directivas contra suplantación de identidad en el centro de seguridad:</span><span class="sxs-lookup"><span data-stu-id="5a164-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the security center:</span></span>

- <span data-ttu-id="5a164-118">Al crear una directiva contra suplantación de identidad ( phishing), en realidad está creando una regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada al mismo tiempo que usa el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="5a164-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="5a164-119">Al modificar una directiva contra suplantación de identidad, la configuración relacionada con el nombre, la prioridad, la habilitada o deshabilitada, y los filtros de destinatarios modifican la regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5a164-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="5a164-120">Todas las demás opciones modifican la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="5a164-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="5a164-121">Al quitar una directiva contra phishing, se quitan la regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada.</span><span class="sxs-lookup"><span data-stu-id="5a164-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="5a164-122">En Exchange Online PowerShell, administra la directiva y la regla por separado.</span><span class="sxs-lookup"><span data-stu-id="5a164-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="5a164-123">Para obtener más información, vea la sección [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5a164-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="5a164-124">Cada organización tiene una directiva contra suplantación de identidad integrada denominada Office365 AntiPhish Default que tiene estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="5a164-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="5a164-125">La directiva se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla contra la suplantación de identidad (filtros de destinatarios) asociada a la directiva.</span><span class="sxs-lookup"><span data-stu-id="5a164-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="5a164-126">La directiva tiene un valor de prioridad personalizado **Mínimo** que no se puede modificar (la directiva siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="5a164-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="5a164-127">Las directivas personalizadas que cree siempre tendrán una prioridad mayor.</span><span class="sxs-lookup"><span data-stu-id="5a164-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="5a164-128">La directiva es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True`), y no puede eliminar esta directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a164-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="5a164-129">Para aumentar la eficacia de la protección contra phishing, puede crear directivas personalizadas contra suplantación de identidad con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="5a164-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5a164-130">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="5a164-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5a164-131">Puede abrir el Centro de seguridad en <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="5a164-131">You open the security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="5a164-132">Para ir directamente a la **página Anti-phishing,** use <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="5a164-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="5a164-133">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5a164-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="5a164-134">No puede administrar directivas contra suplantación de identidad (phishing) en PowerShell de EOP independiente.</span><span class="sxs-lookup"><span data-stu-id="5a164-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="5a164-135">Debe tener permisos asignados en **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="5a164-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="5a164-136">Para agregar, modificar y eliminar directivas contra suplantación de identidad, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="5a164-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="5a164-137">Para obtener acceso de solo lectura a directivas contra suplantación de identidad, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="5a164-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="5a164-138">Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="5a164-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="5a164-139">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="5a164-139">**Notes**:</span></span>

  - <span data-ttu-id="5a164-140">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a164-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5a164-141">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5a164-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="5a164-142">El **grupo de roles Administración** de la organización de solo vista [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="5a164-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="5a164-143">Para obtener nuestra configuración recomendada para las directivas contra suplantación de identidad, vea Configuración de directivas [de EOP contra suplantación de identidad](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="5a164-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="5a164-144">Permitir hasta 30 minutos para que se aplique la directiva actualizada.</span><span class="sxs-lookup"><span data-stu-id="5a164-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="5a164-145">Para obtener información sobre dónde se aplican las directivas contra suplantación de identidad en la canalización de filtrado, vea [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="5a164-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security-center-to-create-anti-phishing-policies"></a><span data-ttu-id="5a164-146">Usar el centro de seguridad para crear directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-146">Use the security center to create anti-phishing policies</span></span>

<span data-ttu-id="5a164-147">La creación de una directiva contra suplantación de identidad personalizada en el centro de seguridad crea la regla contra suplantación de identidad (phishing) y la directiva contra suplantación de identidad asociada al mismo tiempo con el mismo nombre para ambos.</span><span class="sxs-lookup"><span data-stu-id="5a164-147">Creating a custom anti-phishing policy in the security center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="5a164-148">En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="5a164-148">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="5a164-149">En la **página Anti-phishing,** haga clic ![ en Crear icono ](../../media/m365-cc-sc-create-icon.png) **Crear**.</span><span class="sxs-lookup"><span data-stu-id="5a164-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="5a164-150">Se abrirá el asistente para directivas.</span><span class="sxs-lookup"><span data-stu-id="5a164-150">The policy wizard opens.</span></span> <span data-ttu-id="5a164-151">En la **página Nombre de directiva,** configure estas opciones:</span><span class="sxs-lookup"><span data-stu-id="5a164-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="5a164-152">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="5a164-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="5a164-153">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="5a164-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="5a164-154">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a164-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="5a164-155">En la página **Usuarios, grupos y dominios** que aparece, identifique los destinatarios internos a los que se aplica la directiva (condiciones de destinatario):</span><span class="sxs-lookup"><span data-stu-id="5a164-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="5a164-156">**Usuarios**: los buzones, usuarios de correo o contactos de correo especificados de su organización.</span><span class="sxs-lookup"><span data-stu-id="5a164-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="5a164-157">**Grupos**: los grupos de distribución, los grupos de seguridad habilitados para correo electrónico o los Grupos de Microsoft 365 especificados de la organización.</span><span class="sxs-lookup"><span data-stu-id="5a164-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="5a164-158">**Dominios**: todos los destinatarios de los [dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) especificados en la organización.</span><span class="sxs-lookup"><span data-stu-id="5a164-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="5a164-159">Haga clic en el cuadro correspondiente, comience a escribir un valor y seleccione el valor que desee de los resultados.</span><span class="sxs-lookup"><span data-stu-id="5a164-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="5a164-160">Repita este proceso tantas veces como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="5a164-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="5a164-161">Para quitar un valor existente, haga clic en Quitar</span><span class="sxs-lookup"><span data-stu-id="5a164-161">To remove an existing value, click remove</span></span> ![Icono de quitar](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="5a164-163">junto al valor.</span><span class="sxs-lookup"><span data-stu-id="5a164-163">next to the value.</span></span>

   <span data-ttu-id="5a164-164">Para los usuarios o grupos, puede usar la mayoría de los identificadores (nombre, nombre para mostrar, alias, dirección de correo electrónico, nombre de cuenta, etc.), pero el nombre para mostrar correspondiente se muestra en los resultados.</span><span class="sxs-lookup"><span data-stu-id="5a164-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="5a164-165">Para los usuarios, escriba un asterisco (\*) para ver todos los valores disponibles.</span><span class="sxs-lookup"><span data-stu-id="5a164-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="5a164-166">Varios valores en la misma condición usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="5a164-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="5a164-167">Hay diferentes condiciones que usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="5a164-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="5a164-168">**Excluir estos usuarios, grupos y dominios**: para agregar excepciones a los destinatarios internos a los que se aplica la directiva (excepciones de destinatarios), seleccione esta opción y configure las excepciones.</span><span class="sxs-lookup"><span data-stu-id="5a164-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="5a164-169">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="5a164-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="5a164-170">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a164-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="5a164-171">En la **página Protección contra &** de suplantación de identidad que aparece, use la casilla Habilitar la inteligencia suplantación de identidad para activar o desactivar la inteligencia suplantación de identidad. </span><span class="sxs-lookup"><span data-stu-id="5a164-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="5a164-172">El valor predeterminado está en (seleccionado) y se recomienda dejarlo en.</span><span class="sxs-lookup"><span data-stu-id="5a164-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="5a164-173">La acción se configura para realizar en mensajes suplantados bloqueados en la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="5a164-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="5a164-174">Para desactivar la inteligencia de suplantación, desactive la casilla.</span><span class="sxs-lookup"><span data-stu-id="5a164-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5a164-175">No es necesario desactivar la protección contra la suplantación si el registro MX no apunta a Microsoft 365; habilitar el filtrado mejorado para conectores en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5a164-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="5a164-176">Para obtener instrucciones, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="5a164-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="5a164-177">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a164-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="5a164-178">En la página **Acciones** que aparece, configure las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5a164-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="5a164-179">**Si el mensaje se detecta como** suplantación: esta configuración solo está disponible si seleccionó Habilitar la inteligencia de suplantación en la página anterior. </span><span class="sxs-lookup"><span data-stu-id="5a164-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="5a164-180">Seleccione una de las siguientes acciones en la lista desplegable para los mensajes de remitentes suplantados bloqueados:</span><span class="sxs-lookup"><span data-stu-id="5a164-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="5a164-181">**Mover el mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="5a164-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="5a164-182">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="5a164-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="5a164-183">**Sugerencias de seguridad & indicadores:** esta configuración solo está disponible si seleccionó Habilitar la inteligencia de suplantación **en** la página anterior:</span><span class="sxs-lookup"><span data-stu-id="5a164-183">**Safety tips & indicators**: This setting is available only if you selected **Enable spoof intelligence** on the previous page:</span></span>
     - <span data-ttu-id="5a164-184">**Mostrar (?)** para remitentes no autenticados para suplantación de identidad: agrega un signo de interrogación a la foto del remitente  en el cuadro De de Outlook si el mensaje no pasa comprobaciones SPF o DKIM y el mensaje no pasa dmarc ni autenticación compuesta [.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="5a164-184">**Show (?) for unauthenticated senders for spoof**: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="5a164-185">**Mostrar etiqueta "via":** agrega una etiqueta via (chris@contoso.com a través de fabrikam.com) a la dirección De si es diferente del dominio en la firma DKIM o la dirección **MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="5a164-185">**Show "via" tag**: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

       > [!NOTE]
       > <span data-ttu-id="5a164-186">Actualmente, la configuración de la etiqueta **Mostrar "a través"** no está disponible en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="5a164-186">Currently, the **Show "via" tag** setting is not available in all organizations.</span></span> <span data-ttu-id="5a164-187">Si no tiene la configuración de etiqueta **Mostrar "a** través", el signo de interrogación y la etiqueta via están controlados por show  **(?)** para remitentes no autenticados para la configuración de suplantación de identidad en su organización.</span><span class="sxs-lookup"><span data-stu-id="5a164-187">If you don't have the **Show "via" tag** setting, the the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="5a164-188">Para activar una configuración, active la casilla.</span><span class="sxs-lookup"><span data-stu-id="5a164-188">To turn on a setting, select the check box.</span></span> <span data-ttu-id="5a164-189">Para desactivarla, desactive la casilla.</span><span class="sxs-lookup"><span data-stu-id="5a164-189">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="5a164-190">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5a164-190">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="5a164-191">En la página **Revisar** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="5a164-191">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="5a164-192">Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="5a164-192">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="5a164-193">También puede hacer clic en **Atrás** o seleccionar la página específica del asistente.</span><span class="sxs-lookup"><span data-stu-id="5a164-193">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="5a164-194">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="5a164-194">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="5a164-195">En la página de confirmación que aparece, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="5a164-195">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-security-center-to-view-anti-phishing-policies"></a><span data-ttu-id="5a164-196">Usar el centro de seguridad para ver directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-196">Use the security center to view anti-phishing policies</span></span>

1. <span data-ttu-id="5a164-197">En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="5a164-197">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="5a164-198">En la **página Anti-phishing,** las siguientes propiedades se muestran en la lista de directivas contra suplantación de identidad:</span><span class="sxs-lookup"><span data-stu-id="5a164-198">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="5a164-199">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5a164-199">**Name**</span></span>
   - <span data-ttu-id="5a164-200">**Estado**</span><span class="sxs-lookup"><span data-stu-id="5a164-200">**Status**</span></span>
   - <span data-ttu-id="5a164-201">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="5a164-201">**Priority**</span></span>
   - <span data-ttu-id="5a164-202">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="5a164-202">**Last modified**</span></span>

3. <span data-ttu-id="5a164-203">Al seleccionar una directiva haciendo clic en el nombre, la configuración de la directiva se muestra en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="5a164-203">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-security-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="5a164-204">Usar el centro de seguridad para modificar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-204">Use the security center to modify anti-phishing policies</span></span>

1. <span data-ttu-id="5a164-205">En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="5a164-205">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="5a164-206">En la **página Anti-phishing,** seleccione una directiva de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="5a164-206">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="5a164-207">En el control flotante de detalles de la directiva que aparece, seleccione **Editar** en cada sección para modificar la configuración dentro de la sección.</span><span class="sxs-lookup"><span data-stu-id="5a164-207">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="5a164-208">Para obtener más información acerca de la configuración, vea la sección Usar el centro de seguridad para crear directivas [contra suplantación](#use-the-security-center-to-create-anti-phishing-policies) de identidad anteriores en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5a164-208">For more information about the settings, see the [Use the security center to create anti-phishing policies](#use-the-security-center-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="5a164-209">Para la directiva contra suplantación de identidad predeterminada, la sección **Usuarios,** grupos y dominios no está disponible (la directiva se aplica a todos) y no puede cambiar el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="5a164-209">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="5a164-210">Para habilitar o deshabilitar una directiva o establecer el orden de prioridad de la directiva, consulte las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="5a164-210">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="5a164-211">Habilitar o deshabilitar directivas personalizadas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-211">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="5a164-212">No puede deshabilitar la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a164-212">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="5a164-213">En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="5a164-213">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="5a164-214">En la **página Anti-phishing,** seleccione una directiva personalizada de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="5a164-214">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="5a164-215">En la parte superior del control flotante de detalles de la directiva que aparece, verá uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="5a164-215">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="5a164-216">**Directiva desactivada**: para activar la directiva, haga clic en el ![Icono Activar](../../media/m365-cc-sc-turn-on-off-icon.png) **Activar**.</span><span class="sxs-lookup"><span data-stu-id="5a164-216">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="5a164-217">**Directiva activada**: Para desactivar la directiva, haga clic en el ![Icono desactivar](../../media/m365-cc-sc-turn-on-off-icon.png) y **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="5a164-217">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="5a164-218">En el cuadro de diálogo de confirmación que aparece, haga clic **Activar** o **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="5a164-218">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="5a164-219">Haga clic en **Cerrar** en el control flotante de detalles de la directiva.</span><span class="sxs-lookup"><span data-stu-id="5a164-219">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="5a164-220">De nuevo en la página principal de la directiva, el valor **Estado** de la directiva estará **Activado** o **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="5a164-220">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="5a164-221">Establecer la prioridad de las directivas contra suplantación de identidad personalizadas</span><span class="sxs-lookup"><span data-stu-id="5a164-221">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="5a164-222">De forma predeterminada, las directivas contra suplantación de identidad tienen una prioridad que se basa en el orden en que se crearon (las directivas más recientes son de menor prioridad que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="5a164-222">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="5a164-223">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="5a164-223">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="5a164-224">Ninguna de las dos directivas puede tener la misma prioridad, y el procesamiento de directivas se detendrá cuando se aplique la primera directiva.</span><span class="sxs-lookup"><span data-stu-id="5a164-224">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="5a164-225">Para cambiar la prioridad de una directiva, haga clic en **Aumentar la prioridad** o en **Reducir la prioridad** en las propiedades de la directiva (no se puede modificar directamente el número de **Prioridad** en el Centro de seguridad).</span><span class="sxs-lookup"><span data-stu-id="5a164-225">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the security center).</span></span> <span data-ttu-id="5a164-226">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="5a164-226">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="5a164-227">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="5a164-227">**Notes**:</span></span>

- <span data-ttu-id="5a164-228">En el centro de seguridad, solo puede cambiar la prioridad de la directiva contra suplantación de identidad después de crearla.</span><span class="sxs-lookup"><span data-stu-id="5a164-228">In the security center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="5a164-229">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla contra suplantación de identidad (lo que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="5a164-229">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="5a164-230">Las directivas contra suplantación de identidad se procesan en el orden en que se muestran (la primera directiva tiene el **valor de prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="5a164-230">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="5a164-231">La directiva contra suplantación de identidad predeterminada tiene el valor de prioridad **Lowest** y no puede cambiarla.</span><span class="sxs-lookup"><span data-stu-id="5a164-231">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="5a164-232">En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="5a164-232">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="5a164-233">En la **página Anti-phishing,** seleccione una directiva personalizada de la lista haciendo clic en el nombre.</span><span class="sxs-lookup"><span data-stu-id="5a164-233">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="5a164-234">En la parte superior del control flotante de detalles de la directiva que aparece, verá **Aumentar la prioridad** o **Disminuir la prioridad** en función del valor de prioridad actual y del número de directivas personalizadas:</span><span class="sxs-lookup"><span data-stu-id="5a164-234">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="5a164-235">La directiva contra suplantación de identidad con el valor **de** prioridad **0** solo tiene disponible **la opción Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="5a164-235">The anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="5a164-236">La directiva contra suplantación de identidad con el valor **priority** más bajo (por ejemplo, **3**) solo tiene disponible **la opción Aumentar** prioridad.</span><span class="sxs-lookup"><span data-stu-id="5a164-236">The anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="5a164-237">Si tiene tres o más directivas contra la suplantación de identidad, las directivas entre los valores de prioridad más alta y más baja tienen disponibles las opciones **Aumentar** prioridad y **Disminuir** prioridad.</span><span class="sxs-lookup"><span data-stu-id="5a164-237">If you have three or more anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="5a164-238">Haga clic en el ![Icono Aumentar la prioridad](../../media/m365-cc-sc-increase-icon.png) **Aumentar la prioridad** o en el ![Icono Disminuir la prioridad](../../media/m365-cc-sc-decrease-icon.png) **Reducir la prioridad** para cambiar el valor de **Prioridad**.</span><span class="sxs-lookup"><span data-stu-id="5a164-238">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="5a164-239">Cuando haya terminado, haga clic en **Cerrar** en el control flotante de detalles de la directiva.</span><span class="sxs-lookup"><span data-stu-id="5a164-239">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-security-center-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="5a164-240">Usar el centro de seguridad para quitar directivas personalizadas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-240">Use the security center to remove custom anti-phishing policies</span></span>

<span data-ttu-id="5a164-241">Cuando se usa el centro de seguridad para quitar una directiva de anti phishing personalizada, se eliminan tanto la regla contra suplantación de identidad como la directiva anti phishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5a164-241">When you use the security center to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="5a164-242">No puede quitar la directiva contra suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a164-242">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="5a164-243">En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="5a164-243">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="5a164-244">Seleccione una directiva personalizada de la lista haciendo clic en el nombre de la directiva.</span><span class="sxs-lookup"><span data-stu-id="5a164-244">Select a custom policy from the list by clicking on the name of the policy.</span></span> <span data-ttu-id="5a164-245">En la parte superior del control flotante de detalles de la directiva que aparece, haga clic en el ![Icono Más acciones](../../media/m365-cc-sc-more-actions-icon.png) **Más acciones** \> ![Icono Eliminar directiva](../../media/m365-cc-sc-delete-icon.png) **Eliminar directiva**.</span><span class="sxs-lookup"><span data-stu-id="5a164-245">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

3. <span data-ttu-id="5a164-246">En el cuadro de diálogo de confirmación que aparece, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5a164-246">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="5a164-247">Usar Exchange Online PowerShell para configurar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-247">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="5a164-248">Como se describió anteriormente, una directiva contra suplantación de identidad (phishing) consta de una directiva contra suplantación de identidad (phishing) y una regla contra suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="5a164-248">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="5a164-249">En Exchange Online PowerShell, la diferencia entre las directivas contra suplantación de identidad y las reglas contra suplantación de identidad es aparente.</span><span class="sxs-lookup"><span data-stu-id="5a164-249">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="5a164-250">Las directivas contra suplantación de identidad se administran mediante los cmdlets **\* -AntiPhishPolicy** y se administran reglas contra suplantación de identidad mediante los cmdlets **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="5a164-250">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="5a164-251">En PowerShell, primero se crea la directiva contra suplantación de identidad y, a continuación, se crea la regla contra suplantación de identidad que identifica la directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="5a164-251">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="5a164-252">En PowerShell, se modifica la configuración de la directiva contra suplantación de identidad y la regla contra suplantación de identidad por separado.</span><span class="sxs-lookup"><span data-stu-id="5a164-252">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="5a164-253">Al quitar una directiva contra suplantación de identidad de PowerShell, la regla anti-phish correspondiente no se quita automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="5a164-253">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="5a164-254">Los siguientes procedimientos de PowerShell no están disponibles en organizaciones EOP independientes que usan Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a164-254">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="5a164-255">Usar PowerShell para crear directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-255">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="5a164-256">Crear una directiva contra la suplantación de identidad en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="5a164-256">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="5a164-257">Cree la directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5a164-257">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="5a164-258">Cree la regla contra suplantación de identidad que especifica la directiva contra suplantación de identidad a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="5a164-258">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="5a164-259">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="5a164-259">**Notes**:</span></span>

- <span data-ttu-id="5a164-260">Puede crear una nueva regla contra suplantación de identidad (phish) y asignarle una directiva anti-phish existente y no asociada.</span><span class="sxs-lookup"><span data-stu-id="5a164-260">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="5a164-261">Una regla contra la suplantación de identidad no se puede asociar a más de una directiva contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5a164-261">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="5a164-262">Puede configurar las siguientes opciones en las nuevas directivas contra suplantación de identidad en PowerShell que no están disponibles en el centro de seguridad hasta después de crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="5a164-262">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the security center until after you create the policy:</span></span>

  - <span data-ttu-id="5a164-263">Cree la nueva directiva como deshabilitada (_Habilitada_ `$false` en el cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="5a164-263">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="5a164-264">Establezca la prioridad de la directiva durante la creación (_Prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="5a164-264">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="5a164-265">Una nueva directiva contra suplantación de identidad que cree en PowerShell no será visible en el centro de seguridad hasta que asigne la directiva a una regla contra suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="5a164-265">A new anti-phish policy that you create in PowerShell isn't visible in the security center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="5a164-266">Paso 1: Usar PowerShell para crear una directiva contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-266">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="5a164-267">Para crear una directiva contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-267">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="5a164-268">En este ejemplo se crea una directiva contra phishing denominada Cuarentena de investigación con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="5a164-268">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="5a164-269">La descripción es: Directiva del departamento de investigación.</span><span class="sxs-lookup"><span data-stu-id="5a164-269">The description is: Research department policy.</span></span>
- <span data-ttu-id="5a164-270">Cambia la acción predeterminada de suplantación a Cuarentena.</span><span class="sxs-lookup"><span data-stu-id="5a164-270">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="5a164-271">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="5a164-271">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="5a164-272">Paso 2: Usar PowerShell para crear una regla contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-272">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="5a164-273">Para crear una regla contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-273">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="5a164-274">En este ejemplo se crea una regla contra suplantación de identidad (phish) denominada Departamento de investigación con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="5a164-274">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="5a164-275">La regla está asociada con la directiva contra phishing denominada Cuarentena de investigación.</span><span class="sxs-lookup"><span data-stu-id="5a164-275">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="5a164-276">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="5a164-276">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="5a164-277">Dado que no estamos usando el parámetro _Priority,_ se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5a164-277">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="5a164-278">Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="5a164-278">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="5a164-279">Usar PowerShell para ver directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-279">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="5a164-280">Para ver las directivas anti phish existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-280">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="5a164-281">En este ejemplo se devuelve una lista resumida de todas las directivas contra phishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="5a164-281">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="5a164-282">En este ejemplo se devuelven todos los valores de propiedad de la directiva contra suplantación de identidad denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="5a164-282">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="5a164-283">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="5a164-283">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="5a164-284">Usar PowerShell para ver reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-284">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="5a164-285">Para ver las reglas anti phish existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-285">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="5a164-286">En este ejemplo se devuelve una lista resumida de todas las reglas contra phishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="5a164-286">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="5a164-287">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="5a164-287">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="5a164-288">En este ejemplo se devuelven todos los valores de propiedad de la regla contra suplantación de identidad denominada Ejecutivos de Contoso.</span><span class="sxs-lookup"><span data-stu-id="5a164-288">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="5a164-289">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="5a164-289">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="5a164-290">Usar PowerShell para modificar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-290">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="5a164-291">Aparte de los siguientes elementos, la misma configuración está disponible al modificar una directiva contra suplantación de identidad en PowerShell que al crear una directiva como se describe en Paso [1:](#step-1-use-powershell-to-create-an-anti-phish-policy) Usar PowerShell para crear una directiva contra suplantación de identidad anterior en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5a164-291">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="5a164-292">El _modificador MakeDefault_ que convierte la directiva especificada en la directiva predeterminada (aplicada a todos, siempre **con** prioridad más baja y no puede eliminarla) solo está disponible cuando modifica una directiva contra suplantación de identidad en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a164-292">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="5a164-293">No puede cambiar el nombre de una directiva contra suplantación de identidad (el cmdlet **Set-AntiPhishPolicy** no tiene ningún _parámetro Name)._</span><span class="sxs-lookup"><span data-stu-id="5a164-293">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="5a164-294">Al cambiar el nombre de una directiva contra suplantación de identidad en el centro de seguridad, solo se cambia el nombre de la regla contra _suplantación de identidad_.</span><span class="sxs-lookup"><span data-stu-id="5a164-294">When you rename an anti-phishing policy in the security center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="5a164-295">Para modificar una directiva contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-295">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="5a164-296">Para obtener información detallada acerca de la sintaxis y los parámetros, [vea Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="5a164-296">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="5a164-297">Usar PowerShell para modificar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-297">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="5a164-298">La única configuración que no está disponible al modificar una regla contra suplantación de identidad en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="5a164-298">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="5a164-299">Para habilitar o deshabilitar las reglas antiphishing existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="5a164-299">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="5a164-300">De lo contrario, la misma configuración está disponible al crear una regla tal como se describe en el Paso [2: Usar PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) para crear una sección de regla contra suplantación de identidad anterior en este artículo.</span><span class="sxs-lookup"><span data-stu-id="5a164-300">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="5a164-301">Para modificar una regla contra phishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-301">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="5a164-302">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="5a164-302">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="5a164-303">Usar PowerShell para habilitar o deshabilitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-303">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="5a164-304">Habilitar o deshabilitar una regla contra suplantación de identidad en PowerShell habilita o deshabilita toda la directiva contra suplantación de identidad (la regla anti phishing y la directiva contra suplantación de identidad asignada).</span><span class="sxs-lookup"><span data-stu-id="5a164-304">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="5a164-305">No puede habilitar ni deshabilitar la directiva contra suplantación de identidad predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="5a164-305">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="5a164-306">Para habilitar o deshabilitar una regla contra phishing en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-306">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="5a164-307">En este ejemplo se deshabilita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="5a164-307">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="5a164-308">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="5a164-308">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="5a164-309">Para obtener información detallada acerca de la sintaxis y los parámetros, vea [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) y [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="5a164-309">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="5a164-310">Usar PowerShell para establecer la prioridad de las reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-310">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="5a164-p132">El valor de prioridad máximo que se puede establecer en una regla es 0. El valor mínimo depende del número de reglas. Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4. El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas. Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="5a164-p132">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="5a164-316">Para establecer la prioridad de una regla contra suplantación de identidad en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-316">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="5a164-p133">En el ejemplo siguiente, la prioridad de la regla denominada "Marketing Department" se establece en 2. Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="5a164-p133">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="5a164-319">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="5a164-319">**Notes**:</span></span>

- <span data-ttu-id="5a164-320">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="5a164-320">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="5a164-321">La directiva contra suplantación de identidad predeterminada no tiene una regla anti phish correspondiente y siempre tiene el valor de prioridad no modificable **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="5a164-321">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="5a164-322">Usar PowerShell para quitar directivas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-322">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="5a164-323">Cuando se usa PowerShell para quitar una directiva contra suplantación de identidad, no se quita la regla contra suplantación de identidad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5a164-323">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="5a164-324">Para quitar una directiva contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-324">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="5a164-325">En este ejemplo se quita la directiva contra suplantación de identidad denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="5a164-325">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="5a164-326">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="5a164-326">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="5a164-327">Usar PowerShell para quitar reglas contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="5a164-327">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="5a164-328">Cuando usa PowerShell para quitar una regla contra phishing, no se quita la directiva anti phish correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5a164-328">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="5a164-329">Para quitar una regla contra suplantación de identidad en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="5a164-329">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="5a164-330">En este ejemplo se quita la regla contra suplantación de identidad (phish) denominada Departamento de marketing.</span><span class="sxs-lookup"><span data-stu-id="5a164-330">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="5a164-331">Para obtener información detallada sobre la sintaxis y los parámetros, [vea Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="5a164-331">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="5a164-332">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="5a164-332">How do you know these procedures worked?</span></span>

<span data-ttu-id="5a164-333">Para comprobar que ha configurado correctamente directivas contra suplantación de identidad (phishing) en EOP, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5a164-333">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="5a164-334">En el centro de seguridad, vaya a Correo electrónico **& directivas** de colaboración & De directivas de amenazas de reglas \>  \>  \>  sección \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="5a164-334">In the security center, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="5a164-335">Compruebe la lista de directivas, sus **valores de** estado y sus **valores de** prioridad.</span><span class="sxs-lookup"><span data-stu-id="5a164-335">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="5a164-336">Para ver más detalles, seleccione la directiva de la lista haciendo clic en el nombre y viendo los detalles en el menú desplegable que aparece.</span><span class="sxs-lookup"><span data-stu-id="5a164-336">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="5a164-337">En Exchange Online PowerShell, reemplace por el nombre de la directiva o regla, ejecute el \<Name\> siguiente comando y compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="5a164-337">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
