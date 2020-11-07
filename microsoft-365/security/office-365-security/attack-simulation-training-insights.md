---
title: Obtener información mediante el entrenamiento de la simulación de ataques
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
description: Obtenga información sobre cómo el curso de simulación de ataques de los empleados del efecto centro de seguridad de Microsoft 365 y obtenga información de los resultados de la simulación y el entrenamiento.
ms.openlocfilehash: 180ddc773b5a299692e40ddc558d3b3a89f4093b
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944533"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="91b48-103">Obtener información mediante el entrenamiento de la simulación de ataques</span><span class="sxs-lookup"><span data-stu-id="91b48-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="91b48-104">En el curso de la simulación de ataques, Microsoft le proporciona información sobre la base de los resultados de las simulaciones y los empleados de formación que han pasado.</span><span class="sxs-lookup"><span data-stu-id="91b48-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and training employees went through.</span></span> <span data-ttu-id="91b48-105">Esta información le ayudará en el progreso de los empleados en cuanto a la disponibilidad de amenazas, así como recomendar pasos a seguir para preparar mejor a sus empleados y su entorno para los ataques.</span><span class="sxs-lookup"><span data-stu-id="91b48-105">These insights will help inform you on progress your employees are doing on threat readiness, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="91b48-106">Estamos trabajando continuamente en la información de expansión que tiene a su disposición, con el impacto del comportamiento y las acciones recomendadas actualmente disponibles.</span><span class="sxs-lookup"><span data-stu-id="91b48-106">We are continuously working on expanding insights available to you, with behavior impact and recommended actions currently available.</span></span>
<span data-ttu-id="91b48-107">Para empezar, vaya a [formación para la simulación de ataques en el centro de seguridad de Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="91b48-107">To start, head over to [Attack simulation training on the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="91b48-108">Impacto en el comportamiento de la tasa de exposición</span><span class="sxs-lookup"><span data-stu-id="91b48-108">Behavior impact on compromise rate</span></span>

<span data-ttu-id="91b48-109">En la ficha **información general** sobre la simulación de ataques, encontrará el **impacto del comportamiento en la tarjeta de tasa de riesgos** .</span><span class="sxs-lookup"><span data-stu-id="91b48-109">On the Attack simulation training **Overview** tab, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="91b48-110">Esta tarjeta muestra cómo los empleados se ocupan de la simulación que ejecutó en contraste con la **tasa de compromiso pronosticada**.</span><span class="sxs-lookup"><span data-stu-id="91b48-110">This card shows how employees dealt with simulation you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="91b48-111">Puede usar estos conocimientos para realizar un seguimiento del progreso de la disponibilidad de las amenazas de los empleados mediante la ejecución de varias simulaciones en los mismos grupos de empleados.</span><span class="sxs-lookup"><span data-stu-id="91b48-111">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="91b48-112">En el gráfico, puede ver:</span><span class="sxs-lookup"><span data-stu-id="91b48-112">In the graph you can see:</span></span>

- <span data-ttu-id="91b48-113">**Tasa de compromiso pronosticada** que refleja el índice de compromiso medio de las simulaciones usando el mismo tipo de carga entre los inquilinos mediante la simulación de ataques.</span><span class="sxs-lookup"><span data-stu-id="91b48-113">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across tenants using Attack simulation training.</span></span>
- <span data-ttu-id="91b48-114">**Tasa de compromiso real** refleja el porcentaje de empleados que se descendión para la simulación.</span><span class="sxs-lookup"><span data-stu-id="91b48-114">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="91b48-115">Además, `<number> less susceptible to phishing` refleja la diferencia entre el número real de empleados que corre el ataque y la tasa de compromiso pronosticada.</span><span class="sxs-lookup"><span data-stu-id="91b48-115">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="91b48-116">Es menos probable que este número de empleados se vea comprometido por ataques similares en el futuro, a la vez que `<percent%> better than predicted rate` indica el modo en que los empleados en general se comparan con la tasa de compromiso pronosticada.</span><span class="sxs-lookup"><span data-stu-id="91b48-116">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

![Tarjeta de impacto del comportamiento en información general de formación sobre simulación de ataques](../../media/attack-sim-preview-behavior-impact-card.png)

<span data-ttu-id="91b48-118">Para ver un informe más detallado, haga clic en **Ver simulaciones y entrenar la eficacia del informe** , que proporciona la misma información con contexto adicional de la propia simulación, como la técnica de simulación y el total de usuarios a los que se destina.</span><span class="sxs-lookup"><span data-stu-id="91b48-118">To see a more detailed report, click on **View simulations and training efficacy report** which provides the same information with additional context from the simulation itself, like simulation technique and total users targeted.</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="91b48-119">Acciones recomendadas</span><span class="sxs-lookup"><span data-stu-id="91b48-119">Recommended actions</span></span>

<span data-ttu-id="91b48-120">En la [pestaña **simulaciones**](https://security.microsoft.com/attacksimulator?viewid=simulations) , la selección de una de las simulaciones le llevará a los detalles de la simulación.</span><span class="sxs-lookup"><span data-stu-id="91b48-120">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations) selecting any of the simulation will take you to simulation details.</span></span> <span data-ttu-id="91b48-121">A continuación, encontrará la sección **acciones recomendadas** .</span><span class="sxs-lookup"><span data-stu-id="91b48-121">Here you will find the **Recommended actions** section.</span></span>

<span data-ttu-id="91b48-122">En la sección acciones recomendadas se detallan las recomendaciones disponibles en [calificación segura de Microsoft](../mtp/microsoft-secure-score.md).</span><span class="sxs-lookup"><span data-stu-id="91b48-122">The recommended actions section details recommendations as available in [Microsoft Secure Score](../mtp/microsoft-secure-score.md).</span></span> <span data-ttu-id="91b48-123">Estas recomendaciones se basan en la carga que se usa en la simulación y le ayudarán a proteger a sus empleados y su entorno.</span><span class="sxs-lookup"><span data-stu-id="91b48-123">These recommendations are based on the payload used in the simulation and will help you protect your employees and your environment.</span></span> <span data-ttu-id="91b48-124">Al hacer clic en cada acción de mejora irá a sus detalles.</span><span class="sxs-lookup"><span data-stu-id="91b48-124">Clicking on each improvement action will take you to its details.</span></span>

![Sección acciones de recomendación en el aprendizaje de simulación de ataques](../../media/attack-sim-preview-recommended-actions.png)