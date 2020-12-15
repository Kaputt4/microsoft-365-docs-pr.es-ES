---
title: Puntuación de seguridad de Microsoft
description: Describe la puntuación segura de Microsoft en el centro de seguridad 365 de Microsoft, cómo mejorar su postura de seguridad y qué administradores de seguridad pueden esperar.
keywords: puntuación segura de Microsoft, calificación segura, puntuación segura de Office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 7fe5be065ee45700a1f08a39c8050757c3843f7b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682576"
---
# <a name="microsoft-secure-score"></a><span data-ttu-id="b35da-104">Puntuación de seguridad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b35da-104">Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b35da-105">La calificación segura de Microsoft es una medida de la postura de seguridad de una organización, con un número más alto que indica que se han realizado más acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="b35da-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="b35da-106">Puede encontrarse en https://security.microsoft.com/securescore el [centro de seguridad de Microsoft 365](overview-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="b35da-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="b35da-107">Seguir las recomendaciones de puntuación segura puede proteger a su organización de las amenazas.</span><span class="sxs-lookup"><span data-stu-id="b35da-107">Following the Secure Score recommendations can protect your organization from threats.</span></span> <span data-ttu-id="b35da-108">Desde un panel centralizado en el centro de seguridad de Microsoft 365, las organizaciones pueden supervisar y trabajar en la seguridad de sus identidades, aplicaciones y dispositivos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b35da-108">From a centralized dashboard in the Microsoft 365 security center, organizations can monitor and work on the security of their Microsoft 365 identities, apps, and devices.</span></span>

<span data-ttu-id="b35da-109">La puntuación segura ayuda a las organizaciones a:</span><span class="sxs-lookup"><span data-stu-id="b35da-109">Secure Score helps organizations:</span></span>  

* <span data-ttu-id="b35da-110">Informe sobre el estado actual de la postura de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="b35da-110">Report on the current state of the organization's security posture.</span></span>
* <span data-ttu-id="b35da-111">Mejorar su postura de seguridad proporcionando detección, visibilidad, orientación y control.</span><span class="sxs-lookup"><span data-stu-id="b35da-111">Improve their security posture by providing discoverability, visibility, guidance, and control.</span></span>  
* <span data-ttu-id="b35da-112">Comparar con benchmarks y establecer indicadores clave de rendimiento (KPI).</span><span class="sxs-lookup"><span data-stu-id="b35da-112">Compare with benchmarks and establish key performance indicators (KPIs).</span></span>

<span data-ttu-id="b35da-113">Las organizaciones obtienen acceso a las sólidas visualizaciones de métricas y tendencias, la integración con otros productos de Microsoft, la puntuación con organizaciones similares y mucho más.</span><span class="sxs-lookup"><span data-stu-id="b35da-113">Organizations gain access to robust visualizations of metrics and trends, integration with other Microsoft products, score comparison with similar organizations, and much more.</span></span> <span data-ttu-id="b35da-114">La puntuación también puede reflejar Cuándo las soluciones de terceros han tratado las acciones recomendadas.</span><span class="sxs-lookup"><span data-stu-id="b35da-114">The score can also reflect when third-party solutions have addressed recommended actions.</span></span>

![Página principal de puntuación segura](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a><span data-ttu-id="b35da-116">Cómo funciona</span><span class="sxs-lookup"><span data-stu-id="b35da-116">How it works</span></span>

<span data-ttu-id="b35da-117">Se le proporcionan puntos para las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b35da-117">You're given points for the following actions:</span></span>

- <span data-ttu-id="b35da-118">Configuración de las características de seguridad recomendadas</span><span class="sxs-lookup"><span data-stu-id="b35da-118">Configuring recommended security features</span></span>
- <span data-ttu-id="b35da-119">Realización de tareas relacionadas con la seguridad</span><span class="sxs-lookup"><span data-stu-id="b35da-119">Performing security-related tasks</span></span>
- <span data-ttu-id="b35da-120">Solucionar la acción de mejora con una aplicación o software de terceros, o una mitigación alternativa</span><span class="sxs-lookup"><span data-stu-id="b35da-120">Addressing the improvement action with a third-party application or software, or an alternate mitigation</span></span>

<span data-ttu-id="b35da-121">Algunas acciones de mejora solo proporcionan puntos cuando se completan completamente.</span><span class="sxs-lookup"><span data-stu-id="b35da-121">Some improvement actions only give points when fully completed.</span></span> <span data-ttu-id="b35da-122">Algunos proporcionan puntos parciales si están completos para algunos dispositivos o usuarios.</span><span class="sxs-lookup"><span data-stu-id="b35da-122">Some give partial points if they're completed for some devices or users.</span></span> <span data-ttu-id="b35da-123">Si no puede o no desea activar una de las acciones de mejora, puede optar por aceptar el riesgo o el riesgo restante.</span><span class="sxs-lookup"><span data-stu-id="b35da-123">If you can't or don't want to enact one of the improvement actions, you can choose to accept the risk or remaining risk.</span></span>

<span data-ttu-id="b35da-124">Si tiene una licencia para uno de los productos de Microsoft admitidos, verá recomendaciones para esos productos.</span><span class="sxs-lookup"><span data-stu-id="b35da-124">If you have a license for one of the supported Microsoft products, then you'll see recommendations for those products.</span></span> <span data-ttu-id="b35da-125">Le mostramos el conjunto completo de mejoras posibles para un producto, independientemente de la edición de licencia, la suscripción o el plan.</span><span class="sxs-lookup"><span data-stu-id="b35da-125">We show you the full set of possible improvements for a product, regardless of license edition, subscription, or plan.</span></span> <span data-ttu-id="b35da-126">De este modo, puede comprender los procedimientos recomendados de seguridad y mejorar su calificación.</span><span class="sxs-lookup"><span data-stu-id="b35da-126">This way, you can understand security best practices and improve your score.</span></span> <span data-ttu-id="b35da-127">La postura absoluta de seguridad, representada por la puntuación segura, sigue siendo la misma independientemente de las licencias que posea su organización para un producto específico.</span><span class="sxs-lookup"><span data-stu-id="b35da-127">Your absolute security posture, represented by Secure Score, stays the same no matter what licenses your organization owns for a specific product.</span></span> <span data-ttu-id="b35da-128">Tenga en cuenta que la seguridad debe sopesarse con facilidad de uso y no todas las recomendaciones pueden funcionar en su entorno.</span><span class="sxs-lookup"><span data-stu-id="b35da-128">Keep in mind that security should be balanced with usability, and not every recommendation can work for your environment.</span></span>

<span data-ttu-id="b35da-129">La puntuación se actualiza en tiempo real para reflejar la información que se presenta en las páginas de acciones de visualización y de mejora.</span><span class="sxs-lookup"><span data-stu-id="b35da-129">Your score is updated in real time to reflect the information presented in the visualizations and improvement action pages.</span></span> <span data-ttu-id="b35da-130">La puntuación segura también se sincroniza diariamente para recibir datos del sistema sobre los puntos alcanzados para cada acción.</span><span class="sxs-lookup"><span data-stu-id="b35da-130">Secure Score also syncs daily to receive system data about your achieved points for each action.</span></span>

### <a name="key-scenarios"></a><span data-ttu-id="b35da-131">Escenarios clave</span><span class="sxs-lookup"><span data-stu-id="b35da-131">Key scenarios</span></span>

- [<span data-ttu-id="b35da-132">Comprobar el resultado actual</span><span class="sxs-lookup"><span data-stu-id="b35da-132">Check your current score</span></span>](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [<span data-ttu-id="b35da-133">Comparar su calificación con organizaciones como la suya</span><span class="sxs-lookup"><span data-stu-id="b35da-133">Compare your score to organizations like yours</span></span>](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [<span data-ttu-id="b35da-134">Ver acciones de mejora y decidir un plan de acción</span><span class="sxs-lookup"><span data-stu-id="b35da-134">View improvement actions and decide an action plan</span></span>](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [<span data-ttu-id="b35da-135">Iniciar flujos de trabajo para investigar o implementar</span><span class="sxs-lookup"><span data-stu-id="b35da-135">Initiate work flows to investigate or implement</span></span>](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [<span data-ttu-id="b35da-136">Microsoft 365 Security Center and ServiceNow Integration</span><span class="sxs-lookup"><span data-stu-id="b35da-136">Microsoft 365 security center and ServiceNow integration</span></span>](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a><span data-ttu-id="b35da-137">Cómo se puntuan las acciones de mejora</span><span class="sxs-lookup"><span data-stu-id="b35da-137">How improvement actions are scored</span></span>

<span data-ttu-id="b35da-138">Cada acción de mejora vale 10 puntos o menos, y la mayoría se puntúa de una manera binaria.</span><span class="sxs-lookup"><span data-stu-id="b35da-138">Each improvement action is worth 10 points or less, and most are scored in a binary fashion.</span></span> <span data-ttu-id="b35da-139">Si implementa la acción de mejora, como crear una nueva Directiva o activar una configuración específica, obtendrá un 100% de los puntos.</span><span class="sxs-lookup"><span data-stu-id="b35da-139">If you implement the improvement action, like create a new policy or turn on a specific setting, you get 100% of the points.</span></span> <span data-ttu-id="b35da-140">Para otras acciones de mejora, los puntos se dan como un porcentaje de la configuración total.</span><span class="sxs-lookup"><span data-stu-id="b35da-140">For other improvement actions, points are given as a percentage of the total configuration.</span></span>

<span data-ttu-id="b35da-141">Por ejemplo, los Estados de acción de mejora obtienen 10 puntos al proteger a todos los usuarios con la autenticación multifactor.</span><span class="sxs-lookup"><span data-stu-id="b35da-141">For example, an improvement action states you get 10 points by protecting all your users with multi-factor authentication.</span></span> <span data-ttu-id="b35da-142">Solo tiene un 50 de 100 total de usuarios protegidos, por lo que obtendrá una puntuación parcial de 5 puntos (50 protegido/100 total \* 10 máx PTS = 5 PTS).</span><span class="sxs-lookup"><span data-stu-id="b35da-142">You only have 50 of 100 total users protected, so you'd get a partial score of 5 points (50 protected / 100 total \* 10 max pts = 5 pts).</span></span>

### <a name="products-included-in-secure-score"></a><span data-ttu-id="b35da-143">Productos incluidos en la puntuación segura</span><span class="sxs-lookup"><span data-stu-id="b35da-143">Products included in Secure Score</span></span>

<span data-ttu-id="b35da-144">Actualmente hay recomendaciones para Microsoft 365 (incluido Exchange Online), Azure Active Directory, Microsoft defender para extremo, Microsoft defender para identidad y Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="b35da-144">Currently there are recommendations for Microsoft 365 (including Exchange Online), Azure Active Directory, Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Cloud App Security.</span></span> <span data-ttu-id="b35da-145">Pronto estarán disponibles recomendaciones para otros productos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b35da-145">Recommendations for other security products are coming soon.</span></span> <span data-ttu-id="b35da-146">Las recomendaciones no cubren todas las superficies de ataque asociadas con cada producto, pero son una buena línea de base.</span><span class="sxs-lookup"><span data-stu-id="b35da-146">The recommendations won't cover all the attack surfaces associated with each product, but they're a good baseline.</span></span> <span data-ttu-id="b35da-147">También puede marcar las acciones de mejora como cubiertas por un tercero o una mitigación alternativa.</span><span class="sxs-lookup"><span data-stu-id="b35da-147">You can also mark the improvement actions as covered by a third party or alternate mitigation.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="b35da-148">Valores predeterminados de seguridad</span><span class="sxs-lookup"><span data-stu-id="b35da-148">Security defaults</span></span>

<span data-ttu-id="b35da-149">La calificación segura de Microsoft tiene acciones de mejora actualizadas para admitir los [valores predeterminados de seguridad en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), que facilitan la protección de la organización con una configuración de seguridad preconfigurada para ataques comunes.</span><span class="sxs-lookup"><span data-stu-id="b35da-149">Microsoft Secure Score has updated improvement actions to support [security defaults in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with preconfigured security settings for common attacks.</span></span>

<span data-ttu-id="b35da-150">Si activa los valores predeterminados de seguridad, se le otorgarán puntos completos para las siguientes acciones de mejora:</span><span class="sxs-lookup"><span data-stu-id="b35da-150">If you turn on security defaults, you'll be awarded full points for the following improvement actions:</span></span>

- <span data-ttu-id="b35da-151">Asegurarse de que todos los usuarios puedan completar la autenticación multifactor para el acceso seguro (9 puntos)</span><span class="sxs-lookup"><span data-stu-id="b35da-151">Ensure all users can complete multi-factor authentication for secure access (9 points)</span></span>
- <span data-ttu-id="b35da-152">Requerir MFA para roles administrativos (10 puntos)</span><span class="sxs-lookup"><span data-stu-id="b35da-152">Require MFA for administrative roles (10 points)</span></span>
- <span data-ttu-id="b35da-153">Habilitar la Directiva para bloquear la autenticación heredada (7 puntos)</span><span class="sxs-lookup"><span data-stu-id="b35da-153">Enable policy to block legacy authentication (7 points)</span></span>

>[!IMPORTANT]
><span data-ttu-id="b35da-154">Los valores predeterminados de seguridad incluyen características de seguridad que proporcionan seguridad similar a las acciones de mejora "Directiva de riesgo de inicio de sesión" y "Directiva de riesgos de usuario".</span><span class="sxs-lookup"><span data-stu-id="b35da-154">Security defaults include security features that provide similar security to the "sign-in risk policy" and "user risk policy" improvement actions.</span></span> <span data-ttu-id="b35da-155">En lugar de configurar estas directivas sobre los valores predeterminados de seguridad, se recomienda actualizar sus Estados a "resuelto a través de una mitigación alternativa".</span><span class="sxs-lookup"><span data-stu-id="b35da-155">Instead of setting up these policies on top of the security defaults, we recommend updating their statuses to "Resolved through alternative mitigation."</span></span>

## <a name="required-permissions"></a><span data-ttu-id="b35da-156">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="b35da-156">Required permissions</span></span>

<span data-ttu-id="b35da-157">Para tener permiso de acceso a la puntuación segura de Microsoft, debe tener asignado uno de los siguientes roles en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b35da-157">To have permission to access Microsoft Secure Score, you must be assigned one of the following roles in Azure Active Directory.</span></span>

### <a name="read-and-write-roles"></a><span data-ttu-id="b35da-158">Lectura y escritura de roles</span><span class="sxs-lookup"><span data-stu-id="b35da-158">Read and write roles</span></span>

<span data-ttu-id="b35da-159">Con acceso de lectura y escritura, puede realizar cambios e interactuar directamente con la calificación segura.</span><span class="sxs-lookup"><span data-stu-id="b35da-159">With read and write access, you can make changes and directly interact with Secure Score.</span></span> <span data-ttu-id="b35da-160">También puede asignar acceso de solo lectura a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b35da-160">You can also assign read-only access to other users.</span></span>

* <span data-ttu-id="b35da-161">Administrador global</span><span class="sxs-lookup"><span data-stu-id="b35da-161">Global administrator</span></span>
* <span data-ttu-id="b35da-162">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="b35da-162">Security administrator</span></span>
* <span data-ttu-id="b35da-163">Administrador de Exchange</span><span class="sxs-lookup"><span data-stu-id="b35da-163">Exchange administrator</span></span>
* <span data-ttu-id="b35da-164">Administrador de SharePoint</span><span class="sxs-lookup"><span data-stu-id="b35da-164">SharePoint administrator</span></span>
* <span data-ttu-id="b35da-165">Administrador de la cuenta</span><span class="sxs-lookup"><span data-stu-id="b35da-165">Account administrator</span></span>

### <a name="read-only-roles"></a><span data-ttu-id="b35da-166">Solo lectura roles</span><span class="sxs-lookup"><span data-stu-id="b35da-166">Read-only roles</span></span>

<span data-ttu-id="b35da-167">Con acceso de solo lectura, no puede editar el estado o las notas para una acción de mejora, editar zonas de puntuación o editar comparaciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b35da-167">With read-only access, you aren't able to edit status or notes for an improvement action, edit score zones, or edit custom comparisons.</span></span>

* <span data-ttu-id="b35da-168">Administrador del departamento de soporto técnico</span><span class="sxs-lookup"><span data-stu-id="b35da-168">Helpdesk administrator</span></span>
* <span data-ttu-id="b35da-169">Administrador de usuarios</span><span class="sxs-lookup"><span data-stu-id="b35da-169">User administrator</span></span>
* <span data-ttu-id="b35da-170">Administrador de servicios</span><span class="sxs-lookup"><span data-stu-id="b35da-170">Service administrator</span></span>
* <span data-ttu-id="b35da-171">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="b35da-171">Security reader</span></span>
* <span data-ttu-id="b35da-172">Operador de seguridad</span><span class="sxs-lookup"><span data-stu-id="b35da-172">Security operator</span></span>
* <span data-ttu-id="b35da-173">Lector global</span><span class="sxs-lookup"><span data-stu-id="b35da-173">Global reader</span></span>

## <a name="risk-awareness"></a><span data-ttu-id="b35da-174">Conocimiento de riesgos</span><span class="sxs-lookup"><span data-stu-id="b35da-174">Risk awareness</span></span>

<span data-ttu-id="b35da-175">La puntuación segura de Microsoft es un resumen numérico de la postura de seguridad en función de la configuración del sistema, el comportamiento del usuario y otras medidas relacionadas con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="b35da-175">Microsoft Secure Score is a numerical summary of your security posture based on system configurations, user behavior, and other security-related measurements.</span></span> <span data-ttu-id="b35da-176">No es una medida absoluta de la probabilidad de que se infrinja el sistema o sus datos.</span><span class="sxs-lookup"><span data-stu-id="b35da-176">It isn't an absolute measurement of how likely your system or data will be breached.</span></span> <span data-ttu-id="b35da-177">En su lugar, representa en qué medida ha adoptado controles de seguridad en su entorno de Microsoft que pueden ayudar a compensar el riesgo de infracción.</span><span class="sxs-lookup"><span data-stu-id="b35da-177">Rather, it represents the extent to which you have adopted security controls in your Microsoft environment that can help offset the risk of being breached.</span></span> <span data-ttu-id="b35da-178">Ningún servicio en línea está completamente inmune a las infracciones de seguridad y la puntuación segura no se debe interpretar como una garantía contra la infracción de seguridad de ninguna manera.</span><span class="sxs-lookup"><span data-stu-id="b35da-178">No online service is completely immune from security breaches, and secure score shouldn't be interpreted as a guarantee against security breach in any manner.</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="b35da-179">Queremos escuchar sus comentarios</span><span class="sxs-lookup"><span data-stu-id="b35da-179">We want to hear from you</span></span>

<span data-ttu-id="b35da-180">Si tiene algún problema, háganoslo saber mediante la publicación de la comunidad de [seguridad, privacidad & cumplimiento](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) .</span><span class="sxs-lookup"><span data-stu-id="b35da-180">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="b35da-181">Estamos supervisando la comunidad y le proporcionaremos ayuda.</span><span class="sxs-lookup"><span data-stu-id="b35da-181">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="b35da-182">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="b35da-182">Related resources</span></span>

- [<span data-ttu-id="b35da-183">Evaluar su postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="b35da-183">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="b35da-184">Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir los objetivos</span><span class="sxs-lookup"><span data-stu-id="b35da-184">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="b35da-185">Próximas novedades</span><span class="sxs-lookup"><span data-stu-id="b35da-185">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="b35da-186">Novedades</span><span class="sxs-lookup"><span data-stu-id="b35da-186">What's new</span></span>](microsoft-secure-score-whats-new.md)
