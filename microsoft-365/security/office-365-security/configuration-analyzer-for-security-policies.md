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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar el analizador de configuración para buscar y corregir directivas de seguridad que están por debajo de las directivas de seguridad preestablecidas Protección estándar y Protección estricta.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 04027e78a2683c6c33954bb548c502497c5e8323
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029483"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="7ceb1-103">Analizador de configuración para directivas de protección en EOP y Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7ceb1-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7ceb1-104">El analizador de configuración del Centro de seguridad y cumplimiento de & proporciona una ubicación central para buscar y corregir directivas de seguridad en las que la configuración se encuentra por debajo de la configuración de protección estándar y de perfil de protección estricta en directivas de seguridad [preestablecidas.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7ceb1-104">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="7ceb1-105">El analizador de configuración analiza los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-105">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="7ceb1-106">**Directivas de Exchange Online Protection (EOP):** esto incluye organizaciones de Microsoft 365 con buzones de Exchange Online y organizaciones EOP independientes sin buzones de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-106">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="7ceb1-107">[Directivas contra correo no deseado.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7ceb1-107">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="7ceb1-108">[Directivas antimalware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7ceb1-108">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="7ceb1-109">[Directivas de protección contra suplantación de identidad de EOP.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="7ceb1-109">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="7ceb1-110">Directivas de Microsoft Defender para **Office 365:** esto incluye las organizaciones con suscripciones de complemento de Microsoft 365 E5 o Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-110">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="7ceb1-111">Directivas contra la suplantación de identidad en Microsoft Defender para Office 365, que incluyen:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-111">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="7ceb1-112">La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas contra la suplantación de identidad de EOP.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-112">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="7ceb1-113">Configuración de suplantación</span><span class="sxs-lookup"><span data-stu-id="7ceb1-113">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="7ceb1-114">Umbrales avanzados de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="7ceb1-114">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="7ceb1-115">[Directivas de vínculos seguros.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7ceb1-115">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="7ceb1-116">[Directivas de datos adjuntos seguros.](set-up-atp-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7ceb1-116">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="7ceb1-117">Los **valores de** configuración **de** directiva Estándar y Estricto que se usan como líneas base se describen en Configuración recomendada para EOP y Microsoft Defender para la seguridad de [Office 365.](recommended-settings-for-eop-and-office365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="7ceb1-117">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7ceb1-118">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="7ceb1-118">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7ceb1-119">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-119">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7ceb1-120">Para ir directamente a la **página Analizador de configuración,** use <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="7ceb1-120">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="7ceb1-121">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7ceb1-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7ceb1-122">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="7ceb1-123">Para usar el analizador de configuración **y** realizar actualizaciones de  las directivas de seguridad, debe ser miembro de los grupos de roles Administración de la organización o **Administrador de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-123">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="7ceb1-124">Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-124">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="7ceb1-125">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7ceb1-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="7ceb1-126">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7ceb1-127">Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="7ceb1-127">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  > 
  > - <span data-ttu-id="7ceb1-128">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="7ceb1-129">Usar el analizador de configuración en el Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="7ceb1-129">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="7ceb1-130">En el Centro de & cumplimiento, vaya al Analizador **de** configuración de \> **directivas** de administración \> **de amenazas.**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-130">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget Analizador de configuración en la página Directiva de \> administración de amenazas](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="7ceb1-132">El analizador de configuración tiene dos pestañas principales:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-132">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="7ceb1-133">**Configuración y recomendaciones:** elige Estándar o Estricto y compara dicha configuración con las directivas de seguridad existentes.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-133">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="7ceb1-134">En los resultados, puedes ajustar los valores de la configuración para que suban al mismo nivel que Estándar o Estricto.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-134">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="7ceb1-135">**Historial y análisis de deriva de** configuración: esta vista le permite realizar un seguimiento de los cambios de directiva con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-135">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="7ceb1-136">Ficha Configuración y recomendaciones en el analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="7ceb1-136">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="7ceb1-137">De forma predeterminada, la pestaña se abre en la comparación con el perfil de protección estándar.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-137">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="7ceb1-138">Puede cambiar a la comparación del perfil de protección Estricto haciendo clic **en Ver estrictas recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-138">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="7ceb1-139">Para volver atrás, seleccione **Ver recomendaciones estándar.**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-139">To switch back, select **View Standard recommendations**.</span></span>

![Vista Configuración y recomendaciones en el analizador de configuración](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="7ceb1-141">De forma predeterminada, la columna Nombre de grupo **o** configuración de directiva contiene una vista contraida de los distintos tipos de directivas de seguridad y el número de configuraciones que deben mejorarse (si las hay).</span><span class="sxs-lookup"><span data-stu-id="7ceb1-141">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="7ceb1-142">Los tipos de directivas son:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-142">The types of policies are:</span></span>

- <span data-ttu-id="7ceb1-143">**Contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-143">**Anti-spam**</span></span>
- <span data-ttu-id="7ceb1-144">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-144">**Anti-phishing**</span></span>
- <span data-ttu-id="7ceb1-145">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-145">**Anti-malware**</span></span>
- <span data-ttu-id="7ceb1-146">**Datos adjuntos seguros** de ATP (si su suscripción incluye Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="7ceb1-146">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="7ceb1-147">**Vínculos seguros de ATP** (si su suscripción incluye Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="7ceb1-147">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="7ceb1-148">En la vista predeterminada, todo está contraído.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-148">In the default view, everything is collapsed.</span></span> <span data-ttu-id="7ceb1-149">Junto a cada directiva, hay un resumen de los resultados de comparación de las directivas (que puedes modificar) y la configuración de las directivas correspondientes para los perfiles de protección Estándar o Estricto (que no puedes modificar).</span><span class="sxs-lookup"><span data-stu-id="7ceb1-149">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="7ceb1-150">Verá la siguiente información para el perfil de protección con el que está comparando:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-150">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="7ceb1-151">**Verde:** todas las configuraciones de todas las directivas existentes son al menos tan seguras como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-151">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="7ceb1-152">**Ámbar:** un número reducido de configuraciones en las directivas existentes no son tan seguras como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-152">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="7ceb1-153">**Rojo:** un número significativo de configuraciones en las directivas existentes no son tan seguras como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-153">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="7ceb1-154">Puede ser unas pocas opciones de configuración en muchas directivas o muchas opciones de configuración en una directiva.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-154">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="7ceb1-155">Para comparaciones favorables, verá el texto: Todas **las opciones de configuración siguen las** \<**Standard** or **Strict**\> **recomendaciones.**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-155">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="7ceb1-156">De lo contrario, verás el número de opciones de configuración recomendadas para cambiar.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-156">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="7ceb1-157">Si expandes el **nombre de configuración o** grupo de directivas, se revelan todas las directivas y la configuración asociada en cada directiva específica que requiera atención.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-157">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="7ceb1-158">O bien, puede expandir un tipo específico de directiva (por **ejemplo,** Contra correo electrónico no deseado) para ver solo la configuración de esos tipos de directivas que requieren su atención.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-158">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="7ceb1-159">Si la comparación no tiene recomendaciones para la mejora (verde), expandir la directiva no revela nada.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-159">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="7ceb1-160">Si hay alguna cantidad de recomendaciones para la mejora (ámbar o rojo), se muestran las configuraciones que requieren atención y la información correspondiente se muestra en las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-160">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="7ceb1-161">El nombre de la configuración que requiere tu atención.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-161">The name of the setting that requires your attention.</span></span> <span data-ttu-id="7ceb1-162">Por ejemplo, en la captura de pantalla anterior, es el umbral **de correo electrónico** masivo en una directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-162">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="7ceb1-163">**Directiva:** nombre de la directiva afectada que contiene la configuración.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-163">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="7ceb1-164">**Se aplica a:** el número de usuarios a los que se aplican las directivas afectadas.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-164">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="7ceb1-165">**Configuración actual:** el valor actual de la configuración.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-165">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="7ceb1-166">**Última modificación:** la fecha en que se modificó la directiva por última vez.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-166">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="7ceb1-167">**Recomendaciones:** el valor de la configuración en el perfil de protección Estándar o Estricto.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-167">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="7ceb1-168">Para cambiar el valor de la configuración de la directiva para que coincida con el valor recomendado en el perfil de protección, haga clic **en Adoptar**.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-168">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="7ceb1-169">Si el cambio se realiza correctamente, verá el mensaje: **Recomendaciones aprobadas correctamente.**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-169">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="7ceb1-170">Haga **clic en** Actualizar para ver el número reducido de recomendaciones y la eliminación de la fila de configuración o directiva específica de los resultados.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-170">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="7ceb1-171">Análisis de deriva de configuración e ficha historial en el analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="7ceb1-171">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="7ceb1-172">Esta pestaña le permite realizar un seguimiento de los cambios realizados en las directivas de seguridad personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-172">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="7ceb1-173">De forma predeterminada, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-173">By default, the following information is displayed:</span></span>

- <span data-ttu-id="7ceb1-174">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-174">**Last modified**</span></span>
- <span data-ttu-id="7ceb1-175">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-175">**Modified by**</span></span>
- <span data-ttu-id="7ceb1-176">**Nombre de configuración**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-176">**Setting Name**</span></span>
- <span data-ttu-id="7ceb1-177">**Directiva**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-177">**Policy**</span></span>
- <span data-ttu-id="7ceb1-178">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-178">**Type**</span></span>

<span data-ttu-id="7ceb1-179">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-179">To filter the results, click **Filter**.</span></span> <span data-ttu-id="7ceb1-180">En el **menú** desplegable Filtros que aparece, puede seleccionar entre los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="7ceb1-180">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="7ceb1-181">**Hora de inicio** y **hora de finalización** (fecha)</span><span class="sxs-lookup"><span data-stu-id="7ceb1-181">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="7ceb1-182">**Protección estándar o** **protección estricta**</span><span class="sxs-lookup"><span data-stu-id="7ceb1-182">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="7ceb1-183">Para exportar los resultados a un archivo .csv, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="7ceb1-183">To export the results to a .csv file, click **Export**.</span></span>

![Análisis de deriva de configuración y vista de historial en el analizador de configuración](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
