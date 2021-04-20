---
title: Laboratorio de evaluación de Microsoft Defender para puntos de conexión
description: Obtenga información sobre las capacidades de Microsoft Defender para puntos de conexión, ejecute simulaciones de ataques y vea cómo evita, detecta y corrige las amenazas.
keywords: evaluar mdatp, evaluación, laboratorio, simulación, windows 10, windows server 2019, laboratorio de evaluación
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2382281fbb975daa18ec21aabaf5acf8d3fbfb2f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893442"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="44e67-104">Laboratorio de evaluación de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="44e67-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="44e67-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="44e67-105">**Applies to:**</span></span>
- [<span data-ttu-id="44e67-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="44e67-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="44e67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44e67-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="44e67-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="44e67-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="44e67-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="44e67-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="44e67-110">La realización de una evaluación completa de productos de seguridad puede ser un proceso complejo que requiere una configuración de dispositivos y entornos engorrosos antes de poder realizar una simulación de ataque de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="44e67-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="44e67-111">Agregar a la complejidad es el desafío de realizar un seguimiento de dónde se reflejan las actividades de simulación, las alertas y los resultados durante la evaluación.</span><span class="sxs-lookup"><span data-stu-id="44e67-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="44e67-112">El laboratorio de evaluación de Microsoft Defender para endpoints está diseñado para eliminar las complejidades de la configuración de dispositivos y entornos para que puedas centrarte en evaluar las capacidades de la plataforma, ejecutar simulaciones y ver las características de prevención, detección y corrección en acción.</span><span class="sxs-lookup"><span data-stu-id="44e67-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="44e67-113">Con la experiencia de configuración simplificada, puede centrarse en ejecutar sus propios escenarios de prueba y las simulaciones pre-realizadas para ver el rendimiento de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="44e67-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="44e67-114">Tendrás acceso completo a las potentes capacidades de la plataforma, como investigaciones automatizadas, búsqueda avanzada y análisis de amenazas, lo que te permite probar la pila de protección completa que ofrece Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="44e67-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="44e67-115">Puede agregar dispositivos windows 10 o Windows Server 2019 que vienen preconfigurados para tener instaladas las versiones más recientes del sistema operativo y los componentes de seguridad adecuados, así como Office 2019 Standard.</span><span class="sxs-lookup"><span data-stu-id="44e67-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="44e67-116">También puedes instalar simuladores de amenazas.</span><span class="sxs-lookup"><span data-stu-id="44e67-116">You can also install threat simulators.</span></span> <span data-ttu-id="44e67-117">Defender for Endpoint se ha asociado con plataformas de simulación de amenazas líderes del sector para ayudarle a probar las capacidades de Defender for Endpoint sin tener que salir del portal.</span><span class="sxs-lookup"><span data-stu-id="44e67-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="44e67-118">Instale el simulador preferido, ejecute escenarios en el laboratorio de evaluación y vea al instante el rendimiento de la plataforma, todo disponible cómodamente sin costo adicional para usted.</span><span class="sxs-lookup"><span data-stu-id="44e67-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="44e67-119">También tendrás acceso conveniente a una amplia variedad de simulaciones a las que puedes acceder y ejecutar desde el catálogo de simulaciones.</span><span class="sxs-lookup"><span data-stu-id="44e67-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="44e67-120">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="44e67-120">Before you begin</span></span>
<span data-ttu-id="44e67-121">Tendrás que cumplir los requisitos de licencia [o](minimum-requirements.md#licensing-requirements) tener acceso de prueba a Microsoft Defender para endpoint para acceder al laboratorio de evaluación.</span><span class="sxs-lookup"><span data-stu-id="44e67-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="44e67-122">Debe tener permisos **administrar la configuración de** seguridad para:</span><span class="sxs-lookup"><span data-stu-id="44e67-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="44e67-123">Crear el laboratorio</span><span class="sxs-lookup"><span data-stu-id="44e67-123">Create the lab</span></span>
- <span data-ttu-id="44e67-124">Crear dispositivos</span><span class="sxs-lookup"><span data-stu-id="44e67-124">Create devices</span></span>
- <span data-ttu-id="44e67-125">Restablecer contraseña</span><span class="sxs-lookup"><span data-stu-id="44e67-125">Reset password</span></span>
- <span data-ttu-id="44e67-126">Crear simulaciones</span><span class="sxs-lookup"><span data-stu-id="44e67-126">Create simulations</span></span> 
 
<span data-ttu-id="44e67-127">Si habilitó el control de acceso basado en roles (RBAC) y creó al menos un grupo de máquinas, los usuarios deben tener acceso a Todos los grupos de máquinas.</span><span class="sxs-lookup"><span data-stu-id="44e67-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="44e67-128">Para obtener más información, vea [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="44e67-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="44e67-129">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="44e67-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="44e67-130">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="44e67-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="44e67-131">Introducción al laboratorio</span><span class="sxs-lookup"><span data-stu-id="44e67-131">Get started with the lab</span></span>
<span data-ttu-id="44e67-132">Puede acceder al laboratorio desde el menú.</span><span class="sxs-lookup"><span data-stu-id="44e67-132">You can access the lab from the menu.</span></span> <span data-ttu-id="44e67-133">En el menú de navegación, seleccione **Evaluación y tutoriales > Laboratorio de evaluación**.</span><span class="sxs-lookup"><span data-stu-id="44e67-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Imagen del laboratorio de evaluación en el menú](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="44e67-135">Según el tipo de estructura del entorno que selecciones, los dispositivos estarán disponibles para el número especificado de horas desde el día de la activación.</span><span class="sxs-lookup"><span data-stu-id="44e67-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="44e67-136">Cada entorno se aprovisiona con un conjunto limitado de dispositivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="44e67-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="44e67-137">Cuando hayas usado los dispositivos aprovisionados, no se proporciona ningún dispositivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="44e67-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="44e67-138">Un dispositivo eliminado no actualiza el recuento de dispositivos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="44e67-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="44e67-139">Ya no puede usar el laboratorio cuando se han usado los recursos.</span><span class="sxs-lookup"><span data-stu-id="44e67-139">You can no longer use the lab when the resources have been used up.</span></span> <span data-ttu-id="44e67-140">No se restablece ni se actualiza.</span><span class="sxs-lookup"><span data-stu-id="44e67-140">It does not reset nor refresh.</span></span>
>- <span data-ttu-id="44e67-141">Es aconsejable usar los recursos cuidadosamente. Los recursos de laboratorio son limitados.</span><span class="sxs-lookup"><span data-stu-id="44e67-141">It is advisable to use the resources carefully.The lab resources are limited.</span></span> <span data-ttu-id="44e67-142">No se restablecerán ni se actualizarán.</span><span class="sxs-lookup"><span data-stu-id="44e67-142">They will not reset nor refresh.</span></span> 

<span data-ttu-id="44e67-143">¿Ya tienes un laboratorio?</span><span class="sxs-lookup"><span data-stu-id="44e67-143">Already have a lab?</span></span> <span data-ttu-id="44e67-144">Asegúrate de habilitar los nuevos simuladores de amenazas y de tener dispositivos activos.</span><span class="sxs-lookup"><span data-stu-id="44e67-144">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="44e67-145">Configurar el laboratorio de evaluación</span><span class="sxs-lookup"><span data-stu-id="44e67-145">Setup the evaluation lab</span></span>

1. <span data-ttu-id="44e67-146">En el panel de navegación, seleccione **Evaluación y tutoriales** Laboratorio de  >  **evaluación** y, a continuación, seleccione Laboratorio **de instalación.**</span><span class="sxs-lookup"><span data-stu-id="44e67-146">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Imagen de la página de bienvenida del laboratorio de evaluación](images/evaluation-lab-setup.png)

2. <span data-ttu-id="44e67-148">Según tus necesidades de evaluación, puedes elegir configurar un entorno con menos dispositivos durante un período más largo o más dispositivos durante un período más corto.</span><span class="sxs-lookup"><span data-stu-id="44e67-148">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="44e67-149">Seleccione la configuración de laboratorio preferida y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="44e67-149">Select your preferred lab configuration then select **Next**.</span></span>

    ![Imagen de las opciones de configuración de laboratorio](images/lab-creation-page.png) 


3. <span data-ttu-id="44e67-151">(Opcional) Puede elegir instalar simuladores de amenazas en el laboratorio.</span><span class="sxs-lookup"><span data-stu-id="44e67-151">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Imagen del agente de simuladores de instalación](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="44e67-153">Primero deberá aceptar y dar su consentimiento a los términos y las instrucciones de uso compartido de información.</span><span class="sxs-lookup"><span data-stu-id="44e67-153">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="44e67-154">Selecciona el agente de simulación de amenazas que quieras usar y escribe los detalles.</span><span class="sxs-lookup"><span data-stu-id="44e67-154">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="44e67-155">También puedes elegir instalar simuladores de amenazas más adelante.</span><span class="sxs-lookup"><span data-stu-id="44e67-155">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="44e67-156">Si elige instalar agentes de simulación de amenazas durante la configuración del laboratorio, podrá disfrutar de la ventaja de que se instalen cómodamente en los dispositivos que agregue.</span><span class="sxs-lookup"><span data-stu-id="44e67-156">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Imagen de la página de resumen](images/lab-setup-summary.png)

5.  <span data-ttu-id="44e67-158">Revise el resumen y seleccione **Laboratorio de instalación**.</span><span class="sxs-lookup"><span data-stu-id="44e67-158">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="44e67-159">Una vez completado el proceso de configuración del laboratorio, puede agregar dispositivos y ejecutar simulaciones.</span><span class="sxs-lookup"><span data-stu-id="44e67-159">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="44e67-160">Agregar dispositivos</span><span class="sxs-lookup"><span data-stu-id="44e67-160">Add devices</span></span>
<span data-ttu-id="44e67-161">Cuando agregas un dispositivo a tu entorno, Defender para endpoint configura un dispositivo bien configurado con detalles de conexión.</span><span class="sxs-lookup"><span data-stu-id="44e67-161">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="44e67-162">Puedes agregar dispositivos con Windows 10 o Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="44e67-162">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="44e67-163">El dispositivo se configurará con la versión más actualizada del sistema operativo y Office 2019 Standard, así como con otras aplicaciones como Java, Python y SysIntenals.</span><span class="sxs-lookup"><span data-stu-id="44e67-163">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="44e67-164">¿Necesita más dispositivos en el laboratorio?</span><span class="sxs-lookup"><span data-stu-id="44e67-164">Need more devices in your lab?</span></span> <span data-ttu-id="44e67-165">Envía un vale de soporte técnico para que el equipo de Defender for Endpoint revise tu solicitud.</span><span class="sxs-lookup"><span data-stu-id="44e67-165">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="44e67-166">Si optó por agregar un simulador de amenazas durante la configuración del laboratorio, todos los dispositivos tendrán instalado el agente del simulador de amenazas en los dispositivos que agregue.</span><span class="sxs-lookup"><span data-stu-id="44e67-166">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="44e67-167">El dispositivo se incorporará automáticamente al espacio empresarial con los componentes de seguridad de Windows recomendados activados y en modo auditoría, sin ningún esfuerzo de su parte.</span><span class="sxs-lookup"><span data-stu-id="44e67-167">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="44e67-168">Los siguientes componentes de seguridad están preconfigurados en los dispositivos de prueba:</span><span class="sxs-lookup"><span data-stu-id="44e67-168">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="44e67-169">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="44e67-169">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="44e67-170">Bloquear a primera vista</span><span class="sxs-lookup"><span data-stu-id="44e67-170">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="44e67-171">Acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="44e67-171">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="44e67-172">Protección contra vulnerabilidades de seguridad</span><span class="sxs-lookup"><span data-stu-id="44e67-172">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="44e67-173">Protección de red</span><span class="sxs-lookup"><span data-stu-id="44e67-173">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="44e67-174">Detección de aplicaciones potencialmente no deseadas</span><span class="sxs-lookup"><span data-stu-id="44e67-174">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="44e67-175">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="44e67-175">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="44e67-176">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="44e67-176">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="44e67-177">Antivirus de Microsoft Defender estará en (no en modo auditoría).</span><span class="sxs-lookup"><span data-stu-id="44e67-177">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="44e67-178">Si Antivirus de Microsoft Defender te impide ejecutar la simulación, puedes desactivar la protección en tiempo real en el dispositivo a través de Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="44e67-178">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="44e67-179">Para obtener más información, vea [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="44e67-179">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="44e67-180">La configuración de investigación automatizada dependerá de la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="44e67-180">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="44e67-181">Se configurará para que sea semiautoautorista de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="44e67-181">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="44e67-182">Para obtener más información, vea [Overview of Automated investigations](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="44e67-182">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="44e67-183">La conexión a los dispositivos de prueba se realiza con RDP.</span><span class="sxs-lookup"><span data-stu-id="44e67-183">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="44e67-184">Asegúrese de que la configuración del firewall permite conexiones RDP.</span><span class="sxs-lookup"><span data-stu-id="44e67-184">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="44e67-185">En el panel, selecciona **Agregar dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="44e67-185">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="44e67-186">Elige el tipo de dispositivo que quieres agregar.</span><span class="sxs-lookup"><span data-stu-id="44e67-186">Choose the type of device to add.</span></span> <span data-ttu-id="44e67-187">Puedes elegir agregar Windows 10 o Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="44e67-187">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Imagen de configuración de laboratorio con opciones de dispositivo](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="44e67-189">Si algo sale mal con el proceso de creación del dispositivo, se te notificará y tendrás que enviar una nueva solicitud.</span><span class="sxs-lookup"><span data-stu-id="44e67-189">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="44e67-190">Si se produce un error en la creación del dispositivo, no se contará con la cuota total permitida.</span><span class="sxs-lookup"><span data-stu-id="44e67-190">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="44e67-191">Se muestran los detalles de conexión.</span><span class="sxs-lookup"><span data-stu-id="44e67-191">The connection details are displayed.</span></span> <span data-ttu-id="44e67-192">Selecciona **Copiar** para guardar la contraseña del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44e67-192">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="44e67-193">La contraseña solo se muestra una vez.</span><span class="sxs-lookup"><span data-stu-id="44e67-193">The password is only displayed once.</span></span> <span data-ttu-id="44e67-194">Asegúrese de guardarlo para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="44e67-194">Be sure to save it for later use.</span></span>

    ![Imagen del dispositivo agregado con detalles de conexión](images/add-machine-eval-lab.png)

4. <span data-ttu-id="44e67-196">Se inicia la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44e67-196">Device set up begins.</span></span> <span data-ttu-id="44e67-197">Esto puede tardar aproximadamente 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="44e67-197">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="44e67-198">Consulta el estado de los dispositivos de prueba, los niveles de riesgo y exposición y el estado de las instalaciones de simulador seleccionando la **pestaña Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="44e67-198">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Pestaña Imagen de dispositivos](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="44e67-200">En la **columna Estado del** simulador, puede pasar el mouse sobre el icono de información para conocer el estado de instalación de un agente.</span><span class="sxs-lookup"><span data-stu-id="44e67-200">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="44e67-201">Simular escenarios de ataque</span><span class="sxs-lookup"><span data-stu-id="44e67-201">Simulate attack scenarios</span></span>
<span data-ttu-id="44e67-202">Usa los dispositivos de prueba para ejecutar tus propias simulaciones de ataque conectándose a ellos.</span><span class="sxs-lookup"><span data-stu-id="44e67-202">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="44e67-203">Puedes simular escenarios de ataque con:</span><span class="sxs-lookup"><span data-stu-id="44e67-203">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="44e67-204">Escenarios de ataque ["Do It Yourself"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="44e67-204">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="44e67-205">Simuladores de amenazas</span><span class="sxs-lookup"><span data-stu-id="44e67-205">Threat simulators</span></span>

<span data-ttu-id="44e67-206">También puede usar búsqueda avanzada [para consultar](advanced-hunting-query-language.md) datos y [análisis de](threat-analytics.md) amenazas para ver informes sobre amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="44e67-206">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="44e67-207">Escenarios de ataque do-it-yourself</span><span class="sxs-lookup"><span data-stu-id="44e67-207">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="44e67-208">Si está buscando una simulación pre-made, puede usar nuestros escenarios de ataque ["Do It Yourself".](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="44e67-208">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="44e67-209">Estos scripts son seguros, documentados y fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="44e67-209">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="44e67-210">Estos escenarios reflejarán las capacidades de Defender for Endpoint y le ayudarán a través de la experiencia de investigación.</span><span class="sxs-lookup"><span data-stu-id="44e67-210">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="44e67-211">La conexión a los dispositivos de prueba se realiza con RDP.</span><span class="sxs-lookup"><span data-stu-id="44e67-211">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="44e67-212">Asegúrese de que la configuración del firewall permite conexiones RDP.</span><span class="sxs-lookup"><span data-stu-id="44e67-212">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="44e67-213">Conéctese al dispositivo y ejecute una simulación de ataque **seleccionando Conectar**.</span><span class="sxs-lookup"><span data-stu-id="44e67-213">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Imagen del botón conectar para dispositivos de prueba](images/test-machine-table.png)

2. <span data-ttu-id="44e67-215">Guarde el archivo RDP e inicielo **seleccionando Conectar**.</span><span class="sxs-lookup"><span data-stu-id="44e67-215">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Imagen de conexión de escritorio remoto](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="44e67-217">Si no tienes una copia de la contraseña guardada durante la configuración inicial, puedes restablecer la contraseña seleccionando **Restablecer** contraseña en el menú: Imagen de la contraseña de ![ restablecimiento](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="44e67-217">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="44e67-218">El dispositivo cambiará su estado a "Ejecutar el restablecimiento de contraseña" y, a continuación, se te presentará la nueva contraseña en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="44e67-218">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="44e67-219">Escribe la contraseña que se ha mostrado durante el paso de creación del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44e67-219">Enter the password that was displayed during the device creation step.</span></span> 

   ![Imagen de ventana para escribir credenciales](images/enter-password.png)

4. <span data-ttu-id="44e67-221">Ejecuta simulaciones de ataques do-it-yourself en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="44e67-221">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="44e67-222">Escenarios de simulador de amenazas</span><span class="sxs-lookup"><span data-stu-id="44e67-222">Threat simulator scenarios</span></span>
<span data-ttu-id="44e67-223">Si optó por instalar cualquiera de los simuladores de amenazas compatibles durante la configuración del laboratorio, puede ejecutar las simulaciones integradas en los dispositivos de laboratorio de evaluación.</span><span class="sxs-lookup"><span data-stu-id="44e67-223">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="44e67-224">Ejecutar simulaciones de amenazas con plataformas de terceros es una buena manera de evaluar las capacidades de Punto de conexión de Microsoft Defender en los límites de un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="44e67-224">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="44e67-225">Antes de poder ejecutar simulaciones, asegúrese de que se cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="44e67-225">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="44e67-226">Los dispositivos deben agregarse al laboratorio de evaluación</span><span class="sxs-lookup"><span data-stu-id="44e67-226">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="44e67-227">Los simuladores de amenazas deben instalarse en el laboratorio de evaluación</span><span class="sxs-lookup"><span data-stu-id="44e67-227">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="44e67-228">En el portal, seleccione **Crear simulación**.</span><span class="sxs-lookup"><span data-stu-id="44e67-228">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="44e67-229">Seleccione un simulador de amenazas.</span><span class="sxs-lookup"><span data-stu-id="44e67-229">Select a threat simulator.</span></span>

    ![Imagen de selección del simulador de amenazas](images/select-simulator.png)

3. <span data-ttu-id="44e67-231">Elija una simulación o busque en la galería de simulación para examinar las simulaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="44e67-231">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="44e67-232">Puede acceder a la galería de simulación desde:</span><span class="sxs-lookup"><span data-stu-id="44e67-232">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="44e67-233">El panel de evaluación principal en el icono de información general de **Simulaciones** o</span><span class="sxs-lookup"><span data-stu-id="44e67-233">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="44e67-234">Al navegar desde el panel de navegación Evaluación y tutoriales De **simulación**&  >  **tutoriales** y, a continuación, seleccione **Catálogo de simulaciones**.</span><span class="sxs-lookup"><span data-stu-id="44e67-234">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="44e67-235">Selecciona los dispositivos en los que quieres ejecutar la simulación.</span><span class="sxs-lookup"><span data-stu-id="44e67-235">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="44e67-236">Seleccione **Crear simulación**.</span><span class="sxs-lookup"><span data-stu-id="44e67-236">Select **Create simulation**.</span></span>

6. <span data-ttu-id="44e67-237">Para ver el progreso de una simulación, seleccione la **pestaña Simulaciones.** Vea el estado de simulación, las alertas activas y otros detalles.</span><span class="sxs-lookup"><span data-stu-id="44e67-237">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Imagen de la pestaña simulaciones](images/simulations-tab.png)
    
<span data-ttu-id="44e67-239">Después de ejecutar las simulaciones, te animamos a recorrer la barra de progreso del laboratorio y explorar Microsoft Defender for Endpoint desencadenando una **investigación y corrección automatizadas.**</span><span class="sxs-lookup"><span data-stu-id="44e67-239">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="44e67-240">Consulte las pruebas recopiladas y analizadas por la característica.</span><span class="sxs-lookup"><span data-stu-id="44e67-240">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="44e67-241">Busca pruebas de ataque mediante la búsqueda avanzada mediante el lenguaje de consulta enriquecido y telemetría sin procesar y echa un vistazo a algunas amenazas de todo el mundo documentadas en análisis de amenazas.</span><span class="sxs-lookup"><span data-stu-id="44e67-241">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="44e67-242">Galería de simulación</span><span class="sxs-lookup"><span data-stu-id="44e67-242">Simulation gallery</span></span>
<span data-ttu-id="44e67-243">Microsoft Defender para endpoint se ha asociado con varias plataformas de simulación de amenazas para ofrecerte un acceso cómodo para probar las capacidades de la plataforma desde el portal.</span><span class="sxs-lookup"><span data-stu-id="44e67-243">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="44e67-244">Para ver todas las simulaciones disponibles, vaya al catálogo **Simulaciones** y tutoriales Simulaciones  >   desde el menú.</span><span class="sxs-lookup"><span data-stu-id="44e67-244">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="44e67-245">Se muestra una lista de agentes de simulación de amenazas de terceros compatibles y se proporcionan tipos específicos de simulaciones junto con descripciones detalladas en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="44e67-245">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="44e67-246">Puede ejecutar cómodamente cualquier simulación disponible directamente desde el catálogo.</span><span class="sxs-lookup"><span data-stu-id="44e67-246">You can conveniently run any available simulation right from the catalog.</span></span>  


![Imagen del catálogo de simulaciones](images/simulations-catalog.png)

<span data-ttu-id="44e67-248">Cada simulación incluye una descripción detallada del escenario de ataque y referencias como las técnicas de ataque MITRE usadas y las consultas avanzadas de búsqueda de ejemplo que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="44e67-248">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="44e67-249">**Ejemplos:** 
 ![ Imagen de los detalles de la descripción de la simulación1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="44e67-249">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Imagen de detalles de descripción de simulación2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="44e67-251">Informe de evaluación</span><span class="sxs-lookup"><span data-stu-id="44e67-251">Evaluation report</span></span>
<span data-ttu-id="44e67-252">Los informes de laboratorio resumen los resultados de las simulaciones realizadas en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="44e67-252">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Imagen del informe de evaluación](images/eval-report.png)

<span data-ttu-id="44e67-254">De un vistazo, podrás ver rápidamente:</span><span class="sxs-lookup"><span data-stu-id="44e67-254">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="44e67-255">Incidentes que se desencadenaron</span><span class="sxs-lookup"><span data-stu-id="44e67-255">Incidents that were triggered</span></span>
- <span data-ttu-id="44e67-256">Alertas generadas</span><span class="sxs-lookup"><span data-stu-id="44e67-256">Generated alerts</span></span>
- <span data-ttu-id="44e67-257">Evaluaciones en el nivel de exposición</span><span class="sxs-lookup"><span data-stu-id="44e67-257">Assessments on exposure level</span></span> 
- <span data-ttu-id="44e67-258">Categorías de amenazas observadas</span><span class="sxs-lookup"><span data-stu-id="44e67-258">Threat categories observed</span></span>
- <span data-ttu-id="44e67-259">Orígenes de detección</span><span class="sxs-lookup"><span data-stu-id="44e67-259">Detection sources</span></span>
- <span data-ttu-id="44e67-260">Investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="44e67-260">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="44e67-261">Enviar comentarios</span><span class="sxs-lookup"><span data-stu-id="44e67-261">Provide feedback</span></span>
<span data-ttu-id="44e67-262">Sus comentarios nos ayudan a mejorar la protección del entorno frente a ataques avanzados.</span><span class="sxs-lookup"><span data-stu-id="44e67-262">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="44e67-263">Comparta la experiencia y las impresiones de las capacidades del producto y los resultados de evaluación.</span><span class="sxs-lookup"><span data-stu-id="44e67-263">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="44e67-264">Háganos saber lo que piensa, **seleccionando Proporcionar comentarios**.</span><span class="sxs-lookup"><span data-stu-id="44e67-264">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Imagen de proporcionar comentarios](images/send-us-feedback-eval-lab.png)
