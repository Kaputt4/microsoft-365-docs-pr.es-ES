---
title: Configurar directivas contra la suplantación de identidad (phishing) en EOP
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
description: Los administradores pueden aprender a crear, modificar y eliminar las directivas antiphishing que están disponibles en las organizaciones de Exchange Online Protection (EOP) con o sin buzones de correo de Exchange Online.
ms.openlocfilehash: 5c2e036c075072056e7783ca4dc5aeb1289d827a
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213393"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="46107-103">Configurar directivas contra la suplantación de identidad (phishing) en EOP</span><span class="sxs-lookup"><span data-stu-id="46107-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="46107-104">En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, hay una directiva antiphishing predeterminada que contiene un número limitado de características de protección contra la suplantación de identidad habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46107-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="46107-105">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="46107-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="46107-106">Los administradores pueden ver, editar y configurar (pero no eliminar) la Directiva de suplantación de identidad (phishing) predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46107-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="46107-107">Para una mayor granularidad, también puede crear directivas antiphishing personalizadas que se aplican a usuarios, grupos o dominios específicos de la organización.</span><span class="sxs-lookup"><span data-stu-id="46107-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="46107-108">Las directivas personalizadas siempre tienen prioridad sobre las directivas predeterminadas, pero su prioridad (el orden de ejecución) se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="46107-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="46107-109">Las organizaciones con buzones de correo de Exchange online pueden configurar directivas antiphishing en el centro de seguridad & cumplimiento o en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46107-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="46107-110">Las organizaciones de EOP independientes solo pueden usar el centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="46107-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="46107-111">Para obtener información sobre cómo crear y modificar las directivas de protección contra suplantación de identidad (ATP) más avanzadas disponibles en Office 365 Advanced Threat Protection (Office 365 ATP), consulte [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="46107-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="46107-112">Directivas antiphishing en el centro de seguridad & cumplimiento vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="46107-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="46107-113">Los elementos básicos de una directiva contra la suplantación de identidad (phishing) son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="46107-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="46107-114">**La Directiva ANTIPHISH**: especifica las protecciones de suplantación de identidad (phishing) que se deben habilitar o deshabilitar y las acciones para aplicar opciones.</span><span class="sxs-lookup"><span data-stu-id="46107-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="46107-115">**La regla anti-phish**: especifica la prioridad y los filtros de destinatarios (a los que se aplica la Directiva) para una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="46107-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="46107-116">La diferencia entre estos dos elementos no es obvia cuando administra directivas antiphishing en el centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="46107-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="46107-117">Al crear una directiva antiphishing en el centro de seguridad & cumplimiento, en realidad está creando una regla ANTIPHISH y la Directiva ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="46107-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="46107-118">Cuando se modifica una directiva antiphishing en el centro de seguridad & cumplimiento, la configuración relacionada con los filtros nombre, prioridad, habilitado o deshabilitado, y de destinatarios modifica la regla contra el phish.</span><span class="sxs-lookup"><span data-stu-id="46107-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="46107-119">Todas las demás opciones modifican la Directiva ANTIPHISH asociada.</span><span class="sxs-lookup"><span data-stu-id="46107-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="46107-120">Cuando se elimina una directiva antiphishing del centro de seguridad & cumplimiento, se quita la regla antiphishing y la Directiva ANTIPHISH asociada.</span><span class="sxs-lookup"><span data-stu-id="46107-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="46107-121">En Exchange Online PowerShell, la diferencia entre las directivas antiphishing y las reglas antiphishing es evidente.</span><span class="sxs-lookup"><span data-stu-id="46107-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="46107-122">Las directivas antiphishing se administran mediante los cmdlets \*\* \* -AntiPhishPolicy\*\* y se administran las reglas antiphishing mediante los cmdlets \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="46107-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="46107-123">En PowerShell, se crea la Directiva ANTIPHISH en primer lugar y, a continuación, se crea la regla ANTIPHISH que identifica la Directiva a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="46107-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="46107-124">En PowerShell, la configuración de la Directiva antiphishing y la regla antiphishing se modifican por separado.</span><span class="sxs-lookup"><span data-stu-id="46107-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="46107-125">Directiva antiphishing de ATP predeterminada</span><span class="sxs-lookup"><span data-stu-id="46107-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="46107-126">Cada organización tiene una directiva antiphishing integrada denominada Office365 ANTIPHISH predeterminada con estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="46107-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="46107-127">La Directiva denominada Office365 ANTIPHISH predeterminada se aplica a todos los destinatarios de la organización, aunque no haya ninguna regla antiphishing (filtros de destinatario) asociada a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="46107-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="46107-128">La Directiva denominada predeterminada de la ANTIPHISH de Office365 tiene el valor de prioridad personalizado **más bajo** que no se puede modificar (la Directiva se aplica siempre en último lugar).</span><span class="sxs-lookup"><span data-stu-id="46107-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="46107-129">Cualquier directiva personalizada que cree siempre tendrá una prioridad mayor que la Directiva denominada Office365 ANTIPHISH predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46107-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="46107-130">La Directiva denominada Office365 ANTIPHISH predeterminada es la directiva predeterminada (la propiedad **IsDefault** tiene el valor `True` ) y no se puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46107-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="46107-131">Para aumentar la eficacia de la protección contra suplantación de identidad (phishing), puede crear directivas antiphishing personalizadas con una configuración más estricta que se aplique a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="46107-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="46107-132">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="46107-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="46107-133">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="46107-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="46107-134">Para ir directamente a la página de **contra la suplantación de identidad (phishing** ), use <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="46107-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="46107-135">Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="46107-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="46107-136">No puede administrar las directivas antiphishing en PowerShell de EOP independiente.</span><span class="sxs-lookup"><span data-stu-id="46107-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="46107-137">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="46107-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="46107-138">Para agregar, modificar y eliminar directivas antiphishing, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="46107-138">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="46107-139">Para el acceso de solo lectura a las directivas antiphishing, debe ser miembro del grupo de roles **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="46107-139">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="46107-140">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="46107-140">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="46107-141">Para poder crear y modificar directivas contra correo no deseado en EOP independiente, debe hacer algo que requiera la _hidratación_ de su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="46107-141">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="46107-142">Por ejemplo, en el EAC, puede ir a la pestaña **permisos** , seleccionar un grupo de roles existente, hacer clic en **Editar** ![ icono Editar ](../../media/ITPro-EAC-EditIcon.png) y quitar una función (que más adelante se agregará).</span><span class="sxs-lookup"><span data-stu-id="46107-142">For example, in the EAC, you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="46107-143">Si nunca se ha hidratado el espacio empresarial, se obtiene un cuadro de diálogo denominado configuración de la **organización de actualización** con una barra de progreso que debería completarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="46107-143">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="46107-144">Para obtener más información sobre la hidratación, consulte el cmdlet [enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization) (que no está disponible en POWERSHELL de EOP independiente ni en el centro de seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="46107-144">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/organization/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="46107-145">Para conocer la configuración recomendada para las directivas antiphishing, consulte [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="46107-145">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="46107-146">Espere hasta 30 minutos para que se aplique la directiva actualizada.</span><span class="sxs-lookup"><span data-stu-id="46107-146">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="46107-147">Para obtener información acerca de dónde se aplican las directivas contra la suplantación de identidad (phishing) en la canalización de filtros, consulte [Order and Precedence of email Protection](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="46107-147">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="46107-148">Usar el centro de seguridad & cumplimiento para crear directivas contra la suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="46107-148">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="46107-149">La creación de una directiva antiphishing personalizada en el centro de seguridad & cumplimiento crea la regla antiphishing y la Directiva ANTIPHISH asociada al mismo tiempo con el mismo nombre para ambas.</span><span class="sxs-lookup"><span data-stu-id="46107-149">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="46107-150">Cuando se crea una directiva antiphishing, solo se puede especificar el nombre de la Directiva, la descripción y el filtro de destinatarios que identifican a quién se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="46107-150">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="46107-151">Después de crear la Directiva, puede modificar la Directiva para cambiar o revisar la configuración predeterminada de la suplantación de identidad (phishing).</span><span class="sxs-lookup"><span data-stu-id="46107-151">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="46107-152">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="46107-152">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="46107-153">En la página **contra la suplantación de identidad** , haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="46107-153">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="46107-154">Se abrirá el Asistente para **crear una nueva Directiva antiphishing** .</span><span class="sxs-lookup"><span data-stu-id="46107-154">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="46107-155">En la página **asigne un nombre a la Directiva** , configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="46107-155">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="46107-156">**Nombre**: escriba un nombre único y descriptivo para la directiva.</span><span class="sxs-lookup"><span data-stu-id="46107-156">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="46107-157">**Descripción**: escriba una descripción opcional para la directiva.</span><span class="sxs-lookup"><span data-stu-id="46107-157">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="46107-158">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="46107-158">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="46107-159">En la página **aplicado a** que aparece, identifique los destinatarios internos a los que se aplica la Directiva.</span><span class="sxs-lookup"><span data-stu-id="46107-159">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="46107-160">Solo puede usar una condición o excepción una vez, pero puede especificar varios valores para la condición o excepción.</span><span class="sxs-lookup"><span data-stu-id="46107-160">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="46107-161">Varios valores de la misma condición o excepción usan la lógica OR (por ejemplo, _\<recipient1\>_ or _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="46107-161">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="46107-162">Diversas condiciones o excepciones usan la lógica AND (por ejemplo, _\<recipient1\>_ and _\<miembro del grupo 1\>_).</span><span class="sxs-lookup"><span data-stu-id="46107-162">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="46107-163">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="46107-163">Click **Add a condition**.</span></span> <span data-ttu-id="46107-164">En la lista desplegable que aparece, seleccione una condición en **aplicado si**:</span><span class="sxs-lookup"><span data-stu-id="46107-164">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="46107-165">**El destinatario es**: especifica uno o más buzones de correo, usuarios de correo o contactos de correo de su organización.</span><span class="sxs-lookup"><span data-stu-id="46107-165">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="46107-166">**El destinatario es un miembro de**: especifica uno o más grupos de la organización.</span><span class="sxs-lookup"><span data-stu-id="46107-166">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="46107-167">**El dominio del destinatario es**: especifica los destinatarios en uno o varios de los dominios aceptados configurados en la organización.</span><span class="sxs-lookup"><span data-stu-id="46107-167">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="46107-168">Después de seleccionar la condición, aparece la lista desplegable correspondiente con una **de estas** casillas.</span><span class="sxs-lookup"><span data-stu-id="46107-168">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="46107-169">Haga clic en el cuadro y desplácese por la lista de valores que desea seleccionar.</span><span class="sxs-lookup"><span data-stu-id="46107-169">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="46107-170">Haga clic en el cuadro y comience a escribir para filtrar la lista y seleccionar un valor.</span><span class="sxs-lookup"><span data-stu-id="46107-170">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="46107-171">Para agregar más valores, haga clic en un área vacía del cuadro.</span><span class="sxs-lookup"><span data-stu-id="46107-171">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="46107-172">Para quitar entradas individuales, haga **Remove** clic en ![ el icono quitar quitar del ](../../media/scc-remove-icon.png) valor.</span><span class="sxs-lookup"><span data-stu-id="46107-172">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="46107-173">Para quitar toda la condición, haga clic en **quitar** ![ icono ](../../media/scc-remove-icon.png) de eliminación en la condición.</span><span class="sxs-lookup"><span data-stu-id="46107-173">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="46107-174">Para agregar una condición adicional, haga clic en **Agregar condición** y seleccione un valor restante en **aplicado si**.</span><span class="sxs-lookup"><span data-stu-id="46107-174">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="46107-175">Para agregar excepciones, haga clic en **Agregar una condición** y seleccione una excepción en **excepto si**.</span><span class="sxs-lookup"><span data-stu-id="46107-175">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="46107-176">La configuración y el comportamiento se muestran exactamente igual que las condiciones.</span><span class="sxs-lookup"><span data-stu-id="46107-176">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="46107-177">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="46107-177">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="46107-178">En la página **Revise la configuración** que aparece, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="46107-178">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="46107-179">Puede hacer clic en **Editar** en cada configuración para modificarla.</span><span class="sxs-lookup"><span data-stu-id="46107-179">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="46107-180">Cuando haya terminado, haga clic en **crear esta directiva**.</span><span class="sxs-lookup"><span data-stu-id="46107-180">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="46107-181">Haga clic en **Aceptar** en el cuadro de diálogo de confirmación que aparece.</span><span class="sxs-lookup"><span data-stu-id="46107-181">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="46107-182">Después de crear la Directiva antiphishing con estas opciones de directiva generales, siga las instrucciones de la siguiente sección para establecer la configuración de protección en la Directiva.</span><span class="sxs-lookup"><span data-stu-id="46107-182">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="46107-183">Usar el centro de seguridad & cumplimiento para modificar las directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="46107-183">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="46107-184">Use los siguientes procedimientos para modificar las directivas antiphishing: una nueva directiva que ha creado o las directivas existentes que ya ha personalizado.</span><span class="sxs-lookup"><span data-stu-id="46107-184">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="46107-185">Si aún no está ahí, abra el centro de seguridad & cumplimiento y vaya a la Directiva de **Administración de amenazas** \> **Policy** \> **contra la suplantación de identidad (phishing)**.</span><span class="sxs-lookup"><span data-stu-id="46107-185">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="46107-186">Seleccione la Directiva antiphishing personalizada que quiera modificar.</span><span class="sxs-lookup"><span data-stu-id="46107-186">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="46107-187">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="46107-187">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="46107-188">Aparece el control flotante **editar el \< nombre \> de la Directiva** .</span><span class="sxs-lookup"><span data-stu-id="46107-188">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="46107-189">Al hacer clic en **Editar** en cualquier sección, obtendrá acceso a la configuración de esa sección.</span><span class="sxs-lookup"><span data-stu-id="46107-189">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="46107-190">Los pasos siguientes se presentan en el orden en que aparecen las secciones, pero no son secuenciales (puede seleccionar y modificar las secciones en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="46107-190">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="46107-191">Después de hacer clic en **Editar** en una sección, la configuración disponible se presenta en un formato de asistente, pero puede saltar dentro de las páginas en cualquier orden y puede hacer clic en **Guardar** en cualquier página (o en **Cancelar** o **cerrar** el ![ icono cerrar ](../../media/scc-remove-icon.png) para volver a la página **editar el \< nombre \> de la Directiva** (no es necesario visitar la última página del Asistente para guardarla o dejarla).</span><span class="sxs-lookup"><span data-stu-id="46107-191">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="46107-192">**Configuración de directiva**: haga clic en **Editar** para modificar la misma configuración que estaba disponible cuando [creó la Directiva](#use-the-security--compliance-center-to-create-anti-phishing-policies) en la sección anterior:</span><span class="sxs-lookup"><span data-stu-id="46107-192">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="46107-193">**Name**</span><span class="sxs-lookup"><span data-stu-id="46107-193">**Name**</span></span>
   - <span data-ttu-id="46107-194">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="46107-194">**Description**</span></span>
   - <span data-ttu-id="46107-195">**Aplicado a**</span><span class="sxs-lookup"><span data-stu-id="46107-195">**Applied to**</span></span>
   - <span data-ttu-id="46107-196">**Revisar la configuración**</span><span class="sxs-lookup"><span data-stu-id="46107-196">**Review your settings**</span></span>

   <span data-ttu-id="46107-197">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="46107-197">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="46107-198">**Suplantación de identidad**: haga clic en **Editar** para activar o desactivar la inteligencia de suplantación, activar o desactivar la identificación del remitente sin autenticar en Outlook y configurar la acción para aplicar a los mensajes de los remitentes suplantados bloqueados.</span><span class="sxs-lookup"><span data-stu-id="46107-198">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="46107-199">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="46107-199">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="46107-200">Tenga en cuenta que esta misma configuración también está disponible en las directivas contra la suplantación de identidad (phishing) de ATP.</span><span class="sxs-lookup"><span data-stu-id="46107-200">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="46107-201">**Configuración del filtro de suplantación de identidad**: el valor predeterminado es **activado**y se recomienda que lo deje activado.</span><span class="sxs-lookup"><span data-stu-id="46107-201">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="46107-202">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="46107-202">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="46107-203">Para obtener más información, vea [Configure outsimulate Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="46107-203">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="46107-204">No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Microsoft 365; en su lugar, se habilita el filtrado mejorado para los conectores.</span><span class="sxs-lookup"><span data-stu-id="46107-204">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="46107-205">Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="46107-205">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="46107-206">**Habilitar la característica de remitente sin autenticar**: el valor predeterminado es **activado**.</span><span class="sxs-lookup"><span data-stu-id="46107-206">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="46107-207">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="46107-207">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="46107-208">**Acciones**: especificar la acción que se realizará en los mensajes que no superen la inteligencia de identidad:</span><span class="sxs-lookup"><span data-stu-id="46107-208">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="46107-209">**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio**:</span><span class="sxs-lookup"><span data-stu-id="46107-209">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="46107-210">**Mover mensaje a las carpetas de correo no deseado de los destinatarios**</span><span class="sxs-lookup"><span data-stu-id="46107-210">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="46107-211">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="46107-211">**Quarantine the message**</span></span>

   - <span data-ttu-id="46107-212">**Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="46107-212">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="46107-213">Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="46107-213">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="46107-214">Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:</span><span class="sxs-lookup"><span data-stu-id="46107-214">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="46107-215">**Habilitar la protección contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="46107-215">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="46107-216">**Habilitar la característica de remitente sin autenticar**</span><span class="sxs-lookup"><span data-stu-id="46107-216">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="46107-217">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="46107-217">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="46107-218">De nuevo en la página **Editar \< el \> nombre de la Directiva** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="46107-218">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="46107-219">Usar el centro de seguridad & cumplimiento para modificar la Directiva contra suplantación de identidad (phishing) predeterminada</span><span class="sxs-lookup"><span data-stu-id="46107-219">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="46107-220">La Directiva antiphishing predeterminada se denomina Office365 ANTIPHISH predeterminada y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="46107-220">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="46107-221">Para modificar la Directiva de suplantación de identidad (phishing) predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46107-221">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="46107-222">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="46107-222">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="46107-223">En la página **contra la suplantación de identidad** , haga clic en **directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="46107-223">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="46107-224">Aparecerá la página **editar la Directiva de ANTIPHISH predeterminada de Office365** .</span><span class="sxs-lookup"><span data-stu-id="46107-224">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="46107-225">Las siguientes secciones están disponibles, que contienen ajustes idénticos para cuando se [modifica una directiva personalizada](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="46107-225">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="46107-226">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="46107-226">**Impersonation**</span></span>
   - <span data-ttu-id="46107-227">**Suplantación**</span><span class="sxs-lookup"><span data-stu-id="46107-227">**Spoof**</span></span>
   - <span data-ttu-id="46107-228">**Configuración avanzada**</span><span class="sxs-lookup"><span data-stu-id="46107-228">**Advanced settings**</span></span>

   <span data-ttu-id="46107-229">Las siguientes opciones de configuración no están disponibles cuando se modifica la directiva predeterminada:</span><span class="sxs-lookup"><span data-stu-id="46107-229">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="46107-230">Puede ver la sección y los valores de configuración de la **Directiva** , pero no hay ningún vínculo **Editar** , por lo que no puede modificar la configuración (nombre de Directiva, Descripción y a quién se aplica la Directiva (se aplica a todos los destinatarios)).</span><span class="sxs-lookup"><span data-stu-id="46107-230">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="46107-231">No puede eliminar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46107-231">You can't delete the default policy.</span></span>
   - <span data-ttu-id="46107-232">No puede cambiar la prioridad de la directiva predeterminada (siempre se aplica en último lugar).</span><span class="sxs-lookup"><span data-stu-id="46107-232">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="46107-233">En la página **editar la Directiva de ANTIPHISH predeterminada de Office365** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="46107-233">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="46107-234">Habilitar o deshabilitar las directivas antiphishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="46107-234">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="46107-235">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="46107-235">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="46107-236">Observe el valor de la columna **Estado** :</span><span class="sxs-lookup"><span data-stu-id="46107-236">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="46107-237">Deslice el botón de alternancia a **desactivado** para deshabilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="46107-237">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="46107-238">Deslice el botón de alternancia a **activado** para habilitar la Directiva.</span><span class="sxs-lookup"><span data-stu-id="46107-238">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="46107-239">No se puede deshabilitar la Directiva antiphishing predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46107-239">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="46107-240">Establecer la prioridad de las directivas antiphishing personalizadas</span><span class="sxs-lookup"><span data-stu-id="46107-240">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="46107-241">De forma predeterminada, las directivas antiphishing reciben una prioridad que se basa en el orden en que se crearon (las directivas más recientes tienen prioridad más baja que las directivas anteriores).</span><span class="sxs-lookup"><span data-stu-id="46107-241">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="46107-242">Un número de prioridad más bajo indica una prioridad mayor de la directiva (0 es el más alto) y las directivas se procesan por orden de prioridad (las directivas de prioridad mayor se procesan antes que las directivas de prioridad menor).</span><span class="sxs-lookup"><span data-stu-id="46107-242">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="46107-243">Dos directivas no pueden tener la misma prioridad.</span><span class="sxs-lookup"><span data-stu-id="46107-243">No two policies can have the same priority.</span></span>

<span data-ttu-id="46107-244">Las directivas de suplantación de identidad personalizadas se muestran en el orden en que se procesan (la primera Directiva tiene el valor de **prioridad** 0).</span><span class="sxs-lookup"><span data-stu-id="46107-244">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="46107-245">La Directiva antiphishing predeterminada denominada Office365 ANTIPHISH predeterminada tiene el valor de prioridad personalizado **más bajo**y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="46107-245">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="46107-246">**Nota**: en el centro de seguridad & cumplimiento, solo puede cambiar la prioridad de la Directiva contra el suplantación de identidad (phishing) después de crearla.</span><span class="sxs-lookup"><span data-stu-id="46107-246">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="46107-247">En PowerShell, puede invalidar la prioridad predeterminada al crear la regla antiphishing (que puede afectar a la prioridad de las reglas existentes).</span><span class="sxs-lookup"><span data-stu-id="46107-247">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="46107-248">Para cambiar la prioridad de una directiva, haga clic en **aumentar prioridad** o **disminuir prioridad** en las propiedades de la Directiva (no puede modificar directamente el número de **prioridad** en el centro de seguridad & cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="46107-248">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="46107-249">Cambiar la prioridad de una directiva solo tiene sentido si tiene varias directivas.</span><span class="sxs-lookup"><span data-stu-id="46107-249">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="46107-250">En el centro de seguridad & cumplimiento, vaya a Directiva de **Administración de amenazas** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="46107-250">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="46107-251">Seleccione la Directiva que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="46107-251">Select the policy that you want to modify.</span></span> <span data-ttu-id="46107-252">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="46107-252">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="46107-253">Aparece el control flotante **editar el \< nombre \> de la Directiva** .</span><span class="sxs-lookup"><span data-stu-id="46107-253">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="46107-254">La Directiva antiphishing personalizada con el valor **Priority** de prioridad **0** solo tiene el botón **disminuir prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="46107-254">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="46107-255">La Directiva antiphishing personalizada con el valor de **prioridad** más bajo (por ejemplo, **3**) solo tiene el botón **aumentar prioridad** disponible.</span><span class="sxs-lookup"><span data-stu-id="46107-255">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="46107-256">Si tiene tres o más directivas de suplantación de identidad personalizadas, las directivas entre los valores de prioridad mayor y menor tienen los botones **aumentar prioridad** y **disminuir prioridad** disponibles.</span><span class="sxs-lookup"><span data-stu-id="46107-256">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="46107-257">Haga clic en **aumentar prioridad** o **disminuir prioridad** para cambiar el valor de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="46107-257">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="46107-258">Cuando haya terminado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="46107-258">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="46107-259">Usar el centro de seguridad & cumplimiento para ver las directivas de protección contra suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="46107-259">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="46107-260">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="46107-260">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="46107-261">Realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="46107-261">Do one of the following steps:</span></span>

   - <span data-ttu-id="46107-262">Seleccione una directiva de antiphishing personalizada que quiera ver.</span><span class="sxs-lookup"><span data-stu-id="46107-262">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="46107-263">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="46107-263">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="46107-264">Haga clic en **directiva predeterminada** para ver la Directiva contra la suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46107-264">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="46107-265">Aparece el control flotante **editar el \< nombre \> de la Directiva** , donde puede ver la configuración y los valores.</span><span class="sxs-lookup"><span data-stu-id="46107-265">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="46107-266">Usar el centro de seguridad & cumplimiento para eliminar las directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="46107-266">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="46107-267">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="46107-267">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="46107-268">Seleccione la Directiva que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="46107-268">Select the policy that you want to remove.</span></span> <span data-ttu-id="46107-269">Si ya está seleccionada, anule la selección y vuelva a seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="46107-269">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="46107-270">En el control flotante **Editar \< el \> nombre** de la Directiva que aparece, haga clic en **eliminar Directiva**y, a continuación, haga clic en **sí** en el cuadro de diálogo de advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="46107-270">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="46107-271">No puede quitar la directiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46107-271">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="46107-272">Usar Exchange Online PowerShell para configurar las directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="46107-272">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="46107-273">Los siguientes procedimientos no están disponibles en organizaciones de EOP independientes.</span><span class="sxs-lookup"><span data-stu-id="46107-273">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="46107-274">Usar PowerShell para crear directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="46107-274">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="46107-275">La creación de una directiva contra la suplantación de identidad (phishing) en PowerShell es un proceso de dos pasos:</span><span class="sxs-lookup"><span data-stu-id="46107-275">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="46107-276">Cree la Directiva contra phish.</span><span class="sxs-lookup"><span data-stu-id="46107-276">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="46107-277">Cree la regla ANTIPHISH que especifica la Directiva antiphishing a la que se aplica la regla.</span><span class="sxs-lookup"><span data-stu-id="46107-277">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="46107-278">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="46107-278">**Notes**:</span></span>

- <span data-ttu-id="46107-279">Puede crear una nueva regla antiphishing y asignarle una directiva ANTIPHISH existente no asociada.</span><span class="sxs-lookup"><span data-stu-id="46107-279">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="46107-280">Una regla antiphishing no puede asociarse con más de una directiva antiphishing.</span><span class="sxs-lookup"><span data-stu-id="46107-280">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="46107-281">Puede configurar las siguientes opciones en nuevas directivas antiphishing en PowerShell que no están disponibles en el centro de seguridad & cumplimiento hasta que se crea la Directiva:</span><span class="sxs-lookup"><span data-stu-id="46107-281">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="46107-282">Cree la nueva directiva como deshabilitada (_habilitada_ `$false` en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="46107-282">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="46107-283">Establezca la prioridad de la Directiva durante la creación ( _ \< número \> _de_prioridad_ ) en el cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="46107-283">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="46107-284">Una nueva Directiva antiphishing que cree en PowerShell no es visible en el centro de seguridad & cumplimiento hasta que asigna la Directiva a una regla antiphishing.</span><span class="sxs-lookup"><span data-stu-id="46107-284">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="46107-285">Paso 1: usar PowerShell para crear una directiva ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="46107-285">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="46107-286">Para crear una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-286">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="46107-287">En este ejemplo se crea una directiva contra phish denominada Research Quarantine con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="46107-287">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="46107-288">La Directiva está habilitada (no se usa el parámetro _Enabled_ y el valor predeterminado es `$true` ).</span><span class="sxs-lookup"><span data-stu-id="46107-288">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="46107-289">La descripción es: Research Department Policy.</span><span class="sxs-lookup"><span data-stu-id="46107-289">The description is: Research department policy.</span></span>
- <span data-ttu-id="46107-290">Cambia la acción predeterminada para la suplantación de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="46107-290">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="46107-291">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="46107-291">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="46107-292">Paso 2: usar PowerShell para crear una regla contra el phish</span><span class="sxs-lookup"><span data-stu-id="46107-292">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="46107-293">Para crear una regla contra el phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-293">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="46107-294">En este ejemplo se crea una regla ANTIPHISH denominada Research Department con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="46107-294">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="46107-295">La regla está asociada a la Directiva ANTIPHISH denominada Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="46107-295">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="46107-296">La regla se aplica a los miembros del grupo denominado Research Department.</span><span class="sxs-lookup"><span data-stu-id="46107-296">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="46107-297">Como no se usa el parámetro _Priority_ , se usa la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="46107-297">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="46107-298">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="46107-298">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="46107-299">Usar PowerShell para ver las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="46107-299">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="46107-300">Para ver las directivas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-300">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="46107-301">En este ejemplo se devuelve una lista resumida de todas las directivas contra phish junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="46107-301">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="46107-302">En este ejemplo se devuelven todos los valores de propiedad de la Directiva ANTIPHISH denominada Executives.</span><span class="sxs-lookup"><span data-stu-id="46107-302">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="46107-303">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="46107-303">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="46107-304">Usar PowerShell para ver las reglas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="46107-304">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="46107-305">Para ver las reglas ANTIPHISH existentes, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-305">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="46107-306">En este ejemplo se devuelve una lista resumida de todas las reglas antiphishing junto con las propiedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="46107-306">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="46107-307">Para filtrar la lista mediante las reglas habilitadas o deshabilitadas, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="46107-307">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="46107-308">En este ejemplo se devuelven todos los valores de propiedad de la regla antiphishing denominada ejecutivos de contoso.</span><span class="sxs-lookup"><span data-stu-id="46107-308">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="46107-309">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="46107-309">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="46107-310">Usar PowerShell para modificar las directivas ANTIPHISH</span><span class="sxs-lookup"><span data-stu-id="46107-310">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="46107-311">Aparte de los siguientes elementos, la misma configuración está disponible cuando se modifica una directiva ANTIPHISH en PowerShell como cuando se crea la Directiva tal como se describe en la sección [paso 1: usar PowerShell para crear una directiva ANTIPHISH](#step-1-use-powershell-to-create-an-anti-phish-policy) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="46107-311">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="46107-312">El modificador _MakeDefault_ que convierte la Directiva especificada en la directiva predeterminada (aplicado a todos, siempre la prioridad **más baja** y no puede eliminarla) solo está disponible cuando se modifica una directiva ANTIPHISH en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46107-312">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="46107-313">No se puede cambiar el nombre de una directiva antiphishing (el cmdlet **set-AntiPhishPolicy** no tiene un parámetro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="46107-313">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="46107-314">Al cambiar el nombre de una directiva antiphishing en el centro de seguridad & cumplimiento, sólo cambia el nombre de la _regla_antiphishing.</span><span class="sxs-lookup"><span data-stu-id="46107-314">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="46107-315">Para modificar una directiva contra phish, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-315">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="46107-316">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="46107-316">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="46107-317">Usar PowerShell para modificar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="46107-317">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="46107-318">La única opción que no está disponible cuando se modifica una regla antiphishing en PowerShell es el parámetro _Enabled_ que permite crear una regla deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="46107-318">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="46107-319">Para habilitar o deshabilitar las reglas de ANTIPHISH existentes, consulte la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="46107-319">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="46107-320">De lo contrario, no hay opciones de configuración adicionales disponibles cuando se modifica una regla antiphishing en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46107-320">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="46107-321">La misma configuración está disponible cuando se crea una regla tal y como se describe en la sección [paso 2: usar PowerShell para crear una regla ANTIPHISH](#step-2-use-powershell-to-create-an-anti-phish-rule) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="46107-321">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="46107-322">Para modificar una regla antiphishing, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-322">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="46107-323">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="46107-323">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="46107-324">Usar PowerShell para habilitar o deshabilitar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="46107-324">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="46107-325">La habilitación o deshabilitación de una regla antiphishing en PowerShell habilita o deshabilita toda la Directiva antiphishing (la regla ANTIPHISH y la Directiva de ANTIPHISH asignada).</span><span class="sxs-lookup"><span data-stu-id="46107-325">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="46107-326">No se puede habilitar o deshabilitar la Directiva de suplantación de identidad (phishing) predeterminada (siempre se aplica a todos los destinatarios).</span><span class="sxs-lookup"><span data-stu-id="46107-326">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="46107-327">Para habilitar o deshabilitar una regla antiphishing en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-327">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="46107-328">En este ejemplo se deshabilita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="46107-328">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="46107-329">Este ejemplo habilita la misma regla.</span><span class="sxs-lookup"><span data-stu-id="46107-329">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="46107-330">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) y [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="46107-330">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="46107-331">Usar PowerShell para establecer la prioridad de las reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="46107-331">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="46107-332">El valor de prioridad máximo que se puede establecer en una regla es 0.</span><span class="sxs-lookup"><span data-stu-id="46107-332">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="46107-333">El valor mínimo que se puede establecer depende del número de reglas.</span><span class="sxs-lookup"><span data-stu-id="46107-333">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="46107-334">Por ejemplo, si tiene cinco reglas, puede usar los valores de prioridad del 0 al 4.</span><span class="sxs-lookup"><span data-stu-id="46107-334">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="46107-335">El cambio de prioridad de una regla existente puede tener un efecto cascada en otras reglas.</span><span class="sxs-lookup"><span data-stu-id="46107-335">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="46107-336">Por ejemplo, si tiene cinco reglas personalizadas (prioridades del 0 al 4) y cambia la prioridad de una regla a 2, la regla existente de prioridad 2 cambia a prioridad 3 y la regla de prioridad 3 cambia a prioridad 4.</span><span class="sxs-lookup"><span data-stu-id="46107-336">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="46107-337">Para establecer la prioridad de una regla anti-phish en PowerShell, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-337">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="46107-338">Este ejemplo establece la prioridad de la regla denominada Marketing Department en 2.</span><span class="sxs-lookup"><span data-stu-id="46107-338">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="46107-339">Todas las reglas existentes que tienen una prioridad menor o igual a 2 se reducen en 1 (sus números de prioridad aumentan en 1).</span><span class="sxs-lookup"><span data-stu-id="46107-339">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="46107-340">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="46107-340">**Notes**:</span></span>

- <span data-ttu-id="46107-341">Para establecer la prioridad de una nueva regla al crearla, use el parámetro _Priority_ en el cmdlet **New-AntiPhishRule** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="46107-341">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="46107-342">La Directiva ANTIPHISH predeterminada no tiene una regla ANTIPHISH correspondiente y siempre tiene el valor de prioridad no modificable **más bajo**.</span><span class="sxs-lookup"><span data-stu-id="46107-342">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="46107-343">Usar PowerShell para quitar directivas antiphishing</span><span class="sxs-lookup"><span data-stu-id="46107-343">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="46107-344">Cuando se usa PowerShell para quitar una directiva antiphishing, no se elimina la regla antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="46107-344">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="46107-345">Para quitar una directiva ANTIPHISH en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-345">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="46107-346">En este ejemplo se quita la Directiva antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="46107-346">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="46107-347">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="46107-347">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="46107-348">Usar PowerShell para eliminar reglas antiphishing</span><span class="sxs-lookup"><span data-stu-id="46107-348">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="46107-349">Cuando se usa PowerShell para quitar una regla antiphishing, no se elimina la Directiva antiphishing correspondiente.</span><span class="sxs-lookup"><span data-stu-id="46107-349">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="46107-350">Para quitar una regla contra el phish en PowerShell, use esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="46107-350">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="46107-351">En este ejemplo se quita la regla antiphishing denominada Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="46107-351">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="46107-352">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="46107-352">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="46107-353">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="46107-353">How do you know these procedures worked?</span></span>

<span data-ttu-id="46107-354">Para comprobar que ha configurado correctamente las directivas antiphishing de ATP, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46107-354">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="46107-355">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="46107-355">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="46107-356">Compruebe la lista de directivas, sus valores de **Estado** y sus valores de **prioridad** .</span><span class="sxs-lookup"><span data-stu-id="46107-356">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="46107-357">Para ver más detalles, realice uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="46107-357">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="46107-358">Seleccione la Directiva de la lista y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="46107-358">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="46107-359">Haga clic en **directiva predeterminada** y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="46107-359">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="46107-360">En Exchange Online PowerShell, reemplace \< name \> por el nombre de la Directiva o regla y ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="46107-360">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
