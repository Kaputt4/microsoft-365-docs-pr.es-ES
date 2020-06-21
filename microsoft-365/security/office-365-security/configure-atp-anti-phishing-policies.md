---
title: Configurar directivas contra phishing de ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo crear, modificar y eliminar las Directivas avanzadas de suplantación de identidad (phishing) que están disponibles en las organizaciones con Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 458a4eac348598d1b752267ed7d79b97bc594580
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726769"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="0b77e-103">Configurar directivas contra phishing de ATP</span><span class="sxs-lookup"><span data-stu-id="0b77e-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="0b77e-104">Las directivas antiphishing de ATP forman parte de la [protección contra amenazas avanzada de Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="0b77e-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="0b77e-105">Las directivas antiphishing de ATP pueden ayudar a proteger a su organización de ataques de suplantación de identidad (phishing) malintencionados y otros tipos de ataques de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="0b77e-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="0b77e-106">Para obtener más información acerca de las diferencias entre las directivas antiphishing en Exchange Online Protection (EOP) y las directivas antiphishing de ATP, consulte [anti-phishing Protection](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="0b77e-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="0b77e-107">Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva antiphishing predeterminada de ATP.</span><span class="sxs-lookup"><span data-stu-id="0b77e-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="0b77e-108">Para una mayor granularidad, también puede crear directivas antiphishing de ATP personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="0b77e-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0b77e-109">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="0b77e-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="0b77e-110">Puede configurar las directivas antiphishing de ATP en el centro de seguridad & cumplimiento o en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b77e-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="0b77e-111">Para obtener información acerca de la configuración de las directivas antiphishing más limitadas que están disponibles en las organizaciones de Exchange Online Protection (es decir, las organizaciones de Microsoft 365 sin ATP de Office 365), vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0b77e-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="0b77e-112">Directivas antiphishing de ATP en el centro de seguridad & cumplimiento de vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b77e-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="0b77e-113">Los elementos básicos de una directiva contra la suplantación de identidad ATP son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0b77e-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="0b77e-114">**La Directiva ANTIPHISH**: especifica las protecciones de suplantación de identidad (phishing) que se deben habilitar o deshabilitar y las acciones para aplicar opciones.</span><span class="sxs-lookup"><span data-stu-id="0b77e-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="0b77e-115">**La regla anti-phish**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="0b77e-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="0b77e-116">La diferencia entre estos dos elementos no es obvia cuando se administran las directivas antiphishing de ATP en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="0b77e-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="0b77e-117">Al crear una directiva contra la suplantación de identidad ATP en el centro de seguridad & cumplimiento, en realidad está creando una regla ANTIPHISH y la Directiva ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="0b77e-118">Cuando modifica una directiva de ATP antiphishing en el centro de seguridad & cumplimiento, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado, y de destinatarios modifica la regla contra el phish.</span><span class="sxs-lookup"><span data-stu-id="0b77e-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="0b77e-119">Todas las demás opciones modifican la Directiva ANTIPHISH asociada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="0b77e-120">Al quitar una directiva de ATP contra la suplantación de identidad del centro de seguridad & cumplimiento, se quita la regla antiphishing y la Directiva de ANTIPHISH asociada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="0b77e-121">En Exchange Online PowerShell, la diferencia entre las directivas antiphishing y las reglas antiphishing es evidente.</span><span class="sxs-lookup"><span data-stu-id="0b77e-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="0b77e-122">Las directivas antiphishing se administran mediante los cmdlets \*\* \* -AntiPhishPolicy\*\* y se administran las reglas antiphishing mediante los cmdlets \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="0b77e-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="0b77e-123">En PowerShell, se crea la Directiva ANTIPHISH en primer lugar y, a continuación, se crea la regla ANTIPHISH que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="0b77e-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="0b77e-124">En PowerShell, la configuración de la Directiva antiphishing y la regla antiphishing se modifican por separado.</span><span class="sxs-lookup"><span data-stu-id="0b77e-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="0b77e-125">Cuando se quita una directiva ANTIPHISH de PowerShell, la regla antiphishing correspondiente no se elimina automáticamente y viceversa.</span><span class="sxs-lookup"><span data-stu-id="0b77e-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="0b77e-126">Directiva antiphishing de ATP predeterminada</span><span class="sxs-lookup"><span data-stu-id="0b77e-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="0b77e-127">Cada organización ATP tiene una directiva antiphishing de ATP integrada llamada Office365 ANTIPHISH predeterminada con estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="0b77e-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="0b77e-128">La Directiva ANTIPHISH denominada Office365 ANTIPHISH predeterminada se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla antiphishing (filtros de destinatario) asociada a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="0b77e-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="0b77e-129">La Directiva denominada predeterminada de la ANTIPHISH de Office365 tiene el valor de prioridad personalizado **más bajo** que no se puede modificar (la Directiva se aplica siempre en último lugar).</span><span class="sxs-lookup"><span data-stu-id="0b77e-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="0b77e-130">Cualquier directiva personalizada que cree siempre tendrá una prioridad mayor que la Directiva denominada Office365 ANTIPHISH predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="0b77e-131">La Directiva denominada Office365 ANTIPHISH predeterminada es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True` ) y no se puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="0b77e-132">Para aumentar la eficacia de la protección contra suplantación de identidad (phishing), puede crear directivas antiphishing personalizadas de ATP con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="0b77e-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b77e-133">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="0b77e-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b77e-134">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0b77e-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0b77e-135">Para ir directamente a la página **contra la suplantación de identidad ATP** , use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="0b77e-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0b77e-136">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0b77e-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0b77e-137">Debe tener permisos asignados para poder realizar los procedimientos de este tema:</span><span class="sxs-lookup"><span data-stu-id="0b77e-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="0b77e-138">Para agregar, modificar y eliminar directivas antiphishing de ATP, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="0b77e-138">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0b77e-139">**Administración** de la organización o **Administrador de seguridad** en el [centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0b77e-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0b77e-140">Administración de la administración de la **organización** o administración de la **higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="0b77e-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="0b77e-141">Para obtener acceso de solo lectura a las directivas antiphishing de ATP, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="0b77e-141">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="0b77e-142">**Lector de seguridad** en el [centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0b77e-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="0b77e-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="0b77e-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="0b77e-144">Para obtener la configuración recomendada para las directivas antiphishing de ATP, consulte [configuración de la Directiva de antiphishing de Office ATP](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="0b77e-144">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="0b77e-145">Permitir que se aplique una directiva nueva o actualizada durante un máximo de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="0b77e-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="0b77e-146">Para obtener información acerca de dónde se aplican las directivas contra la suplantación de identidad (phishing) en la canalización de filtros, consulte [Order and Precedence of email Protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0b77e-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="0b77e-147">Usar el centro de seguridad & cumplimiento para crear directivas contra la suplantación de identidad ATP</span><span class="sxs-lookup"><span data-stu-id="0b77e-147">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="0b77e-148">La creación de una directiva antiphishing de ATP personalizada en el centro de seguridad & cumplimiento crea la regla ANTIPHISH y la Directiva de ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-148">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="0b77e-149">Al crear una directiva contra la suplantación de identidad ATP, solo puede especificar el nombre de la Directiva, la descripción y el filtro de destinatarios que identifica a quién se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="0b77e-149">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="0b77e-150">Después de crear la Directiva, puede modificar la Directiva para cambiar o revisar la configuración predeterminada de la suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="0b77e-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="0b77e-151">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0b77e-152">En la página **contra la suplantación de identidad** , haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="0b77e-153">Se abrirá el Asistente para **crear una nueva Directiva antiphishing** .</span><span class="sxs-lookup"><span data-stu-id="0b77e-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="0b77e-154">En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0b77e-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0b77e-155">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="0b77e-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0b77e-156">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="0b77e-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0b77e-157">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0b77e-158">En la página **aplicado a** que aparece, identifique los destinatarios internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="0b77e-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="0b77e-159">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="0b77e-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0b77e-160">Varios valores de una misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="0b77e-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0b77e-161">Condiciones o excepciones diversas usan la lógica AND (por ejemplo, _\<recipient1\>_ y _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="0b77e-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="0b77e-162">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-162">Click **Add a condition**.</span></span> <span data-ttu-id="0b77e-163">En la lista desplegable que aparece, seleccione una condición en **aplicado si**:</span><span class="sxs-lookup"><span data-stu-id="0b77e-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="0b77e-164">**El destinatario es**: especifica uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="0b77e-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0b77e-165">**El destinatario es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="0b77e-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="0b77e-166">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="0b77e-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="0b77e-167">Después de seleccionar la condición, aparece la lista desplegable correspondiente con una **de estas** casillas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="0b77e-168">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="0b77e-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="0b77e-169">Haga clic en el cuadro y comience a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="0b77e-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="0b77e-170">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="0b77e-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="0b77e-171">Para quitar entradas individuales, haga **Remove** clic en ![ el icono quitar quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="0b77e-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="0b77e-172">Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.</span><span class="sxs-lookup"><span data-stu-id="0b77e-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="0b77e-173">Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="0b77e-174">Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="0b77e-175">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="0b77e-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0b77e-176">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0b77e-177">En la página **Revise la configuración** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="0b77e-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="0b77e-178">Puede hacer clic en **Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="0b77e-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0b77e-179">Cuando haya terminado, haga clic en **crear esta directiva**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="0b77e-180">Haga clic en **Aceptar** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="0b77e-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="0b77e-181">Después de crear la Directiva contra la suplantación de identidad ATP con estas opciones de directiva generales, siga las instrucciones de la siguiente sección para configurar las opciones de protección de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="0b77e-181">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="0b77e-182">Usar el centro de seguridad & cumplimiento para modificar las directivas antiphishing de ATP</span><span class="sxs-lookup"><span data-stu-id="0b77e-182">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="0b77e-183">Use los siguientes procedimientos para modificar las directivas antiphishing de ATP: una nueva directiva que ha creado o las directivas existentes que ya ha personalizado.</span><span class="sxs-lookup"><span data-stu-id="0b77e-183">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="0b77e-184">Si aún no está ahí, abra el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0b77e-185">Seleccione la Directiva antiphishing de ATP personalizada que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="0b77e-185">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="0b77e-186">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="0b77e-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0b77e-187">Aparece el control flotante \*\*editar la directiva \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="0b77e-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="0b77e-188">Al hacer clic en **Editar** en cualquier sección, obtendrá acceso a la configuración de esa sección.</span><span class="sxs-lookup"><span data-stu-id="0b77e-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="0b77e-189">Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="0b77e-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="0b77e-190">Después de hacer clic en **Editar** en una sección, la configuración disponible se presenta en un formato de asistente, pero puede saltar dentro de las páginas en cualquier orden y puede hacer clic en **Guardar** en cualquier página (o en **Cancelar** o **cerrar** el ![ icono cerrar ](../../media/scc-remove-icon.png) para volver a la página \*\*editar la directiva \<name\> \*\* ) (no es necesario visitar la última página del Asistente para guardarla o dejarla).</span><span class="sxs-lookup"><span data-stu-id="0b77e-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="0b77e-191">**Configuración de directiva**: haga clic en **Editar** para modificar la misma configuración que estaba disponible cuando [creó la Directiva](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="0b77e-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="0b77e-192">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="0b77e-192">**Name**</span></span>
   - <span data-ttu-id="0b77e-193">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0b77e-193">**Description**</span></span>
   - <span data-ttu-id="0b77e-194">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="0b77e-194">**Applied to**</span></span>
   - <span data-ttu-id="0b77e-195">**Revisar la configuración**</span><span class="sxs-lookup"><span data-stu-id="0b77e-195">**Review your settings**</span></span>

   <span data-ttu-id="0b77e-196">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="0b77e-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="0b77e-197">**Suplantación**: haga clic en **Editar** para modificar los remitentes protegidos y los dominios protegidos en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="0b77e-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="0b77e-198">Esta configuración es una condición para la Directiva que identifica a los remitentes suplantados para que busquen (de forma individual o por dominio) en la dirección de de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="0b77e-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="0b77e-199">Para obtener más información, consulte [configuración de suplantación en las directivas de antiphishing de ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="0b77e-199">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="0b77e-200">**Agregar usuarios para proteger**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="0b77e-201">Para activarla, deslice el botón de alternancia a **activado**y, a continuación, haga clic en el botón **Agregar usuario** que aparece.</span><span class="sxs-lookup"><span data-stu-id="0b77e-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="0b77e-202">En el control flotante **Agregar usuario** que aparece, configure los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0b77e-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="0b77e-203">**Dirección de correo electrónico**:</span><span class="sxs-lookup"><span data-stu-id="0b77e-203">**Email address**:</span></span>

        - <span data-ttu-id="0b77e-204">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="0b77e-204">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="0b77e-205">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="0b77e-205">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="0b77e-206">Para quitar una entrada, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en el usuario.</span><span class="sxs-lookup"><span data-stu-id="0b77e-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0b77e-207">**Nombre**: este valor se rellena en función de la dirección de correo electrónico que haya seleccionado, pero puede cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="0b77e-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="0b77e-208">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="0b77e-208">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="0b77e-209">Para editar una entrada existente, seleccione el usuario protegido en la lista.</span><span class="sxs-lookup"><span data-stu-id="0b77e-209">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="0b77e-210">**Agregar dominios para proteger**: configure una o ambas de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0b77e-210">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="0b77e-211">**Incluir automáticamente los dominios que tengo**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-211">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="0b77e-212">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-212">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0b77e-213">**Incluir dominios personalizados**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-213">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="0b77e-214">Para activarla, deslice el botón de alternancia a **activado**y, en el cuadro **Agregar dominios** , escriba el nombre de dominio (por ejemplo, contoso.com), presione entrar y repita lo mismo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0b77e-214">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="0b77e-215">**Acciones**: haga clic en **Editar**</span><span class="sxs-lookup"><span data-stu-id="0b77e-215">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="0b77e-216">**Si un usuario suplantado envía un correo electrónico**: configure una de las siguientes acciones para los mensajes en los que el remitente falso sea uno de los usuarios protegidos que ha especificado en **Agregar usuarios para proteger**:</span><span class="sxs-lookup"><span data-stu-id="0b77e-216">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="0b77e-217">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="0b77e-217">**Don't apply any action**</span></span>
       - <span data-ttu-id="0b77e-218">**Redirigir un mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="0b77e-218">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0b77e-219">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="0b77e-219">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0b77e-220">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="0b77e-220">**Quarantine the message**</span></span>
       - <span data-ttu-id="0b77e-221">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="0b77e-221">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0b77e-222">**Eliminar el mensaje antes de su entrega**</span><span class="sxs-lookup"><span data-stu-id="0b77e-222">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="0b77e-223">**Si un dominio suplantado envía un correo electrónico**: configure una de las siguientes acciones para los mensajes en los que el remitente falso esté en uno de los dominios protegidos que ha especificado en **Agregar dominios para proteger**:</span><span class="sxs-lookup"><span data-stu-id="0b77e-223">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="0b77e-224">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="0b77e-224">**Don't apply any action**</span></span>
     - <span data-ttu-id="0b77e-225">**Redirigir un mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="0b77e-225">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="0b77e-226">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="0b77e-226">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="0b77e-227">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="0b77e-227">**Quarantine the message**</span></span>
     - <span data-ttu-id="0b77e-228">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="0b77e-228">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="0b77e-229">**Eliminar el mensaje antes de su entrega**</span><span class="sxs-lookup"><span data-stu-id="0b77e-229">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0b77e-230">Haga clic en **Activar sugerencias de seguridad de suplantación** y configure cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="0b77e-230">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="0b77e-231">**Mostrar sugerencia para usuarios suplantados**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-231">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="0b77e-232">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0b77e-233">**Mostrar sugerencia para dominios suplantados**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-233">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="0b77e-234">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0b77e-235">**Mostrar sugerencia para caracteres inusuales**: el valor predeterminado es **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-235">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="0b77e-236">Para activarla, deslice el botón de alternancia a **activado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-236">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="0b77e-237">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-237">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="0b77e-238">**Inteligencia de buzones de correo**:</span><span class="sxs-lookup"><span data-stu-id="0b77e-238">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="0b77e-239">**¿Habilitar la inteligencia de buzones?**: el valor predeterminado es **activado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-239">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="0b77e-240">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-240">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="0b77e-241">**¿Habilitar la protección de suplantación basada en buzones de correo?**: esta opción solo está disponible si **Habilitar inteligencia de buzones de correo?** es **activado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-241">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="0b77e-242">En **si un usuario suplantado envía un correo electrónico**, puede especificar una de las siguientes acciones para que se realicen en los mensajes que no superen la inteligencia del buzón (las mismas acciones que están disponibles para los usuarios protegidos y los dominios protegidos):</span><span class="sxs-lookup"><span data-stu-id="0b77e-242">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="0b77e-243">**No aplicar ninguna acción**</span><span class="sxs-lookup"><span data-stu-id="0b77e-243">**Don't apply any action**</span></span>
       - <span data-ttu-id="0b77e-244">**Redirigir un mensaje a otras direcciones de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="0b77e-244">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0b77e-245">**Mover mensaje a la carpeta Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="0b77e-245">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0b77e-246">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="0b77e-246">**Quarantine the message**</span></span>
       - <span data-ttu-id="0b77e-247">**Entregar el mensaje y agregar otras direcciones a la línea CCO**</span><span class="sxs-lookup"><span data-stu-id="0b77e-247">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0b77e-248">**Eliminar el mensaje antes de su entrega**</span><span class="sxs-lookup"><span data-stu-id="0b77e-248">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0b77e-249">**Agregue los remitentes y dominios de confianza**: especifique las excepciones de la Directiva:</span><span class="sxs-lookup"><span data-stu-id="0b77e-249">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="0b77e-250">**Remitentes de confianza**:</span><span class="sxs-lookup"><span data-stu-id="0b77e-250">**Trusted senders**:</span></span>

       - <span data-ttu-id="0b77e-251">Haga clic en el cuadro y desplácese por la lista de usuarios que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="0b77e-251">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0b77e-252">Haga clic en el cuadro y empiece a escribir para filtrar la lista y seleccionar un usuario.</span><span class="sxs-lookup"><span data-stu-id="0b77e-252">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0b77e-253">Para quitar una entrada, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en el usuario.</span><span class="sxs-lookup"><span data-stu-id="0b77e-253">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0b77e-254">**Dominios de confianza**: escriba el nombre del dominio (por ejemplo, contoso.com), presione entrar y repita el procedimiento según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0b77e-254">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="0b77e-255">**Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="0b77e-255">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0b77e-256">Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0b77e-256">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0b77e-257">Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:</span><span class="sxs-lookup"><span data-stu-id="0b77e-257">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0b77e-258">**Usuarios protegidos**</span><span class="sxs-lookup"><span data-stu-id="0b77e-258">**Protected users**</span></span>
       - <span data-ttu-id="0b77e-259">**Dominios protegidos** \> **Incluir dominios de su propiedad**</span><span class="sxs-lookup"><span data-stu-id="0b77e-259">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="0b77e-260">**Dominios protegidos** \> **Dominios protegidos** (dominios personalizados)</span><span class="sxs-lookup"><span data-stu-id="0b77e-260">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="0b77e-261">**Inteligencia de buzones**</span><span class="sxs-lookup"><span data-stu-id="0b77e-261">**Mailbox intelligence**</span></span>

   <span data-ttu-id="0b77e-262">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="0b77e-262">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="0b77e-263">**Suplantación de identidad**: haga clic en **Editar** para activar o desactivar la inteligencia de suplantación, activar o desactivar la identificación del remitente sin autenticar en Outlook y configurar la acción para aplicar a los mensajes de los remitentes suplantados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="0b77e-263">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="0b77e-264">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="0b77e-264">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="0b77e-265">Tenga en cuenta que esta misma configuración también está disponible en las directivas antiphishing en EOP.</span><span class="sxs-lookup"><span data-stu-id="0b77e-265">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="0b77e-266">**Configuración del filtro de suplantación de identidad**: el valor predeterminado es **activado**y se recomienda que lo deje activado.</span><span class="sxs-lookup"><span data-stu-id="0b77e-266">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="0b77e-267">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-267">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="0b77e-268">Para obtener más información, vea [Configure outsimulate Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="0b77e-268">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="0b77e-269">No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Microsoft 365; en su lugar, se habilita el filtrado mejorado para los conectores.</span><span class="sxs-lookup"><span data-stu-id="0b77e-269">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="0b77e-270">Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="0b77e-270">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="0b77e-271">**Habilitar la característica de remitente sin autenticar**: el valor predeterminado es **activado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-271">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="0b77e-272">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-272">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="0b77e-273">**Acciones**: especificar la acción que se realizará en los mensajes que no superen la inteligencia de identidad:</span><span class="sxs-lookup"><span data-stu-id="0b77e-273">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="0b77e-274">**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio**:</span><span class="sxs-lookup"><span data-stu-id="0b77e-274">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="0b77e-275">**Mover mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="0b77e-275">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="0b77e-276">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="0b77e-276">**Quarantine the message**</span></span>

   - <span data-ttu-id="0b77e-277">**Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="0b77e-277">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0b77e-278">Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0b77e-278">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0b77e-279">Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:</span><span class="sxs-lookup"><span data-stu-id="0b77e-279">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0b77e-280">**Habilitar la protección contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="0b77e-280">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="0b77e-281">**Habilitar la característica de remitente sin autenticar**</span><span class="sxs-lookup"><span data-stu-id="0b77e-281">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="0b77e-282">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="0b77e-282">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="0b77e-283">**Configuración avanzada**: haga clic en **Editar** para configurar los umbrales de suplantación de identidad avanzada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-283">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="0b77e-284">Para obtener más información, consulte [umbrales de suplantación de identidad avanzada en las directivas de antiphishing de ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="0b77e-284">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="0b77e-285">**Umbrales de suplantación de identidad avanzada**: Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0b77e-285">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="0b77e-286">**1-estándar** (este es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="0b77e-286">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="0b77e-287">**2-agresivo**</span><span class="sxs-lookup"><span data-stu-id="0b77e-287">**2 - Aggressive**</span></span>
   - <span data-ttu-id="0b77e-288">**3-más agresivo**</span><span class="sxs-lookup"><span data-stu-id="0b77e-288">**3 - More aggressive**</span></span>
   - <span data-ttu-id="0b77e-289">**4: más agresivo**</span><span class="sxs-lookup"><span data-stu-id="0b77e-289">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="0b77e-290">**Revise la configuración**: haga clic en **Editar** para volver a la página **umbrales de suplantación de identidad avanzada** .</span><span class="sxs-lookup"><span data-stu-id="0b77e-290">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="0b77e-291">Cuando haya terminado, haga clic en **Guardar** en cualquiera de las páginas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-291">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="0b77e-292">De nuevo en la página **Editar \<Name\> la Directiva** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-292">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="0b77e-293">Usar el centro de seguridad & cumplimiento para modificar la Directiva antiphishing de ATP predeterminada</span><span class="sxs-lookup"><span data-stu-id="0b77e-293">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="0b77e-294">La Directiva antiphishing de ATP predeterminada se denomina Office365 ANTIPHISH predeterminada y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-294">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="0b77e-295">Para modificar la Directiva antiphishing de ATP predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0b77e-295">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="0b77e-296">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-296">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0b77e-297">En la página **contra la suplantación de identidad** , haga clic en **directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-297">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="0b77e-298">Aparecerá la página **editar la Directiva de ANTIPHISH predeterminada de Office365** .</span><span class="sxs-lookup"><span data-stu-id="0b77e-298">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="0b77e-299">Las siguientes secciones están disponibles, que contienen ajustes idénticos para cuando se [modifica una directiva personalizada](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span><span class="sxs-lookup"><span data-stu-id="0b77e-299">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="0b77e-300">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="0b77e-300">**Impersonation**</span></span>
   - <span data-ttu-id="0b77e-301">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="0b77e-301">**Spoof**</span></span>
   - <span data-ttu-id="0b77e-302">**Configuración avanzada**</span><span class="sxs-lookup"><span data-stu-id="0b77e-302">**Advanced settings**</span></span>

   <span data-ttu-id="0b77e-303">Las siguientes opciones de configuración no están disponibles cuando se modifica la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="0b77e-303">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="0b77e-304">Puede ver la sección y los valores de configuración de la **Directiva** , pero no hay ningún vínculo **Editar** , por lo que no puede modificar la configuración (nombre de Directiva, Descripción y a quién se aplica la Directiva (se aplica a todos los destinatarios)).</span><span class="sxs-lookup"><span data-stu-id="0b77e-304">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="0b77e-305">No puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-305">You can't delete the default policy.</span></span>
   - <span data-ttu-id="0b77e-306">No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="0b77e-306">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="0b77e-307">En la página **editar la Directiva de ANTIPHISH predeterminada de Office365** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-307">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="0b77e-308">Habilitar o deshabilitar las directivas antiphishing de ATP personalizadas</span><span class="sxs-lookup"><span data-stu-id="0b77e-308">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="0b77e-309">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0b77e-310">Observe el valor de la columna **Estado** :</span><span class="sxs-lookup"><span data-stu-id="0b77e-310">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="0b77e-311">Deslice el botón de alternancia a **desactivado** para deshabilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="0b77e-311">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="0b77e-312">Deslice el botón de alternancia a **activado** para habilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="0b77e-312">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="0b77e-313">No se puede deshabilitar la Directiva antiphishing predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-313">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="0b77e-314">Establecer la prioridad de las directivas anti-phishing personalizadas de ATP</span><span class="sxs-lookup"><span data-stu-id="0b77e-314">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="0b77e-315">De forma predeterminada, las directivas antiphishing de ATP reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen una prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="0b77e-315">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="0b77e-316">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="0b77e-316">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0b77e-317">Dos directivas no pueden tener la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="0b77e-317">No two policies can have the same priority.</span></span>

<span data-ttu-id="0b77e-318">Las directivas de antiphishing de ATP personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="0b77e-318">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0b77e-319">La Directiva antiphishing predeterminada denominada Office365 ANTIPHISH predeterminada tiene el valor de prioridad personalizado **más bajo**y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="0b77e-319">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="0b77e-320">**Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva contra la suplantación de identidad (phishing) de ATP después de crearla.</span><span class="sxs-lookup"><span data-stu-id="0b77e-320">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="0b77e-321">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla antiphishing (que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="0b77e-321">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="0b77e-322">Para cambiar la prioridad de una directiva, haga clic en **aumentar prioridad** o **disminuir prioridad** en las propiedades de la Directiva (no puede modificar directamente el número de **prioridad** en el centro de seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="0b77e-322">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="0b77e-323">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-323">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="0b77e-324">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-324">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0b77e-325">Seleccione la Directiva que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="0b77e-325">Select the policy that you want to modify.</span></span> <span data-ttu-id="0b77e-326">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="0b77e-326">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0b77e-327">Aparece el control flotante \*\*editar la directiva \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="0b77e-327">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="0b77e-328">La Directiva antiphishing de ATP personalizada con el valor de **prioridad** **0** solo tiene el botón **disminuir prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="0b77e-328">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="0b77e-329">La Directiva antiphishing de ATP personalizada con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="0b77e-329">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="0b77e-330">Si tiene tres o más directivas de suplantación de identidad personalizadas, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.</span><span class="sxs-lookup"><span data-stu-id="0b77e-330">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="0b77e-331">Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="0b77e-331">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="0b77e-332">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-332">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="0b77e-333">Usar el centro de seguridad & cumplimiento para ver las directivas de ATP antiphishing</span><span class="sxs-lookup"><span data-stu-id="0b77e-333">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="0b77e-334">En el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** de \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-334">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0b77e-335">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0b77e-335">Do one of the following steps:</span></span>

   - <span data-ttu-id="0b77e-336">Seleccione una directiva antiphishing de ATP personalizada que quiera ver.</span><span class="sxs-lookup"><span data-stu-id="0b77e-336">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="0b77e-337">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="0b77e-337">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="0b77e-338">Haga clic en **directiva predeterminada** para ver la Directiva contra la suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-338">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="0b77e-339">Aparece el control flotante \*\*editar la directiva \<name\> \*\* , donde puede ver la configuración y los valores.</span><span class="sxs-lookup"><span data-stu-id="0b77e-339">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="0b77e-340">Usar el centro de seguridad & cumplimiento para quitar las directivas antiphishing de ATP</span><span class="sxs-lookup"><span data-stu-id="0b77e-340">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="0b77e-341">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-341">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0b77e-342">Seleccione la Directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="0b77e-342">Select the policy that you want to remove.</span></span> <span data-ttu-id="0b77e-343">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="0b77e-343">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0b77e-344">En el control flotante **Editar \<name\> la Directiva** que aparece, haga clic en **eliminar Directiva**y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="0b77e-344">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="0b77e-345">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-345">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="0b77e-346">Usar Exchange Online PowerShell para configurar las directivas antiphishing de ATP</span><span class="sxs-lookup"><span data-stu-id="0b77e-346">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="0b77e-347">Usar PowerShell para crear directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="0b77e-347">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="0b77e-348">La creación de una directiva contra la suplantación de identidad (phishing) en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="0b77e-348">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0b77e-349">Cree la Directiva contra phish.</span><span class="sxs-lookup"><span data-stu-id="0b77e-349">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="0b77e-350">Cree la regla ANTIPHISH que especifica la Directiva antiphishing a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="0b77e-350">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="0b77e-351">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="0b77e-351">**Notes**:</span></span>

- <span data-ttu-id="0b77e-352">Puede crear una nueva regla antiphishing y asignarle una directiva ANTIPHISH existente no asociada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-352">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="0b77e-353">Una regla antiphishing no puede asociarse con más de una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="0b77e-353">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="0b77e-354">Puede configurar las siguientes opciones en nuevas directivas antiphishing en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="0b77e-354">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="0b77e-355">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="0b77e-355">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="0b77e-356">Establezca la prioridad de la Directiva durante la creación (_prioridad_ _\<Number\>_ ) en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="0b77e-356">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="0b77e-357">Una nueva Directiva antiphishing que cree en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que asigna la Directiva a una regla antiphishing.</span><span class="sxs-lookup"><span data-stu-id="0b77e-357">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="0b77e-358">Paso 1: usar PowerShell para crear una directiva ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="0b77e-358">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="0b77e-359">Para crear una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-359">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="0b77e-360">En este ejemplo se crea una directiva contra phish denominada Research Quarantine con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="0b77e-360">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="0b77e-361">La Directiva está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="0b77e-361">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="0b77e-362">La descripción es: Research Department Policy.</span><span class="sxs-lookup"><span data-stu-id="0b77e-362">The description is: Research department policy.</span></span>
- <span data-ttu-id="0b77e-363">Habilita la protección de dominios de organización para todos los dominios aceptados y la protección de dominios de destino para fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0b77e-363">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="0b77e-364">Especifica el Mai Fuji (mfujito@fabrikam.com) como el usuario que se va a proteger de la suplantación.</span><span class="sxs-lookup"><span data-stu-id="0b77e-364">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="0b77e-365">Habilita la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="0b77e-365">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="0b77e-366">Habilita la protección de inteligencia de buzones de correo y especifica la acción de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="0b77e-366">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="0b77e-367">Habilita las sugerencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0b77e-367">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="0b77e-368">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0b77e-368">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="0b77e-369">Paso 2: usar PowerShell para crear una regla contra el phish</span><span class="sxs-lookup"><span data-stu-id="0b77e-369">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="0b77e-370">Para crear una regla contra el phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-370">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="0b77e-371">En este ejemplo se crea una regla ANTIPHISH denominada Research Department con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="0b77e-371">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="0b77e-372">La regla está asociada a la Directiva ANTIPHISH denominada Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="0b77e-372">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="0b77e-373">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="0b77e-373">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="0b77e-374">Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-374">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="0b77e-375">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0b77e-375">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="0b77e-376">Usar PowerShell para ver las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="0b77e-376">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="0b77e-377">Para ver las directivas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-377">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0b77e-378">En este ejemplo se devuelve una lista resumida de todas las directivas contra phish junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-378">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="0b77e-379">En este ejemplo se devuelven todos los valores de propiedad de la Directiva ANTIPHISH denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="0b77e-379">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="0b77e-380">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0b77e-380">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="0b77e-381">Usar PowerShell para ver las reglas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="0b77e-381">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="0b77e-382">Para ver las reglas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-382">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0b77e-383">En este ejemplo se devuelve una lista resumida de todas las reglas antiphishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-383">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="0b77e-384">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="0b77e-384">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="0b77e-385">En este ejemplo se devuelven todos los valores de propiedad de la regla antiphishing denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="0b77e-385">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="0b77e-386">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="0b77e-386">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="0b77e-387">Usar PowerShell para modificar las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="0b77e-387">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="0b77e-388">Aparte de los siguientes elementos, la misma configuración está disponible cuando se modifica una directiva ANTIPHISH en PowerShell como cuando se crea la Directiva tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva ANTIPHISH](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="0b77e-388">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="0b77e-389">El modificador _MakeDefault_ que convierte la Directiva especificada en la directiva predeterminada (aplicado a todos, siempre la prioridad **más baja** y no puede eliminarla) solo está disponible cuando se modifica una directiva ANTIPHISH en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b77e-389">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="0b77e-390">No se puede cambiar el nombre de una directiva antiphishing (el cmdlet **set-AntiPhishPolicy** no tiene un parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="0b77e-390">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0b77e-391">Al cambiar el nombre de una directiva antiphishing en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_antiphishing.</span><span class="sxs-lookup"><span data-stu-id="0b77e-391">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="0b77e-392">Para modificar una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-392">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0b77e-393">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0b77e-393">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="0b77e-394">Usar PowerShell para modificar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="0b77e-394">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="0b77e-395">La única opción que no está disponible cuando se modifica una regla antiphishing en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0b77e-395">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0b77e-396">Para habilitar o deshabilitar las reglas de ANTIPHISH existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="0b77e-396">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="0b77e-397">De lo contrario, no hay opciones de configuración adicionales disponibles cuando se modifica una regla antiphishing en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0b77e-397">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="0b77e-398">La misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla ANTIPHISH](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="0b77e-398">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="0b77e-399">Para modificar una regla antiphishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-399">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0b77e-400">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="0b77e-400">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="0b77e-401">Usar PowerShell para habilitar o deshabilitar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="0b77e-401">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="0b77e-402">La habilitación o deshabilitación de una regla antiphishing en PowerShell habilita o deshabilita toda la Directiva antiphishing (la regla ANTIPHISH y la Directiva de ANTIPHISH asignada).</span><span class="sxs-lookup"><span data-stu-id="0b77e-402">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="0b77e-403">No se puede habilitar o deshabilitar la Directiva de suplantación de identidad (phishing) predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="0b77e-403">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="0b77e-404">Para habilitar o deshabilitar una regla antiphishing en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-404">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="0b77e-405">En este ejemplo se deshabilita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="0b77e-405">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0b77e-406">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="0b77e-406">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0b77e-407">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) y [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="0b77e-407">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="0b77e-408">Usar PowerShell para establecer la prioridad de las reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="0b77e-408">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="0b77e-409">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="0b77e-409">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0b77e-410">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-410">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0b77e-411">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="0b77e-411">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0b77e-412">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="0b77e-412">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0b77e-413">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="0b77e-413">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0b77e-414">Para establecer la prioridad de una regla anti-phish en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-414">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0b77e-415">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="0b77e-415">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="0b77e-416">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="0b77e-416">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="0b77e-417">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="0b77e-417">**Notes**:</span></span>

- <span data-ttu-id="0b77e-418">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="0b77e-418">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="0b77e-419">La Directiva ANTIPHISH predeterminada no tiene una regla ANTIPHISH correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-419">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="0b77e-420">Usar PowerShell para quitar directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="0b77e-420">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="0b77e-421">Cuando se usa PowerShell para quitar una directiva antiphishing, no se elimina la regla antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0b77e-421">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="0b77e-422">Para quitar una directiva ANTIPHISH en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-422">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0b77e-423">En este ejemplo se quita la Directiva antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="0b77e-423">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0b77e-424">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="0b77e-424">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="0b77e-425">Usar PowerShell para eliminar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="0b77e-425">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="0b77e-426">Cuando se usa PowerShell para quitar una regla antiphishing, no se elimina la Directiva antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0b77e-426">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="0b77e-427">Para quitar una regla contra el phish en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0b77e-427">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="0b77e-428">En este ejemplo se quita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="0b77e-428">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0b77e-429">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="0b77e-429">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0b77e-430">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="0b77e-430">How do you know these procedures worked?</span></span>

<span data-ttu-id="0b77e-431">Para comprobar que ha configurado correctamente las directivas antiphishing de ATP, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0b77e-431">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="0b77e-432">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="0b77e-432">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="0b77e-433">Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="0b77e-433">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0b77e-434">Para ver más detalles, realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0b77e-434">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="0b77e-435">Seleccione la Directiva de la lista y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="0b77e-435">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="0b77e-436">Haga clic en **directiva predeterminada** y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="0b77e-436">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="0b77e-437">En Exchange Online PowerShell, reemplace \<Name\> por el nombre de la Directiva o regla y ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="0b77e-437">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
