---
title: Analizador de configuración para directivas de seguridad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar el analizador de configuración para encontrar y corregir directivas de seguridad que están por debajo de las directivas de seguridad estándar protección estándar y protección estricta.
ms.openlocfilehash: 7d02a6f83ceb06eb56039b449890fd90712c76e5
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572542"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="56098-103">Analizador de configuración para directivas de protección en EOP y Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="56098-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="56098-104">Las características descritas en este tema están en versión preliminar, no están disponibles en todas las organizaciones y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="56098-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="56098-105">Para obtener información sobre la programación de versiones, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="56098-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="56098-106">El analizador de configuración del centro de seguridad & cumplimiento ofrece una ubicación central para buscar y corregir directivas de seguridad en las que la configuración está por debajo de la configuración de Perfil de protección estándar y protección estricta en [directivas de seguridad predeterminadas](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="56098-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="56098-107">El analizador de configuración analiza los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="56098-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="56098-108">**Directivas de Exchange Online Protection (EOP)**: Esto incluye a Microsoft 365 organizaciones con buzones de Exchange Online y organizaciones independientes de EOP sin buzones de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="56098-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="56098-109">[Directivas contra correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="56098-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="56098-110">[Directivas antimalware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="56098-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="56098-111">[Directivas de protección contra suplantación de EOP](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="56098-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="56098-112">**Directivas de Microsoft defender para office 365**: Esto incluye a las organizaciones con las suscripciones complementarias de Microsoft 365 E5 o defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="56098-112">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="56098-113">Directivas antiphishing en Microsoft defender para Office 365, que incluyen:</span><span class="sxs-lookup"><span data-stu-id="56098-113">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="56098-114">La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas de protección contra suplantación de EOP.</span><span class="sxs-lookup"><span data-stu-id="56098-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="56098-115">Configuración de suplantación</span><span class="sxs-lookup"><span data-stu-id="56098-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="56098-116">Umbrales de suplantación de identidad avanzada</span><span class="sxs-lookup"><span data-stu-id="56098-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="56098-117">[Directivas de vínculos a prueba](set-up-atp-safe-links-policies.md)de errores.</span><span class="sxs-lookup"><span data-stu-id="56098-117">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="56098-118">[Directivas de datos adjuntos seguros](set-up-atp-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="56098-118">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="56098-119">Los valores de configuración **estándar** y **estricta** de la Directiva que se usan como líneas de base se describen en [configuración recomendada para EOP y Microsoft defender para Office 365 Security](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="56098-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="56098-120">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="56098-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="56098-121">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="56098-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="56098-122">Para ir directamente a la página del **analizador de configuración** , use <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="56098-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="56098-123">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="56098-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="56098-124">Debe tener asignados permisos en el centro de seguridad & cumplimiento antes de poder llevar a cabo los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="56098-124">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="56098-125">Para usar el analizador de configuración **y** realizar actualizaciones en las directivas de seguridad, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="56098-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="56098-126">Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="56098-126">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="56098-127">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="56098-127">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="56098-128">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="56098-128">**Notes**:</span></span>

  - <span data-ttu-id="56098-129">La adición de usuarios al rol correspondiente de Azure Active Directory en el centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el centro de seguridad & cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56098-129">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="56098-130">Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="56098-130">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="56098-131">El grupo de roles administración de la **organización de solo vista** de [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="56098-131">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="56098-132">Uso del analizador de configuración en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="56098-132">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="56098-133">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **Configuration Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="56098-133">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget analizador de configuración en la página Directiva de administración de amenazas \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="56098-135">El analizador de configuración tiene dos pestañas principales:</span><span class="sxs-lookup"><span data-stu-id="56098-135">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="56098-136">**Configuración y recomendaciones**: elige estándar o estricto y compara esa configuración con las directivas de seguridad existentes.</span><span class="sxs-lookup"><span data-stu-id="56098-136">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="56098-137">En los resultados, puede ajustar los valores de la configuración para que aparezcan en el mismo nivel que el estándar o estricto.</span><span class="sxs-lookup"><span data-stu-id="56098-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="56098-138">**Análisis e historial de la fase de configuración**: esta vista permite realizar un seguimiento de los cambios de directiva con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="56098-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="56098-139">Configuración y ficha recomendaciones en el analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="56098-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="56098-140">De forma predeterminada, la pestaña se abre en la comparación con el perfil de protección estándar.</span><span class="sxs-lookup"><span data-stu-id="56098-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="56098-141">Puede cambiar a la comparación de un perfil de protección estricto haciendo clic en **Ver recomendaciones estrictas**.</span><span class="sxs-lookup"><span data-stu-id="56098-141">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="56098-142">Para cambiar de nuevo, seleccione **Ver recomendaciones estándar**.</span><span class="sxs-lookup"><span data-stu-id="56098-142">To switch back, select **View Standard recommendations**.</span></span>

![Vista de configuración y recomendaciones en el analizador de configuración](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="56098-144">De forma predeterminada, la columna **grupo de directivas/nombre de configuración** contiene una vista contraída de los distintos tipos de directivas de seguridad y el número de opciones de configuración que necesitan mejorar (si las hay).</span><span class="sxs-lookup"><span data-stu-id="56098-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="56098-145">Los tipos de directivas son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="56098-145">The types of policies are:</span></span>

- <span data-ttu-id="56098-146">**Contra correo electrónico no deseado**</span><span class="sxs-lookup"><span data-stu-id="56098-146">**Anti-spam**</span></span>
- <span data-ttu-id="56098-147">**Contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="56098-147">**Anti-phishing**</span></span>
- <span data-ttu-id="56098-148">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="56098-148">**Anti-malware**</span></span>
- <span data-ttu-id="56098-149">**Datos adjuntos seguros de ATP** (si su suscripción incluye a Microsoft defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="56098-149">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="56098-150">**Vínculos seguros ATP** (si la suscripción incluye Microsoft defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="56098-150">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="56098-151">En la vista predeterminada, todo se contrae.</span><span class="sxs-lookup"><span data-stu-id="56098-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="56098-152">Junto a cada Directiva, hay un resumen de los resultados de la comparación de las directivas (que puede modificar) y la configuración de las directivas correspondientes para los perfiles de protección estándar o estricto (que no se pueden modificar).</span><span class="sxs-lookup"><span data-stu-id="56098-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="56098-153">Verá la siguiente información del perfil de protección que está comparando con:</span><span class="sxs-lookup"><span data-stu-id="56098-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="56098-154">**Verde**: todas las opciones de configuración de todas las directivas existentes son al menos tan seguras como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="56098-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="56098-155">**Ámbar**: un número reducido de configuraciones en las directivas existentes no es tan seguro como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="56098-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="56098-156">**Red**: un número significativo de configuraciones en las directivas existentes no es tan seguro como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="56098-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="56098-157">Esto puede deberse a algunas configuraciones en muchas directivas o muchas opciones de configuración en una directiva.</span><span class="sxs-lookup"><span data-stu-id="56098-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="56098-158">Para comparaciones favorables, verá el texto: **todas las opciones siguen** \<**Standard** or **Strict**\> **recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="56098-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="56098-159">De lo contrario, verá el número de opciones de configuración recomendadas que se deben cambiar.</span><span class="sxs-lookup"><span data-stu-id="56098-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="56098-160">Si amplía el **nombre del grupo o la configuración de directivas**, se muestran todas las directivas y la configuración asociada en cada Directiva específica que requieran atención.</span><span class="sxs-lookup"><span data-stu-id="56098-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="56098-161">O bien, puede expandir un tipo específico de directiva (por ejemplo, **contra el correo no deseado**) para ver sólo la configuración en los tipos de directivas que requieren su atención.</span><span class="sxs-lookup"><span data-stu-id="56098-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="56098-162">Si la comparación no tiene recomendaciones para la mejora (verde), la expansión de la Directiva no revela nada.</span><span class="sxs-lookup"><span data-stu-id="56098-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="56098-163">Si hay algún número de recomendaciones para la mejora (ámbar o rojo), se revela la configuración que requiere atención y se revela la información correspondiente en las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="56098-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="56098-164">El nombre de la configuración que requiere su atención.</span><span class="sxs-lookup"><span data-stu-id="56098-164">The name of the setting that requires your attention.</span></span> <span data-ttu-id="56098-165">Por ejemplo, en la captura de pantalla anterior, se trata del **umbral de correo electrónico masivo** en una directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="56098-165">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="56098-166">**Directiva**: el nombre de la Directiva afectada que contiene la configuración.</span><span class="sxs-lookup"><span data-stu-id="56098-166">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="56098-167">Se **aplica a**: el número de usuarios a los que se aplican las directivas afectadas.</span><span class="sxs-lookup"><span data-stu-id="56098-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="56098-168">**Configuración actual**: el valor actual de la configuración.</span><span class="sxs-lookup"><span data-stu-id="56098-168">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="56098-169">**Última modificación**: la fecha en la que la Directiva se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="56098-169">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="56098-170">**Recomendaciones**: el valor de la configuración en el perfil de protección estándar o estricta.</span><span class="sxs-lookup"><span data-stu-id="56098-170">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="56098-171">Para cambiar el valor de la configuración de la Directiva de manera que se ajuste al valor recomendado en el perfil de protección, haga clic en **adoptar**.</span><span class="sxs-lookup"><span data-stu-id="56098-171">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="56098-172">Si el cambio se realiza correctamente, verá el mensaje: **recomendaciones adoptadas correctamente**.</span><span class="sxs-lookup"><span data-stu-id="56098-172">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="56098-173">Haga clic en **Actualizar** para ver el menor número de recomendaciones y para quitar la configuración específica o la fila de la Directiva de los resultados.</span><span class="sxs-lookup"><span data-stu-id="56098-173">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="56098-174">Ficha historial y análisis de derivación de configuración del analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="56098-174">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="56098-175">Esta pestaña le permite realizar un seguimiento de los cambios realizados en las directivas de seguridad personalizadas.</span><span class="sxs-lookup"><span data-stu-id="56098-175">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="56098-176">De forma predeterminada, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="56098-176">By default, the following information is displayed:</span></span>

- <span data-ttu-id="56098-177">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="56098-177">**Last modified**</span></span>
- <span data-ttu-id="56098-178">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="56098-178">**Modified by**</span></span>
- <span data-ttu-id="56098-179">**Nombre de la configuración**</span><span class="sxs-lookup"><span data-stu-id="56098-179">**Setting Name**</span></span>
- <span data-ttu-id="56098-180">**Directiva**</span><span class="sxs-lookup"><span data-stu-id="56098-180">**Policy**</span></span>
- <span data-ttu-id="56098-181">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="56098-181">**Type**</span></span>

<span data-ttu-id="56098-182">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="56098-182">To filter the results, click **Filter**.</span></span> <span data-ttu-id="56098-183">En el control flotante **filtros** que aparece, puede seleccionar entre los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="56098-183">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="56098-184">**Hora de inicio** y **hora de finalización** (fecha)</span><span class="sxs-lookup"><span data-stu-id="56098-184">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="56098-185">**Protección estándar** o **protección estricta**</span><span class="sxs-lookup"><span data-stu-id="56098-185">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="56098-186">Para exportar los resultados a un archivo. csv, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="56098-186">To export the results to a .csv file, click **Export**.</span></span>

![Vista de historial y análisis de derivación de configuración en el analizador de configuración](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
