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
description: Los administradores pueden aprender a usar el analizador de configuración para buscar y corregir directivas de seguridad que están por debajo de las directivas de seguridad predeterminadas protección estándar y Protección estricta.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 65fd67c93711dc847a25be485b4b016af55e4a31
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205060"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="41a14-103">Analizador de configuración para directivas de protección en EOP y Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="41a14-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41a14-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="41a14-104">**Applies to**</span></span>
- [<span data-ttu-id="41a14-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="41a14-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="41a14-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="41a14-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="41a14-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41a14-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="41a14-108">El analizador de configuración del Centro de seguridad y cumplimiento de & proporciona una ubicación central para buscar y corregir directivas de seguridad en las que la configuración está por debajo de la configuración protección estándar y la configuración de perfil de protección estricta en directivas de seguridad [preestablecidas.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="41a14-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="41a14-109">El analizador de configuración analiza los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="41a14-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="41a14-110">**Directivas de Exchange Online Protection (EOP):** esto incluye organizaciones de Microsoft 365 con buzones de Exchange Online y organizaciones EOP independientes sin buzones de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="41a14-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="41a14-111">[Directivas contra correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="41a14-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="41a14-112">[Directivas antimalware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="41a14-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="41a14-113">[Directivas de EOP contra suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="41a14-113">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="41a14-114">Directivas de **Microsoft Defender para Office 365:** esto incluye organizaciones con suscripciones de complementos de Microsoft 365 E5 o Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="41a14-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="41a14-115">Directivas contra suplantación de identidad en Microsoft Defender para Office 365, que incluyen:</span><span class="sxs-lookup"><span data-stu-id="41a14-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="41a14-116">La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas contra suplantación de identidad de EOP.</span><span class="sxs-lookup"><span data-stu-id="41a14-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="41a14-117">Configuración de suplantación</span><span class="sxs-lookup"><span data-stu-id="41a14-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="41a14-118">Umbrales de suplantación de identidad avanzada</span><span class="sxs-lookup"><span data-stu-id="41a14-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="41a14-119">[Directivas de vínculos seguros](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="41a14-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>

  - <span data-ttu-id="41a14-120">[Directivas de datos adjuntos seguros](set-up-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="41a14-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="41a14-121">Los **valores de** configuración de directiva Estándar y Estricto que se usan como líneas base se describen en Configuración recomendada para EOP y Microsoft Defender para la seguridad de Office  [365](recommended-settings-for-eop-and-office365.md).</span><span class="sxs-lookup"><span data-stu-id="41a14-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="41a14-122">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="41a14-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="41a14-123">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="41a14-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="41a14-124">Para ir directamente a la **página Analizador de configuración,** use <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="41a14-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="41a14-125">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="41a14-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="41a14-126">Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="41a14-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="41a14-127">Para usar el analizador de configuración **y** realizar actualizaciones de directivas de seguridad, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="41a14-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="41a14-128">Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de los grupos de roles **Lector global** o **Lector de** seguridad.</span><span class="sxs-lookup"><span data-stu-id="41a14-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="41a14-129">Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="41a14-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="41a14-130">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41a14-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="41a14-131">Para más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="41a14-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="41a14-132">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="41a14-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="41a14-133">Usar el analizador de configuración en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="41a14-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="41a14-134">En el Centro de & cumplimiento, vaya al Analizador **de** configuración de directivas \>  \> **de administración de amenazas**.</span><span class="sxs-lookup"><span data-stu-id="41a14-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget analizador de configuración en la página Directiva de administración \> de amenazas](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="41a14-136">El analizador de configuración tiene dos pestañas principales:</span><span class="sxs-lookup"><span data-stu-id="41a14-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="41a14-137">**Configuración y recomendaciones:** elija Estándar o Estricto y compare dicha configuración con las directivas de seguridad existentes.</span><span class="sxs-lookup"><span data-stu-id="41a14-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="41a14-138">En los resultados, puede ajustar los valores de la configuración para que suban al mismo nivel que Standard o Strict.</span><span class="sxs-lookup"><span data-stu-id="41a14-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="41a14-139">**Historial y análisis de deriva de configuración:** esta vista le permite realizar un seguimiento de los cambios de directiva con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="41a14-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="41a14-140">Ficha Configuración y recomendaciones en el analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="41a14-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="41a14-141">De forma predeterminada, la pestaña se abre en la comparación con el perfil de protección estándar.</span><span class="sxs-lookup"><span data-stu-id="41a14-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="41a14-142">Puede cambiar a la comparación del perfil de protección estricta haciendo clic en **Ver recomendaciones estrictas**.</span><span class="sxs-lookup"><span data-stu-id="41a14-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="41a14-143">Para volver atrás, seleccione **Ver recomendaciones estándar**.</span><span class="sxs-lookup"><span data-stu-id="41a14-143">To switch back, select **View Standard recommendations**.</span></span>

![Vista Configuración y recomendaciones en el analizador de configuración](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="41a14-145">De forma predeterminada, la columna Nombre de configuración **o** grupo de directivas contiene una vista contraida de los distintos tipos de directivas de seguridad y el número de configuraciones que necesitan mejoras (si las hay).</span><span class="sxs-lookup"><span data-stu-id="41a14-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="41a14-146">Los tipos de directivas son:</span><span class="sxs-lookup"><span data-stu-id="41a14-146">The types of policies are:</span></span>

- <span data-ttu-id="41a14-147">**Contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="41a14-147">**Anti-spam**</span></span>
- <span data-ttu-id="41a14-148">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="41a14-148">**Anti-phishing**</span></span>
- <span data-ttu-id="41a14-149">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="41a14-149">**Anti-malware**</span></span>
- <span data-ttu-id="41a14-150">**Datos adjuntos seguros** de ATP (si la suscripción incluye Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="41a14-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="41a14-151">**Vínculos seguros de ATP** (si su suscripción incluye Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="41a14-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="41a14-152">En la vista predeterminada, todo está contraído.</span><span class="sxs-lookup"><span data-stu-id="41a14-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="41a14-153">Junto a cada directiva, hay un resumen de los resultados de comparación de las directivas (que puede modificar) y la configuración de las directivas correspondientes para los perfiles de protección estándar o estricto (que no puede modificar).</span><span class="sxs-lookup"><span data-stu-id="41a14-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="41a14-154">Verá la siguiente información para el perfil de protección con el que está comparando:</span><span class="sxs-lookup"><span data-stu-id="41a14-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="41a14-155">**Verde:** todas las configuraciones de todas las directivas existentes son al menos tan seguras como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="41a14-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="41a14-156">**Ámbar:** un pequeño número de configuraciones en las directivas existentes no son tan seguras como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="41a14-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="41a14-157">**Rojo:** un número significativo de configuraciones en las directivas existentes no son tan seguras como el perfil de protección.</span><span class="sxs-lookup"><span data-stu-id="41a14-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="41a14-158">Esta puede ser una configuración en muchas directivas o en muchas configuraciones de una directiva.</span><span class="sxs-lookup"><span data-stu-id="41a14-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="41a14-159">Para las comparaciones favorables, verá el texto: **Todas las opciones de configuración siguen las** \<**Standard** or **Strict**\> **recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="41a14-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="41a14-160">De lo contrario, verá el número de opciones recomendadas para cambiar.</span><span class="sxs-lookup"><span data-stu-id="41a14-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="41a14-161">Si expande **Grupo de directivas o nombre de** configuración, se revelan todas las directivas y la configuración asociada en cada directiva específica que requiera atención.</span><span class="sxs-lookup"><span data-stu-id="41a14-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="41a14-162">O bien, puede expandir un tipo específico de directiva (por ejemplo, **Contra** correo no deseado) para ver solo esa configuración en esos tipos de directivas que requieren su atención.</span><span class="sxs-lookup"><span data-stu-id="41a14-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="41a14-163">Si la comparación no tiene recomendaciones de mejora (verde), expandir la directiva no revela nada.</span><span class="sxs-lookup"><span data-stu-id="41a14-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="41a14-164">Si hay un número de recomendaciones para mejorar (ámbar o rojo), se revelan las configuraciones que requieren atención y la información correspondiente se muestra en las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="41a14-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="41a14-165">El nombre de la configuración que requiere su atención.</span><span class="sxs-lookup"><span data-stu-id="41a14-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="41a14-166">Por ejemplo, en la captura de pantalla anterior, es el umbral **de correo electrónico** masivo en una directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="41a14-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="41a14-167">**Directiva:** nombre de la directiva afectada que contiene la configuración.</span><span class="sxs-lookup"><span data-stu-id="41a14-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="41a14-168">**Se aplica a**: el número de usuarios a los que se aplican las directivas afectadas.</span><span class="sxs-lookup"><span data-stu-id="41a14-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="41a14-169">**Configuración actual:** el valor actual de la configuración.</span><span class="sxs-lookup"><span data-stu-id="41a14-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="41a14-170">**Last modified**: The date that the policy was last modified.</span><span class="sxs-lookup"><span data-stu-id="41a14-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="41a14-171">**Recomendaciones:** el valor de la configuración en el perfil de protección estándar o estricta.</span><span class="sxs-lookup"><span data-stu-id="41a14-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="41a14-172">Para cambiar el valor de la configuración de la directiva para que coincida con el valor recomendado en el perfil de protección, haga clic en **Adoptar**.</span><span class="sxs-lookup"><span data-stu-id="41a14-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="41a14-173">Si el cambio se realiza correctamente, verá el mensaje: **Recomendaciones adoptadas correctamente.**</span><span class="sxs-lookup"><span data-stu-id="41a14-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="41a14-174">Haga **clic en** Actualizar para ver el número reducido de recomendaciones y la eliminación de la fila de configuración o directiva específica de los resultados.</span><span class="sxs-lookup"><span data-stu-id="41a14-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="41a14-175">Ficha Historial y análisis de deriva de configuración en el analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="41a14-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="41a14-176">Esta pestaña le permite realizar un seguimiento de los cambios realizados en las directivas de seguridad personalizadas.</span><span class="sxs-lookup"><span data-stu-id="41a14-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="41a14-177">De forma predeterminada, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="41a14-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="41a14-178">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="41a14-178">**Last modified**</span></span>
- <span data-ttu-id="41a14-179">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="41a14-179">**Modified by**</span></span>
- <span data-ttu-id="41a14-180">**Nombre de configuración**</span><span class="sxs-lookup"><span data-stu-id="41a14-180">**Setting Name**</span></span>
- <span data-ttu-id="41a14-181">**Directiva**</span><span class="sxs-lookup"><span data-stu-id="41a14-181">**Policy**</span></span>
- <span data-ttu-id="41a14-182">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41a14-182">**Type**</span></span>

<span data-ttu-id="41a14-183">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="41a14-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="41a14-184">En el **menú** desplegable Filtros que aparece, puede seleccionar entre los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="41a14-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="41a14-185">**Hora de inicio** y **hora de finalización** (fecha)</span><span class="sxs-lookup"><span data-stu-id="41a14-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="41a14-186">**Protección estándar o** **protección estricta**</span><span class="sxs-lookup"><span data-stu-id="41a14-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="41a14-187">Para exportar los resultados a un archivo .csv, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="41a14-187">To export the results to a .csv file, click **Export**.</span></span>

![Análisis de deriva de configuración y vista de historial en el analizador de configuración](../../media/configuration-analyzer-configuration-drift-analysis-view.png)