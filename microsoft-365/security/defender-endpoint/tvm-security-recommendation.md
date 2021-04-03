---
title: Recomendaciones de seguridad por la administración de amenazas y vulnerabilidades
description: Obtenga recomendaciones de seguridad de acción priorizadas por amenaza, probabilidad de vulneración y valor en la administración de amenazas y vulnerabilidades.
keywords: administración de amenazas y vulnerabilidades, recomendación de seguridad mdatp tvm, recomendación de ciberseguridad, recomendación de seguridad que se puede actuar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 97d496271c1ef7185419f7d39956da0429f070aa
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500487"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="b8442-104">Recomendaciones de seguridad: administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="b8442-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b8442-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b8442-105">**Applies to:**</span></span>

- [<span data-ttu-id="b8442-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b8442-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="b8442-107">Administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="b8442-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b8442-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8442-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b8442-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="b8442-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b8442-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="b8442-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="b8442-111">Las debilidades de seguridad cibernética identificadas en su organización se asignan a recomendaciones de seguridad que se pueden usar y se priorizan por su impacto.</span><span class="sxs-lookup"><span data-stu-id="b8442-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="b8442-112">Las recomendaciones prioritarias ayudan a acortar el tiempo para mitigar o corregir las vulnerabilidades e impulsar el cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="b8442-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="b8442-113">Cada recomendación de seguridad incluye pasos de corrección que se pueden tomar.</span><span class="sxs-lookup"><span data-stu-id="b8442-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="b8442-114">Para ayudar con la administración de tareas, la recomendación también se puede enviar con Microsoft Intune y Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b8442-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="b8442-115">Cuando cambia el panorama de amenazas, la recomendación también cambia a medida que recopila continuamente información del entorno.</span><span class="sxs-lookup"><span data-stu-id="b8442-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="b8442-116">Para obtener correos electrónicos sobre nuevos eventos de vulnerabilidad, consulte [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="b8442-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="b8442-117">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="b8442-117">How it works</span></span>

<span data-ttu-id="b8442-118">Cada dispositivo de la organización se puntua en función de tres factores importantes para ayudar a los clientes a centrarse en las cosas correctas en el momento adecuado.</span><span class="sxs-lookup"><span data-stu-id="b8442-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="b8442-119">**Amenaza:** características de las vulnerabilidades y vulnerabilidades en los dispositivos de la organización y el historial de infracciones.</span><span class="sxs-lookup"><span data-stu-id="b8442-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="b8442-120">En función de estos factores, las recomendaciones de seguridad muestran los vínculos correspondientes a alertas activas, campañas de amenazas en curso y sus correspondientes informes analíticos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="b8442-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="b8442-121">**Probabilidad de vulneración:** la posición de seguridad y resistencia de la organización frente a las amenazas</span><span class="sxs-lookup"><span data-stu-id="b8442-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="b8442-122">**Valor empresarial:** activos, procesos críticos y propiedades intelectuales de la organización</span><span class="sxs-lookup"><span data-stu-id="b8442-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="b8442-123">Vaya a la página Recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="b8442-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="b8442-124">Acceda a la página Recomendaciones de seguridad de varias maneras diferentes:</span><span class="sxs-lookup"><span data-stu-id="b8442-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="b8442-125">Menú de navegación de administración de amenazas y vulnerabilidades en el [Centro de seguridad de Microsoft Defender](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b8442-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="b8442-126">Recomendaciones de seguridad principales en el panel de administración de [amenazas y vulnerabilidades](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="b8442-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="b8442-127">Vea las recomendaciones de seguridad relacionadas en los siguientes lugares:</span><span class="sxs-lookup"><span data-stu-id="b8442-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="b8442-128">Página de software</span><span class="sxs-lookup"><span data-stu-id="b8442-128">Software page</span></span>
- <span data-ttu-id="b8442-129">Página del dispositivo</span><span class="sxs-lookup"><span data-stu-id="b8442-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="b8442-130">Menú navegación</span><span class="sxs-lookup"><span data-stu-id="b8442-130">Navigation menu</span></span>

<span data-ttu-id="b8442-131">Vaya al menú de navegación de administración de amenazas y vulnerabilidades y seleccione **Recomendaciones de seguridad.**</span><span class="sxs-lookup"><span data-stu-id="b8442-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="b8442-132">La página contiene una lista de recomendaciones de seguridad para las amenazas y vulnerabilidades encontradas en su organización.</span><span class="sxs-lookup"><span data-stu-id="b8442-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="b8442-133">Recomendaciones de seguridad principales en el panel de administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="b8442-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="b8442-134">En un día determinado como administrador de seguridad, [](tvm-dashboard-insights.md) puedes echar un vistazo [](tvm-exposure-score.md) al panel de administración de amenazas y vulnerabilidades para ver la puntuación de exposición en paralelo con la puntuación segura de Microsoft para [dispositivos.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="b8442-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="b8442-135">El objetivo es reducir **la** exposición de la  organización frente a vulnerabilidades y aumentar la seguridad del dispositivo de la organización para que sea más resistente frente a los ataques de amenazas de ciberseguridad.</span><span class="sxs-lookup"><span data-stu-id="b8442-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="b8442-136">La lista de recomendaciones de seguridad superior puede ayudarle a lograr ese objetivo.</span><span class="sxs-lookup"><span data-stu-id="b8442-136">The top security recommendations list can help you achieve that goal.</span></span>

![Ejemplo de tarjeta de recomendaciones de seguridad superior, con cuatro recomendaciones de seguridad.](images/top-security-recommendations350.png)

<span data-ttu-id="b8442-138">Las recomendaciones de seguridad principales incluyen las oportunidades de mejora priorizadas en función de los factores importantes mencionados en la sección anterior: amenaza, probabilidad de vulneración y valor.</span><span class="sxs-lookup"><span data-stu-id="b8442-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="b8442-139">La selección de una recomendación le llevará a la página de recomendaciones de seguridad con más detalles.</span><span class="sxs-lookup"><span data-stu-id="b8442-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="b8442-140">Introducción a las recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="b8442-140">Security recommendations overview</span></span>

<span data-ttu-id="b8442-141">Vea recomendaciones, número de puntos débiles encontrados, componentes relacionados, información sobre amenazas, número de dispositivos expuestos, estado, tipo de corrección, actividades de corrección, impacto en la puntuación de exposición y Puntuación segura de Microsoft para dispositivos y etiquetas asociadas.</span><span class="sxs-lookup"><span data-stu-id="b8442-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="b8442-142">El color del gráfico de **dispositivos expuestos** cambia a medida que cambia la tendencia.</span><span class="sxs-lookup"><span data-stu-id="b8442-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="b8442-143">Si el número de dispositivos expuestos va en aumento, el color cambia a rojo.</span><span class="sxs-lookup"><span data-stu-id="b8442-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="b8442-144">Si hay una disminución en el número de dispositivos expuestos, el color del gráfico cambiará a verde.</span><span class="sxs-lookup"><span data-stu-id="b8442-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="b8442-145">La administración de amenazas y vulnerabilidades muestra los dispositivos que estaban en uso hasta **hace 30** días.</span><span class="sxs-lookup"><span data-stu-id="b8442-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="b8442-146">Esto es diferente del resto de Microsoft Defender para Endpoint, donde si un dispositivo no ha estado en uso durante más de 7 días tiene un estado "Inactivo".</span><span class="sxs-lookup"><span data-stu-id="b8442-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![Ejemplo de la página de aterrizaje para recomendaciones de seguridad.](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="b8442-148">Iconos</span><span class="sxs-lookup"><span data-stu-id="b8442-148">Icons</span></span>

<span data-ttu-id="b8442-149">Los iconos útiles también llaman rápidamente la atención sobre:</span><span class="sxs-lookup"><span data-stu-id="b8442-149">Useful icons also quickly call your attention to:</span></span>
- ![flecha que alcanza un destino](images/tvm_alert_icon.png) <span data-ttu-id="b8442-151">posibles alertas activas</span><span class="sxs-lookup"><span data-stu-id="b8442-151">possible active alerts</span></span>
- ![error rojo](images/tvm_bug_icon.png) <span data-ttu-id="b8442-153">vulnerabilidades públicas asociadas</span><span class="sxs-lookup"><span data-stu-id="b8442-153">associated public exploits</span></span>
- ![bombilla](images/tvm_insight_icon.png) <span data-ttu-id="b8442-155">recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b8442-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="b8442-156">Explorar opciones de recomendación de seguridad</span><span class="sxs-lookup"><span data-stu-id="b8442-156">Explore security recommendation options</span></span>

<span data-ttu-id="b8442-157">Seleccione la recomendación de seguridad que desea investigar o procesar.</span><span class="sxs-lookup"><span data-stu-id="b8442-157">Select the security recommendation that you want to investigate or process.</span></span>

![Ejemplo de una página desplegable de recomendación de seguridad.](images/secrec-flyouteolsw.png)

<span data-ttu-id="b8442-159">En el menú desplegable, puede elegir cualquiera de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b8442-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="b8442-160">**Página de software abierto:** abra la página de software para obtener más contexto en el software y cómo se distribuye.</span><span class="sxs-lookup"><span data-stu-id="b8442-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="b8442-161">La información puede incluir contexto de amenaza, recomendaciones asociadas, debilidades detectadas, número de dispositivos expuestos, vulnerabilidades detectadas, nombres y detalles de dispositivos con el software instalado y distribución de versiones.</span><span class="sxs-lookup"><span data-stu-id="b8442-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="b8442-162">[**Opciones de corrección:**](tvm-remediation.md) envíe una solicitud de corrección para abrir un vale en Microsoft Intune para que el administrador de TI pueda recoger y dirigirse.</span><span class="sxs-lookup"><span data-stu-id="b8442-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="b8442-163">Realice un seguimiento de la actividad de corrección en la página Corrección.</span><span class="sxs-lookup"><span data-stu-id="b8442-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="b8442-164">[**Opciones de excepción:**](tvm-exception.md) envíe una excepción, proporcione una justificación y establezca la duración de la excepción si aún no puede corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="b8442-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="b8442-165">Cuando se realiza un cambio de software en un dispositivo, normalmente los datos tardan dos horas en reflejarse en el portal de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b8442-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="b8442-166">Sin embargo, a veces puede tardar más tiempo.</span><span class="sxs-lookup"><span data-stu-id="b8442-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="b8442-167">Los cambios de configuración pueden tardar entre 4 y 24 horas.</span><span class="sxs-lookup"><span data-stu-id="b8442-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="b8442-168">Investigar los cambios en la exposición o el impacto del dispositivo</span><span class="sxs-lookup"><span data-stu-id="b8442-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="b8442-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span><span class="sxs-lookup"><span data-stu-id="b8442-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="b8442-170">Seleccione la recomendación y **la página Abrir software**</span><span class="sxs-lookup"><span data-stu-id="b8442-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="b8442-171">Seleccione la **pestaña Escala de tiempo** de eventos para ver todos los eventos de impacto relacionados con ese software, como nuevas vulnerabilidades o nuevas vulnerabilidades públicas.</span><span class="sxs-lookup"><span data-stu-id="b8442-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="b8442-172">Más información sobre la escala de tiempo de eventos</span><span class="sxs-lookup"><span data-stu-id="b8442-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="b8442-173">Decidir cómo abordar el aumento o la exposición de su organización, como enviar una solicitud de corrección</span><span class="sxs-lookup"><span data-stu-id="b8442-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="b8442-174">Corrección de solicitudes</span><span class="sxs-lookup"><span data-stu-id="b8442-174">Request remediation</span></span>

<span data-ttu-id="b8442-175">La capacidad de corrección de la administración de amenazas y vulnerabilidades separa la brecha entre los administradores de SEGURIDAD y TI a través del flujo de trabajo de solicitud de corrección.</span><span class="sxs-lookup"><span data-stu-id="b8442-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="b8442-176">Los administradores de seguridad como puede solicitar al administrador de TI que corrija una vulnerabilidad desde la página Recomendación **de** seguridad a Intune.</span><span class="sxs-lookup"><span data-stu-id="b8442-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="b8442-177">Más información sobre las opciones de corrección</span><span class="sxs-lookup"><span data-stu-id="b8442-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="b8442-178">Cómo solicitar corrección</span><span class="sxs-lookup"><span data-stu-id="b8442-178">How to request remediation</span></span>

<span data-ttu-id="b8442-179">Seleccione una recomendación de seguridad para la que desea solicitar corrección y, a continuación, seleccione **Opciones de corrección**.</span><span class="sxs-lookup"><span data-stu-id="b8442-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="b8442-180">Rellene el formulario y seleccione **Enviar solicitud**.</span><span class="sxs-lookup"><span data-stu-id="b8442-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="b8442-181">Vaya a la [**página Corrección**](tvm-remediation.md) para ver el estado de la solicitud de corrección.</span><span class="sxs-lookup"><span data-stu-id="b8442-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="b8442-182">Obtenga más información sobre cómo solicitar corrección</span><span class="sxs-lookup"><span data-stu-id="b8442-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="b8442-183">Archivo para excepción</span><span class="sxs-lookup"><span data-stu-id="b8442-183">File for exception</span></span>

<span data-ttu-id="b8442-184">Como alternativa a una solicitud de corrección cuando una recomendación no es relevante en este momento, puede crear excepciones para las recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="b8442-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="b8442-185">Más información sobre las excepciones</span><span class="sxs-lookup"><span data-stu-id="b8442-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="b8442-186">Solo los usuarios con permisos de "control de excepciones" pueden agregar excepciones.</span><span class="sxs-lookup"><span data-stu-id="b8442-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="b8442-187">[Obtenga más información sobre los roles RBAC](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b8442-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="b8442-188">Cuando se crea una excepción para una recomendación, la recomendación ya no está activa.</span><span class="sxs-lookup"><span data-stu-id="b8442-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="b8442-189">El estado de recomendación cambiará a **Excepción completa** o **Excepción parcial** (por grupo de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="b8442-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="b8442-190">Cómo crear una excepción</span><span class="sxs-lookup"><span data-stu-id="b8442-190">How to create an exception</span></span>

<span data-ttu-id="b8442-191">Seleccione una recomendación de seguridad para la que quiera crear una excepción y, a continuación, seleccione **Opciones de excepción**.</span><span class="sxs-lookup"><span data-stu-id="b8442-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

![Mostrar dónde se encuentra el botón de "opciones de excepción" en un control de control de recomendación de seguridad.](images/tvm-exception-options.png)

<span data-ttu-id="b8442-193">Rellene el formulario y envíelo.</span><span class="sxs-lookup"><span data-stu-id="b8442-193">Fill out the form and submit.</span></span> <span data-ttu-id="b8442-194">Para ver todas las excepciones (actuales [](tvm-remediation.md) y pasadas), vaya a la página Corrección en el menú Administración de vulnerabilidades de **threat &** y seleccione la pestaña **Excepciones.** Obtenga más información sobre cómo crear [una](tvm-exception.md#create-an-exception) excepción</span><span class="sxs-lookup"><span data-stu-id="b8442-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="b8442-195">Imprecisión de informe</span><span class="sxs-lookup"><span data-stu-id="b8442-195">Report inaccuracy</span></span>

<span data-ttu-id="b8442-196">Puede informar de un falso positivo cuando vea información imprecisa, inexacta, incompleta o que ya haya corregido la recomendación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b8442-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="b8442-197">Abra la recomendación seguridad.</span><span class="sxs-lookup"><span data-stu-id="b8442-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="b8442-198">Seleccione los tres puntos junto a la recomendación de seguridad que desea notificar y, a continuación, seleccione **Informar de imprecisión.**</span><span class="sxs-lookup"><span data-stu-id="b8442-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![Muestra dónde se encuentra el botón "Informar de imprecisión" en un control desplegable de recomendación de seguridad.](images/report-inaccuracy500.png)

3. <span data-ttu-id="b8442-200">En el panel desplegable, seleccione la categoría de imprecisión en el menú desplegable, rellene su dirección de correo electrónico y detalles sobre la imprecisión.</span><span class="sxs-lookup"><span data-stu-id="b8442-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="b8442-201">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b8442-201">Select **Submit**.</span></span> <span data-ttu-id="b8442-202">Sus comentarios se envían inmediatamente a los expertos en administración de amenazas y vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="b8442-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b8442-203">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="b8442-203">Related articles</span></span>

- [<span data-ttu-id="b8442-204">Introducción a la administración de amenazas y vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="b8442-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="b8442-205">Panel</span><span class="sxs-lookup"><span data-stu-id="b8442-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="b8442-206">Puntuación de exposición</span><span class="sxs-lookup"><span data-stu-id="b8442-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="b8442-207">Puntuación de seguridad de Microsoft para dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8442-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="b8442-208">Corregir puntos vulnerables</span><span class="sxs-lookup"><span data-stu-id="b8442-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="b8442-209">Crear y ver excepciones para recomendaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="b8442-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="b8442-210">Línea de tiempo de eventos</span><span class="sxs-lookup"><span data-stu-id="b8442-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
