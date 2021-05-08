---
title: Evaluar la posición de seguridad a través de Puntuación segura de Microsoft
description: Describe cómo tomar medidas para mejorar la puntuación segura de Microsoft en el centro Microsoft 365 seguridad.
keywords: puntuación segura de microsoft, puntuación segura, puntuación segura de office 365, puntuación de seguridad de Microsoft, centro de seguridad de Microsoft 365, acciones de mejora
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 8b321fc8883cf490cb5b2814d5c2b617a52dbb29
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246402"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a><span data-ttu-id="36c23-104">Evaluar la posición de seguridad con Puntuación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="36c23-104">Assess your security posture with Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="36c23-105">La Puntuación de seguridad de Microsoft es una medida de la actitud de seguridad de una organización, donde un número más alto indica que se han tomado más acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="36c23-105">Microsoft Secure Score is a measurement of an organization's security posture, with a higher number indicating more improvement actions taken.</span></span> <span data-ttu-id="36c23-106">Se puede encontrar en https://security.microsoft.com/securescore el centro Microsoft 365 [seguridad.](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="36c23-106">It can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

<span data-ttu-id="36c23-107">Para ayudarle a encontrar la información que necesita más rápidamente, las acciones de mejora de Microsoft se organizan en grupos:</span><span class="sxs-lookup"><span data-stu-id="36c23-107">To help you find the information you need more quickly, Microsoft improvement actions are organized into groups:</span></span>

* <span data-ttu-id="36c23-108">Identidad (Azure Active Directory cuentas & roles)</span><span class="sxs-lookup"><span data-stu-id="36c23-108">Identity (Azure Active Directory accounts & roles)</span></span>
* <span data-ttu-id="36c23-109">Device (Microsoft Defender para endpoint, conocido como [Puntuación segura de Microsoft para dispositivos](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span><span class="sxs-lookup"><span data-stu-id="36c23-109">Device (Microsoft Defender for Endpoint, known as [Microsoft Secure Score for Devices](/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices))</span></span>
* <span data-ttu-id="36c23-110">Aplicaciones (correo electrónico y aplicaciones en la nube, incluidas Office 365 y Microsoft Cloud App Security)</span><span class="sxs-lookup"><span data-stu-id="36c23-110">Apps (email and cloud apps, including Office 365 and Microsoft Cloud App Security)</span></span>

>[!NOTE]
><span data-ttu-id="36c23-111">En la versión reciente de Puntuación segura de Microsoft, se ha publicado un modelo de puntuación mejorado que hizo que Puntuación segura de Microsoft sea temporalmente incompatible con la puntuación segura de identidad y la API Graph puntuación.</span><span class="sxs-lookup"><span data-stu-id="36c23-111">In the recent release of Microsoft Secure Score, an improved scoring model has been released which made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span> [<span data-ttu-id="36c23-112">Ver detalles</span><span class="sxs-lookup"><span data-stu-id="36c23-112">View details</span></span>](microsoft-secure-score-whats-new.md)

<span data-ttu-id="36c23-113">En la página Introducción a la puntuación segura de Microsoft, vea cómo se dividen los puntos entre estos grupos y qué puntos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="36c23-113">In the Microsoft Secure Score overview page, view how points are split between these groups and what points are available.</span></span> <span data-ttu-id="36c23-114">También puedes obtener una vista general de la puntuación total, la tendencia histórica de tu puntuación segura con comparaciones comparativas comparativas y las acciones de mejora prioritarias que se pueden realizar para mejorar la puntuación.</span><span class="sxs-lookup"><span data-stu-id="36c23-114">You can also get an all-up view of the total score, historical trend of your secure score with benchmark comparisons, and prioritized improvement actions that can be taken to improve your score.</span></span>

![Página principal de puntuación segura](../../media/secure-score/secure-score-home-page.png)

## <a name="check-your-current-score"></a><span data-ttu-id="36c23-116">Comprobar la puntuación actual</span><span class="sxs-lookup"><span data-stu-id="36c23-116">Check your current score</span></span>

<span data-ttu-id="36c23-117">Para comprobar la puntuación actual, vaya a la página de información general de puntuación segura de Microsoft y busque el icono que indica **La puntuación segura**.</span><span class="sxs-lookup"><span data-stu-id="36c23-117">To check on your current score, go to the Microsoft Secure Score overview page and look for the tile that says **Your secure score**.</span></span> <span data-ttu-id="36c23-118">La puntuación se mostrará como un porcentaje, junto con el número de puntos que has logrado del total de puntos posibles.</span><span class="sxs-lookup"><span data-stu-id="36c23-118">Your score will be shown as a percentage, along with the number of points you've achieved out of the total possible points.</span></span>

<span data-ttu-id="36c23-119">Además, si selecciona el botón **Incluir** junto a la puntuación, puede elegir diferentes vistas de la puntuación.</span><span class="sxs-lookup"><span data-stu-id="36c23-119">Additionally, if you select the **Include** button next to your score, you can choose different views of your score.</span></span> <span data-ttu-id="36c23-120">Estas diferentes vistas de puntuación se mostrarán en el gráfico en el icono de puntuación y en el gráfico de desglose de puntos.</span><span class="sxs-lookup"><span data-stu-id="36c23-120">These different score views will display in the graph on the score tile and the point breakdown chart.</span></span>

<span data-ttu-id="36c23-121">Las siguientes son las puntuaciones que puedes agregar a tu vista de la puntuación general para ofrecerte una imagen más completa de la puntuación general:</span><span class="sxs-lookup"><span data-stu-id="36c23-121">The following are scores you can add to your view of your overall score to give you a fuller picture of your overall score:</span></span>

- <span data-ttu-id="36c23-122">**Puntuación planeada:** mostrar la puntuación proyectada cuando se completan las acciones planeadas</span><span class="sxs-lookup"><span data-stu-id="36c23-122">**Planned score**: Show projected score when planned actions are completed</span></span>
- <span data-ttu-id="36c23-123">**Puntuación de licencia actual:** mostrar la puntuación que se puede lograr con la licencia de Microsoft actual</span><span class="sxs-lookup"><span data-stu-id="36c23-123">**Current license score**: Show score that can be achieved with your current Microsoft license</span></span>
- <span data-ttu-id="36c23-124">**Puntuación alcanzable:** mostrar la puntuación que se puede lograr con las licencias de Microsoft y la aceptación del riesgo actual</span><span class="sxs-lookup"><span data-stu-id="36c23-124">**Achievable score**: Show score that can be achieved with your Microsoft licenses and current risk acceptance</span></span>

<span data-ttu-id="36c23-125">Esta vista es la que tendrá si has incluido todas las vistas de puntuación posibles:</span><span class="sxs-lookup"><span data-stu-id="36c23-125">This view is what it will look like if you've included all possible score views:</span></span>

![Su puntuación segura, incluida la puntuación planeada, la puntuación de licencia actual y la puntuación alcanzable](../../media/secure-score/secure-score-achievable.png)

## <a name="take-action-to-improve-your-score"></a><span data-ttu-id="36c23-127">Tomar medidas para mejorar la puntuación</span><span class="sxs-lookup"><span data-stu-id="36c23-127">Take action to improve your score</span></span>

<span data-ttu-id="36c23-128">La **pestaña Acciones de** mejora enumera las recomendaciones de seguridad que abordan posibles superficies de ataque.</span><span class="sxs-lookup"><span data-stu-id="36c23-128">The **Improvement actions** tab lists the security recommendations that address possible attack surfaces.</span></span> <span data-ttu-id="36c23-129">También incluye su estado (para abordar, planear, aceptar riesgos, resolver a través de terceros, resolver mediante mitigación alternativa y completar).</span><span class="sxs-lookup"><span data-stu-id="36c23-129">It also includes their status (to address, planned, risk accepted, resolved through third party, resolved through alternate mitigation, and completed).</span></span> <span data-ttu-id="36c23-130">Puede buscar, filtrar y agrupar todas las acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="36c23-130">You can search, filter, and group all the improvement actions.</span></span>  

### <a name="ranking"></a><span data-ttu-id="36c23-131">Clasificación</span><span class="sxs-lookup"><span data-stu-id="36c23-131">Ranking</span></span>

<span data-ttu-id="36c23-132">La clasificación se basa en el número de puntos que queda por lograr, la dificultad de implementación, el impacto del usuario y la complejidad.</span><span class="sxs-lookup"><span data-stu-id="36c23-132">Ranking is based on the number of points left to achieve, implementation difficulty, user impact, and complexity.</span></span> <span data-ttu-id="36c23-133">Las acciones de mejora clasificadas más altas tienen un gran número de puntos restantes con dificultad baja, impacto del usuario y complejidad.</span><span class="sxs-lookup"><span data-stu-id="36c23-133">The highest ranked improvement actions have a large number of points remaining with low difficulty, user impact, and complexity.</span></span>

### <a name="view-improvement-action-details"></a><span data-ttu-id="36c23-134">Ver detalles de la acción de mejora</span><span class="sxs-lookup"><span data-stu-id="36c23-134">View improvement action details</span></span>

<span data-ttu-id="36c23-135">Al seleccionar una acción de mejora específica, aparece un control desplegable de página completa.</span><span class="sxs-lookup"><span data-stu-id="36c23-135">When you select a specific improvement action, a full page flyout appears.</span></span>  

![Ejemplo de acción de mejora](../../media/secure-score/secure-score-improvement-action-details.png)

<span data-ttu-id="36c23-137">Para completar la acción, tienes algunas opciones:</span><span class="sxs-lookup"><span data-stu-id="36c23-137">To complete the action, you have a few options:</span></span>

- <span data-ttu-id="36c23-138">Seleccione **Administrar** para ir a la pantalla de configuración y realizar el cambio.</span><span class="sxs-lookup"><span data-stu-id="36c23-138">Select **Manage** to go the configuration screen and make the change.</span></span> <span data-ttu-id="36c23-139">A continuación, obtendrás los puntos que vale la acción, visibles en el vuelo hacia fuera. Los puntos suelen tardar unas 24 horas en actualizarse.</span><span class="sxs-lookup"><span data-stu-id="36c23-139">You'll then gain the points that the action is worth, visible in the fly out. Points generally take about 24 hours to update.</span></span>

- <span data-ttu-id="36c23-140">Seleccione **Compartir** para copiar el vínculo directo a la acción de mejora.</span><span class="sxs-lookup"><span data-stu-id="36c23-140">Select **Share** to copy the direct link to the improvement action.</span></span> <span data-ttu-id="36c23-141">También puede elegir la plataforma para compartir el vínculo, como correo electrónico, Microsoft Teams o Microsoft Planner.</span><span class="sxs-lookup"><span data-stu-id="36c23-141">You can also choose the platform to share the link, such as email, Microsoft Teams, or Microsoft Planner.</span></span>

<span data-ttu-id="36c23-142">Agrega **notas** para realizar un seguimiento del progreso o cualquier otra cosa en la que quieras comentar.</span><span class="sxs-lookup"><span data-stu-id="36c23-142">Add **Notes** to keep track of progress or anything else you want to comment on.</span></span> <span data-ttu-id="36c23-143">Si agrega sus propias **etiquetas a** la acción de mejora, puede filtrar por dichas etiquetas.</span><span class="sxs-lookup"><span data-stu-id="36c23-143">If you add your own **tags** to the improvement action, you can filter by those tags.</span></span>

### <a name="choose-an-improvement-action-status"></a><span data-ttu-id="36c23-144">Elegir un estado de acción de mejora</span><span class="sxs-lookup"><span data-stu-id="36c23-144">Choose an improvement action status</span></span>

<span data-ttu-id="36c23-145">Elija los estados y las notas de registro específicas de la acción de mejora.</span><span class="sxs-lookup"><span data-stu-id="36c23-145">Choose any statuses and record notes specific to the improvement action.</span></span>

- <span data-ttu-id="36c23-146">**To address:** you recognize that the improvement action is necessary and plan to address it at some point in the future.</span><span class="sxs-lookup"><span data-stu-id="36c23-146">**To address** - You recognize that the improvement action is necessary and plan to address it at some point in the future.</span></span> <span data-ttu-id="36c23-147">Este estado también se aplica a las acciones que se detectan como parcialmente, pero que no se completan completamente.</span><span class="sxs-lookup"><span data-stu-id="36c23-147">This state also applies to actions that are detected as partially, but not fully completed.</span></span>
- <span data-ttu-id="36c23-148">**Planeado:** hay planes concretos para completar la acción de mejora.</span><span class="sxs-lookup"><span data-stu-id="36c23-148">**Planned** - There are concrete plans in place to complete the improvement action.</span></span>
- <span data-ttu-id="36c23-149">**Riesgo aceptado:** la seguridad siempre debe estar equilibrada con la facilidad de uso y no todas las recomendaciones funcionarán para su entorno.</span><span class="sxs-lookup"><span data-stu-id="36c23-149">**Risk accepted** - Security should always be balanced with usability, and not every recommendation will work for your environment.</span></span> <span data-ttu-id="36c23-150">Cuando ese es el caso, puede optar por aceptar el riesgo, o el riesgo restante, y no aplicar la acción de mejora.</span><span class="sxs-lookup"><span data-stu-id="36c23-150">When that is the case, you can choose to accept the risk, or the remaining risk, and not enact the improvement action.</span></span> <span data-ttu-id="36c23-151">No se le dará ningún punto, pero la acción ya no estará visible en la lista de acciones de mejora.</span><span class="sxs-lookup"><span data-stu-id="36c23-151">You won't be given any points, but the action will no longer be visible in the list of improvement actions.</span></span> <span data-ttu-id="36c23-152">Puede ver esta acción en el historial o deshacerla en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="36c23-152">You can view this action in history or undo it at any time.</span></span>
- <span data-ttu-id="36c23-153">**Resuelto a través de** terceros y **Resuelto** mediante mitigación alternativa: la acción de mejora ya ha sido abordada por una aplicación o software de terceros, o una herramienta interna.</span><span class="sxs-lookup"><span data-stu-id="36c23-153">**Resolved through third party** and **Resolved through alternate mitigation** - The improvement action has already been addressed by a third-party application or software, or an internal tool.</span></span> <span data-ttu-id="36c23-154">Obtendrás los puntos que vale la acción, por lo que tu puntuación refleja mejor tu posición de seguridad general.</span><span class="sxs-lookup"><span data-stu-id="36c23-154">You'll gain the points that the action is worth, so your score better reflects your overall security posture.</span></span> <span data-ttu-id="36c23-155">Si una herramienta interna o de terceros ya no cubre el control, puede elegir otro estado.</span><span class="sxs-lookup"><span data-stu-id="36c23-155">If a third party or internal tool no longer covers the control, you can choose another status.</span></span> <span data-ttu-id="36c23-156">Tenga en cuenta que Microsoft no tendrá visibilidad sobre la integridad de la implementación si la acción de mejora se marca como uno de estos estados.</span><span class="sxs-lookup"><span data-stu-id="36c23-156">Keep in mind, Microsoft will have no visibility into the completeness of implementation if the improvement action is marked as either of these statuses.</span></span>

#### <a name="threat--vulnerability-management-improvement-actions"></a><span data-ttu-id="36c23-157">Acciones de & administración de vulnerabilidades de amenazas</span><span class="sxs-lookup"><span data-stu-id="36c23-157">Threat & vulnerability management improvement actions</span></span>

<span data-ttu-id="36c23-158">Para las acciones de mejora en la categoría "Dispositivo", no puedes elegir estados.</span><span class="sxs-lookup"><span data-stu-id="36c23-158">For improvement actions in the "Device" category, you can't choose statuses.</span></span> <span data-ttu-id="36c23-159">En su lugar, se le dirigirá a la recomendación de Administración de amenazas y vulnerabilidades [de](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) seguridad asociada [en el Centro de seguridad de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/use) para tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="36c23-159">Instead, you'll be directed to the associated [threat and vulnerability management security recommendation](/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use) to take action.</span></span> <span data-ttu-id="36c23-160">La excepción que elija y la justificación que escriba será específica de ese portal.</span><span class="sxs-lookup"><span data-stu-id="36c23-160">The exception you choose and justification you write will be specific to that portal.</span></span> <span data-ttu-id="36c23-161">No estará presente en el portal de puntuación segura de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36c23-161">It won't be present in the Microsoft Secure Score portal.</span></span>

#### <a name="completed-improvement-actions"></a><span data-ttu-id="36c23-162">Acciones de mejora completadas</span><span class="sxs-lookup"><span data-stu-id="36c23-162">Completed improvement actions</span></span>

<span data-ttu-id="36c23-163">Las acciones de mejora tienen un estado "completado" una vez que se han logrado todos los puntos posibles para la acción de mejora.</span><span class="sxs-lookup"><span data-stu-id="36c23-163">Improvement actions have a "completed" status once all possible points for the improvement action have been achieved.</span></span> <span data-ttu-id="36c23-164">Las acciones de mejora completadas se confirman a través de los datos de Microsoft y no se puede cambiar el estado.</span><span class="sxs-lookup"><span data-stu-id="36c23-164">Completed improvement actions are confirmed though Microsoft data, and you can't change the status.</span></span>

### <a name="assess-information-and-review-user-impact"></a><span data-ttu-id="36c23-165">Evaluar la información y revisar el impacto del usuario</span><span class="sxs-lookup"><span data-stu-id="36c23-165">Assess information and review user impact</span></span>

<span data-ttu-id="36c23-166">La sección denominada **De un vistazo** te mostrará la categoría, los ataques contra los que puede proteger y el producto.</span><span class="sxs-lookup"><span data-stu-id="36c23-166">The section called **At a glance** will tell you the category, attacks it can protect against, and the product.</span></span>

<span data-ttu-id="36c23-167">**El impacto** del usuario es lo que experimentarán los  usuarios si se aprueba la acción de mejora y los usuarios afectados son las personas que se verán afectadas.</span><span class="sxs-lookup"><span data-stu-id="36c23-167">**User impact** is what the users will experience if the improvement action is enacted, and **Users affected** are the people who will be impacted.</span></span>

### <a name="implement-the-improvement-action"></a><span data-ttu-id="36c23-168">Implementar la acción de mejora</span><span class="sxs-lookup"><span data-stu-id="36c23-168">Implement the improvement action</span></span>

<span data-ttu-id="36c23-169">En **la sección** Implementación se muestran los requisitos previos, los pasos siguientes paso a paso para completar la acción de mejora, el estado actual de implementación de la acción de mejora y cualquier vínculo más información.</span><span class="sxs-lookup"><span data-stu-id="36c23-169">The **Implementation** section shows any prerequisites, step-by-step next steps to complete the improvement action, the current implementation status of the improvement action, and any learn more links.</span></span>

<span data-ttu-id="36c23-170">Entre los requisitos previos se incluyen las licencias necesarias o las acciones que se deben completar antes de abordar la acción de mejora.</span><span class="sxs-lookup"><span data-stu-id="36c23-170">Prerequisites include any licenses that are needed or actions to be completed before the improvement action is addressed.</span></span> <span data-ttu-id="36c23-171">Asegúrese de que tiene suficientes puestos en la licencia para completar la acción de mejora y que dichas licencias se aplican a los usuarios necesarios.</span><span class="sxs-lookup"><span data-stu-id="36c23-171">Make sure you have enough seats in your license to complete the improvement action and that those licenses are applied to the necessary users.</span></span>  

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="36c23-172">Queremos escuchar sus comentarios</span><span class="sxs-lookup"><span data-stu-id="36c23-172">We want to hear from you</span></span>

<span data-ttu-id="36c23-173">Si tiene algún problema, háganoslo saber publicando en la comunidad [seguridad, privacidad & cumplimiento.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy)</span><span class="sxs-lookup"><span data-stu-id="36c23-173">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="36c23-174">Estamos supervisando la comunidad y proporcionaremos ayuda.</span><span class="sxs-lookup"><span data-stu-id="36c23-174">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="36c23-175">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="36c23-175">Related resources</span></span>

- [<span data-ttu-id="36c23-176">Introducción a la puntuación segura de Microsoft</span><span class="sxs-lookup"><span data-stu-id="36c23-176">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="36c23-177">Realizar un seguimiento del historial de puntuación segura de Microsoft y cumplir objetivos</span><span class="sxs-lookup"><span data-stu-id="36c23-177">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="36c23-178">Próximas novedades</span><span class="sxs-lookup"><span data-stu-id="36c23-178">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
- [<span data-ttu-id="36c23-179">Novedades</span><span class="sxs-lookup"><span data-stu-id="36c23-179">What's new</span></span>](microsoft-secure-score-whats-new.md)