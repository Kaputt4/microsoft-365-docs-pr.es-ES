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
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656156"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="099d2-104">Solucionar problemas encontrados por la herramienta de evaluación de preparación</span><span class="sxs-lookup"><span data-stu-id="099d2-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="099d2-105">Para cada comprobación, la herramienta informará de uno de los tres resultados posibles:</span><span class="sxs-lookup"><span data-stu-id="099d2-105">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="099d2-106">Resultado</span><span class="sxs-lookup"><span data-stu-id="099d2-106">Result</span></span>  |<span data-ttu-id="099d2-107">Significado</span><span class="sxs-lookup"><span data-stu-id="099d2-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="099d2-108">Listo</span><span class="sxs-lookup"><span data-stu-id="099d2-108">Ready</span></span>     | <span data-ttu-id="099d2-109">No es necesario realizar ninguna acción antes de completar la inscripción.</span><span class="sxs-lookup"><span data-stu-id="099d2-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="099d2-110">Consejo</span><span class="sxs-lookup"><span data-stu-id="099d2-110">Advisory</span></span>    | <span data-ttu-id="099d2-111">Siga los pasos de la herramienta o este artículo para obtener la mejor experiencia con la inscripción y para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="099d2-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="099d2-112">*Puede* completar la inscripción, pero debe solucionar estos problemas antes de implementar el primer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="099d2-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="099d2-113">No preparado</span><span class="sxs-lookup"><span data-stu-id="099d2-113">Not ready</span></span> | <span data-ttu-id="099d2-114">*Se producirá un error en la inscripción si no soluciona estos problemas.*</span><span class="sxs-lookup"><span data-stu-id="099d2-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="099d2-115">Siga los pasos de la herramienta o este artículo para resolverlos.</span><span class="sxs-lookup"><span data-stu-id="099d2-115">Follow the steps in the tool or this article to resolve them.</span></span>        |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="099d2-116">Configuración de Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="099d2-116">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="099d2-117">Perfil de implementación de piloto automático</span><span class="sxs-lookup"><span data-stu-id="099d2-117">Autopilot deployment profile</span></span>

<span data-ttu-id="099d2-118">No debe tener ningún perfil de AutoPilot existente destinado a grupos dinámicos o asignados que use el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-118">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="099d2-119">Microsoft Managed Desktop usa AutoPilot para aprovisionar nuevos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="099d2-119">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="099d2-120">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-120">**Not ready**</span></span>

<span data-ttu-id="099d2-121">Tiene un perfil de AutoPilot asignado a todos los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="099d2-121">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="099d2-122">Para conocer los pasos, vea [inscribir dispositivos Windows en Intune mediante Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="099d2-122">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="099d2-123">Después de la inscripción de escritorio administrada de Microsoft, establezca su Directiva de AutoPilot para excluir los **dispositivos del área de trabajo modernos: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="099d2-123">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="099d2-124">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-124">**Advisory**</span></span>

<span data-ttu-id="099d2-125">Asegúrese de que los perfiles de AutoPilot están destinados a un grupo de Azure AD asignado o dinámico que no incluye los dispositivos de escritorio administrados por Microsoft que se crearán durante la inscripción.</span><span class="sxs-lookup"><span data-stu-id="099d2-125">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="099d2-126">Para conocer los pasos, vea [inscribir dispositivos Windows en Intune mediante Windows AutoPilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="099d2-126">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="099d2-127">Después de la inscripción de escritorio administrada de Microsoft, establezca su Directiva de AutoPilot para excluir los **dispositivos del área de trabajo modernos: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="099d2-127">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="099d2-128">Conectores de certificados</span><span class="sxs-lookup"><span data-stu-id="099d2-128">Certificate connectors</span></span>

<span data-ttu-id="099d2-129">Si tiene algún conector de certificados usado por los dispositivos que desea inscribir en el escritorio administrado de Microsoft, los conectores no pueden tener errores.</span><span class="sxs-lookup"><span data-stu-id="099d2-129">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="099d2-130">Solo uno de los siguientes avisos se aplicará a su situación, por lo que debe comprobarlos cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="099d2-130">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="099d2-131">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-131">**Advisory**</span></span>

<span data-ttu-id="099d2-132">No hay conectores de certificado presentes.</span><span class="sxs-lookup"><span data-stu-id="099d2-132">No certificate connectors are present.</span></span> <span data-ttu-id="099d2-133">Es posible que no necesite ningún conector, pero debe evaluar si es posible que necesite alguna conectividad de red para los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-133">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="099d2-134">Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="099d2-134">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="099d2-135">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-135">**Advisory**</span></span>

<span data-ttu-id="099d2-136">Al menos un conector de certificado tiene un error.</span><span class="sxs-lookup"><span data-stu-id="099d2-136">At least one certificate connector has an error.</span></span> <span data-ttu-id="099d2-137">Si necesita este conector para la conectividad con dispositivos de escritorio administrados por Microsoft, debe resolver el error.</span><span class="sxs-lookup"><span data-stu-id="099d2-137">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="099d2-138">Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="099d2-138">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="099d2-139">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-139">**Advisory**</span></span>

<span data-ttu-id="099d2-140">Tiene al menos un conector de certificados y no se ha notificado ningún error.</span><span class="sxs-lookup"><span data-stu-id="099d2-140">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="099d2-141">Sin embargo, es posible que deba crear un perfil para volver a usar el conector para dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-141">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="099d2-142">Para obtener más información, vea [preparar certificados y perfiles de red para el escritorio administrado por Microsoft](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="099d2-142">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="099d2-143">Directivas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="099d2-143">Conditional access policies</span></span>

<span data-ttu-id="099d2-144">Las directivas de acceso condicional en su organización de Azure AD no deben dirigirse a ningún usuario de escritorio de Microsoft Manage.</span><span class="sxs-lookup"><span data-stu-id="099d2-144">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="099d2-145">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-145">**Not ready**</span></span>

<span data-ttu-id="099d2-146">Tiene al menos una directiva de acceso condicional dirigida a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="099d2-146">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="099d2-147">Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya el grupo de Azure AD de las cuentas de servicio de escritorio administrado por Microsoft que se crearán en la inscripción.</span><span class="sxs-lookup"><span data-stu-id="099d2-147">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="099d2-148">Para conocer los pasos, consulte el [acceso condicional: usuarios y grupos](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="099d2-148">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="099d2-149">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-149">**Advisory**</span></span>

<span data-ttu-id="099d2-150">Asegúrese de que las directivas de acceso condicional que haya excluido excluyan el grupo de Azure AD de las **cuentas de servicio del lugar de trabajo moderno** .</span><span class="sxs-lookup"><span data-stu-id="099d2-150">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="099d2-151">Para conocer los pasos, consulte [ajustar el acceso condicional](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="099d2-151">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="099d2-152">El grupo de Azure AD de las **cuentas de servicio del lugar de trabajo modernos** es un grupo dinámico que creamos para el servicio al inscribirse.</span><span class="sxs-lookup"><span data-stu-id="099d2-152">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="099d2-153">Tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="099d2-153">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="099d2-154">Para obtener más información acerca de estas cuentas de servicio, consulte [Standard Operations Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="099d2-154">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="099d2-155">Directivas de cumplimiento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="099d2-155">Device Compliance policies</span></span>

<span data-ttu-id="099d2-156">Las directivas de cumplimiento de dispositivos de Intune en su organización de Azure AD no deben dirigirse a ningún usuario de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-156">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="099d2-157">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-157">**Not ready**</span></span>

<span data-ttu-id="099d2-158">Tiene al menos una directiva de cumplimiento que tiene como objetivo todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="099d2-158">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="099d2-159">Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún usuario de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-159">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="099d2-160">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="099d2-160">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="099d2-161">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-161">**Advisory**</span></span>

<span data-ttu-id="099d2-162">Asegúrese de que las directivas de cumplimiento que tenga no incluyan ningún usuario de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-162">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="099d2-163">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="099d2-163">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="099d2-164">Directivas de configuración de dispositivo</span><span class="sxs-lookup"><span data-stu-id="099d2-164">Device Configuration policies</span></span>

<span data-ttu-id="099d2-165">Las directivas de configuración de dispositivo de Intune en la organización de Azure AD no deben dirigirse a ningún usuario o dispositivo de escritorio de Microsoft Manage.</span><span class="sxs-lookup"><span data-stu-id="099d2-165">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="099d2-166">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-166">**Not ready**</span></span>

<span data-ttu-id="099d2-167">Tiene al menos una directiva de configuración que tiene como objetivo todos los usuarios, todos los dispositivos o ambos.</span><span class="sxs-lookup"><span data-stu-id="099d2-167">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="099d2-168">Restablezca la Directiva para dirigirse a un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-168">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="099d2-169">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="099d2-169">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="099d2-170">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-170">**Advisory**</span></span>

<span data-ttu-id="099d2-171">Asegúrese de que las directivas de cumplimiento que tenga no incluyan ningún usuario o dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-171">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="099d2-172">Para conocer los pasos, consulte [crear una directiva de cumplimiento en Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="099d2-172">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="099d2-173">Restricciones de tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="099d2-173">Device type restrictions</span></span>

<span data-ttu-id="099d2-174">Los dispositivos de escritorio administrados por Microsoft deben estar autorizados para inscribirse en Intune.</span><span class="sxs-lookup"><span data-stu-id="099d2-174">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="099d2-175">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-175">**Not ready**</span></span>

<span data-ttu-id="099d2-176">Siga los pasos de [establecer restricciones de inscripción](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) para cambiar la configuración a **permitir**.</span><span class="sxs-lookup"><span data-stu-id="099d2-176">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="099d2-177">Página de estado de inscripción</span><span class="sxs-lookup"><span data-stu-id="099d2-177">Enrollment Status Page</span></span>

<span data-ttu-id="099d2-178">Actualmente tiene la página de estado de inscripción (ESP) habilitada.</span><span class="sxs-lookup"><span data-stu-id="099d2-178">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="099d2-179">Si está participando en la versión preliminar pública de esta característica, puede omitir este elemento.</span><span class="sxs-lookup"><span data-stu-id="099d2-179">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="099d2-180">Para obtener más información, vea [experiencia de primera ejecución con AutoPilot y página de estado de inscripción](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="099d2-180">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="099d2-181">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-181">**Not ready**</span></span>

<span data-ttu-id="099d2-182">Tiene el perfil predeterminado ESP configurado para mostrar el progreso de la configuración de la **aplicación y el perfil**.</span><span class="sxs-lookup"><span data-stu-id="099d2-182">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="099d2-183">Para deshabilitar esta configuración, siga los pasos de la [Página configurar el estado de inscripción](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="099d2-183">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="099d2-184">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-184">**Advisory**</span></span>

<span data-ttu-id="099d2-185">Asegúrese de que los perfiles que tienen la configuración **Mostrar progreso de configuración de aplicación y perfil** no se asignan a ningún grupo de Azure ad que incluya dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-185">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="099d2-186">Para obtener más información, consulte [configurar la página de estado de inscripción](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="099d2-186">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="099d2-187">Inscripción de Intune</span><span class="sxs-lookup"><span data-stu-id="099d2-187">Intune enrollment</span></span>

<span data-ttu-id="099d2-188">Los dispositivos con Windows 10 en la organización de Azure AD deben inscribirse automáticamente en Intune.</span><span class="sxs-lookup"><span data-stu-id="099d2-188">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="099d2-189">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-189">**Not ready**</span></span>

<span data-ttu-id="099d2-190">Los usuarios de la organización de Azure AD no se inscriben automáticamente en Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="099d2-190">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="099d2-191">Cambie el **ámbito de usuario** de MDM a **todos o todos**.</span><span class="sxs-lookup"><span data-stu-id="099d2-191">Change the MDM User scope to **Some** or **All**.</span></span> <span data-ttu-id="099d2-192">Si elige.</span><span class="sxs-lookup"><span data-stu-id="099d2-192">If you choose.</span></span> <span data-ttu-id="099d2-193">Algunos \* \*, regresan después de la inscripción y seleccionan el **lugar de trabajo moderno: todos los** grupos de Azure ad para los **grupos**.</span><span class="sxs-lookup"><span data-stu-id="099d2-193">Some\*\*, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="099d2-194">Microsoft Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="099d2-194">Microsoft Store for Business</span></span>

<span data-ttu-id="099d2-195">Usamos Microsoft Store for Business para que pueda descargar el portal de la empresa para implementar algunas aplicaciones, como Microsoft Project y Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="099d2-195">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="099d2-196">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-196">**Not ready**</span></span>

<span data-ttu-id="099d2-197">Microsoft Store para empresas ya no está habilitado o no está sincronizado con Intune.</span><span class="sxs-lookup"><span data-stu-id="099d2-197">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="099d2-198">Para obtener más información, consulte [How to Manage Volume adquiried apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) e [install Intune Company Portal in on Devices](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="099d2-198">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="099d2-199">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="099d2-199">Multi-factor authentication</span></span>

<span data-ttu-id="099d2-200">La autenticación multifactor no se debe aplicar por accidente a las cuentas de servicio de escritorio administradas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-200">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="099d2-201">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-201">**Not ready**</span></span>

<span data-ttu-id="099d2-202">Tiene algunas directivas de multi-factor Authentication (MFA) establecidas como "necesarias" para las directivas de acceso condicional asignadas a todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="099d2-202">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="099d2-203">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-203">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="099d2-204">Para obtener más información, consulte [directivas de acceso condicional](#conditional-access-policies) y [acceso condicional: solicitar MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="099d2-204">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="099d2-205">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-205">**Advisory**</span></span>

<span data-ttu-id="099d2-206">Asegúrese de que las directivas de acceso condicional que requieran MFA excluyan el **lugar de trabajo moderno: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="099d2-206">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="099d2-207">Para obtener más información, consulte [directivas de acceso condicional](#conditional-access-policies) y [acceso condicional: solicitar MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="099d2-207">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="099d2-208">El **área de trabajo moderna: todo** grupo de Azure ad es un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="099d2-208">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>



### <a name="powershell-scripts"></a><span data-ttu-id="099d2-209">Scripts de PowerShell</span><span class="sxs-lookup"><span data-stu-id="099d2-209">PowerShell scripts</span></span>

<span data-ttu-id="099d2-210">Los scripts de Windows PowerShell no se pueden asignar de una manera que se dirija a los dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-210">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="099d2-211">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-211">**Advisory**</span></span>

<span data-ttu-id="099d2-212">Asegúrese de que los scripts de Windows PowerShell de la organización de Azure AD no tienen como objetivo ningún usuario o dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-212">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="099d2-213">Para obtener más información, vea [usar scripts de PowerShell en dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="099d2-213">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="099d2-214">Región</span><span class="sxs-lookup"><span data-stu-id="099d2-214">Region</span></span>

<span data-ttu-id="099d2-215">Su región debe ser compatible con el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-215">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="099d2-216">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-216">**Not ready**</span></span>

<span data-ttu-id="099d2-217">Actualmente, la región de la organización de Azure AD no es compatible con el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-217">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="099d2-218">Para obtener más información, consulte [regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="099d2-218">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="099d2-219">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-219">**Advisory**</span></span>

<span data-ttu-id="099d2-220">Uno o más de los países en los que se encuentra su organización de Azure AD no es compatible con el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-220">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="099d2-221">Para obtener más información, consulte [regiones e idiomas admitidos por Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="099d2-221">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="099d2-222">Líneas de base de seguridad</span><span class="sxs-lookup"><span data-stu-id="099d2-222">Security baselines</span></span>

<span data-ttu-id="099d2-223">Las directivas de línea de base de seguridad no deben dirigirse a ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-223">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="099d2-224">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-224">**Not ready**</span></span>

<span data-ttu-id="099d2-225">Tiene un perfil de línea de base de seguridad destinado a todos los usuarios, todos los dispositivos o ambos.</span><span class="sxs-lookup"><span data-stu-id="099d2-225">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="099d2-226">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-226">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="099d2-227">Para conocer los pasos, consulte [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="099d2-227">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="099d2-228">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-228">**Advisory**</span></span>

<span data-ttu-id="099d2-229">Asegúrese de que todas las directivas de línea base de seguridad que haya excluido sean dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-229">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="099d2-230">Para conocer los pasos, consulte [usar líneas de base de seguridad para configurar dispositivos Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="099d2-230">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="099d2-231">Los **dispositivos modernos del área de trabajo: todos los** grupos de Azure ad son un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="099d2-231">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="099d2-232">Aplicaciones de Windows</span><span class="sxs-lookup"><span data-stu-id="099d2-232">Windows apps</span></span>

<span data-ttu-id="099d2-233">Revise las aplicaciones que desea que tengan los usuarios de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-233">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="099d2-234">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-234">**Advisory**</span></span>

<span data-ttu-id="099d2-235">Debe preparar un inventario de las aplicaciones que desea que tengan los usuarios de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-235">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="099d2-236">Asegúrese de que estas aplicaciones se pueden implementar con Intune.</span><span class="sxs-lookup"><span data-stu-id="099d2-236">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="099d2-237">Para obtener más información, vea [aplicaciones en el escritorio administrado de Microsoft](apps.md).</span><span class="sxs-lookup"><span data-stu-id="099d2-237">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="099d2-238">Puede pedir a su representante de su cuenta de Microsoft una consulta en Microsoft Endpoint Configuration Manager para identificar las aplicaciones que están preparadas para la migración a Intune o el ajuste necesario.</span><span class="sxs-lookup"><span data-stu-id="099d2-238">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="099d2-239">Windows Hello para empresas</span><span class="sxs-lookup"><span data-stu-id="099d2-239">Windows Hello for Business</span></span>

<span data-ttu-id="099d2-240">El escritorio administrado de Microsoft requiere que Windows Hello para empresas esté habilitado.</span><span class="sxs-lookup"><span data-stu-id="099d2-240">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="099d2-241">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-241">**Not ready**</span></span>

<span data-ttu-id="099d2-242">Windows Hello para empresas está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="099d2-242">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="099d2-243">Habilítelo siguiendo los pasos de [crear una directiva de Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="099d2-243">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="099d2-244">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-244">**Advisory**</span></span>

<span data-ttu-id="099d2-245">Windows Hello para empresas no está configurado.</span><span class="sxs-lookup"><span data-stu-id="099d2-245">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="099d2-246">Para habilitarla, siga los pasos de [crear una directiva de Windows Hello para empresas](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="099d2-246">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="099d2-247">Anillos de actualización de Windows 10</span><span class="sxs-lookup"><span data-stu-id="099d2-247">Windows 10 update rings</span></span>

<span data-ttu-id="099d2-248">La Directiva "Windows 10 Update Ring" en Intune no debe dirigirse a ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-248">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="099d2-249">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-249">**Not ready**</span></span>

<span data-ttu-id="099d2-250">Tiene una directiva "actualizar anillo" que tiene como objetivo todos los dispositivos, todos los usuarios o ambos.</span><span class="sxs-lookup"><span data-stu-id="099d2-250">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="099d2-251">Cambie la Directiva para usar una asignación que tenga como destino un grupo específico de Azure AD que no incluya ningún dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-251">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="099d2-252">Para conocer los pasos, consulte [administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="099d2-252">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="099d2-253">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-253">**Advisory**</span></span>

<span data-ttu-id="099d2-254">Asegúrese de que todas las directivas de Update Ring que tiene excluyan el **lugar de trabajo moderno: todos los grupos de** Azure ad.</span><span class="sxs-lookup"><span data-stu-id="099d2-254">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="099d2-255">Para conocer los pasos, consulte [administrar las actualizaciones de software de Windows 10 en Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="099d2-255">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="099d2-256">Los **dispositivos modernos del área de trabajo: todos los** grupos de Azure ad son un grupo dinámico que creamos al inscribirse en el escritorio administrado de Microsoft, por lo que tendrá que volver a excluir este grupo después de la inscripción.</span><span class="sxs-lookup"><span data-stu-id="099d2-256">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="099d2-257">Configuración de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="099d2-257">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="099d2-258">Suscripciones ad hoc</span><span class="sxs-lookup"><span data-stu-id="099d2-258">Ad hoc subscriptions</span></span>

<span data-ttu-id="099d2-259">Aconseja comprobar una opción que (si se establece en "false") impedir que la itinerancia del estado de la empresa funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="099d2-259">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="099d2-260">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-260">**Advisory**</span></span>

<span data-ttu-id="099d2-261">Asegúrese de que **AllowAdHocSubscriptions** está establecido en **true**.</span><span class="sxs-lookup"><span data-stu-id="099d2-261">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="099d2-262">De lo contrario, es posible que la itinerancia del estado de la empresa no funcione.</span><span class="sxs-lookup"><span data-stu-id="099d2-262">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="099d2-263">Para obtener más información, vea [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="099d2-263">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="099d2-264">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="099d2-264">Enterprise State Roaming</span></span>

<span data-ttu-id="099d2-265">La itinerancia del estado de la empresa debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="099d2-265">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="099d2-266">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-266">**Advisory**</span></span>

<span data-ttu-id="099d2-267">Asegúrese de que la itinerancia del estado de la empresa esté habilitada para todos o para **los** grupos **seleccionados** .</span><span class="sxs-lookup"><span data-stu-id="099d2-267">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="099d2-268">Para obtener más información, consulte [Habilitar la itinerancia del estado de la empresa en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="099d2-268">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="099d2-269">Licencias</span><span class="sxs-lookup"><span data-stu-id="099d2-269">Licenses</span></span>

<span data-ttu-id="099d2-270">Se necesita un número de licencias para usar el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-270">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="099d2-271">**No está listo**</span><span class="sxs-lookup"><span data-stu-id="099d2-271">**Not Ready**</span></span>

<span data-ttu-id="099d2-272">No tiene todas las licencias que necesita para usar Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="099d2-272">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="099d2-273">Para obtener más información, consulte [tecnologías de escritorio administradas de Microsoft](../intro/technologies.md) y más información [sobre licencias](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="099d2-273">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="099d2-274">Nombres de cuenta de seguridad</span><span class="sxs-lookup"><span data-stu-id="099d2-274">Security account names</span></span>

<span data-ttu-id="099d2-275">Algunos nombres de cuentas de seguridad podrían entrar en conflicto con los creados por el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-275">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="099d2-276">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-276">**Not ready**</span></span>

<span data-ttu-id="099d2-277">Tiene al menos un nombre de cuenta que entrará en conflicto con los creados por el escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-277">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="099d2-278">Trabaje con el representante de su cuenta de Microsoft para excluir estos nombres de cuenta.</span><span class="sxs-lookup"><span data-stu-id="099d2-278">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="099d2-279">Roles de administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="099d2-279">Security administrator roles</span></span>

<span data-ttu-id="099d2-280">Los usuarios con determinados roles de seguridad deben tener los asignados en Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="099d2-280">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="099d2-281">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-281">**Advisory**</span></span>

<span data-ttu-id="099d2-282">Si tiene cualquiera de estos roles asignados en su organización de Azure AD, asegúrese de que también tengan estos roles asignados en Microsoft defender para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="099d2-282">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="099d2-283">De lo contrario, los administradores con estos roles no podrán obtener acceso al portal de administración.</span><span class="sxs-lookup"><span data-stu-id="099d2-283">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="099d2-284">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="099d2-284">Security Reader</span></span>
- <span data-ttu-id="099d2-285">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="099d2-285">Security Operator</span></span>
- <span data-ttu-id="099d2-286">Lector global</span><span class="sxs-lookup"><span data-stu-id="099d2-286">Global Reader</span></span>

<span data-ttu-id="099d2-287">Para obtener más información, vea [Create and Manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="099d2-287">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="099d2-288">Seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="099d2-288">Security default</span></span>

<span data-ttu-id="099d2-289">Los valores predeterminados de seguridad de Azure Active Directory impedirán que Microsoft administre el escritorio de sus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="099d2-289">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="099d2-290">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-290">**Not ready**</span></span>

<span data-ttu-id="099d2-291">Tiene los valores predeterminados de seguridad activados.</span><span class="sxs-lookup"><span data-stu-id="099d2-291">You have Security defaults turned on.</span></span> <span data-ttu-id="099d2-292">Desactivar los valores predeterminados de seguridad y configurar directivas de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="099d2-292">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="099d2-293">Para obtener más información, consulte [directivas de acceso condicional comunes](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="099d2-293">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="099d2-294">Restablecimiento de contraseña de autoservicio</span><span class="sxs-lookup"><span data-stu-id="099d2-294">Self-service Password Reset</span></span>

<span data-ttu-id="099d2-295">Debe estar habilitado el restablecimiento de contraseña de autoservicio (SSPR).</span><span class="sxs-lookup"><span data-stu-id="099d2-295">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="099d2-296">**No preparado**</span><span class="sxs-lookup"><span data-stu-id="099d2-296">**Not ready**</span></span>

<span data-ttu-id="099d2-297">SSPR debe estar habilitado para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="099d2-297">SSPR must be enabled for all users.</span></span> <span data-ttu-id="099d2-298">Si no es así, las cuentas de servicio de escritorio administradas de Microsoft no pueden funcionar.</span><span class="sxs-lookup"><span data-stu-id="099d2-298">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="099d2-299">Para obtener más información, vea [Tutorial: permitir a los usuarios desbloquear su cuenta o restablecer contraseñas con el restablecimiento de contraseña de autoservicio de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="099d2-299">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="099d2-300">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-300">**Advisory**</span></span>

<span data-ttu-id="099d2-301">Asegúrese de que la configuración de SSPR **seleccionada** incluye dispositivos de escritorio administrados por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-301">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

### <a name="standard-user-role"></a><span data-ttu-id="099d2-302">Rol de usuario estándar</span><span class="sxs-lookup"><span data-stu-id="099d2-302">Standard user role</span></span>

<span data-ttu-id="099d2-303">Los usuarios de escritorio administrados de Microsoft deben ser usuarios estándar sin privilegios de administrador local.</span><span class="sxs-lookup"><span data-stu-id="099d2-303">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="099d2-304">Se les asignará un rol de usuario estándar cuando inicien su dispositivo de escritorio administrado por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-304">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="099d2-305">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-305">**Advisory**</span></span>

<span data-ttu-id="099d2-306">Los usuarios de escritorio administrado de Microsoft no deben tener privilegios de administrador local antes de inscribirse.</span><span class="sxs-lookup"><span data-stu-id="099d2-306">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="099d2-307">Aplicaciones de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="099d2-307">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="099d2-308">OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="099d2-308">OneDrive for Business</span></span>

<span data-ttu-id="099d2-309">La opción **permitir sincronización solo en equipos Unidos a dominios específicos** entrará en conflicto con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="099d2-309">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="099d2-310">**Consejo**</span><span class="sxs-lookup"><span data-stu-id="099d2-310">**Advisory**</span></span>

<span data-ttu-id="099d2-311">Está usando la opción **permitir sincronización solo en equipos Unidos a dominios específicos** .</span><span class="sxs-lookup"><span data-stu-id="099d2-311">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="099d2-312">Esta configuración no funcionará con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="099d2-312">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="099d2-313">Deshabilite esta opción y, en su lugar, configure OneDrive para la empresa para usar una directiva de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="099d2-313">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="099d2-314">Consulte [planear una implementación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="099d2-314">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

