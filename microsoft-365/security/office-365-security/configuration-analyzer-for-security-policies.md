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
description: Los administradores pueden aprender a usar el analizador de configuración para buscar y corregir directivas de seguridad que contengan opciones de configuración inferiores a las directivas de seguridad de protección estándar y protección estricta.
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825778"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="447a2-103">Analizador de configuración para directivas de protección en EOP y Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="447a2-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="447a2-104">Las características descritas en este tema están en versión preliminar, no están disponibles en todas las organizaciones y están sujetas a cambios.</span><span class="sxs-lookup"><span data-stu-id="447a2-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="447a2-105">El analizador de configuración del centro de seguridad & cumplimiento ofrece una ubicación central para buscar y corregir cualquiera de las directivas de seguridad que contengan valores inferiores a la configuración de Perfil de protección estándar y protección estricta en [directivas de seguridad predeterminadas](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="447a2-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="447a2-106">El analizador de configuración analiza los siguientes tipos de directivas:</span><span class="sxs-lookup"><span data-stu-id="447a2-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="447a2-107">**Directivas de Exchange Online Protection (EOP)**: Esto incluye a Microsoft 365 organizaciones con buzones de Exchange Online y organizaciones independientes de EOP sin buzones de Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="447a2-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="447a2-108">[Directivas contra correo no deseado](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="447a2-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="447a2-109">[Directivas antimalware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="447a2-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="447a2-110">[Directivas de protección contra suplantación de EOP](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="447a2-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="447a2-111">**Directivas de protección contra amenazas avanzada (ATP) de Office 365**: Esto incluye a las organizaciones con suscripciones de complementos de ATP de Microsoft 365 E5 u Office 365:</span><span class="sxs-lookup"><span data-stu-id="447a2-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="447a2-112">Directivas antiphishing de ATP, que incluyen:</span><span class="sxs-lookup"><span data-stu-id="447a2-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="447a2-113">La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas de protección contra suplantación de EOP.</span><span class="sxs-lookup"><span data-stu-id="447a2-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="447a2-114">Configuración de suplantación</span><span class="sxs-lookup"><span data-stu-id="447a2-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="447a2-115">Umbrales de suplantación de identidad avanzada</span><span class="sxs-lookup"><span data-stu-id="447a2-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="447a2-116">[Directivas de vínculos a prueba](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)de errores.</span><span class="sxs-lookup"><span data-stu-id="447a2-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="447a2-117">[Directivas de datos adjuntos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="447a2-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="447a2-118">Los valores de configuración **estándar** y **estricta** de la Directiva que se usan como líneas de base se describen en [configuración recomendada para EOP y Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="447a2-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="447a2-119">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="447a2-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="447a2-120">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="447a2-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="447a2-121">Para ir directamente a la página del **analizador de configuración** , use <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="447a2-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="447a2-122">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="447a2-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="447a2-123">Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:</span><span class="sxs-lookup"><span data-stu-id="447a2-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="447a2-124">Para usar el analizador de configuración **y** realizar actualizaciones en las directivas de seguridad, debe pertenecer a uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="447a2-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="447a2-125">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="447a2-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="447a2-126">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="447a2-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="447a2-127">Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="447a2-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="447a2-128">**Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="447a2-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="447a2-129">**Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="447a2-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="447a2-130">Uso del analizador de configuración en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="447a2-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="447a2-131">En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **Configuration Analyzer**.</span><span class="sxs-lookup"><span data-stu-id="447a2-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget analizador de configuración en la página Directiva de administración de amenazas \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="447a2-133">El analizador de configuración tiene dos pestañas principales:</span><span class="sxs-lookup"><span data-stu-id="447a2-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="447a2-134">**Configuración y recomendaciones**: elige estándar o estricto y compara esa configuración con las directivas de seguridad existentes.</span><span class="sxs-lookup"><span data-stu-id="447a2-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="447a2-135">En los resultados, puede ajustar los valores de la configuración para que aparezcan en el mismo nivel que el estándar o estricto.</span><span class="sxs-lookup"><span data-stu-id="447a2-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="447a2-136">**Análisis e historial de desplazamiento de configuración**: esta vista permite realizar un seguimiento de los cambios realizados en las directivas en función de los resultados del analizador de configuración a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="447a2-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="447a2-137">Configuración y ficha recomendaciones en el analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="447a2-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="447a2-138">De forma predeterminada, la pestaña se abre en la comparación con el perfil de protección estándar.</span><span class="sxs-lookup"><span data-stu-id="447a2-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="447a2-139">Puede cambiar a la comparación de un perfil de protección estricto haciendo clic en **Ver recomendaciones estrictas**.</span><span class="sxs-lookup"><span data-stu-id="447a2-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="447a2-140">Para cambiar de nuevo, seleccione **Ver recomendaciones estándar**.</span><span class="sxs-lookup"><span data-stu-id="447a2-140">To switch back, select **View Standard recommendations**.</span></span>

![Vista de configuración y recomendaciones en el analizador de configuración](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="447a2-142">De forma predeterminada, la columna de **nombre de configuración/grupo de directivas** contiene una vista contraída de los diferentes tipos de directivas de seguridad y el número de configuraciones de las directivas que necesitan mejorar (si las hay).</span><span class="sxs-lookup"><span data-stu-id="447a2-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="447a2-143">Los tipos de directivas son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="447a2-143">The types of policies are:</span></span>

- <span data-ttu-id="447a2-144">**Contra correo electrónico no deseado**</span><span class="sxs-lookup"><span data-stu-id="447a2-144">**Anti-spam**</span></span>
- <span data-ttu-id="447a2-145">**Contra la suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="447a2-145">**Anti-phishing**</span></span>
- <span data-ttu-id="447a2-146">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="447a2-146">**Anti-malware**</span></span>
- <span data-ttu-id="447a2-147">**Datos adjuntos seguros de ATP** (si la suscripción incluye ATP)</span><span class="sxs-lookup"><span data-stu-id="447a2-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="447a2-148">**Vínculos seguros ATP** (si la suscripción incluye ATP)</span><span class="sxs-lookup"><span data-stu-id="447a2-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="447a2-149">En la vista predeterminada, todo se contrae.</span><span class="sxs-lookup"><span data-stu-id="447a2-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="447a2-150">Junto a cada Directiva, se muestra un resumen de los resultados de la comparación de las directivas (que puede modificar) y la configuración de las directivas correspondientes para los perfiles de protección estándar o estricto (que no se pueden modificar).</span><span class="sxs-lookup"><span data-stu-id="447a2-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="447a2-151">Verá la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="447a2-151">You'll see the following information:</span></span>

- <span data-ttu-id="447a2-152">**Verde**: todas las opciones de configuración de todas las directivas existentes son al menos tan seguras como el perfil de protección al que se realiza la comparación.</span><span class="sxs-lookup"><span data-stu-id="447a2-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="447a2-153">**Ámbar**: un número reducido de configuraciones en las directivas existentes no es tan seguro como el perfil de protección al que se realiza la comparación.</span><span class="sxs-lookup"><span data-stu-id="447a2-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="447a2-154">**Rojo**: un número significativo de configuraciones en las directivas existentes no es tan seguro como el perfil de protección al que se realiza la comparación.</span><span class="sxs-lookup"><span data-stu-id="447a2-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="447a2-155">Esto puede deberse a algunas configuraciones en muchas directivas o muchas opciones de configuración en una directiva.</span><span class="sxs-lookup"><span data-stu-id="447a2-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="447a2-156">Para comparaciones favorables, verá el texto: **todas las opciones siguen** \<**Standard** or **Strict**\> **recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="447a2-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="447a2-157">De lo contrario, verá el número de opciones de configuración recomendadas que se deben cambiar.</span><span class="sxs-lookup"><span data-stu-id="447a2-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="447a2-158">Si amplía el **nombre del grupo o la configuración de directivas**, se muestran todas las directivas y la configuración asociada en cada Directiva específica que requieran atención.</span><span class="sxs-lookup"><span data-stu-id="447a2-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="447a2-159">O bien, puede expandir un tipo específico de directiva (por ejemplo, **contra el correo no deseado**) para ver sólo la configuración en los tipos de directivas que requieren su atención.</span><span class="sxs-lookup"><span data-stu-id="447a2-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="447a2-160">Si la comparación no tiene recomendaciones para la mejora (verde), la expansión de la Directiva no revela nada.</span><span class="sxs-lookup"><span data-stu-id="447a2-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="447a2-161">Si hay algún número de recomendaciones para la mejora (ámbar o rojo), se revela la configuración que requiere atención y se revela la información correspondiente en las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="447a2-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="447a2-162">El nombre de la configuración que requiere su atención.</span><span class="sxs-lookup"><span data-stu-id="447a2-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="447a2-163">Por ejemplo, en la captura de pantalla anterior, se trata del **umbral de correo electrónico masivo** en una directiva contra correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="447a2-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="447a2-164">**Directiva**: el nombre de la Directiva afectada que contiene la configuración.</span><span class="sxs-lookup"><span data-stu-id="447a2-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="447a2-165">Se **aplica a**: el número de usuarios a los que se aplican las directivas afectadas.</span><span class="sxs-lookup"><span data-stu-id="447a2-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="447a2-166">**Configuración actual**: el valor actual de la configuración.</span><span class="sxs-lookup"><span data-stu-id="447a2-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="447a2-167">**Última modificación**: la fecha en la que la Directiva se modificó por última vez.</span><span class="sxs-lookup"><span data-stu-id="447a2-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="447a2-168">**Recomendaciones**: el valor de la configuración en el perfil de protección estándar o estricta.</span><span class="sxs-lookup"><span data-stu-id="447a2-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="447a2-169">Para cambiar el valor de la configuración de la Directiva de manera que se ajuste al valor recomendado en el perfil de protección, haga clic en **adoptar**.</span><span class="sxs-lookup"><span data-stu-id="447a2-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="447a2-170">Si el cambio se realiza correctamente, verá el mensaje: **recomendaciones adoptadas correctamente**.</span><span class="sxs-lookup"><span data-stu-id="447a2-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="447a2-171">Haga clic en **Actualizar** para ver el menor número de recomendaciones y para quitar la configuración específica o la fila de la Directiva de los resultados.</span><span class="sxs-lookup"><span data-stu-id="447a2-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="447a2-172">Ficha historial y análisis de derivación de configuración del analizador de configuración</span><span class="sxs-lookup"><span data-stu-id="447a2-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="447a2-173">Esta ficha permite realizar un seguimiento de los cambios realizados en las directivas de seguridad personalizadas en función de la información del analizador de seguridad.</span><span class="sxs-lookup"><span data-stu-id="447a2-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="447a2-174">De forma predeterminada, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="447a2-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="447a2-175">**Última modificación**</span><span class="sxs-lookup"><span data-stu-id="447a2-175">**Last modified**</span></span>
- <span data-ttu-id="447a2-176">**Modificado por**</span><span class="sxs-lookup"><span data-stu-id="447a2-176">**Modified by**</span></span>
- <span data-ttu-id="447a2-177">**Nombre de la configuración**</span><span class="sxs-lookup"><span data-stu-id="447a2-177">**Setting Name**</span></span>
- <span data-ttu-id="447a2-178">**Directiva**</span><span class="sxs-lookup"><span data-stu-id="447a2-178">**Policy**</span></span>
- <span data-ttu-id="447a2-179">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="447a2-179">**Type**</span></span>

<span data-ttu-id="447a2-180">Para filtrar los resultados, haga clic en **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="447a2-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="447a2-181">En el control flotante **filtros** que aparece, puede seleccionar entre los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="447a2-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="447a2-182">**Hora de inicio** y **hora de finalización** (fecha)</span><span class="sxs-lookup"><span data-stu-id="447a2-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="447a2-183">**Protección estándar** o **protección estricta**</span><span class="sxs-lookup"><span data-stu-id="447a2-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="447a2-184">Para exportar los resultados a un archivo. csv, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="447a2-184">To export the results to a .csv file, click **Export**.</span></span>

![Vista de historial y análisis de derivación de configuración en el analizador de configuración](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
