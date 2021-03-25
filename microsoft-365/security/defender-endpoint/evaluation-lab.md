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
ms.openlocfilehash: ead616b7af3df05f4c0c5755ad779f0251555734
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074584"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="0df2b-104">Laboratorio de evaluación de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="0df2b-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0df2b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0df2b-105">**Applies to:**</span></span>
- [<span data-ttu-id="0df2b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0df2b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0df2b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0df2b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0df2b-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="0df2b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0df2b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0df2b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="0df2b-110">La realización de una evaluación completa de productos de seguridad puede ser un proceso complejo que requiere una configuración de dispositivos y entornos engorrosos antes de poder realizar una simulación de ataque de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="0df2b-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="0df2b-111">Agregar a la complejidad es el desafío de realizar un seguimiento de dónde se reflejan las actividades de simulación, las alertas y los resultados durante la evaluación.</span><span class="sxs-lookup"><span data-stu-id="0df2b-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="0df2b-112">El laboratorio de evaluación de Microsoft Defender para endpoints está diseñado para eliminar las complejidades de la configuración de dispositivos y entornos para que puedas centrarte en evaluar las capacidades de la plataforma, ejecutar simulaciones y ver las características de prevención, detección y corrección en acción.</span><span class="sxs-lookup"><span data-stu-id="0df2b-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="0df2b-113">Con la experiencia de configuración simplificada, puede centrarse en ejecutar sus propios escenarios de prueba y las simulaciones pre-realizadas para ver el rendimiento de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0df2b-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="0df2b-114">Tendrás acceso completo a las potentes capacidades de la plataforma, como investigaciones automatizadas, búsqueda avanzada y análisis de amenazas, lo que te permite probar la pila de protección completa que ofrece Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0df2b-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="0df2b-115">Puede agregar dispositivos windows 10 o Windows Server 2019 que vienen preconfigurados para tener instaladas las versiones más recientes del sistema operativo y los componentes de seguridad adecuados, así como Office 2019 Standard.</span><span class="sxs-lookup"><span data-stu-id="0df2b-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="0df2b-116">También puedes instalar simuladores de amenazas.</span><span class="sxs-lookup"><span data-stu-id="0df2b-116">You can also install threat simulators.</span></span> <span data-ttu-id="0df2b-117">Defender for Endpoint se ha asociado con plataformas de simulación de amenazas líderes del sector para ayudarle a probar las capacidades de Defender for Endpoint sin tener que salir del portal.</span><span class="sxs-lookup"><span data-stu-id="0df2b-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="0df2b-118">Instale el simulador preferido, ejecute escenarios en el laboratorio de evaluación y vea al instante el rendimiento de la plataforma, todo disponible cómodamente sin costo adicional para usted.</span><span class="sxs-lookup"><span data-stu-id="0df2b-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="0df2b-119">También tendrás acceso conveniente a una amplia variedad de simulaciones a las que puedes acceder y ejecutar desde el catálogo de simulaciones.</span><span class="sxs-lookup"><span data-stu-id="0df2b-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="0df2b-120">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="0df2b-120">Before you begin</span></span>
<span data-ttu-id="0df2b-121">Tendrás que cumplir los requisitos de licencia [o](minimum-requirements.md#licensing-requirements) tener acceso de prueba a Microsoft Defender para endpoint para acceder al laboratorio de evaluación.</span><span class="sxs-lookup"><span data-stu-id="0df2b-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="0df2b-122">Debe tener permisos **administrar la configuración de** seguridad para:</span><span class="sxs-lookup"><span data-stu-id="0df2b-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="0df2b-123">Crear el laboratorio</span><span class="sxs-lookup"><span data-stu-id="0df2b-123">Create the lab</span></span>
- <span data-ttu-id="0df2b-124">Crear dispositivos</span><span class="sxs-lookup"><span data-stu-id="0df2b-124">Create devices</span></span>
- <span data-ttu-id="0df2b-125">Restablecer contraseña</span><span class="sxs-lookup"><span data-stu-id="0df2b-125">Reset password</span></span>
- <span data-ttu-id="0df2b-126">Crear simulaciones</span><span class="sxs-lookup"><span data-stu-id="0df2b-126">Create simulations</span></span> 
 
<span data-ttu-id="0df2b-127">Si habilitó el control de acceso basado en roles (RBAC) y creó al menos un grupo de máquinas, los usuarios deben tener acceso a Todos los grupos de máquinas.</span><span class="sxs-lookup"><span data-stu-id="0df2b-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="0df2b-128">Para obtener más información, vea [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0df2b-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="0df2b-129">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="0df2b-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0df2b-130">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0df2b-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="0df2b-131">Introducción al laboratorio</span><span class="sxs-lookup"><span data-stu-id="0df2b-131">Get started with the lab</span></span>
<span data-ttu-id="0df2b-132">Puede acceder al laboratorio desde el menú.</span><span class="sxs-lookup"><span data-stu-id="0df2b-132">You can access the lab from the menu.</span></span> <span data-ttu-id="0df2b-133">En el menú de navegación, seleccione **Evaluación y tutoriales > Laboratorio de evaluación**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Imagen del laboratorio de evaluación en el menú](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="0df2b-135">Cada entorno se aprovisiona con un conjunto limitado de dispositivos de prueba.</span><span class="sxs-lookup"><span data-stu-id="0df2b-135">Each environment is provisioned with a limited set of test devices.</span></span>
>- <span data-ttu-id="0df2b-136">Según el tipo de estructura del entorno que selecciones, los dispositivos estarán disponibles para el número especificado de horas desde el día de la activación.</span><span class="sxs-lookup"><span data-stu-id="0df2b-136">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="0df2b-137">Cuando hayas usado los dispositivos aprovisionados, no se proporciona ningún dispositivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="0df2b-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="0df2b-138">Un dispositivo eliminado no actualiza el recuento de dispositivos de prueba disponibles.</span><span class="sxs-lookup"><span data-stu-id="0df2b-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="0df2b-139">Dados los recursos limitados, es aconsejable usar los dispositivos con cuidado.</span><span class="sxs-lookup"><span data-stu-id="0df2b-139">Given the limited resources, it’s advisable to use the devices carefully.</span></span>

<span data-ttu-id="0df2b-140">¿Ya tienes un laboratorio?</span><span class="sxs-lookup"><span data-stu-id="0df2b-140">Already have a lab?</span></span> <span data-ttu-id="0df2b-141">Asegúrate de habilitar los nuevos simuladores de amenazas y de tener dispositivos activos.</span><span class="sxs-lookup"><span data-stu-id="0df2b-141">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="0df2b-142">Configurar el laboratorio de evaluación</span><span class="sxs-lookup"><span data-stu-id="0df2b-142">Setup the evaluation lab</span></span>

1. <span data-ttu-id="0df2b-143">En el panel de navegación, seleccione **Evaluación y tutoriales** Laboratorio de  >  **evaluación** y, a continuación, seleccione Laboratorio **de instalación.**</span><span class="sxs-lookup"><span data-stu-id="0df2b-143">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Imagen de la página de bienvenida del laboratorio de evaluación](images/evaluation-lab-setup.png)

2. <span data-ttu-id="0df2b-145">Según tus necesidades de evaluación, puedes elegir configurar un entorno con menos dispositivos durante un período más largo o más dispositivos durante un período más corto.</span><span class="sxs-lookup"><span data-stu-id="0df2b-145">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="0df2b-146">Seleccione la configuración de laboratorio preferida y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-146">Select your preferred lab configuration then select **Next**.</span></span>

    ![Imagen de las opciones de configuración de laboratorio](images/lab-creation-page.png) 


3. <span data-ttu-id="0df2b-148">(Opcional) Puede elegir instalar simuladores de amenazas en el laboratorio.</span><span class="sxs-lookup"><span data-stu-id="0df2b-148">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Imagen del agente de simuladores de instalación](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="0df2b-150">Primero deberá aceptar y dar su consentimiento a los términos y las instrucciones de uso compartido de información.</span><span class="sxs-lookup"><span data-stu-id="0df2b-150">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="0df2b-151">Selecciona el agente de simulación de amenazas que quieras usar y escribe los detalles.</span><span class="sxs-lookup"><span data-stu-id="0df2b-151">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="0df2b-152">También puedes elegir instalar simuladores de amenazas más adelante.</span><span class="sxs-lookup"><span data-stu-id="0df2b-152">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="0df2b-153">Si elige instalar agentes de simulación de amenazas durante la configuración del laboratorio, podrá disfrutar de la ventaja de que se instalen cómodamente en los dispositivos que agregue.</span><span class="sxs-lookup"><span data-stu-id="0df2b-153">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Imagen de la página de resumen](images/lab-setup-summary.png)

5.  <span data-ttu-id="0df2b-155">Revise el resumen y seleccione **Laboratorio de instalación**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-155">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="0df2b-156">Una vez completado el proceso de configuración del laboratorio, puede agregar dispositivos y ejecutar simulaciones.</span><span class="sxs-lookup"><span data-stu-id="0df2b-156">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="0df2b-157">Agregar dispositivos</span><span class="sxs-lookup"><span data-stu-id="0df2b-157">Add devices</span></span>
<span data-ttu-id="0df2b-158">Cuando agregas un dispositivo a tu entorno, Defender para endpoint configura un dispositivo bien configurado con detalles de conexión.</span><span class="sxs-lookup"><span data-stu-id="0df2b-158">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="0df2b-159">Puedes agregar dispositivos con Windows 10 o Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0df2b-159">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="0df2b-160">El dispositivo se configurará con la versión más actualizada del sistema operativo y Office 2019 Standard, así como con otras aplicaciones como Java, Python y SysIntenals.</span><span class="sxs-lookup"><span data-stu-id="0df2b-160">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="0df2b-161">¿Necesita más dispositivos en el laboratorio?</span><span class="sxs-lookup"><span data-stu-id="0df2b-161">Need more devices in your lab?</span></span> <span data-ttu-id="0df2b-162">Envía un vale de soporte técnico para que el equipo de Defender for Endpoint revise tu solicitud.</span><span class="sxs-lookup"><span data-stu-id="0df2b-162">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="0df2b-163">Si optó por agregar un simulador de amenazas durante la configuración del laboratorio, todos los dispositivos tendrán instalado el agente del simulador de amenazas en los dispositivos que agregue.</span><span class="sxs-lookup"><span data-stu-id="0df2b-163">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="0df2b-164">El dispositivo se incorporará automáticamente al espacio empresarial con los componentes de seguridad de Windows recomendados activados y en modo auditoría, sin ningún esfuerzo de su parte.</span><span class="sxs-lookup"><span data-stu-id="0df2b-164">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="0df2b-165">Los siguientes componentes de seguridad están preconfigurados en los dispositivos de prueba:</span><span class="sxs-lookup"><span data-stu-id="0df2b-165">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="0df2b-166">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="0df2b-166">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="0df2b-167">Bloquear a primera vista</span><span class="sxs-lookup"><span data-stu-id="0df2b-167">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="0df2b-168">Acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="0df2b-168">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="0df2b-169">Protección contra vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="0df2b-169">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="0df2b-170">Protección de red</span><span class="sxs-lookup"><span data-stu-id="0df2b-170">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="0df2b-171">Detección de aplicaciones potencialmente no deseadas</span><span class="sxs-lookup"><span data-stu-id="0df2b-171">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="0df2b-172">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="0df2b-172">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="0df2b-173">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="0df2b-173">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="0df2b-174">Antivirus de Microsoft Defender estará en (no en modo auditoría).</span><span class="sxs-lookup"><span data-stu-id="0df2b-174">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="0df2b-175">Si Antivirus de Microsoft Defender te impide ejecutar la simulación, puedes desactivar la protección en tiempo real en el dispositivo a través de Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="0df2b-175">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="0df2b-176">Para obtener más información, vea [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="0df2b-176">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="0df2b-177">La configuración de investigación automatizada dependerá de la configuración del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="0df2b-177">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="0df2b-178">Se configurará para que sea semiautoautorista de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0df2b-178">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="0df2b-179">Para obtener más información, vea [Overview of Automated investigations](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="0df2b-179">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="0df2b-180">La conexión a los dispositivos de prueba se realiza con RDP.</span><span class="sxs-lookup"><span data-stu-id="0df2b-180">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="0df2b-181">Asegúrese de que la configuración del firewall permite conexiones RDP.</span><span class="sxs-lookup"><span data-stu-id="0df2b-181">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="0df2b-182">En el panel, selecciona **Agregar dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-182">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="0df2b-183">Elige el tipo de dispositivo que quieres agregar.</span><span class="sxs-lookup"><span data-stu-id="0df2b-183">Choose the type of device to add.</span></span> <span data-ttu-id="0df2b-184">Puedes elegir agregar Windows 10 o Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0df2b-184">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Imagen de configuración de laboratorio con opciones de dispositivo](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="0df2b-186">Si algo sale mal con el proceso de creación del dispositivo, se te notificará y tendrás que enviar una nueva solicitud.</span><span class="sxs-lookup"><span data-stu-id="0df2b-186">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="0df2b-187">Si se produce un error en la creación del dispositivo, no se contará con la cuota total permitida.</span><span class="sxs-lookup"><span data-stu-id="0df2b-187">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="0df2b-188">Se muestran los detalles de conexión.</span><span class="sxs-lookup"><span data-stu-id="0df2b-188">The connection details are displayed.</span></span> <span data-ttu-id="0df2b-189">Selecciona **Copiar** para guardar la contraseña del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0df2b-189">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="0df2b-190">La contraseña solo se muestra una vez.</span><span class="sxs-lookup"><span data-stu-id="0df2b-190">The password is only displayed once.</span></span> <span data-ttu-id="0df2b-191">Asegúrese de guardarlo para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="0df2b-191">Be sure to save it for later use.</span></span>

    ![Imagen del dispositivo agregado con detalles de conexión](images/add-machine-eval-lab.png)

4. <span data-ttu-id="0df2b-193">Se inicia la configuración del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0df2b-193">Device set up begins.</span></span> <span data-ttu-id="0df2b-194">Esto puede tardar aproximadamente 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="0df2b-194">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="0df2b-195">Consulta el estado de los dispositivos de prueba, los niveles de riesgo y exposición y el estado de las instalaciones de simulador seleccionando la **pestaña Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="0df2b-195">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Pestaña Imagen de dispositivos](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="0df2b-197">En la **columna Estado del** simulador, puede pasar el mouse sobre el icono de información para conocer el estado de instalación de un agente.</span><span class="sxs-lookup"><span data-stu-id="0df2b-197">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="0df2b-198">Simular escenarios de ataque</span><span class="sxs-lookup"><span data-stu-id="0df2b-198">Simulate attack scenarios</span></span>
<span data-ttu-id="0df2b-199">Usa los dispositivos de prueba para ejecutar tus propias simulaciones de ataque conectándose a ellos.</span><span class="sxs-lookup"><span data-stu-id="0df2b-199">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="0df2b-200">Puedes simular escenarios de ataque con:</span><span class="sxs-lookup"><span data-stu-id="0df2b-200">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="0df2b-201">Escenarios de ataque ["Do It Yourself"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="0df2b-201">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="0df2b-202">Simuladores de amenazas</span><span class="sxs-lookup"><span data-stu-id="0df2b-202">Threat simulators</span></span>

<span data-ttu-id="0df2b-203">También puede usar búsqueda avanzada [para consultar](advanced-hunting-query-language.md) datos y [análisis de](threat-analytics.md) amenazas para ver informes sobre amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="0df2b-203">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="0df2b-204">Escenarios de ataque do-it-yourself</span><span class="sxs-lookup"><span data-stu-id="0df2b-204">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="0df2b-205">Si está buscando una simulación pre-made, puede usar nuestros escenarios de ataque ["Do It Yourself".](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="0df2b-205">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="0df2b-206">Estos scripts son seguros, documentados y fáciles de usar.</span><span class="sxs-lookup"><span data-stu-id="0df2b-206">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="0df2b-207">Estos escenarios reflejarán las capacidades de Defender for Endpoint y le ayudarán a través de la experiencia de investigación.</span><span class="sxs-lookup"><span data-stu-id="0df2b-207">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="0df2b-208">La conexión a los dispositivos de prueba se realiza con RDP.</span><span class="sxs-lookup"><span data-stu-id="0df2b-208">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="0df2b-209">Asegúrese de que la configuración del firewall permite conexiones RDP.</span><span class="sxs-lookup"><span data-stu-id="0df2b-209">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="0df2b-210">Conéctese al dispositivo y ejecute una simulación de ataque **seleccionando Conectar**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-210">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Imagen del botón conectar para dispositivos de prueba](images/test-machine-table.png)

2. <span data-ttu-id="0df2b-212">Guarde el archivo RDP e inicielo **seleccionando Conectar**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-212">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Imagen de conexión de escritorio remoto](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="0df2b-214">Si no tienes una copia de la contraseña guardada durante la configuración inicial, puedes restablecer la contraseña seleccionando **Restablecer** contraseña en el menú: Imagen de la contraseña de ![ restablecimiento](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="0df2b-214">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="0df2b-215">El dispositivo cambiará su estado a "Ejecutar el restablecimiento de contraseña" y, a continuación, se te presentará la nueva contraseña en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="0df2b-215">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="0df2b-216">Escribe la contraseña que se ha mostrado durante el paso de creación del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0df2b-216">Enter the password that was displayed during the device creation step.</span></span> 

   ![Imagen de ventana para escribir credenciales](images/enter-password.png)

4. <span data-ttu-id="0df2b-218">Ejecuta simulaciones de ataques do-it-yourself en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0df2b-218">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="0df2b-219">Escenarios de simulador de amenazas</span><span class="sxs-lookup"><span data-stu-id="0df2b-219">Threat simulator scenarios</span></span>
<span data-ttu-id="0df2b-220">Si optó por instalar cualquiera de los simuladores de amenazas compatibles durante la configuración del laboratorio, puede ejecutar las simulaciones integradas en los dispositivos de laboratorio de evaluación.</span><span class="sxs-lookup"><span data-stu-id="0df2b-220">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="0df2b-221">Ejecutar simulaciones de amenazas con plataformas de terceros es una buena manera de evaluar las capacidades de Punto de conexión de Microsoft Defender en los límites de un entorno de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="0df2b-221">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="0df2b-222">Antes de poder ejecutar simulaciones, asegúrese de que se cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="0df2b-222">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="0df2b-223">Los dispositivos deben agregarse al laboratorio de evaluación</span><span class="sxs-lookup"><span data-stu-id="0df2b-223">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="0df2b-224">Los simuladores de amenazas deben instalarse en el laboratorio de evaluación</span><span class="sxs-lookup"><span data-stu-id="0df2b-224">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="0df2b-225">En el portal, seleccione **Crear simulación**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-225">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="0df2b-226">Seleccione un simulador de amenazas.</span><span class="sxs-lookup"><span data-stu-id="0df2b-226">Select a threat simulator.</span></span>

    ![Imagen de selección del simulador de amenazas](images/select-simulator.png)

3. <span data-ttu-id="0df2b-228">Elija una simulación o busque en la galería de simulación para examinar las simulaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="0df2b-228">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="0df2b-229">Puede acceder a la galería de simulación desde:</span><span class="sxs-lookup"><span data-stu-id="0df2b-229">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="0df2b-230">El panel de evaluación principal en el icono de información general de **Simulaciones** o</span><span class="sxs-lookup"><span data-stu-id="0df2b-230">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="0df2b-231">Al navegar desde el panel de navegación Evaluación y tutoriales De **simulación**&  >  **tutoriales** y, a continuación, seleccione **Catálogo de simulaciones**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-231">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="0df2b-232">Selecciona los dispositivos en los que quieres ejecutar la simulación.</span><span class="sxs-lookup"><span data-stu-id="0df2b-232">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="0df2b-233">Seleccione **Crear simulación**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-233">Select **Create simulation**.</span></span>

6. <span data-ttu-id="0df2b-234">Para ver el progreso de una simulación, seleccione la **pestaña Simulaciones.** Vea el estado de simulación, las alertas activas y otros detalles.</span><span class="sxs-lookup"><span data-stu-id="0df2b-234">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Imagen de la pestaña simulaciones](images/simulations-tab.png)
    
<span data-ttu-id="0df2b-236">Después de ejecutar las simulaciones, te animamos a recorrer la barra de progreso del laboratorio y explorar Microsoft Defender for Endpoint desencadenando una **investigación y corrección automatizadas.**</span><span class="sxs-lookup"><span data-stu-id="0df2b-236">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="0df2b-237">Consulte las pruebas recopiladas y analizadas por la característica.</span><span class="sxs-lookup"><span data-stu-id="0df2b-237">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="0df2b-238">Busca pruebas de ataque mediante la búsqueda avanzada mediante el lenguaje de consulta enriquecido y telemetría sin procesar y echa un vistazo a algunas amenazas de todo el mundo documentadas en análisis de amenazas.</span><span class="sxs-lookup"><span data-stu-id="0df2b-238">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="0df2b-239">Galería de simulación</span><span class="sxs-lookup"><span data-stu-id="0df2b-239">Simulation gallery</span></span>
<span data-ttu-id="0df2b-240">Microsoft Defender para endpoint se ha asociado con varias plataformas de simulación de amenazas para ofrecerte un acceso cómodo para probar las capacidades de la plataforma desde el portal.</span><span class="sxs-lookup"><span data-stu-id="0df2b-240">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="0df2b-241">Para ver todas las simulaciones disponibles, vaya al catálogo **Simulaciones** y tutoriales Simulaciones  >   desde el menú.</span><span class="sxs-lookup"><span data-stu-id="0df2b-241">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="0df2b-242">Se muestra una lista de agentes de simulación de amenazas de terceros compatibles y se proporcionan tipos específicos de simulaciones junto con descripciones detalladas en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="0df2b-242">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="0df2b-243">Puede ejecutar cómodamente cualquier simulación disponible directamente desde el catálogo.</span><span class="sxs-lookup"><span data-stu-id="0df2b-243">You can conveniently run any available simulation right from the catalog.</span></span>  


![Imagen del catálogo de simulaciones](images/simulations-catalog.png)

<span data-ttu-id="0df2b-245">Cada simulación incluye una descripción detallada del escenario de ataque y referencias como las técnicas de ataque MITRE usadas y las consultas avanzadas de búsqueda de ejemplo que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="0df2b-245">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="0df2b-246">**Ejemplos:** 
 ![ Imagen de los detalles de la descripción de la simulación1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="0df2b-246">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Imagen de detalles de descripción de simulación2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="0df2b-248">Informe de evaluación</span><span class="sxs-lookup"><span data-stu-id="0df2b-248">Evaluation report</span></span>
<span data-ttu-id="0df2b-249">Los informes de laboratorio resumen los resultados de las simulaciones realizadas en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0df2b-249">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Imagen del informe de evaluación](images/eval-report.png)

<span data-ttu-id="0df2b-251">De un vistazo, podrás ver rápidamente:</span><span class="sxs-lookup"><span data-stu-id="0df2b-251">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="0df2b-252">Incidentes que se desencadenaron</span><span class="sxs-lookup"><span data-stu-id="0df2b-252">Incidents that were triggered</span></span>
- <span data-ttu-id="0df2b-253">Alertas generadas</span><span class="sxs-lookup"><span data-stu-id="0df2b-253">Generated alerts</span></span>
- <span data-ttu-id="0df2b-254">Evaluaciones en el nivel de exposición</span><span class="sxs-lookup"><span data-stu-id="0df2b-254">Assessments on exposure level</span></span> 
- <span data-ttu-id="0df2b-255">Categorías de amenazas observadas</span><span class="sxs-lookup"><span data-stu-id="0df2b-255">Threat categories observed</span></span>
- <span data-ttu-id="0df2b-256">Orígenes de detección</span><span class="sxs-lookup"><span data-stu-id="0df2b-256">Detection sources</span></span>
- <span data-ttu-id="0df2b-257">Investigaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="0df2b-257">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="0df2b-258">Enviar comentarios</span><span class="sxs-lookup"><span data-stu-id="0df2b-258">Provide feedback</span></span>
<span data-ttu-id="0df2b-259">Sus comentarios nos ayudan a mejorar la protección del entorno frente a ataques avanzados.</span><span class="sxs-lookup"><span data-stu-id="0df2b-259">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="0df2b-260">Comparta la experiencia y las impresiones de las capacidades del producto y los resultados de evaluación.</span><span class="sxs-lookup"><span data-stu-id="0df2b-260">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="0df2b-261">Háganos saber lo que piensa, **seleccionando Proporcionar comentarios**.</span><span class="sxs-lookup"><span data-stu-id="0df2b-261">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Imagen de proporcionar comentarios](images/send-us-feedback-eval-lab.png)
