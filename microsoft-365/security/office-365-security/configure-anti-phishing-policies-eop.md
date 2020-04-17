---
title: Configurar la Directiva antiphishing predeterminada en EOP
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
description: Los administradores pueden obtener información sobre cómo modificar las opciones de configuración contra la suplantación de identidad disponibles en la Directiva antiphishing predeterminada en las organizaciones de Office 365 con buzones de Exchange Online.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537538"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="36f5a-103">Configurar la Directiva antiphishing predeterminada en EOP</span><span class="sxs-lookup"><span data-stu-id="36f5a-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="36f5a-104">Office 365 organizaciones con buzones de Exchange Online y organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo de Exchange Online tienen una directiva antiphishing predeterminada.</span><span class="sxs-lookup"><span data-stu-id="36f5a-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="36f5a-105">Esta Directiva contiene un número limitado de características de suplantación de identidad que están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="36f5a-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="36f5a-106">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="36f5a-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="36f5a-107">Office 365 las organizaciones con buzones de correo de Exchange online pueden modificar la Directiva antiphishing predeterminada en el centro de seguridad & cumplimiento de Office 365 o en Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36f5a-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="36f5a-108">Las organizaciones de EOP independientes sin buzones de Exchange online no pueden modificar su Directiva antiphishing predeterminada.</span><span class="sxs-lookup"><span data-stu-id="36f5a-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="36f5a-109">Para obtener información sobre cómo crear y modificar las directivas de protección contra suplantación de identidad (ATP) más avanzadas disponibles en Office 365 Advanced Threat Protection, vea [Configure ATP anti-phishing policies in office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="36f5a-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="36f5a-110">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="36f5a-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="36f5a-111">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="36f5a-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="36f5a-112">Para ir directamente a la página de **contra la suplantación de identidad (phishing** ), use. <https://protection.office.com/antiphishing></span><span class="sxs-lookup"><span data-stu-id="36f5a-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="36f5a-113">Para conectarse a PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="36f5a-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="36f5a-114">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="36f5a-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="36f5a-115">Para agregar, modificar y eliminar directivas antiphishing, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="36f5a-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="36f5a-116">Para el acceso de solo lectura a las directivas antiphishing, debe ser miembro del grupo de roles **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="36f5a-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="36f5a-117">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento de Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="36f5a-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="36f5a-118">Para conocer la configuración recomendada para la Directiva antiphishing predeterminada, consulte [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="36f5a-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="36f5a-119">Espere hasta 30 minutos para que se aplique la directiva actualizada.</span><span class="sxs-lookup"><span data-stu-id="36f5a-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="36f5a-120">Para obtener información sobre la aplicación de directivas contra la suplantación de identidad (phishing) en la canalización de filtros, consulte [Order and Precedence of email Protection in Office 365](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="36f5a-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="36f5a-121">Usar el centro de seguridad & cumplimiento para modificar la Directiva contra suplantación de identidad (phishing) predeterminada</span><span class="sxs-lookup"><span data-stu-id="36f5a-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="36f5a-122">La Directiva antiphishing predeterminada se denomina Office365 ANTIPHISH predeterminada y no aparece en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="36f5a-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="36f5a-123">Para modificar la Directiva de suplantación de identidad (phishing) predeterminada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="36f5a-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="36f5a-124">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="36f5a-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="36f5a-125">En la página **contra la suplantación de identidad** , haga clic en **directiva predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="36f5a-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="36f5a-126">Aparecerá la página **editar la Directiva de ANTIPHISH predeterminada de Office365** .</span><span class="sxs-lookup"><span data-stu-id="36f5a-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="36f5a-127">En la sección **suplantación** , haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="36f5a-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="36f5a-128">Tenga en cuenta que esta configuración es idéntica a la configuración de suplantación que está disponible en las directivas antiphishing de ATP.</span><span class="sxs-lookup"><span data-stu-id="36f5a-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="36f5a-129">**Configuración del filtro de suplantación de identidad**: el valor predeterminado es **activado**y se recomienda que lo deje activado.</span><span class="sxs-lookup"><span data-stu-id="36f5a-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="36f5a-130">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="36f5a-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="36f5a-131">Para obtener más información, consulte [configurar inteligencia de identidades en Office 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="36f5a-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="36f5a-132">No es necesario deshabilitar la protección contra la suplantación de identidad si el registro MX no apunta a Office 365; en su lugar, se habilita el filtrado mejorado para los conectores.</span><span class="sxs-lookup"><span data-stu-id="36f5a-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="36f5a-133">Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="36f5a-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="36f5a-134">**Habilitar la característica de remitente sin autenticar**: agrega un signo de interrogación a la foto del remitente si el mensaje no supera las comprobaciones de autenticación de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="36f5a-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="36f5a-135">Para obtener más información, consulte [configuración de la suplantación de identidades en directivas antiphishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="36f5a-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="36f5a-136">El valor predeterminado es **Activada**.</span><span class="sxs-lookup"><span data-stu-id="36f5a-136">The default value is **On**.</span></span> <span data-ttu-id="36f5a-137">Para desactivarla, deslice el botón de alternancia a **desactivado**.</span><span class="sxs-lookup"><span data-stu-id="36f5a-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="36f5a-138">**Acciones**: especificar la acción que se realizará en los mensajes que no superen la inteligencia de identidad:</span><span class="sxs-lookup"><span data-stu-id="36f5a-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="36f5a-139">**Si el correo electrónico lo envía alguien que no tiene permiso para suplantar su dominio**:</span><span class="sxs-lookup"><span data-stu-id="36f5a-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="36f5a-140">**Mover mensaje a las carpetas de correo no deseado de los destinatarios** (este es el valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="36f5a-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="36f5a-141">**Poner en cuarentena el mensaje**</span><span class="sxs-lookup"><span data-stu-id="36f5a-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="36f5a-142">**Revise la configuración**: en lugar de hacer clic en cada paso individual, la configuración se muestra en un resumen.</span><span class="sxs-lookup"><span data-stu-id="36f5a-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="36f5a-143">Puede hacer clic en **Editar** en cada sección para volver a la página correspondiente.</span><span class="sxs-lookup"><span data-stu-id="36f5a-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="36f5a-144">Puede activar o **desactivar** la siguiente configuración **directamente en esta** página:</span><span class="sxs-lookup"><span data-stu-id="36f5a-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="36f5a-145">**Habilitar la protección contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="36f5a-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="36f5a-146">**Habilitar la característica de remitente sin autenticar**</span><span class="sxs-lookup"><span data-stu-id="36f5a-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="36f5a-147">Cuando haya terminado, haga clic en **Guardar** en cualquier página.</span><span class="sxs-lookup"><span data-stu-id="36f5a-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="36f5a-148">De nuevo en la página **Editar directiva predeterminada de Office365 ANTIPHISH** , revise la configuración y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="36f5a-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="36f5a-149">Usar el centro de seguridad & cumplimiento para ver la Directiva contra suplantación de identidad (phishing) predeterminada</span><span class="sxs-lookup"><span data-stu-id="36f5a-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="36f5a-150">En el centro de seguridad & cumplimiento y vaya a la **Directiva** \> de **Administración** \> de amenazas de **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="36f5a-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="36f5a-151">Haga clic en **directiva predeterminada** para ver la Directiva contra la suplantación de identidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="36f5a-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="36f5a-152">Usar Exchange Online PowerShell para configurar la Directiva antiphishing predeterminada</span><span class="sxs-lookup"><span data-stu-id="36f5a-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="36f5a-153">Usar PowerShell para ver la Directiva ANTIPHISH predeterminada</span><span class="sxs-lookup"><span data-stu-id="36f5a-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="36f5a-154">Para ver la Directiva ANTIPHISH predeterminada, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="36f5a-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="36f5a-155">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="36f5a-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="36f5a-156">Usar PowerShell para modificar la Directiva ANTIPHISH predeterminada</span><span class="sxs-lookup"><span data-stu-id="36f5a-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="36f5a-157">Para modificar la Directiva ANTIPHISH predeterminada, use la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="36f5a-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="36f5a-158">En este ejemplo se cambia la acción de los mensajes suplantados que no superan la autenticación de las comprobaciones en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="36f5a-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="36f5a-159">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="36f5a-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="36f5a-160">¿Cómo saber si estos procedimientos han funcionado?</span><span class="sxs-lookup"><span data-stu-id="36f5a-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="36f5a-161">Para comprobar que ha configurado correctamente la Directiva de suplantación de identidad (phishing) predeterminada, realice uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="36f5a-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="36f5a-162">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **anti-phishing** \> haga clic en **directiva predeterminada** y vea los detalles en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="36f5a-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="36f5a-163">En Exchange Online PowerShell, ejecute el siguiente comando y Compruebe la configuración:</span><span class="sxs-lookup"><span data-stu-id="36f5a-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
