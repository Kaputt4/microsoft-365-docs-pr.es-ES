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
ms.openlocfilehash: 642de80e1a133f212b7afb6774d9aab2eeaabdbf
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941414"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="290c8-104">Solucionar problemas encontrados por la herramienta de evaluación de preparación</span><span class="sxs-lookup"><span data-stu-id="290c8-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="290c8-105">Para cada comprobación, la herramienta notificará uno de los cuatro resultados posibles:</span><span class="sxs-lookup"><span data-stu-id="290c8-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="290c8-106">Resultado</span><span class="sxs-lookup"><span data-stu-id="290c8-106">Result</span></span>  |<span data-ttu-id="290c8-107">Significado</span><span class="sxs-lookup"><span data-stu-id="290c8-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="290c8-108">Listo</span><span class="sxs-lookup"><span data-stu-id="290c8-108">Ready</span></span>     | <span data-ttu-id="290c8-109">No es necesario realizar ninguna acción antes de completar la inscripción.</span><span class="sxs-lookup"><span data-stu-id="290c8-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="290c8-110">Consejo</span><span class="sxs-lookup"><span data-stu-id="290c8-110">Advisory</span></span>    | <span data-ttu-id="290c8-111">Siga los pasos de la herramienta o este artículo para obtener la mejor experiencia con la inscripción y para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="290c8-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="290c8-112">*Puede* completar la inscripción, pero debe solucionar estos problemas antes de implementar el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="290c8-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="290c8-113">No preparado</span><span class="sxs-lookup"><span data-stu-id="290c8-113">Not ready</span></span> | <span data-ttu-id="290c8-114">*Se producirá un error en la inscripción si no soluciona estos problemas.*</span><span class="sxs-lookup"><span data-stu-id="290c8-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="290c8-115">Siga los pasos de la herramienta o este artículo para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="290c8-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="290c8-116">Error</span><span class="sxs-lookup"><span data-stu-id="290c8-116">Error</span></span> | <span data-ttu-id="290c8-117">El rol de Azure Active Director (AD) que está usando no tiene permisos suficientes para ejecutar esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="290c8-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="290c8-118">Configuración de Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="290c8-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="290c8-119">Perfil de implementación de piloto automático</span><span class="sxs-lookup"><span data-stu-id="290c8-119">Autopilot deployment profile</span></span>

<span data-ttu-id="290c8-120">No debe tener ningún perfil de AutoPilot existente destinado a grupos dinámicos o asignados que use el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="290c8-121">Microsoft Managed Desktop usa AutoPilot para aprovisionar nuevos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="290c8-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="290c8-122">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-122">**Not ready**</span></span>

<span data-ttu-id="290c8-123">Tiene un perfil de AutoPilot asignado a todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="290c8-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="290c8-124">Para conocer los pasos, vea [inscribir dispositivos Windows en Intune mediante Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="290c8-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="290c8-125">Después de la inscripción de escritorio administrada de Microsoft, establezca su Directiva de AutoPilot para excluir los **dispositivos del área de trabajo modernos: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="290c8-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="290c8-126">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-126">**Advisory**</span></span>

<span data-ttu-id="290c8-127">Asegúrese de que los perfiles de AutoPilot están destinados a un grupo de Azure AD asignado o dinámico que no incluye los dispositivos de escritorio administrados por Microsoft que se crearán durante la inscripción.</span><span class="sxs-lookup"><span data-stu-id="290c8-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="290c8-128">Para conocer los pasos, vea [inscribir dispositivos Windows en Intune mediante Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="290c8-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="290c8-129">Después de la inscripción de escritorio administrada de Microsoft, establezca su Directiva de AutoPilot para excluir los **dispositivos del área de trabajo modernos: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="290c8-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="290c8-130">Conectores de certificados</span><span class="sxs-lookup"><span data-stu-id="290c8-130">Certificate connectors</span></span>

<span data-ttu-id="290c8-131">Si tiene algún conector de certificados usado por los dispositivos que desea inscribir en el escritorio administrado de Microsoft, los conectores no pueden tener errores.</span><span class="sxs-lookup"><span data-stu-id="290c8-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="290c8-132">Solo uno de los siguientes avisos se aplicará a su situación, por lo que debe comprobarlos cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="290c8-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="290c8-133">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-133">**Advisory**</span></span>

<span data-ttu-id="290c8-134">No hay conectores de certificado presentes.</span><span class="sxs-lookup"><span data-stu-id="290c8-134">No certificate connectors are present.</span></span> <span data-ttu-id="290c8-135">Es posible que no necesite ningún conector, pero debe evaluar si es posible que necesite alguna conectividad de red para los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="290c8-136">Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="290c8-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="290c8-137">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-137">**Advisory**</span></span>

<span data-ttu-id="290c8-138">Al menos un conector de certificado tiene un error.</span><span class="sxs-lookup"><span data-stu-id="290c8-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="290c8-139">Si necesita este conector para la conectividad con dispositivos de escritorio administrados por Microsoft, debe resolver el error.</span><span class="sxs-lookup"><span data-stu-id="290c8-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="290c8-140">Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="290c8-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="290c8-141">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-141">**Advisory**</span></span>

<span data-ttu-id="290c8-142">Tiene al menos un conector de certificados y no se ha notificado ningún error.</span><span class="sxs-lookup"><span data-stu-id="290c8-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="290c8-143">Sin embargo, es posible que deba crear un perfil para volver a usar el conector para dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="290c8-144">Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="290c8-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="290c8-145">Directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="290c8-145">Conditional access policies</span></span>

<span data-ttu-id="290c8-146">Las directivas de acceso condicional en su organización de Azure AD no deben dirigirse a ningún usuario de escritorio de Microsoft Manage.</span><span class="sxs-lookup"><span data-stu-id="290c8-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="290c8-147">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-147">**Not ready**</span></span>

<span data-ttu-id="290c8-148">Tiene al menos una directiva de acceso condicional dirigida a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="290c8-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="290c8-149">Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya el grupo de Azure AD de las cuentas de servicio de escritorio administrado por Microsoft que se crearán en la inscripción.</span><span class="sxs-lookup"><span data-stu-id="290c8-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="290c8-150">Para conocer los pasos, consulte el [acceso condicional: usuarios y grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="290c8-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="290c8-151">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-151">**Advisory**</span></span>

<span data-ttu-id="290c8-152">Asegúrese de que las directivas de acceso condicional que haya excluido excluyan el grupo de Azure AD de las **cuentas de servicio del lugar de trabajo moderno** .</span><span class="sxs-lookup"><span data-stu-id="290c8-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="290c8-153">Para conocer los pasos, consulte [ajustar el acceso condicional](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="290c8-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="290c8-154">El grupo de Azure AD de las **cuentas de servicio del lugar de trabajo modernos** es un grupo dinámico que creamos para el servicio al inscribirse.</span><span class="sxs-lookup"><span data-stu-id="290c8-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="290c8-155">Tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="290c8-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="290c8-156">Para obtener más información acerca de estas cuentas de servicio, consulte [Standard Operations Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="290c8-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="290c8-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="290c8-157">**Error**</span></span>

<span data-ttu-id="290c8-158">El rol de administrador de Intune no tiene permisos suficientes para esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="290c8-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="290c8-159">También necesitará cualquiera de estas funciones de Azure AD asignadas para ejecutar esta comprobación:</span><span class="sxs-lookup"><span data-stu-id="290c8-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="290c8-160">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="290c8-160">Security Reader</span></span>
- <span data-ttu-id="290c8-161">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="290c8-161">Security Administrator</span></span>
- <span data-ttu-id="290c8-162">Administrador de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="290c8-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="290c8-163">Lector global</span><span class="sxs-lookup"><span data-stu-id="290c8-163">Global Reader</span></span>
- <span data-ttu-id="290c8-164">Administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="290c8-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="290c8-165">Directivas de cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="290c8-165">Device Compliance policies</span></span>

<span data-ttu-id="290c8-166">Las directivas de cumplimiento de dispositivos de Intune en su organización de Azure AD no deben dirigirse a ningún usuario de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="290c8-167">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-167">**Not ready**</span></span>

<span data-ttu-id="290c8-168">Tiene al menos una directiva de cumplimiento que tiene como objetivo todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="290c8-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="290c8-169">Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún usuario de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="290c8-170">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="290c8-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="290c8-171">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-171">**Advisory**</span></span>

<span data-ttu-id="290c8-172">Asegúrese de que las directivas de cumplimiento que tenga no incluyan ningún usuario de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="290c8-173">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="290c8-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="290c8-174">Directivas de configuración de dispositivo</span><span class="sxs-lookup"><span data-stu-id="290c8-174">Device Configuration policies</span></span>

<span data-ttu-id="290c8-175">Las directivas de configuración de dispositivo de Intune en la organización de Azure AD no deben dirigirse a ningún usuario o dispositivo de escritorio de Microsoft Manage.</span><span class="sxs-lookup"><span data-stu-id="290c8-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="290c8-176">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-176">**Not ready**</span></span>

<span data-ttu-id="290c8-177">Tiene al menos una directiva de configuración que tiene como objetivo todos los usuarios, todos los dispositivos o ambos.</span><span class="sxs-lookup"><span data-stu-id="290c8-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="290c8-178">Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="290c8-179">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="290c8-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="290c8-180">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-180">**Advisory**</span></span>

<span data-ttu-id="290c8-181">Asegúrese de que las directivas de cumplimiento que tenga no incluyan ningún usuario o dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="290c8-182">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="290c8-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="290c8-183">Restricciones de tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="290c8-183">Device type restrictions</span></span>

<span data-ttu-id="290c8-184">Los dispositivos de escritorio administrados por Microsoft deben estar autorizados para inscribirse en Intune.</span><span class="sxs-lookup"><span data-stu-id="290c8-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="290c8-185">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-185">**Not ready**</span></span>

<span data-ttu-id="290c8-186">Siga los pasos de [establecer restricciones de inscripción](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) para cambiar la configuración a **permitir**.</span><span class="sxs-lookup"><span data-stu-id="290c8-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="290c8-187">Página de estado de inscripción</span><span class="sxs-lookup"><span data-stu-id="290c8-187">Enrollment Status Page</span></span>

<span data-ttu-id="290c8-188">Actualmente tiene la página de estado de inscripción (ESP) habilitada.</span><span class="sxs-lookup"><span data-stu-id="290c8-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="290c8-189">Si está participando en la versión preliminar pública de esta característica, puede omitir este elemento.</span><span class="sxs-lookup"><span data-stu-id="290c8-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="290c8-190">Para obtener más información, vea [experiencia de primera ejecución con AutoPilot y página de estado de inscripción](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="290c8-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="290c8-191">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-191">**Not ready**</span></span>

<span data-ttu-id="290c8-192">Tiene el perfil predeterminado ESP configurado para mostrar el progreso de la configuración de la **aplicación y el perfil**.</span><span class="sxs-lookup"><span data-stu-id="290c8-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="290c8-193">Deshabilite esta opción o asegúrese de que las asignaciones a cualquier grupo de Azure AD no incluyen dispositivos de escritorio administrados por Microsoft mediante los pasos de la [página Configuración del estado de inscripción](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="290c8-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="290c8-194">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-194">**Advisory**</span></span>

<span data-ttu-id="290c8-195">Asegúrese de que los perfiles que tienen la configuración **Mostrar progreso de configuración de aplicación y perfil** no se asignan a ningún grupo de Azure ad que incluya dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="290c8-196">Para obtener más información, consulte [configurar la página de estado de inscripción](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="290c8-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="290c8-197">Inscripción de Intune</span><span class="sxs-lookup"><span data-stu-id="290c8-197">Intune enrollment</span></span>

<span data-ttu-id="290c8-198">Los dispositivos con Windows 10 en la organización de Azure AD deben inscribirse automáticamente en Intune.</span><span class="sxs-lookup"><span data-stu-id="290c8-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="290c8-199">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-199">**Advisory**</span></span>

<span data-ttu-id="290c8-200">Asegúrese de que el ámbito de usuario de MDM esté establecido en **alguno** o en **todos** , no en **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="290c8-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="290c8-201">Si elige **algunos** , vuelva atrás después de la inscripción y seleccione el **lugar de trabajo moderno: todos los** grupos de Azure ad para los **grupos**.</span><span class="sxs-lookup"><span data-stu-id="290c8-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="290c8-202">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="290c8-202">Microsoft Store for Business</span></span>

<span data-ttu-id="290c8-203">Usamos Microsoft Store for Business para que pueda descargar el portal de la empresa para implementar algunas aplicaciones, como Microsoft Project y Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="290c8-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="290c8-204">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-204">**Not ready**</span></span>

<span data-ttu-id="290c8-205">Microsoft Store para empresas ya no está habilitado o no está sincronizado con Intune.</span><span class="sxs-lookup"><span data-stu-id="290c8-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="290c8-206">Para obtener más información, consulte [How to Manage Volume adquiried apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) e [install Intune Company Portal in on Devices](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="290c8-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="290c8-207">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="290c8-207">Multi-factor authentication</span></span>

<span data-ttu-id="290c8-208">La autenticación multifactor no se debe aplicar por accidente a las cuentas de servicio de escritorio administradas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="290c8-209">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-209">**Not ready**</span></span>

<span data-ttu-id="290c8-210">Tiene algunas directivas de multi-factor Authentication (MFA) establecidas como "necesarias" para las directivas de acceso condicional asignadas a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="290c8-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="290c8-211">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="290c8-212">Para obtener más información, consulte [directivas de acceso condicional](#conditional-access-policies) y [acceso condicional: solicitar MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="290c8-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="290c8-213">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-213">**Advisory**</span></span>

<span data-ttu-id="290c8-214">Asegúrese de que las directivas de acceso condicional que requieran MFA excluyan el **lugar de trabajo moderno: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="290c8-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="290c8-215">Para obtener más información, consulte [directivas de acceso condicional](#conditional-access-policies) y [acceso condicional: solicitar MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="290c8-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="290c8-216">El **área de trabajo moderna: todo** grupo de Azure ad es un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="290c8-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="290c8-217">**Error**</span><span class="sxs-lookup"><span data-stu-id="290c8-217">**Error**</span></span>

<span data-ttu-id="290c8-218">El rol de administrador de Intune no tiene permisos suficientes para esta comprobación.</span><span class="sxs-lookup"><span data-stu-id="290c8-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="290c8-219">También necesitará cualquiera de estas funciones de Azure AD asignadas para ejecutar esta comprobación:</span><span class="sxs-lookup"><span data-stu-id="290c8-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="290c8-220">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="290c8-220">Security Reader</span></span>
- <span data-ttu-id="290c8-221">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="290c8-221">Security Administrator</span></span>
- <span data-ttu-id="290c8-222">Administrador de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="290c8-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="290c8-223">Lector global</span><span class="sxs-lookup"><span data-stu-id="290c8-223">Global Reader</span></span>
- <span data-ttu-id="290c8-224">Administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="290c8-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="290c8-225">Scripts de PowerShell</span><span class="sxs-lookup"><span data-stu-id="290c8-225">PowerShell scripts</span></span>

<span data-ttu-id="290c8-226">Los scripts de Windows PowerShell no se pueden asignar de una manera que se dirija a los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="290c8-227">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-227">**Advisory**</span></span>

<span data-ttu-id="290c8-228">Asegúrese de que los scripts de Windows PowerShell de la organización de Azure AD no tienen como objetivo ningún usuario o dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="290c8-229">No asigne un script de PowerShell para dirigirse a todos los usuarios, todos los dispositivos o ambos.</span><span class="sxs-lookup"><span data-stu-id="290c8-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="290c8-230">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="290c8-231">Para obtener más información, vea [usar scripts de PowerShell en dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="290c8-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="290c8-232">Región</span><span class="sxs-lookup"><span data-stu-id="290c8-232">Region</span></span>

<span data-ttu-id="290c8-233">Su región debe ser compatible con el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="290c8-234">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-234">**Not ready**</span></span>

<span data-ttu-id="290c8-235">Actualmente, la región de la organización de Azure AD no es compatible con el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="290c8-236">Para obtener más información, consulte [regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="290c8-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="290c8-237">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-237">**Advisory**</span></span>

<span data-ttu-id="290c8-238">Uno o más de los países en los que se encuentra su organización de Azure AD no es compatible con el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="290c8-239">Para obtener más información, consulte [regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="290c8-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="290c8-240">Líneas de base de seguridad</span><span class="sxs-lookup"><span data-stu-id="290c8-240">Security baselines</span></span>

<span data-ttu-id="290c8-241">Las directivas de línea de base de seguridad no deben dirigirse a ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="290c8-242">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-242">**Not ready**</span></span>

<span data-ttu-id="290c8-243">Tiene un perfil de línea de base de seguridad destinado a todos los usuarios, todos los dispositivos o ambos.</span><span class="sxs-lookup"><span data-stu-id="290c8-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="290c8-244">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="290c8-245">Para conocer los pasos, consulte [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="290c8-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="290c8-246">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-246">**Advisory**</span></span>

<span data-ttu-id="290c8-247">Asegúrese de que todas las directivas de línea base de seguridad que haya excluido sean dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="290c8-248">Para conocer los pasos, consulte [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="290c8-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="290c8-249">Los **dispositivos modernos del área de trabajo: todos los** grupos de Azure ad son un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="290c8-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="290c8-250">Aplicaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="290c8-250">Windows apps</span></span>

<span data-ttu-id="290c8-251">Revise las aplicaciones que desea que tengan los usuarios de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="290c8-252">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-252">**Advisory**</span></span>

<span data-ttu-id="290c8-253">Debe preparar un inventario de las aplicaciones que desea que tengan los usuarios de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="290c8-254">Asegúrese de que estas aplicaciones se pueden implementar con Intune.</span><span class="sxs-lookup"><span data-stu-id="290c8-254">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="290c8-255">Para obtener más información, vea [aplicaciones en el escritorio administrado de Microsoft](apps.md).</span><span class="sxs-lookup"><span data-stu-id="290c8-255">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="290c8-256">Puede pedir a su representante de su cuenta de Microsoft una consulta en Microsoft Endpoint Configuration Manager para identificar las aplicaciones que están preparadas para la migración a Intune o el ajuste necesario.</span><span class="sxs-lookup"><span data-stu-id="290c8-256">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="290c8-257">Windows Hello para empresas</span><span class="sxs-lookup"><span data-stu-id="290c8-257">Windows Hello for Business</span></span>

<span data-ttu-id="290c8-258">El escritorio administrado de Microsoft requiere que Windows Hello para empresas esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="290c8-258">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="290c8-259">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-259">**Not ready**</span></span>

<span data-ttu-id="290c8-260">Windows Hello para empresas está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="290c8-260">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="290c8-261">Habilítelo siguiendo los pasos de [crear una directiva de Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="290c8-261">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="290c8-262">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-262">**Advisory**</span></span>

<span data-ttu-id="290c8-263">Windows Hello para empresas no está configurado.</span><span class="sxs-lookup"><span data-stu-id="290c8-263">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="290c8-264">Para habilitarla, siga los pasos de [crear una directiva de Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="290c8-264">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="290c8-265">Anillos de actualización de Windows 10</span><span class="sxs-lookup"><span data-stu-id="290c8-265">Windows 10 update rings</span></span>

<span data-ttu-id="290c8-266">La Directiva "Windows 10 Update Ring" en Intune no debe dirigirse a ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-266">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="290c8-267">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-267">**Not ready**</span></span>

<span data-ttu-id="290c8-268">Tiene una directiva "actualizar anillo" que tiene como objetivo todos los dispositivos, todos los usuarios o ambos.</span><span class="sxs-lookup"><span data-stu-id="290c8-268">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="290c8-269">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-269">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="290c8-270">Para conocer los pasos, consulte [administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="290c8-270">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="290c8-271">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-271">**Advisory**</span></span>

<span data-ttu-id="290c8-272">Asegúrese de que todas las directivas de Update Ring que tiene excluyan el **lugar de trabajo moderno: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="290c8-272">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="290c8-273">Para conocer los pasos, consulte [administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="290c8-273">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="290c8-274">Los **dispositivos modernos del área de trabajo: todos los** grupos de Azure ad son un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="290c8-274">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="290c8-275">Configuración de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="290c8-275">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="290c8-276">Suscripciones ad hoc</span><span class="sxs-lookup"><span data-stu-id="290c8-276">Ad hoc subscriptions</span></span>

<span data-ttu-id="290c8-277">Aconseja comprobar una opción que (si se establece en "false") impedir que la itinerancia del estado de la empresa funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="290c8-277">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="290c8-278">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-278">**Advisory**</span></span>

<span data-ttu-id="290c8-279">Asegúrese de que **AllowAdHocSubscriptions** está establecido en **true**.</span><span class="sxs-lookup"><span data-stu-id="290c8-279">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="290c8-280">De lo contrario, es posible que la itinerancia del estado de la empresa no funcione.</span><span class="sxs-lookup"><span data-stu-id="290c8-280">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="290c8-281">Para obtener más información, vea [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="290c8-281">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="290c8-282">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="290c8-282">Enterprise State Roaming</span></span>

<span data-ttu-id="290c8-283">La itinerancia del estado de la empresa debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="290c8-283">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="290c8-284">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-284">**Advisory**</span></span>

<span data-ttu-id="290c8-285">Asegúrese de que la itinerancia del estado de la empresa esté habilitada para todos o para **los** grupos **seleccionados** .</span><span class="sxs-lookup"><span data-stu-id="290c8-285">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="290c8-286">Para obtener más información, consulte [Habilitar la itinerancia del estado de la empresa en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="290c8-286">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="290c8-287">Licencias</span><span class="sxs-lookup"><span data-stu-id="290c8-287">Licenses</span></span>

<span data-ttu-id="290c8-288">Se necesita un número de licencias para usar el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-288">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="290c8-289">**No está listo**</span><span class="sxs-lookup"><span data-stu-id="290c8-289">**Not Ready**</span></span>

<span data-ttu-id="290c8-290">No tiene todas las licencias que necesita para usar Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="290c8-290">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="290c8-291">Para obtener más información, consulte [tecnologías de escritorio administradas de Microsoft](../intro/technologies.md) y más información [sobre licencias](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="290c8-291">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="290c8-292">Nombres de cuenta de seguridad</span><span class="sxs-lookup"><span data-stu-id="290c8-292">Security account names</span></span>

<span data-ttu-id="290c8-293">Algunos nombres de cuentas de seguridad podrían entrar en conflicto con los creados por el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-293">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="290c8-294">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-294">**Not ready**</span></span>

<span data-ttu-id="290c8-295">Tiene al menos un nombre de cuenta que entrará en conflicto con los creados por el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-295">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="290c8-296">Trabaje con el representante de su cuenta de Microsoft para excluir estos nombres de cuenta.</span><span class="sxs-lookup"><span data-stu-id="290c8-296">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="290c8-297">Roles de administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="290c8-297">Security administrator roles</span></span>

<span data-ttu-id="290c8-298">Los usuarios con determinados roles de seguridad deben tener los asignados en Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="290c8-298">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="290c8-299">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-299">**Advisory**</span></span>

<span data-ttu-id="290c8-300">Si tiene cualquiera de estos roles asignados en su organización de Azure AD, asegúrese de que también tengan estos roles asignados en Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="290c8-300">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="290c8-301">De lo contrario, los administradores con estos roles no podrán obtener acceso al portal de administración.</span><span class="sxs-lookup"><span data-stu-id="290c8-301">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="290c8-302">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="290c8-302">Security Reader</span></span>
- <span data-ttu-id="290c8-303">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="290c8-303">Security Operator</span></span>
- <span data-ttu-id="290c8-304">Lector global</span><span class="sxs-lookup"><span data-stu-id="290c8-304">Global Reader</span></span>

<span data-ttu-id="290c8-305">Para obtener más información, vea [Create and Manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="290c8-305">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="290c8-306">Seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="290c8-306">Security default</span></span>

<span data-ttu-id="290c8-307">Los valores predeterminados de seguridad de Azure Active Directory impedirán que Microsoft administre el escritorio de sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="290c8-307">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="290c8-308">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="290c8-308">**Not ready**</span></span>

<span data-ttu-id="290c8-309">Tiene los valores predeterminados de seguridad activados.</span><span class="sxs-lookup"><span data-stu-id="290c8-309">You have Security defaults turned on.</span></span> <span data-ttu-id="290c8-310">Desactivar los valores predeterminados de seguridad y configurar directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="290c8-310">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="290c8-311">Para obtener más información, consulte [directivas de acceso condicional comunes](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="290c8-311">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="290c8-312">Restablecimiento de contraseña de autoservicio</span><span class="sxs-lookup"><span data-stu-id="290c8-312">Self-service Password Reset</span></span>

<span data-ttu-id="290c8-313">El restablecimiento de contraseña de autoservicio (SSPR) debe estar habilitado para todos los usuarios, excepto las cuentas de servicio de escritorio administradas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-313">Self-service Password Reset (SSPR) should be enabled for all users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="290c8-314">Para obtener más información, vea [Tutorial: permitir a los usuarios desbloquear su cuenta o restablecer contraseñas con el restablecimiento de contraseña de autoservicio de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="290c8-314">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="290c8-315">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-315">**Advisory**</span></span>

<span data-ttu-id="290c8-316">Asegúrese de que la configuración de SSPR **seleccionada** incluye dispositivos de escritorio administrados por Microsoft, pero excluye las cuentas de servicio de escritorio administradas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-316">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="290c8-317">Las cuentas de servicio de escritorio administradas de Microsoft no pueden funcionar como se esperaba cuando SSPR está habilitado.</span><span class="sxs-lookup"><span data-stu-id="290c8-317">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="290c8-318">Rol de usuario estándar</span><span class="sxs-lookup"><span data-stu-id="290c8-318">Standard user role</span></span>

<span data-ttu-id="290c8-319">Excepto los usuarios a los que se han asignado roles de Azure AD de administrador global y de administrador de dispositivos, los usuarios de escritorio administrados de Microsoft serán usuarios estándar sin privilegios de administrador local.</span><span class="sxs-lookup"><span data-stu-id="290c8-319">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="290c8-320">A todos los demás usuarios se les asignará una función de usuario estándar cuando inicien su dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-320">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="290c8-321">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-321">**Advisory**</span></span>

<span data-ttu-id="290c8-322">Los usuarios de escritorio administrados de Microsoft no tendrán privilegios de administrador local en sus dispositivos de escritorio administrados por Microsoft tras la inscripción.</span><span class="sxs-lookup"><span data-stu-id="290c8-322">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="290c8-323">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="290c8-323">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="290c8-324">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="290c8-324">OneDrive for Business</span></span>

<span data-ttu-id="290c8-325">La opción **permitir sincronización solo en equipos Unidos a dominios específicos** entrará en conflicto con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="290c8-325">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="290c8-326">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="290c8-326">**Advisory**</span></span>

<span data-ttu-id="290c8-327">Está usando la opción **permitir sincronización solo en equipos Unidos a dominios específicos** .</span><span class="sxs-lookup"><span data-stu-id="290c8-327">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="290c8-328">Esta configuración no funcionará con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="290c8-328">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="290c8-329">Deshabilite esta opción y, en su lugar, configure OneDrive para la empresa para usar una directiva de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="290c8-329">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="290c8-330">Consulte [planear una implementación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="290c8-330">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

