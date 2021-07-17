---
title: Cree el entorno Microsoft 365 Defender evaluación. Active o habilite licencias de prueba y continúe con Microsoft Defender for Identity (MDI).
description: Configure el entorno Microsoft 365 Defender prueba o entorno piloto mediante la activación de licencias de prueba. A continuación, configure Microsoft Defender for Identity (MDI) y todas las demás evaluaciones M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 04f7a746788ebcf67525020515cdc7bb20c41bb6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458687"
---
# <a name="create-the-microsoft-365-defender-evaluation-environment"></a><span data-ttu-id="33092-105">Crear el entorno Microsoft 365 Defender evaluación</span><span class="sxs-lookup"><span data-stu-id="33092-105">Create the Microsoft 365 Defender Evaluation Environment</span></span>

<span data-ttu-id="33092-106">Hay dos maneras comunes de realizar este siguiente paso en la evaluación.</span><span class="sxs-lookup"><span data-stu-id="33092-106">There are two common ways to do this next step in evaluation.</span></span> <span data-ttu-id="33092-107">Este documento supone que ya tiene un inquilino M365 de producción y activará las licencias de prueba de E5 para evaluar M365 Defender en *el entorno actual.*</span><span class="sxs-lookup"><span data-stu-id="33092-107">This document assumes you already have a production M365 tenant, and will activate E5 trial licenses to evaluate M365 Defender in *the current environment*.</span></span> <span data-ttu-id="33092-108">Una evaluación local le permitirá mantener los métodos de seguridad con la compra de licencias después del período de evaluación.</span><span class="sxs-lookup"><span data-stu-id="33092-108">An in-place evaluation will let you keep any security methods with the purchase of licenses after the evaluation period.</span></span>

<span data-ttu-id="33092-109">El segundo es configurar [el entorno de Microsoft 365 Defender de prueba](setup-m365deval.md) para la evaluación.</span><span class="sxs-lookup"><span data-stu-id="33092-109">The second is to  [Set up your Microsoft 365 Defender trial lab environment](setup-m365deval.md) for the purpose of evaluation.</span></span> <span data-ttu-id="33092-110">Puede que no tenga muchas señales reales de la empresa, por lo que tenga en cuenta esa advertencia.</span><span class="sxs-lookup"><span data-stu-id="33092-110">It may not have many real signals from the business, so be aware of that caveat.</span></span>

## <a name="to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a><span data-ttu-id="33092-111">Para activar las licencias de prueba de E5 para evaluar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33092-111">To activate E5 trial licenses to evaluate Microsoft 365 Defender</span></span> 
1. <span data-ttu-id="33092-112">Inicie sesión en el portal de administración de inquilinos M365 existente.</span><span class="sxs-lookup"><span data-stu-id="33092-112">Log on to your existing M365 tenant administration portal.</span></span>
2. <span data-ttu-id="33092-113">Seleccione *Servicios de compra* en el menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="33092-113">Select *Purchase Services* from the navigation menu.</span></span>
3. <span data-ttu-id="33092-114">Desplácese hacia abajo hasta *la Office 365* y seleccione el botón "Detalles" en Office 365 E5 licencia.</span><span class="sxs-lookup"><span data-stu-id="33092-114">Scroll down to the *Office 365* section and select "Details" button under Office 365 E5 license.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="La Office 365 tiene un botón Detalles para hacer clic.":::

4. <span data-ttu-id="33092-116">Seleccione *Iniciar vínculo de prueba* gratuita.</span><span class="sxs-lookup"><span data-stu-id="33092-116">Select *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Haga clic en &quot;Iniciar prueba gratuita&quot; (hay una tarifa de 35 $).":::

5. <span data-ttu-id="33092-118">Confirme la solicitud y haga clic *en El botón Probar* ahora.</span><span class="sxs-lookup"><span data-stu-id="33092-118">Confirm your request and click *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Hay un botón &quot;Probar ahora&quot; en el panel &quot;Desproteja, confirma tu pedido&quot; (para una Office 365 E5 de prueba de un mes para 25 usuarios).":::

## <a name="next-steps"></a><span data-ttu-id="33092-120">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="33092-120">Next steps</span></span>
[<span data-ttu-id="33092-121">Habilitar Microsoft 365 identidad</span><span class="sxs-lookup"><span data-stu-id="33092-121">Enable Microsoft 365 for Identity</span></span>](eval-defender-identity-overview.md)

<span data-ttu-id="33092-122">Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="33092-122">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>