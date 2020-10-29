---
title: Solucionar problemas encontrados por la herramienta de evaluación de preparación
description: Acciones detalladas que se deben realizar para cada problema que encuentra la herramienta
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a6dec9473ee632b74bb79e50156cedff53a3cba3
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795122"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="fd3a0-104">Solucionar problemas encontrados por la herramienta de evaluación de preparación</span><span class="sxs-lookup"><span data-stu-id="fd3a0-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="fd3a0-105">Para cada comprobación, la herramienta notificará uno de los cuatro resultados posibles:</span><span class="sxs-lookup"><span data-stu-id="fd3a0-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="fd3a0-106">Resultado</span><span class="sxs-lookup"><span data-stu-id="fd3a0-106">Result</span></span>  |<span data-ttu-id="fd3a0-107">Significado</span><span class="sxs-lookup"><span data-stu-id="fd3a0-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="fd3a0-108">Listo</span><span class="sxs-lookup"><span data-stu-id="fd3a0-108">Ready</span></span>     | <span data-ttu-id="fd3a0-109">No es necesario realizar ninguna acción antes de completar la inscripción.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="fd3a0-110">Consejo</span><span class="sxs-lookup"><span data-stu-id="fd3a0-110">Advisory</span></span>    | <span data-ttu-id="fd3a0-111">Siga los pasos de la herramienta o este artículo para obtener la mejor experiencia con la inscripción y para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="fd3a0-112">*Puede* completar la inscripción, pero debe solucionar estos problemas antes de implementar el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="fd3a0-113">No preparado</span><span class="sxs-lookup"><span data-stu-id="fd3a0-113">Not ready</span></span> | <span data-ttu-id="fd3a0-114">*Se producirá un error en la inscripción si no soluciona estos problemas.*</span><span class="sxs-lookup"><span data-stu-id="fd3a0-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="fd3a0-115">Siga los pasos de la herramienta o este artículo para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="fd3a0-116">Error</span><span class="sxs-lookup"><span data-stu-id="fd3a0-116">Error</span></span> | <span data-ttu-id="fd3a0-117">El rol de Azure Active Director (AD) que está usando no tiene permisos suficientes para ejecutar esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="fd3a0-118">Configuración de Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fd3a0-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="fd3a0-119">Perfil de implementación de piloto automático</span><span class="sxs-lookup"><span data-stu-id="fd3a0-119">Autopilot deployment profile</span></span>

<span data-ttu-id="fd3a0-120">No debe tener ningún perfil de AutoPilot existente destinado a grupos dinámicos o asignados que use el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="fd3a0-121">Microsoft Managed Desktop usa AutoPilot para aprovisionar nuevos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="fd3a0-122">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-122">**Not ready**</span></span>

<span data-ttu-id="fd3a0-123">Tiene un perfil de AutoPilot asignado a todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="fd3a0-124">Para conocer los pasos, vea [inscribir dispositivos Windows en Intune mediante Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="fd3a0-125">Después de la inscripción de escritorio administrada de Microsoft, establezca su Directiva de AutoPilot para excluir los **dispositivos del área de trabajo modernos: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="fd3a0-126">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-126">**Advisory**</span></span>

<span data-ttu-id="fd3a0-127">Asegúrese de que los perfiles de AutoPilot están destinados a un grupo de Azure AD asignado o dinámico que no incluye los dispositivos de escritorio administrados por Microsoft que se crearán durante la inscripción.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="fd3a0-128">Para conocer los pasos, vea [inscribir dispositivos Windows en Intune mediante Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="fd3a0-129">Después de la inscripción de escritorio administrada de Microsoft, establezca su Directiva de AutoPilot para excluir los **dispositivos del área de trabajo modernos: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="fd3a0-130">Conectores de certificados</span><span class="sxs-lookup"><span data-stu-id="fd3a0-130">Certificate connectors</span></span>

<span data-ttu-id="fd3a0-131">Si tiene algún conector de certificados usado por los dispositivos que desea inscribir en el escritorio administrado de Microsoft, los conectores no pueden tener errores.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="fd3a0-132">Solo uno de los siguientes avisos se aplicará a su situación, por lo que debe comprobarlos cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="fd3a0-133">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-133">**Advisory**</span></span>

<span data-ttu-id="fd3a0-134">No hay conectores de certificado presentes.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-134">No certificate connectors are present.</span></span> <span data-ttu-id="fd3a0-135">Es posible que no necesite ningún conector, pero debe evaluar si es posible que necesite alguna conectividad de red para los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fd3a0-136">Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="fd3a0-137">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-137">**Advisory**</span></span>

<span data-ttu-id="fd3a0-138">Al menos un conector de certificado tiene un error.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="fd3a0-139">Si necesita este conector para la conectividad con dispositivos de escritorio administrados por Microsoft, debe resolver el error.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="fd3a0-140">Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="fd3a0-141">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-141">**Advisory**</span></span>

<span data-ttu-id="fd3a0-142">Tiene al menos un conector de certificados y no se ha notificado ningún error.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="fd3a0-143">Sin embargo, es posible que deba crear un perfil para volver a usar el conector para dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fd3a0-144">Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="fd3a0-145">Directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="fd3a0-145">Conditional access policies</span></span>

<span data-ttu-id="fd3a0-146">Las directivas de acceso condicional en su organización de Azure AD no deben dirigirse a ningún usuario de escritorio de Microsoft Manage.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="fd3a0-147">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-147">**Not ready**</span></span>

<span data-ttu-id="fd3a0-148">Tiene al menos una directiva de acceso condicional dirigida a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="fd3a0-149">Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya el grupo de Azure AD de las cuentas de servicio de escritorio administrado por Microsoft que se crearán en la inscripción.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="fd3a0-150">Para conocer los pasos, consulte el [acceso condicional: usuarios y grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="fd3a0-151">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-151">**Advisory**</span></span>

<span data-ttu-id="fd3a0-152">Asegúrese de que las directivas de acceso condicional que haya excluido excluyan el grupo de Azure AD de las **cuentas de servicio del lugar de trabajo moderno** .</span><span class="sxs-lookup"><span data-stu-id="fd3a0-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="fd3a0-153">Para conocer los pasos, consulte [ajustar el acceso condicional](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="fd3a0-154">El grupo de Azure AD de las **cuentas de servicio del lugar de trabajo modernos** es un grupo dinámico que creamos para el servicio al inscribirse.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="fd3a0-155">Tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="fd3a0-156">Para obtener más información acerca de estas cuentas de servicio, consulte [Standard Operations Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="fd3a0-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-157">**Error**</span></span>

<span data-ttu-id="fd3a0-158">El rol de administrador de Intune no tiene permisos suficientes para esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="fd3a0-159">También necesitará cualquiera de estas funciones de Azure AD asignadas para ejecutar esta comprobación:</span><span class="sxs-lookup"><span data-stu-id="fd3a0-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="fd3a0-160">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="fd3a0-160">Security Reader</span></span>
- <span data-ttu-id="fd3a0-161">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="fd3a0-161">Security Administrator</span></span>
- <span data-ttu-id="fd3a0-162">Administrador de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="fd3a0-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="fd3a0-163">Lector global</span><span class="sxs-lookup"><span data-stu-id="fd3a0-163">Global Reader</span></span>
- <span data-ttu-id="fd3a0-164">Administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="fd3a0-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="fd3a0-165">Directivas de cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="fd3a0-165">Device Compliance policies</span></span>

<span data-ttu-id="fd3a0-166">Las directivas de cumplimiento de dispositivos de Intune en su organización de Azure AD no deben dirigirse a ningún usuario de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="fd3a0-167">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-167">**Not ready**</span></span>

<span data-ttu-id="fd3a0-168">Tiene al menos una directiva de cumplimiento que tiene como objetivo todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="fd3a0-169">Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún usuario de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="fd3a0-170">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="fd3a0-171">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-171">**Advisory**</span></span>

<span data-ttu-id="fd3a0-172">Asegúrese de que las directivas de cumplimiento que tenga no incluyan ningún usuario de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="fd3a0-173">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="fd3a0-174">Directivas de configuración de dispositivo</span><span class="sxs-lookup"><span data-stu-id="fd3a0-174">Device Configuration policies</span></span>

<span data-ttu-id="fd3a0-175">Las directivas de configuración de dispositivo de Intune en la organización de Azure AD no deben dirigirse a ningún usuario o dispositivo de escritorio de Microsoft Manage.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="fd3a0-176">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-176">**Not ready**</span></span>

<span data-ttu-id="fd3a0-177">Tiene al menos una directiva de configuración que tiene como objetivo todos los usuarios, todos los dispositivos o ambos.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="fd3a0-178">Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fd3a0-179">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="fd3a0-180">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-180">**Advisory**</span></span>

<span data-ttu-id="fd3a0-181">Asegúrese de que las directivas de cumplimiento que tenga no incluyan ningún usuario o dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="fd3a0-182">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="fd3a0-183">Restricciones de tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="fd3a0-183">Device type restrictions</span></span>

<span data-ttu-id="fd3a0-184">Los dispositivos de escritorio administrados por Microsoft deben estar autorizados para inscribirse en Intune.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="fd3a0-185">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-185">**Not ready**</span></span>

<span data-ttu-id="fd3a0-186">Siga los pasos de [establecer restricciones de inscripción](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) para cambiar la configuración a **permitir** .</span><span class="sxs-lookup"><span data-stu-id="fd3a0-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow** .</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="fd3a0-187">Página de estado de inscripción</span><span class="sxs-lookup"><span data-stu-id="fd3a0-187">Enrollment Status Page</span></span>

<span data-ttu-id="fd3a0-188">Actualmente tiene la página de estado de inscripción (ESP) habilitada.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="fd3a0-189">Si está participando en la versión preliminar pública de esta característica, puede omitir este elemento.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="fd3a0-190">Para obtener más información, vea [experiencia de primera ejecución con AutoPilot y página de estado de inscripción](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="fd3a0-191">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-191">**Not ready**</span></span>

<span data-ttu-id="fd3a0-192">Tiene el perfil predeterminado ESP configurado para mostrar el progreso de la configuración de la **aplicación y el perfil** .</span><span class="sxs-lookup"><span data-stu-id="fd3a0-192">You have the ESP default profile set to **Show app and profile configuration progress** .</span></span> <span data-ttu-id="fd3a0-193">Para deshabilitar esta configuración, siga los pasos de la [Página configurar el estado de inscripción](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-193">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="fd3a0-194">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-194">**Advisory**</span></span>

<span data-ttu-id="fd3a0-195">Asegúrese de que los perfiles que tienen la configuración **Mostrar progreso de configuración de aplicación y perfil** no se asignan a ningún grupo de Azure ad que incluya dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fd3a0-196">Para obtener más información, consulte [configurar la página de estado de inscripción](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="fd3a0-197">Inscripción de Intune</span><span class="sxs-lookup"><span data-stu-id="fd3a0-197">Intune enrollment</span></span>

<span data-ttu-id="fd3a0-198">Los dispositivos con Windows 10 en la organización de Azure AD deben inscribirse automáticamente en Intune.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="fd3a0-199">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-199">**Not ready**</span></span>

<span data-ttu-id="fd3a0-200">Los usuarios de la organización de Azure AD no se inscriben automáticamente en Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-200">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="fd3a0-201">Cambie el **ámbito de usuario** de MDM a **todos o todos** .</span><span class="sxs-lookup"><span data-stu-id="fd3a0-201">Change the MDM User scope to **Some** or **All** .</span></span> <span data-ttu-id="fd3a0-202">Si elige **algunos** , vuelva atrás después de la inscripción y seleccione el **lugar de trabajo moderno: todos los** grupos de Azure ad para los **grupos** .</span><span class="sxs-lookup"><span data-stu-id="fd3a0-202">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** .</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="fd3a0-203">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="fd3a0-203">Microsoft Store for Business</span></span>

<span data-ttu-id="fd3a0-204">Usamos Microsoft Store for Business para que pueda descargar el portal de la empresa para implementar algunas aplicaciones, como Microsoft Project y Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-204">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="fd3a0-205">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-205">**Not ready**</span></span>

<span data-ttu-id="fd3a0-206">Microsoft Store para empresas ya no está habilitado o no está sincronizado con Intune.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="fd3a0-207">Para obtener más información, consulte [How to Manage Volume adquiried apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) e [install Intune Company Portal in on Devices](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="fd3a0-208">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="fd3a0-208">Multi-factor authentication</span></span>

<span data-ttu-id="fd3a0-209">La autenticación multifactor no se debe aplicar por accidente a las cuentas de servicio de escritorio administradas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-209">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="fd3a0-210">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-210">**Not ready**</span></span>

<span data-ttu-id="fd3a0-211">Tiene algunas directivas de multi-factor Authentication (MFA) establecidas como "necesarias" para las directivas de acceso condicional asignadas a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-211">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="fd3a0-212">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-212">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fd3a0-213">Para obtener más información, consulte [directivas de acceso condicional](#conditional-access-policies) y [acceso condicional: solicitar MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-213">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="fd3a0-214">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-214">**Advisory**</span></span>

<span data-ttu-id="fd3a0-215">Asegúrese de que las directivas de acceso condicional que requieran MFA excluyan el **lugar de trabajo moderno: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-215">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="fd3a0-216">Para obtener más información, consulte [directivas de acceso condicional](#conditional-access-policies) y [acceso condicional: solicitar MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="fd3a0-217">El **área de trabajo moderna: todo** grupo de Azure ad es un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-217">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="fd3a0-218">**Error**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-218">**Error**</span></span>

<span data-ttu-id="fd3a0-219">El rol de administrador de Intune no tiene permisos suficientes para esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="fd3a0-220">También necesitará cualquiera de estas funciones de Azure AD asignadas para ejecutar esta comprobación:</span><span class="sxs-lookup"><span data-stu-id="fd3a0-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="fd3a0-221">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="fd3a0-221">Security Reader</span></span>
- <span data-ttu-id="fd3a0-222">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="fd3a0-222">Security Administrator</span></span>
- <span data-ttu-id="fd3a0-223">Administrador de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="fd3a0-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="fd3a0-224">Lector global</span><span class="sxs-lookup"><span data-stu-id="fd3a0-224">Global Reader</span></span>
- <span data-ttu-id="fd3a0-225">Administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="fd3a0-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="fd3a0-226">Scripts de PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd3a0-226">PowerShell scripts</span></span>

<span data-ttu-id="fd3a0-227">Los scripts de Windows PowerShell no se pueden asignar de una manera que se dirija a los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="fd3a0-228">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-228">**Advisory**</span></span>

<span data-ttu-id="fd3a0-229">Asegúrese de que los scripts de Windows PowerShell de la organización de Azure AD no tienen como objetivo ningún usuario o dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="fd3a0-230">Para obtener más información, vea [usar scripts de PowerShell en dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-230">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="fd3a0-231">Región</span><span class="sxs-lookup"><span data-stu-id="fd3a0-231">Region</span></span>

<span data-ttu-id="fd3a0-232">Su región debe ser compatible con el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-232">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="fd3a0-233">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-233">**Not ready**</span></span>

<span data-ttu-id="fd3a0-234">Actualmente, la región de la organización de Azure AD no es compatible con el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-234">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="fd3a0-235">Para obtener más información, consulte [regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-235">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="fd3a0-236">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-236">**Advisory**</span></span>

<span data-ttu-id="fd3a0-237">Uno o más de los países en los que se encuentra su organización de Azure AD no es compatible con el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-237">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="fd3a0-238">Para obtener más información, consulte [regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-238">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="fd3a0-239">Líneas de base de seguridad</span><span class="sxs-lookup"><span data-stu-id="fd3a0-239">Security baselines</span></span>

<span data-ttu-id="fd3a0-240">Las directivas de línea de base de seguridad no deben dirigirse a ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-240">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="fd3a0-241">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-241">**Not ready**</span></span>

<span data-ttu-id="fd3a0-242">Tiene un perfil de línea de base de seguridad destinado a todos los usuarios, todos los dispositivos o ambos.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-242">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="fd3a0-243">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-243">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fd3a0-244">Para conocer los pasos, consulte [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-244">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="fd3a0-245">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-245">**Advisory**</span></span>

<span data-ttu-id="fd3a0-246">Asegúrese de que todas las directivas de línea base de seguridad que haya excluido sean dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-246">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fd3a0-247">Para conocer los pasos, consulte [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-247">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="fd3a0-248">Los **dispositivos modernos del área de trabajo: todos los** grupos de Azure ad son un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-248">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="fd3a0-249">Aplicaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="fd3a0-249">Windows apps</span></span>

<span data-ttu-id="fd3a0-250">Revise las aplicaciones que desea que tengan los usuarios de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-250">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="fd3a0-251">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-251">**Advisory**</span></span>

<span data-ttu-id="fd3a0-252">Debe preparar un inventario de las aplicaciones que desea que tengan los usuarios de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-252">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="fd3a0-253">Asegúrese de que estas aplicaciones se pueden implementar con Intune.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-253">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="fd3a0-254">Para obtener más información, vea [aplicaciones en el escritorio administrado de Microsoft](apps.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-254">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="fd3a0-255">Puede pedir a su representante de su cuenta de Microsoft una consulta en Microsoft Endpoint Configuration Manager para identificar las aplicaciones que están preparadas para la migración a Intune o el ajuste necesario.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-255">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="fd3a0-256">Windows Hello para empresas</span><span class="sxs-lookup"><span data-stu-id="fd3a0-256">Windows Hello for Business</span></span>

<span data-ttu-id="fd3a0-257">El escritorio administrado de Microsoft requiere que Windows Hello para empresas esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-257">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="fd3a0-258">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-258">**Not ready**</span></span>

<span data-ttu-id="fd3a0-259">Windows Hello para empresas está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-259">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="fd3a0-260">Habilítelo siguiendo los pasos de [crear una directiva de Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="fd3a0-260">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="fd3a0-261">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-261">**Advisory**</span></span>

<span data-ttu-id="fd3a0-262">Windows Hello para empresas no está configurado.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-262">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="fd3a0-263">Para habilitarla, siga los pasos de [crear una directiva de Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-263">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="fd3a0-264">Anillos de actualización de Windows 10</span><span class="sxs-lookup"><span data-stu-id="fd3a0-264">Windows 10 update rings</span></span>

<span data-ttu-id="fd3a0-265">La Directiva "Windows 10 Update Ring" en Intune no debe dirigirse a ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-265">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="fd3a0-266">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-266">**Not ready**</span></span>

<span data-ttu-id="fd3a0-267">Tiene una directiva "actualizar anillo" que tiene como objetivo todos los dispositivos, todos los usuarios o ambos.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-267">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="fd3a0-268">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-268">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fd3a0-269">Para conocer los pasos, consulte [administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-269">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="fd3a0-270">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-270">**Advisory**</span></span>

<span data-ttu-id="fd3a0-271">Asegúrese de que todas las directivas de Update Ring que tiene excluyan el **lugar de trabajo moderno: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-271">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="fd3a0-272">Para conocer los pasos, consulte [administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-272">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="fd3a0-273">Los **dispositivos modernos del área de trabajo: todos los** grupos de Azure ad son un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-273">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="fd3a0-274">Configuración de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fd3a0-274">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="fd3a0-275">Suscripciones ad hoc</span><span class="sxs-lookup"><span data-stu-id="fd3a0-275">Ad hoc subscriptions</span></span>

<span data-ttu-id="fd3a0-276">Aconseja comprobar una opción que (si se establece en "false") impedir que la itinerancia del estado de la empresa funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-276">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="fd3a0-277">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-277">**Advisory**</span></span>

<span data-ttu-id="fd3a0-278">Asegúrese de que **AllowAdHocSubscriptions** está establecido en **true** .</span><span class="sxs-lookup"><span data-stu-id="fd3a0-278">Ensure that **AllowAdHocSubscriptions** is set to **True** .</span></span> <span data-ttu-id="fd3a0-279">De lo contrario, es posible que la itinerancia del estado de la empresa no funcione.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-279">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="fd3a0-280">Para obtener más información, vea [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-280">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="fd3a0-281">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="fd3a0-281">Enterprise State Roaming</span></span>

<span data-ttu-id="fd3a0-282">La itinerancia del estado de la empresa debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-282">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="fd3a0-283">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-283">**Advisory**</span></span>

<span data-ttu-id="fd3a0-284">Asegúrese de que la itinerancia del estado de la empresa esté habilitada para todos o para **los** grupos **seleccionados** .</span><span class="sxs-lookup"><span data-stu-id="fd3a0-284">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="fd3a0-285">Para obtener más información, consulte [Habilitar la itinerancia del estado de la empresa en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-285">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="fd3a0-286">Licencias</span><span class="sxs-lookup"><span data-stu-id="fd3a0-286">Licenses</span></span>

<span data-ttu-id="fd3a0-287">Se necesita un número de licencias para usar el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-287">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="fd3a0-288">**No está listo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-288">**Not Ready**</span></span>

<span data-ttu-id="fd3a0-289">No tiene todas las licencias que necesita para usar Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-289">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="fd3a0-290">Para obtener más información, consulte [tecnologías de escritorio administradas de Microsoft](../intro/technologies.md) y más información [sobre licencias](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-290">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="fd3a0-291">Nombres de cuenta de seguridad</span><span class="sxs-lookup"><span data-stu-id="fd3a0-291">Security account names</span></span>

<span data-ttu-id="fd3a0-292">Algunos nombres de cuentas de seguridad podrían entrar en conflicto con los creados por el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-292">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="fd3a0-293">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-293">**Not ready**</span></span>

<span data-ttu-id="fd3a0-294">Tiene al menos un nombre de cuenta que entrará en conflicto con los creados por el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-294">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="fd3a0-295">Trabaje con el representante de su cuenta de Microsoft para excluir estos nombres de cuenta.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-295">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="fd3a0-296">Roles de administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="fd3a0-296">Security administrator roles</span></span>

<span data-ttu-id="fd3a0-297">Los usuarios con determinados roles de seguridad deben tener los asignados en Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-297">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="fd3a0-298">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-298">**Advisory**</span></span>

<span data-ttu-id="fd3a0-299">Si tiene cualquiera de estos roles asignados en su organización de Azure AD, asegúrese de que también tengan estos roles asignados en Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-299">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="fd3a0-300">De lo contrario, los administradores con estos roles no podrán obtener acceso al portal de administración.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-300">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="fd3a0-301">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="fd3a0-301">Security Reader</span></span>
- <span data-ttu-id="fd3a0-302">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="fd3a0-302">Security Operator</span></span>
- <span data-ttu-id="fd3a0-303">Lector global</span><span class="sxs-lookup"><span data-stu-id="fd3a0-303">Global Reader</span></span>

<span data-ttu-id="fd3a0-304">Para obtener más información, vea [Create and Manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-304">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="fd3a0-305">Seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="fd3a0-305">Security default</span></span>

<span data-ttu-id="fd3a0-306">Los valores predeterminados de seguridad de Azure Active Directory impedirán que Microsoft administre el escritorio de sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-306">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="fd3a0-307">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-307">**Not ready**</span></span>

<span data-ttu-id="fd3a0-308">Tiene los valores predeterminados de seguridad activados.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-308">You have Security defaults turned on.</span></span> <span data-ttu-id="fd3a0-309">Desactivar los valores predeterminados de seguridad y configurar directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-309">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="fd3a0-310">Para obtener más información, consulte [directivas de acceso condicional comunes](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-310">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="fd3a0-311">Restablecimiento de contraseña de autoservicio</span><span class="sxs-lookup"><span data-stu-id="fd3a0-311">Self-service Password Reset</span></span>

<span data-ttu-id="fd3a0-312">Debe estar habilitado el restablecimiento de contraseña de autoservicio (SSPR).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-312">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="fd3a0-313">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-313">**Not ready**</span></span>

<span data-ttu-id="fd3a0-314">SSPR debe estar habilitado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-314">SSPR must be enabled for all users.</span></span> <span data-ttu-id="fd3a0-315">Si no es así, las cuentas de servicio de escritorio administradas de Microsoft no pueden funcionar.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-315">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="fd3a0-316">Para obtener más información, vea [Tutorial: permitir a los usuarios desbloquear su cuenta o restablecer contraseñas con el restablecimiento de contraseña de autoservicio de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="fd3a0-316">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="fd3a0-317">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-317">**Advisory**</span></span>

<span data-ttu-id="fd3a0-318">Asegúrese de que la configuración de SSPR **seleccionada** incluye dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-318">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="fd3a0-319">**Error**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-319">**Error**</span></span>

<span data-ttu-id="fd3a0-320">El rol de administrador de Intune no tiene permisos suficientes para esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-320">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="fd3a0-321">También necesitará el rol de Azure AD del lector de informes asignado para ejecutar esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-321">You'll also need the Reports Reader Azure AD role assigned to run this check.</span></span>


### <a name="standard-user-role"></a><span data-ttu-id="fd3a0-322">Rol de usuario estándar</span><span class="sxs-lookup"><span data-stu-id="fd3a0-322">Standard user role</span></span>

<span data-ttu-id="fd3a0-323">Los usuarios de escritorio administrados de Microsoft deben ser usuarios estándar sin privilegios de administrador local.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-323">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="fd3a0-324">Se les asignará un rol de usuario estándar cuando inicien su dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-324">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="fd3a0-325">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-325">**Advisory**</span></span>

<span data-ttu-id="fd3a0-326">Los usuarios de escritorio administrado de Microsoft no deben tener privilegios de administrador local antes de inscribirse.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-326">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="fd3a0-327">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="fd3a0-327">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="fd3a0-328">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="fd3a0-328">OneDrive for Business</span></span>

<span data-ttu-id="fd3a0-329">La opción **permitir sincronización solo en equipos Unidos a dominios específicos** entrará en conflicto con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-329">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="fd3a0-330">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="fd3a0-330">**Advisory**</span></span>

<span data-ttu-id="fd3a0-331">Está usando la opción **permitir sincronización solo en equipos Unidos a dominios específicos** .</span><span class="sxs-lookup"><span data-stu-id="fd3a0-331">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="fd3a0-332">Esta configuración no funcionará con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-332">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="fd3a0-333">Deshabilite esta opción y, en su lugar, configure OneDrive para la empresa para usar una directiva de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-333">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="fd3a0-334">Consulte [planear una implementación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="fd3a0-334">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

