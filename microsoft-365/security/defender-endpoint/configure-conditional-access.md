---
title: Configurar el acceso condicional en Microsoft Defender para el extremo
description: Obtenga información sobre los pasos que debe realizar en Intune, Centro de seguridad de Microsoft Defender y Azure para implementar el acceso condicional
keywords: acceso condicional, condicional, acceso, riesgo de dispositivo, nivel de riesgo, integración, integración de Intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ceb69d59dc5208c0908e33d0880d9352562ec140
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843979"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="bd4b6-104">Configurar el acceso condicional en Microsoft Defender para el extremo</span><span class="sxs-lookup"><span data-stu-id="bd4b6-104">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd4b6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bd4b6-105">**Applies to:**</span></span>
- [<span data-ttu-id="bd4b6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bd4b6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bd4b6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd4b6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bd4b6-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="bd4b6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bd4b6-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="bd4b6-110">En esta sección se le guían todos los pasos que debe seguir para implementar correctamente el acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-110">This section guides you through all the steps you need to take to properly implement Conditional Access.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="bd4b6-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="bd4b6-111">Before you begin</span></span>
>[!WARNING]
><span data-ttu-id="bd4b6-112">Es importante tener en cuenta que los dispositivos registrados de Azure AD no se admiten en este escenario.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-112">It's important to note that Azure AD registered devices is not supported in this scenario.</span></span></br>
><span data-ttu-id="bd4b6-113">Solo se admiten dispositivos inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-113">Only Intune enrolled devices are supported.</span></span>


<span data-ttu-id="bd4b6-114">Debes asegurarte de que todos los dispositivos estén inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-114">You need to make sure that all your devices are enrolled in Intune.</span></span> <span data-ttu-id="bd4b6-115">Puede usar cualquiera de las siguientes opciones para inscribir dispositivos en Intune:</span><span class="sxs-lookup"><span data-stu-id="bd4b6-115">You can use any of the following options to enroll devices in Intune:</span></span>


- <span data-ttu-id="bd4b6-116">Administrador de TI: para obtener más información sobre cómo habilitar la inscripción automática, [vea Windows Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="bd4b6-116">IT Admin: For more information on how to enabling auto-enrollment, see [Windows Enrollment](/intune/windows-enroll#enable-windows-10-automatic-enrollment)</span></span>
- <span data-ttu-id="bd4b6-117">Usuario final: para obtener más información sobre cómo inscribir el dispositivo Windows 10 en Intune, consulte Inscribir el [dispositivo Windows 10 en Intune](/intune/quickstart-enroll-windows-device)</span><span class="sxs-lookup"><span data-stu-id="bd4b6-117">End-user: For more information on how to enroll your Windows 10 device in Intune, see [Enroll your Windows 10 device in Intune](/intune/quickstart-enroll-windows-device)</span></span>
- <span data-ttu-id="bd4b6-118">Alternativa de usuario final: para obtener más información sobre cómo unirse a un dominio de Azure AD, vea [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span><span class="sxs-lookup"><span data-stu-id="bd4b6-118">End-user alternative: For more information on joining an Azure AD domain, see [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span>



<span data-ttu-id="bd4b6-119">Hay pasos que deberá seguir en Centro de seguridad de Microsoft Defender, el portal de Intune y el portal de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-119">There are steps you'll need to take in Microsoft Defender Security Center, the Intune portal, and Azure AD portal.</span></span>

<span data-ttu-id="bd4b6-120">Es importante tener en cuenta los roles necesarios para tener acceso a estos portales e implementar el acceso condicional:</span><span class="sxs-lookup"><span data-stu-id="bd4b6-120">It's important to note the required roles to access these portals and implement Conditional access:</span></span>
- <span data-ttu-id="bd4b6-121">**Centro de seguridad de Microsoft Defender:** deberá iniciar sesión en el portal con un rol de administrador global para activar la integración.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-121">**Microsoft Defender Security Center** - You'll need to sign into the portal with a global administrator role to turn on the integration.</span></span>
- <span data-ttu-id="bd4b6-122">**Intune:** deberá iniciar sesión en el portal con derechos de administrador de seguridad con permisos de administración.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-122">**Intune** - You'll need to sign in to the portal with security administrator rights with management permissions.</span></span> 
- <span data-ttu-id="bd4b6-123">**Portal de Azure AD:** deberá iniciar sesión como administrador global, administrador de seguridad o administrador de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-123">**Azure AD portal** - You'll need to sign in as a global administrator, security administrator, or Conditional Access administrator.</span></span>


> [!NOTE]
> <span data-ttu-id="bd4b6-124">Necesitará un entorno Microsoft Intune, con Intune administrado y Azure AD unido a Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-124">You'll need a Microsoft Intune environment, with Intune managed and Azure AD joined Windows 10 devices.</span></span>

<span data-ttu-id="bd4b6-125">Siga estos pasos para habilitar el acceso condicional:</span><span class="sxs-lookup"><span data-stu-id="bd4b6-125">Take the following steps to enable Conditional Access:</span></span>
- <span data-ttu-id="bd4b6-126">Paso 1: Activar la conexión Microsoft Intune desde Centro de seguridad de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bd4b6-126">Step 1: Turn on the Microsoft Intune connection from Microsoft Defender Security Center</span></span>
- <span data-ttu-id="bd4b6-127">Paso 2: Activar la integración de Defender for Endpoint en Intune</span><span class="sxs-lookup"><span data-stu-id="bd4b6-127">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
- <span data-ttu-id="bd4b6-128">Paso 3: Crear la directiva de cumplimiento en Intune</span><span class="sxs-lookup"><span data-stu-id="bd4b6-128">Step 3: Create the compliance policy in Intune</span></span>
- <span data-ttu-id="bd4b6-129">Paso 4: Asignar la directiva</span><span class="sxs-lookup"><span data-stu-id="bd4b6-129">Step 4: Assign the policy</span></span> 
- <span data-ttu-id="bd4b6-130">Paso 5: Crear una directiva de acceso condicional de Azure AD</span><span class="sxs-lookup"><span data-stu-id="bd4b6-130">Step 5: Create an Azure AD Conditional Access policy</span></span>


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a><span data-ttu-id="bd4b6-131">Paso 1: Activar la conexión Microsoft Intune conexión</span><span class="sxs-lookup"><span data-stu-id="bd4b6-131">Step 1: Turn on the Microsoft Intune connection</span></span>
1. <span data-ttu-id="bd4b6-132">En el panel de navegación, **seleccione Configuración** características  >  **avanzadas Microsoft Intune**  >  **conexión**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-132">In the navigation pane, select **Settings** > **Advanced features** > **Microsoft Intune connection**.</span></span>
2. <span data-ttu-id="bd4b6-133">Alterna la Microsoft Intune a **On**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-133">Toggle the Microsoft Intune setting to **On**.</span></span>
3. <span data-ttu-id="bd4b6-134">Haga clic **en Guardar preferencias**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-134">Click **Save preferences**.</span></span>


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a><span data-ttu-id="bd4b6-135">Paso 2: Activar la integración de Defender for Endpoint en Intune</span><span class="sxs-lookup"><span data-stu-id="bd4b6-135">Step 2: Turn on the Defender for Endpoint integration in Intune</span></span>
1. <span data-ttu-id="bd4b6-136">Inicie sesión en el [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="bd4b6-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="bd4b6-137">Seleccione **Cumplimiento de**  >  **dispositivos ATP de Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-137">Select **Device compliance** > **Microsoft Defender ATP**.</span></span>
3. <span data-ttu-id="bd4b6-138">Establezca **Conectar Windows 10.0.15063+** para que Protección contra amenazas avanzada de Microsoft Defender en **On**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-138">Set **Connect Windows 10.0.15063+ devices to Microsoft Defender Advanced Threat Protection** to **On**.</span></span>
4. <span data-ttu-id="bd4b6-139">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-139">Click **Save**.</span></span>


### <a name="step-3-create-the-compliance-policy-in-intune"></a><span data-ttu-id="bd4b6-140">Paso 3: Crear la directiva de cumplimiento en Intune</span><span class="sxs-lookup"><span data-stu-id="bd4b6-140">Step 3: Create the compliance policy in Intune</span></span>
1. <span data-ttu-id="bd4b6-141">En [Azure Portal,](https://portal.azure.com)seleccione **Todos los servicios**, filtre en **Intune** y **seleccione Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-141">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="bd4b6-142">Seleccione **Directivas de cumplimiento de**  >    >  **dispositivos Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-142">Select **Device compliance** > **Policies** > **Create policy**.</span></span>
3. <span data-ttu-id="bd4b6-143">Escriba un **nombre** y **una descripción**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-143">Enter a **Name** and **Description**.</span></span>
4. <span data-ttu-id="bd4b6-144">En **Plataforma,** **seleccione Windows 10 y versiones posteriores**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-144">In **Platform**, select **Windows 10 and later**.</span></span>
5. <span data-ttu-id="bd4b6-145">En la **configuración estado del** dispositivo, establece Requerir que el dispositivo esté en el nivel de amenaza del dispositivo o en el nivel **que** prefieras:</span><span class="sxs-lookup"><span data-stu-id="bd4b6-145">In the **Device Health** settings, set **Require the device to be at or under the Device Threat Level** to your preferred level:</span></span>

   - <span data-ttu-id="bd4b6-146">**Protegido:** este nivel es el más seguro.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-146">**Secured**: This level is the most secure.</span></span> <span data-ttu-id="bd4b6-147">El dispositivo no puede tener amenazas existentes y seguir teniendo acceso a los recursos de la compañía.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-147">The device cannot have any existing threats and still access company resources.</span></span> <span data-ttu-id="bd4b6-148">Si se encuentra alguna amenaza, el dispositivo se evalúa como no compatible.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-148">If any threats are found, the device is evaluated as noncompliant.</span></span>
   - <span data-ttu-id="bd4b6-149">**Bajo:** el dispositivo es compatible si solo existen amenazas de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-149">**Low**: The device is compliant if only low-level threats exist.</span></span> <span data-ttu-id="bd4b6-150">Los dispositivos con niveles de amenazas medianos o altos no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-150">Devices with medium or high threat levels are not compliant.</span></span>
   - <span data-ttu-id="bd4b6-151">**Medium:** el dispositivo es compatible si las amenazas encontradas en el dispositivo son bajas o medianas.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-151">**Medium**: The device is compliant if the threats found on the device are low or medium.</span></span> <span data-ttu-id="bd4b6-152">Si se detectan amenazas de alto nivel, el dispositivo se determina como no compatible.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-152">If high-level threats are detected, the device is determined as noncompliant.</span></span>
   - <span data-ttu-id="bd4b6-153">**Alto:** este nivel es el menos seguro y permite todos los niveles de amenazas.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-153">**High**: This level is the least secure, and allows all threat levels.</span></span> <span data-ttu-id="bd4b6-154">Por lo tanto, los dispositivos que tienen niveles de amenazas altos, medianos o bajos se consideran compatibles.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-154">So devices that with high, medium or low threat levels are considered compliant.</span></span>

6. <span data-ttu-id="bd4b6-155">Seleccione **Aceptar** y **Crear** para guardar los cambios (y crear la directiva).</span><span class="sxs-lookup"><span data-stu-id="bd4b6-155">Select **OK**, and **Create** to save your changes (and create the policy).</span></span>

### <a name="step-4-assign-the-policy"></a><span data-ttu-id="bd4b6-156">Paso 4: Asignar la directiva</span><span class="sxs-lookup"><span data-stu-id="bd4b6-156">Step 4: Assign the policy</span></span>
1. <span data-ttu-id="bd4b6-157">En [Azure Portal,](https://portal.azure.com)seleccione **Todos los servicios**, filtre en **Intune** y **seleccione Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-157">In the [Azure portal](https://portal.azure.com), select **All services**, filter on **Intune**, and select **Microsoft Intune**.</span></span>
2. <span data-ttu-id="bd4b6-158">Selecciona **Directivas de cumplimiento**  >  **de** dispositivos> la directiva de cumplimiento de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-158">Select **Device compliance** > **Policies**> select your Microsoft Defender for Endpoint compliance policy.</span></span>
3. <span data-ttu-id="bd4b6-159">Seleccione **Asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-159">Select **Assignments**.</span></span>
4. <span data-ttu-id="bd4b6-160">Incluya o excluya los grupos de Azure AD para asignarles la directiva.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-160">Include or exclude your Azure AD groups to assign them the policy.</span></span>
5. <span data-ttu-id="bd4b6-161">Para implementar la directiva en los grupos, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-161">To deploy the policy to the groups, select **Save**.</span></span> <span data-ttu-id="bd4b6-162">Los dispositivos de usuario dirigidos por la directiva se evalúan para el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-162">The user devices targeted by the policy are evaluated for compliance.</span></span>

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="bd4b6-163">Paso 5: Crear una directiva de acceso condicional de Azure AD</span><span class="sxs-lookup"><span data-stu-id="bd4b6-163">Step 5: Create an Azure AD Conditional Access policy</span></span>
1. <span data-ttu-id="bd4b6-164">En [Azure Portal,](https://portal.azure.com)abra **Azure Active Directory**  >  **Acceso condicional** Nueva  >  **directiva**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-164">In the [Azure portal](https://portal.azure.com), open **Azure Active Directory** > **Conditional Access** > **New policy**.</span></span>
2. <span data-ttu-id="bd4b6-165">Escriba un nombre **de directiva** y seleccione Usuarios **y grupos**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-165">Enter a policy **Name**, and select **Users and groups**.</span></span> <span data-ttu-id="bd4b6-166">Use las opciones Incluir o Excluir para agregar los grupos para la directiva y seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-166">Use the Include or Exclude options to add your groups for the policy, and select **Done**.</span></span>
3. <span data-ttu-id="bd4b6-167">Selecciona **Aplicaciones en la** nube y elige qué aplicaciones proteger.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-167">Select **Cloud apps**, and choose which apps to protect.</span></span> <span data-ttu-id="bd4b6-168">Por ejemplo, elija **Seleccionar aplicaciones** y seleccione **Office 365 SharePoint Online** y **Office 365 Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-168">For example, choose **Select apps**, and select **Office 365 SharePoint Online** and **Office 365 Exchange Online**.</span></span> <span data-ttu-id="bd4b6-169">Seleccione **Listo** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-169">Select **Done** to save your changes.</span></span>

4. <span data-ttu-id="bd4b6-170">Selecciona **Condiciones**  >  **Aplicaciones cliente para** aplicar la directiva a aplicaciones y exploradores.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-170">Select **Conditions** > **Client apps** to apply the policy to apps and browsers.</span></span> <span data-ttu-id="bd4b6-171">Por ejemplo, seleccione **Sí** y, a continuación, habilite **Explorador** y **Aplicaciones móviles y clientes de escritorio.**</span><span class="sxs-lookup"><span data-stu-id="bd4b6-171">For example, select **Yes**, and then enable **Browser** and **Mobile apps and desktop clients**.</span></span> <span data-ttu-id="bd4b6-172">Seleccione **Listo** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-172">Select **Done** to save your changes.</span></span>

5. <span data-ttu-id="bd4b6-173">Selecciona **Conceder para** aplicar el acceso condicional en función del cumplimiento del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-173">Select **Grant** to apply Conditional Access based on device compliance.</span></span> <span data-ttu-id="bd4b6-174">Por ejemplo, seleccione **Conceder acceso Requerir** que el dispositivo se marque como  >  **compatible.**</span><span class="sxs-lookup"><span data-stu-id="bd4b6-174">For example, select **Grant access** > **Require device to be marked as compliant**.</span></span> <span data-ttu-id="bd4b6-175">Elija **Seleccionar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-175">Choose **Select** to save your changes.</span></span>

6. <span data-ttu-id="bd4b6-176">Seleccione **Habilitar directiva** y, a **continuación, Crear** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-176">Select **Enable policy**, and then **Create** to save your changes.</span></span>

<span data-ttu-id="bd4b6-177">Para obtener más información, vea [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="bd4b6-177">For more information, see [Enforce compliance for Microsoft Defender for Endpoint with Conditional Access in Intune](/intune/advanced-threat-protection).</span></span>

><span data-ttu-id="bd4b6-178">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="bd4b6-178">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bd4b6-179">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="bd4b6-179">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
