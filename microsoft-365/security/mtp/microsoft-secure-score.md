---
title: Puntuación de seguridad de Microsoft
description: Describe la puntuación de seguridad de Microsoft en el Centro de seguridad de Microsoft 365, cómo mejorar su posición de seguridad y lo que los administradores de seguridad pueden esperar.
keywords: puntuación de seguridad de microsoft, puntuación de seguridad, puntuación de seguridad de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 39abcbde82c2902b091b42db3dbc8e1ee2cbd924
ms.sourcegitcommit: 8b3ff6e9f8931327b6f0541fd882107687cd123e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2021
ms.locfileid: "49942795"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="4369d-104">Puntuación de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4369d-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4369d-105">Puntuación de seguridad de Microsoft es una medida de la posición de seguridad de una organización, con un número mayor que indica más acciones de mejora tomadas.</span><span class="sxs-lookup"><span data-stu-id="4369d-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="4369d-106">Puede encontrarse en el Centro de seguridad https://security.microsoft.com/securescore [de Microsoft 365.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="4369d-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="4369d-107">Seguir las recomendaciones de puntuación segura puede proteger a su organización de las amenazas.</span><span class="sxs-lookup"><span data-stu-id="4369d-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="4369d-108">Desde un panel centralizado en el Centro de seguridad de Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de sus identidades, aplicaciones y dispositivos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4369d-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="4369d-109">Puntuación segura ayuda a las organizaciones:</span><span class="sxs-lookup"><span data-stu-id="4369d-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="4369d-110">Informe sobre el estado actual de la posición de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="4369d-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="4369d-111">Mejorar su posición de seguridad proporcionando detectabilidad, visibilidad, orientación y control.</span><span class="sxs-lookup"><span data-stu-id="4369d-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="4369d-112">Comparar con indicadores y establecer indicadores clave de rendimiento (KPI).</span><span class="sxs-lookup"><span data-stu-id="4369d-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="4369d-113">Las organizaciones obtienen acceso a visualizaciones sólidas de métricas y tendencias, integración con otros productos de Microsoft, comparación de puntuaciones con organizaciones similares y mucho más.</span><span class="sxs-lookup"><span data-stu-id="4369d-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="4369d-114">La puntuación también puede reflejar cuándo las soluciones de terceros han abordado las acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="4369d-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Página principal de puntuación segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="4369d-116">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="4369d-116">How it works</span></span>

<span data-ttu-id="4369d-117">Se le han dado puntos para las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4369d-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="4369d-118">Configuración de características de seguridad recomendadas</span><span class="sxs-lookup"><span data-stu-id="4369d-118">Configuring recommended security features</span></span>
- <span data-ttu-id="4369d-119">Realizar tareas relacionadas con la seguridad</span><span class="sxs-lookup"><span data-stu-id="4369d-119">Doing security-related tasks</span></span>
- <span data-ttu-id="4369d-120">Abordar la acción de mejora con una aplicación o software de terceros, o una mitigación alternativa</span><span class="sxs-lookup"><span data-stu-id="4369d-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="4369d-121">Algunas acciones de mejora solo dan puntos cuando se completan.</span><span class="sxs-lookup"><span data-stu-id="4369d-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="4369d-122">Algunos dan puntos parciales si se completan para algunos dispositivos o usuarios.</span><span class="sxs-lookup"><span data-stu-id="4369d-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="4369d-123">Si no puede o no desea aplicar una de las acciones de mejora, puede elegir aceptar el riesgo o el riesgo restante.</span><span class="sxs-lookup"><span data-stu-id="4369d-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="4369d-124">Si tiene una licencia para uno de los productos de Microsoft compatibles, verá recomendaciones para esos productos.</span><span class="sxs-lookup"><span data-stu-id="4369d-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="4369d-125">Le mostramos el conjunto completo de posibles mejoras para un producto, independientemente de la edición de licencia, suscripción o plan.</span><span class="sxs-lookup"><span data-stu-id="4369d-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="4369d-126">De esta forma, puede comprender los procedimientos recomendados de seguridad y mejorar su puntuación.</span><span class="sxs-lookup"><span data-stu-id="4369d-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="4369d-127">Su posición de seguridad absoluta, representada por la puntuación de seguridad, permanece igual independientemente de las licencias que posee su organización para un producto específico.</span><span class="sxs-lookup"><span data-stu-id="4369d-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="4369d-128">Tenga en cuenta que la seguridad debe estar equilibrada con la facilidad de uso y no todas las recomendaciones pueden funcionar para su entorno.</span><span class="sxs-lookup"><span data-stu-id="4369d-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="4369d-129">La puntuación se actualiza en tiempo real para reflejar la información presentada en las páginas de acciones de mejora y visualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4369d-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="4369d-130">Puntuación segura también se sincroniza diariamente para recibir datos del sistema sobre los puntos obtenidos para cada acción.</span><span class="sxs-lookup"><span data-stu-id="4369d-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="4369d-131">Escenarios clave</span><span class="sxs-lookup"><span data-stu-id="4369d-131">Key scenarios</span></span>

- [<span data-ttu-id="4369d-132">Comprobar la puntuación actual</span><span class="sxs-lookup"><span data-stu-id="4369d-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="4369d-133">Comparar tu puntuación con organizaciones como la tuyo</span><span class="sxs-lookup"><span data-stu-id="4369d-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="4369d-134">Ver acciones de mejora y decidir un plan de acción</span><span class="sxs-lookup"><span data-stu-id="4369d-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="4369d-135">Iniciar flujos de trabajo para investigar o implementar</span><span class="sxs-lookup"><span data-stu-id="4369d-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="4369d-136">Cómo se puntuan las acciones de mejora</span><span class="sxs-lookup"><span data-stu-id="4369d-136">How improvement actions are scored</span></span>

<span data-ttu-id="4369d-137">Cada acción de mejora vale 10 puntos o menos y la mayoría se puntua de forma binaria.</span><span class="sxs-lookup"><span data-stu-id="4369d-137">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="4369d-138">Si implementas la acción de mejora, como crear una nueva directiva o activar una configuración específica, obtienes el 100 % de los puntos.</span><span class="sxs-lookup"><span data-stu-id="4369d-138">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="4369d-139">Para otras acciones de mejora, los puntos se dan como un porcentaje de la configuración total.</span><span class="sxs-lookup"><span data-stu-id="4369d-139">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="4369d-140">Por ejemplo, una acción de mejora indica que obtiene 10 puntos al proteger a todos los usuarios con la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="4369d-140">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="4369d-141">Solo tienes 50 de 100 usuarios totales protegidos, por lo que obtenerías una puntuación parcial de 5 puntos (50 protegido / 100 total \* 10 pts máximo = 5 ptos).</span><span class="sxs-lookup"><span data-stu-id="4369d-141">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="4369d-142">Productos incluidos en puntuación de seguridad</span><span class="sxs-lookup"><span data-stu-id="4369d-142">Products included in Secure Score</span></span>

<span data-ttu-id="4369d-143">Actualmente hay recomendaciones para los siguientes productos:</span><span class="sxs-lookup"><span data-stu-id="4369d-143">Currently there are recommendations for the following products:</span></span>

- <span data-ttu-id="4369d-144">Microsoft 365 (incluido Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="4369d-144">Microsoft 365 (including Exchange Online)</span></span>
- <span data-ttu-id="4369d-145">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4369d-145">Azure Active Directory</span></span>
- <span data-ttu-id="4369d-146">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4369d-146">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="4369d-147">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="4369d-147">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="4369d-148">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4369d-148">Cloud App Security</span></span>
- <span data-ttu-id="4369d-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4369d-149">Microsoft Teams</span></span>

<span data-ttu-id="4369d-150">Próximamente se ofrece una serie de recomendaciones para otros productos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4369d-150">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="4369d-151">Las recomendaciones no cubren todas las superficies de ataque asociadas con cada producto, pero son una buena línea base.</span><span class="sxs-lookup"><span data-stu-id="4369d-151">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="4369d-152">También puedes marcar las acciones de mejora como cubiertas por un tercero o mitigación alternativa.</span><span class="sxs-lookup"><span data-stu-id="4369d-152">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="4369d-153">Valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="4369d-153">Security defaults</span></span>

<span data-ttu-id="4369d-154">La puntuación de seguridad de Microsoft ha actualizado las acciones de mejora para admitir los valores predeterminados de seguridad en [Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)lo que facilita la protección de su organización con opciones de seguridad preconfiguradas para ataques comunes.</span><span class="sxs-lookup"><span data-stu-id="4369d-154">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="4369d-155">Si activas los valores predeterminados de seguridad, se te concederán puntos completos para las siguientes acciones de mejora:</span><span class="sxs-lookup"><span data-stu-id="4369d-155">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="4369d-156">Asegurarse de que todos los usuarios pueden completar la autenticación multifactor para el acceso seguro (9 puntos)</span><span class="sxs-lookup"><span data-stu-id="4369d-156">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="4369d-157">Requerir MFA para roles administrativos (10 puntos)</span><span class="sxs-lookup"><span data-stu-id="4369d-157">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="4369d-158">Habilitar la directiva para bloquear la autenticación heredada (7 puntos)</span><span class="sxs-lookup"><span data-stu-id="4369d-158">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="4369d-159">Los valores predeterminados de seguridad incluyen características de seguridad que proporcionan seguridad similar a las acciones de mejora de la "directiva de riesgo de inicio de sesión" y la "directiva de riesgo de usuario".</span><span class="sxs-lookup"><span data-stu-id="4369d-159">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="4369d-160">En lugar de configurar estas directivas por encima de los valores predeterminados de seguridad, recomendamos actualizar sus estados a "Resuelto mediante mitigación alternativa".</span><span class="sxs-lookup"><span data-stu-id="4369d-160">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="4369d-161">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="4369d-161">Required permissions</span></span>

<span data-ttu-id="4369d-162">Para tener permiso para obtener acceso a la puntuación de seguridad de Microsoft, debe tener asignado uno de los siguientes roles en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4369d-162">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="4369d-163">Leer y escribir roles</span><span class="sxs-lookup"><span data-stu-id="4369d-163">Read and write roles</span></span>

<span data-ttu-id="4369d-164">Con el acceso de lectura y escritura, puede realizar cambios e interactuar directamente con la puntuación de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4369d-164">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="4369d-165">También puede asignar acceso de solo lectura a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="4369d-165">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="4369d-166">Administrador global</span><span class="sxs-lookup"><span data-stu-id="4369d-166">Global administrator</span></span>
* <span data-ttu-id="4369d-167">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="4369d-167">Security administrator</span></span>
* <span data-ttu-id="4369d-168">Administrador de Exchange</span><span class="sxs-lookup"><span data-stu-id="4369d-168">Exchange administrator</span></span>
* <span data-ttu-id="4369d-169">Administrador de SharePoint</span><span class="sxs-lookup"><span data-stu-id="4369d-169">SharePoint administrator</span></span>
* <span data-ttu-id="4369d-170">Administrador de cuentas</span><span class="sxs-lookup"><span data-stu-id="4369d-170">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="4369d-171">Roles de solo lectura</span><span class="sxs-lookup"><span data-stu-id="4369d-171">Read-only roles</span></span>

<span data-ttu-id="4369d-172">Con el acceso de solo lectura, no es posible editar el estado o las notas de una acción de mejora, editar zonas de puntuación ni editar comparaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="4369d-172">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="4369d-173">Administrador del departamento de soporto técnico</span><span class="sxs-lookup"><span data-stu-id="4369d-173">Helpdesk administrator</span></span>
* <span data-ttu-id="4369d-174">Administrador de usuarios</span><span class="sxs-lookup"><span data-stu-id="4369d-174">User administrator</span></span>
* <span data-ttu-id="4369d-175">Administrador de servicios</span><span class="sxs-lookup"><span data-stu-id="4369d-175">Service administrator</span></span>
* <span data-ttu-id="4369d-176">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="4369d-176">Security reader</span></span>
* <span data-ttu-id="4369d-177">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="4369d-177">Security operator</span></span>
* <span data-ttu-id="4369d-178">Lector global</span><span class="sxs-lookup"><span data-stu-id="4369d-178">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="4369d-179">Reconocimiento de riesgos</span><span class="sxs-lookup"><span data-stu-id="4369d-179">Risk awareness</span></span>

<span data-ttu-id="4369d-180">Puntuación de seguridad de Microsoft es un resumen numérico de su posición de seguridad en función de las configuraciones del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="4369d-180">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="4369d-181">No es una medida absoluta de la probabilidad de que se infracción el sistema o los datos.</span><span class="sxs-lookup"><span data-stu-id="4369d-181">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="4369d-182">En su lugar, representa el grado en que ha adoptado controles de seguridad en su entorno de Microsoft que pueden ayudar a compensar el riesgo de que se infracción.</span><span class="sxs-lookup"><span data-stu-id="4369d-182">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="4369d-183">Ningún servicio en línea es ileso de las infracciones de seguridad y la puntuación de seguridad no debe interpretarse como una garantía contra las infracciones de seguridad de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="4369d-183">No online service is immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="4369d-184">Queremos escuchar sus comentarios</span><span class="sxs-lookup"><span data-stu-id="4369d-184">We want to hear from you</span></span>

<span data-ttu-id="4369d-185">Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="4369d-185">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="4369d-186">Estamos supervisando la comunidad y proporcionaremos ayuda.</span><span class="sxs-lookup"><span data-stu-id="4369d-186">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="4369d-187">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="4369d-187">Related resources</span></span>

- [<span data-ttu-id="4369d-188">Evaluar su postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="4369d-188">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="4369d-189">Realizar un seguimiento del historial de puntuaciones seguras de Microsoft y cumplir los objetivos</span><span class="sxs-lookup"><span data-stu-id="4369d-189">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="4369d-190">Próximas novedades</span><span class="sxs-lookup"><span data-stu-id="4369d-190">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="4369d-191">Novedades</span><span class="sxs-lookup"><span data-stu-id="4369d-191">What's new</span></span>](microsoft-secure-score-whats-new.md)
