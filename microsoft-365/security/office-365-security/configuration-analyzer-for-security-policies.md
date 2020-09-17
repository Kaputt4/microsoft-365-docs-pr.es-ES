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
ms.openlocfilehash: 022f11013ef49c65b1f94fea7a3872233ff1ab14
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949483"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="e6884-103">Analizador de configuración para directivas de protección en EOP y Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="e6884-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="e6884-104">Las características descritas en este tema están en versión preliminar, no están disponibles en todas las organizaciones y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="e6884-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="e6884-105">Para obtener información sobre la programación de versiones, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="e6884-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="e6884-106">El analizador de configuración del centro de seguridad & cumplimiento ofrece una ubicación central para buscar y corregir directivas de seguridad en las que la configuración está por debajo de la configuración de Perfil de protección estándar y protección estricta en [directivas de seguridad predeterminadas](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e6884-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="e6884-107">El analizador de configuración analiza los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="e6884-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="e6884-108">**Directivas de Exchange Online Protection (EOP)**: Esto incluye a Microsoft 365 organizaciones con buzones de Exchange Online y organizaciones independientes de EOP sin buzones de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="e6884-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="e6884-109">[Directivas contra correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e6884-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="e6884-110">[Directivas antimalware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e6884-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="e6884-111">[Directivas de protección contra suplantación de EOP](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="e6884-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="e6884-112">**Directivas de protección contra amenazas avanzada (ATP) de Office 365**: Esto incluye a las organizaciones con suscripciones de complementos de ATP de Microsoft 365 E5 u Office 365:</span><span class="sxs-lookup"><span data-stu-id="e6884-112">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="e6884-113">Directivas antiphishing de ATP, que incluyen:</span><span class="sxs-lookup"><span data-stu-id="e6884-113">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="e6884-114">La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas de protección contra suplantación de EOP.</span><span class="sxs-lookup"><span data-stu-id="e6884-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="e6884-115">Configuración de suplantación</span><span class="sxs-lookup"><span data-stu-id="e6884-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="e6884-116">Umbrales de suplantación de identidad avanzada</span><span class="sxs-lookup"><span data-stu-id="e6884-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="e6884-117">[Directivas de vínculos a prueba](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)de errores.</span><span class="sxs-lookup"><span data-stu-id="e6884-117">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="e6884-118">[Directivas de datos adjuntos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="e6884-118">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="e6884-119">Los valores de configuración **estándar** y **estricta** de la Directiva que se usan como líneas de base se describen en [configuración recomendada para EOP y Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="e6884-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e6884-120">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="e6884-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e6884-121">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e6884-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e6884-122">Para ir directamente a la página del **analizador de configuración** , use <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="e6884-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="e6884-123">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e6884-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e6884-124">Debe tener permisos asignados para poder realizar los procedimientos descritos en este artículo:</span><span class="sxs-lookup"><span data-stu-id="e6884-124">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="e6884-125">Para usar el analizador de configuración **y** realizar actualizaciones en las directivas de seguridad, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="e6884-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e6884-126">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e6884-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e6884-127">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="e6884-127">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="e6884-128">Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="e6884-128">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e6884-129">**Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e6884-129">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e6884-130">**Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="e6884-130">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="e6884-131">Uso del analizador de configuración en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="e6884-131">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="e6884-132">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **Configuration Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="e6884-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget analizador de configuración en la página Directiva de administración de amenazas \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="e6884-134">El analizador de configuración tiene dos pestañas principales:</span><span class="sxs-lookup"><span data-stu-id="e6884-134">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="e6884-135">**Configuración y recomendaciones**: elige estándar o estricto y compara esa configuración con las directivas de seguridad existentes.</span><span class="sxs-lookup"><span data-stu-id="e6884-135">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="e6884-136">En los resultados, puede ajustar los valores de la configuración para que aparezcan en el mismo nivel que el estándar o estricto.</span><span class="sxs-lookup"><span data-stu-id="e6884-136">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="e6884-137">**Análisis e historial de la fase de configuración**: esta vista permite realizar un seguimiento de los cambios de directiva con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="e6884-137">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="e6884-138">Configuración y ficha recomendaciones en el analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="e6884-138">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="e6884-139">De forma predeterminada, la pestaña se abre en la comparación con el perfil de protección estándar.</span><span class="sxs-lookup"><span data-stu-id="e6884-139">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="e6884-140">Puede cambiar a la comparación de un perfil de protección estricto haciendo clic en **Ver recomendaciones estrictas**.</span><span class="sxs-lookup"><span data-stu-id="e6884-140">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="e6884-141">Para cambiar de nuevo, seleccione **Ver recomendaciones estándar**.</span><span class="sxs-lookup"><span data-stu-id="e6884-141">To switch back, select **View Standard recommendations**.</span></span>

![Vista de configuración y recomendaciones en el analizador de configuración](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="e6884-143">De forma predeterminada, la columna **grupo de directivas/nombre de configuración** contiene una vista contraída de los distintos tipos de directivas de seguridad y el número de opciones de configuración que necesitan mejorar (si las hay).</span><span class="sxs-lookup"><span data-stu-id="e6884-143">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="e6884-144">Los tipos de directivas son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6884-144">The types of policies are:</span></span>

- <span data-ttu-id="e6884-145">**Contra correo electrónico no deseado**</span><span class="sxs-lookup"><span data-stu-id="e6884-145">**Anti-spam**</span></span>
- <span data-ttu-id="e6884-146">**Contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="e6884-146">**Anti-phishing**</span></span>
- <span data-ttu-id="e6884-147">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="e6884-147">**Anti-malware**</span></span>
- <span data-ttu-id="e6884-148">**Datos adjuntos seguros de ATP** (si la suscripción incluye ATP)</span><span class="sxs-lookup"><span data-stu-id="e6884-148">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="e6884-149">**Vínculos seguros ATP** (si la suscripción incluye ATP)</span><span class="sxs-lookup"><span data-stu-id="e6884-149">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="e6884-150">En la vista predeterminada, todo se contrae.</span><span class="sxs-lookup"><span data-stu-id="e6884-150">In the default view, everything is collapsed.</span></span> <span data-ttu-id="e6884-151">Junto a cada Directiva, hay un resumen de los resultados de la comparación de las directivas (que puede modificar) y la configuración de las directivas correspondientes para los perfiles de protección estándar o estricto (que no se pueden modificar).</span><span class="sxs-lookup"><span data-stu-id="e6884-151">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="e6884-152">Verá la siguiente información del perfil de protección que está comparando con:</span><span class="sxs-lookup"><span data-stu-id="e6884-152">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="e6884-153">**Verde**: todas las opciones de configuración de todas las directivas existentes son al menos tan seguras como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="e6884-153">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="e6884-154">**Ámbar**: un número reducido de configuraciones en las directivas existentes no es tan seguro como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="e6884-154">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="e6884-155">**Red**: un número significativo de configuraciones en las directivas existentes no es tan seguro como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="e6884-155">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="e6884-156">Esto puede deberse a algunas configuraciones en muchas directivas o muchas opciones de configuración en una directiva.</span><span class="sxs-lookup"><span data-stu-id="e6884-156">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="e6884-157">Para comparaciones favorables, verá el texto: **todas las opciones siguen** \<**Standard** or **Strict**\> **recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="e6884-157">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="e6884-158">De lo contrario, verá el número de opciones de configuración recomendadas que se deben cambiar.</span><span class="sxs-lookup"><span data-stu-id="e6884-158">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="e6884-159">Si amplía el **nombre del grupo o la configuración de directivas**, se muestran todas las directivas y la configuración asociada en cada Directiva específica que requieran atención.</span><span class="sxs-lookup"><span data-stu-id="e6884-159">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="e6884-160">O bien, puede expandir un tipo específico de directiva (por ejemplo, **contra el correo no deseado**) para ver sólo la configuración en los tipos de directivas que requieren su atención.</span><span class="sxs-lookup"><span data-stu-id="e6884-160">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="e6884-161">Si la comparación no tiene recomendaciones para la mejora (verde), la expansión de la Directiva no revela nada.</span><span class="sxs-lookup"><span data-stu-id="e6884-161">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="e6884-162">Si hay algún número de recomendaciones para la mejora (ámbar o rojo), se revela la configuración que requiere atención y se revela la información correspondiente en las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="e6884-162">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="e6884-163">El nombre de la configuración que requiere su atención.</span><span class="sxs-lookup"><span data-stu-id="e6884-163">The name of the setting that requires your attention.</span></span> <span data-ttu-id="e6884-164">Por ejemplo, en la captura de pantalla anterior, se trata del **umbral de correo electrónico masivo** en una directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="e6884-164">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="e6884-165">**Directiva**: el nombre de la Directiva afectada que contiene la configuración.</span><span class="sxs-lookup"><span data-stu-id="e6884-165">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="e6884-166">Se **aplica a**: el número de usuarios a los que se aplican las directivas afectadas.</span><span class="sxs-lookup"><span data-stu-id="e6884-166">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="e6884-167">**Configuración actual**: el valor actual de la configuración.</span><span class="sxs-lookup"><span data-stu-id="e6884-167">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="e6884-168">**Última modificación**: la fecha en la que la Directiva se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="e6884-168">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="e6884-169">**Recomendaciones**: el valor de la configuración en el perfil de protección estándar o estricta.</span><span class="sxs-lookup"><span data-stu-id="e6884-169">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="e6884-170">Para cambiar el valor de la configuración de la Directiva de manera que se ajuste al valor recomendado en el perfil de protección, haga clic en **adoptar**.</span><span class="sxs-lookup"><span data-stu-id="e6884-170">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="e6884-171">Si el cambio se realiza correctamente, verá el mensaje: **recomendaciones adoptadas correctamente**.</span><span class="sxs-lookup"><span data-stu-id="e6884-171">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="e6884-172">Haga clic en **Actualizar** para ver el menor número de recomendaciones y para quitar la configuración específica o la fila de la Directiva de los resultados.</span><span class="sxs-lookup"><span data-stu-id="e6884-172">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="e6884-173">Ficha historial y análisis de derivación de configuración del analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="e6884-173">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="e6884-174">Esta pestaña le permite realizar un seguimiento de los cambios realizados en las directivas de seguridad personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e6884-174">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="e6884-175">De forma predeterminada, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="e6884-175">By default, the following information is displayed:</span></span>

- <span data-ttu-id="e6884-176">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="e6884-176">**Last modified**</span></span>
- <span data-ttu-id="e6884-177">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="e6884-177">**Modified by**</span></span>
- <span data-ttu-id="e6884-178">**Nombre de la configuración**</span><span class="sxs-lookup"><span data-stu-id="e6884-178">**Setting Name**</span></span>
- <span data-ttu-id="e6884-179">**Directiva**</span><span class="sxs-lookup"><span data-stu-id="e6884-179">**Policy**</span></span>
- <span data-ttu-id="e6884-180">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e6884-180">**Type**</span></span>

<span data-ttu-id="e6884-181">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="e6884-181">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e6884-182">En el control flotante **filtros** que aparece, puede seleccionar entre los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6884-182">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="e6884-183">**Hora de inicio** y **hora de finalización** (fecha)</span><span class="sxs-lookup"><span data-stu-id="e6884-183">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="e6884-184">**Protección estándar** o **protección estricta**</span><span class="sxs-lookup"><span data-stu-id="e6884-184">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="e6884-185">Para exportar los resultados a un archivo. csv, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="e6884-185">To export the results to a .csv file, click **Export**.</span></span>

![Vista de historial y análisis de derivación de configuración en el analizador de configuración](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
