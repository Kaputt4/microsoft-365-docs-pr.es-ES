---
title: Obtenga información a través de la formación de simulación de ataques
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Obtenga información sobre cómo la formación de simulación de ataques en el centro de seguridad 365 de Microsoft afecta a los empleados y información sobre los resultados de simulación y formación.
ms.openlocfilehash: 772815add47d2e0a61187f2d687ff047a4de9c31
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615185"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="d5c76-103">Obtenga información a través de la formación de simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="d5c76-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="d5c76-104">En el curso de la simulación de ataques, Microsoft le proporciona información sobre la base de los resultados de las simulaciones y los empleados de formación que han pasado.</span><span class="sxs-lookup"><span data-stu-id="d5c76-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and training employees went through.</span></span> <span data-ttu-id="d5c76-105">Esta información le ayudará en el progreso de los empleados en cuanto a la disponibilidad de amenazas, así como recomendar pasos a seguir para preparar mejor a sus empleados y su entorno para los ataques.</span><span class="sxs-lookup"><span data-stu-id="d5c76-105">These insights will help inform you on progress your employees are doing on threat readiness, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d5c76-106">Estamos trabajando continuamente en la información de expansión que tiene a su disposición, con el impacto del comportamiento y las acciones recomendadas actualmente disponibles.</span><span class="sxs-lookup"><span data-stu-id="d5c76-106">We are continuously working on expanding insights available to you, with behavior impact and recommended actions currently available.</span></span>
<span data-ttu-id="d5c76-107">Para empezar, vaya a [formación para la simulación de ataques en el centro de seguridad de Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="d5c76-107">To start, head over to [Attack simulation training on the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="d5c76-108">Impacto en el comportamiento de la tasa de exposición</span><span class="sxs-lookup"><span data-stu-id="d5c76-108">Behavior impact on compromise rate</span></span>

<span data-ttu-id="d5c76-109">En la ficha **información general** sobre la simulación de ataques, encontrará el **impacto del comportamiento en la tarjeta de tasa de riesgos** .</span><span class="sxs-lookup"><span data-stu-id="d5c76-109">On the Attack simulation training **Overview** tab, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="d5c76-110">Esta tarjeta muestra cómo los empleados se ocupan de la simulación que ejecutó en contraste con la **tasa de compromiso pronosticada**.</span><span class="sxs-lookup"><span data-stu-id="d5c76-110">This card shows how employees dealt with simulation you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="d5c76-111">Puede usar estos conocimientos para realizar un seguimiento del progreso de la disponibilidad de las amenazas de los empleados mediante la ejecución de varias simulaciones en los mismos grupos de empleados.</span><span class="sxs-lookup"><span data-stu-id="d5c76-111">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="d5c76-112">En el gráfico, puede ver:</span><span class="sxs-lookup"><span data-stu-id="d5c76-112">In the graph you can see:</span></span>

- <span data-ttu-id="d5c76-113">**Tasa de compromiso pronosticada** que refleja el índice de compromiso medio de las simulaciones usando el mismo tipo de carga entre los inquilinos mediante la simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="d5c76-113">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across tenants using Attack simulation training.</span></span>
- <span data-ttu-id="d5c76-114">**Tasa de compromiso real** refleja el porcentaje de empleados que se descendión para la simulación.</span><span class="sxs-lookup"><span data-stu-id="d5c76-114">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="d5c76-115">Además, `<number> less susceptible to phishing` refleja la diferencia entre el número real de empleados que corre el ataque y la tasa de compromiso pronosticada.</span><span class="sxs-lookup"><span data-stu-id="d5c76-115">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="d5c76-116">Es menos probable que este número de empleados se vea comprometido por ataques similares en el futuro, a la vez que `<percent%> better than predicted rate` indica el modo en que los empleados en general se comparan con la tasa de compromiso pronosticada.</span><span class="sxs-lookup"><span data-stu-id="d5c76-116">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d5c76-117">![Tarjeta de impacto del comportamiento en información general de formación sobre simulación de ataques](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="d5c76-117">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="d5c76-118">Para ver un informe más detallado, haga clic en **Ver simulaciones y entrenar la eficacia del informe** , que proporciona la misma información con contexto adicional de la propia simulación, como la técnica de simulación y el total de usuarios a los que se destina.</span><span class="sxs-lookup"><span data-stu-id="d5c76-118">To see a more detailed report, click on **View simulations and training efficacy report** which provides the same information with additional context from the simulation itself, like simulation technique and total users targeted.</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="d5c76-119">Acciones recomendadas</span><span class="sxs-lookup"><span data-stu-id="d5c76-119">Recommended actions</span></span>

<span data-ttu-id="d5c76-120">En la [pestaña **simulaciones**](https://security.microsoft.com/attacksimulator?viewid=simulations), al seleccionar cualquiera de las simulaciones, se mostrarán detalles de simulación.</span><span class="sxs-lookup"><span data-stu-id="d5c76-120">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting any of the simulations will take you to simulation details.</span></span> <span data-ttu-id="d5c76-121">A continuación, encontrará la sección **acciones recomendadas** .</span><span class="sxs-lookup"><span data-stu-id="d5c76-121">Here you will find the **Recommended actions** section.</span></span>

<span data-ttu-id="d5c76-122">En la sección acciones recomendadas se detallan las recomendaciones disponibles en [calificación segura de Microsoft](../mtp/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="d5c76-122">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="d5c76-123">Estas recomendaciones se basan en la carga que se usa en la simulación y le ayudarán a proteger a sus empleados y su entorno.</span><span class="sxs-lookup"><span data-stu-id="d5c76-123">These recommendations are based on the payload used in the simulation and will help you protect your employees and your environment.</span></span> <span data-ttu-id="d5c76-124">Al hacer clic en cada acción de mejora irá a sus detalles.</span><span class="sxs-lookup"><span data-stu-id="d5c76-124">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d5c76-125">![Sección acciones de recomendación en el aprendizaje de simulación de ataques](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="d5c76-125">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="d5c76-126">Vínculos relacionados</span><span class="sxs-lookup"><span data-stu-id="d5c76-126">Related Links</span></span>

<span data-ttu-id="d5c76-127">**Simulador de ataque** [cree una simulación de ataque de suplantación de identidad](attack-simulation-training.md) y [cree una carga para entrenar a sus usuarios](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="d5c76-127">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
