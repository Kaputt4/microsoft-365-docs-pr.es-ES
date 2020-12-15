---
title: Obtenga información a través de la formación de simulación de ataques
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Los administradores pueden obtener información sobre cómo afecta la simulación de ataques en el centro de seguridad de Microsoft 365 y pueden obtener información de los resultados de la simulación y la formación.
ms.openlocfilehash: 6fc109469f8a9a3cf6aa87e9b8f9e3a024fed6e3
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667608"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="d289d-103">Obtenga información a través de la formación de simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="d289d-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="d289d-104">En el curso de la simulación de ataques, Microsoft le proporciona información sobre la base de los resultados de las simulaciones y los entrenamientos que los empleados pasaron.</span><span class="sxs-lookup"><span data-stu-id="d289d-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="d289d-105">Esta información le ayudará a mantenerse informado sobre el progreso de la preparación contra amenazas de sus empleados, así como a recomendar pasos a seguir para preparar mejor a sus empleados y su entorno para los ataques.</span><span class="sxs-lookup"><span data-stu-id="d289d-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d289d-106">Estamos trabajando continuamente en la ampliación de la información que tiene a su disposición.</span><span class="sxs-lookup"><span data-stu-id="d289d-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="d289d-107">El impacto del comportamiento y las acciones recomendadas están actualmente disponibles.</span><span class="sxs-lookup"><span data-stu-id="d289d-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="d289d-108">Para empezar, vaya a [formación para la simulación de ataques en el centro de seguridad de Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="d289d-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="d289d-109">Impacto en el comportamiento de la tasa de exposición</span><span class="sxs-lookup"><span data-stu-id="d289d-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="d289d-110">En la ficha **información general** de formación sobre la simulación de ataques, observará el **impacto del comportamiento en** la tarjeta de tasa de riesgos.</span><span class="sxs-lookup"><span data-stu-id="d289d-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="d289d-111">Esta tarjeta muestra cómo los empleados se ocupan de las simulaciones que ejecutó en contraste con la **tasa de compromiso pronosticada**.</span><span class="sxs-lookup"><span data-stu-id="d289d-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="d289d-112">Puede usar estos conocimientos para realizar un seguimiento del progreso de la disponibilidad de las amenazas de los empleados mediante la ejecución de varias simulaciones en los mismos grupos de empleados.</span><span class="sxs-lookup"><span data-stu-id="d289d-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="d289d-113">En el gráfico, puede ver:</span><span class="sxs-lookup"><span data-stu-id="d289d-113">In the graph you can see:</span></span>

- <span data-ttu-id="d289d-114">**Tasa de compromiso pronosticada** que refleja la tasa de compromiso media de las simulaciones que usan el mismo tipo de carga en otros inquilinos de Microsoft 365 que usan la simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="d289d-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="d289d-115">**Tasa de compromiso real** refleja el porcentaje de empleados que se descendión para la simulación.</span><span class="sxs-lookup"><span data-stu-id="d289d-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="d289d-116">Además, `<number> less susceptible to phishing` refleja la diferencia entre el número real de empleados que corre el ataque y la tasa de compromiso pronosticada.</span><span class="sxs-lookup"><span data-stu-id="d289d-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="d289d-117">Es menos probable que este número de empleados se vea comprometido por ataques similares en el futuro, a la vez que `<percent%> better than predicted rate` indica el modo en que los empleados en general se comparan con la tasa de compromiso pronosticada.</span><span class="sxs-lookup"><span data-stu-id="d289d-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d289d-118">![Tarjeta de impacto del comportamiento en información general de formación sobre simulación de ataques](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="d289d-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="d289d-119">Para ver un informe más detallado, haga clic en **Ver simulaciones y entrenar el informe de eficacia**.</span><span class="sxs-lookup"><span data-stu-id="d289d-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="d289d-120">Este informe proporciona la misma información con contexto adicional de la propia simulación (por ejemplo, técnica de simulación y total de usuarios de destino).</span><span class="sxs-lookup"><span data-stu-id="d289d-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="d289d-121">Acciones recomendadas</span><span class="sxs-lookup"><span data-stu-id="d289d-121">Recommended actions</span></span>

<span data-ttu-id="d289d-122">En la [pestaña **simulaciones**](https://security.microsoft.com/attacksimulator?viewid=simulations), al seleccionar una simulación, irá a los detalles de la simulación, donde encontrará la sección **acciones recomendadas** .</span><span class="sxs-lookup"><span data-stu-id="d289d-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="d289d-123">En la sección acciones recomendadas se detallan las recomendaciones disponibles en [calificación segura de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="d289d-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="d289d-124">Estas recomendaciones se basan en la carga que se usa en la simulación y le ayudarán a proteger a sus empleados y su entorno.</span><span class="sxs-lookup"><span data-stu-id="d289d-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="d289d-125">Al hacer clic en cada acción de mejora irá a sus detalles.</span><span class="sxs-lookup"><span data-stu-id="d289d-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d289d-126">![Sección acciones de recomendación en el aprendizaje de simulación de ataques](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="d289d-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="d289d-127">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="d289d-127">Related Links</span></span>

<span data-ttu-id="d289d-128">**Simulador de ataque** [cree una simulación de ataque de suplantación de identidad](attack-simulation-training.md) y [cree una carga para entrenar a sus usuarios](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="d289d-128">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
