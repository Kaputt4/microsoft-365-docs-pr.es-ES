---
title: Crear el entorno Microsoft 365 Defender evaluación
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
ms.openlocfilehash: 6e89591b57be2bf79664547715906074b92b54649e1858bde9ffe06cb2be9335
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53867624"
---
# <a name="create-the-microsoft-365-defender-evaluation-environment"></a>Crear el entorno Microsoft 365 Defender evaluación

Hay dos maneras comunes de realizar este siguiente paso en la evaluación. Este documento supone que ya tiene un inquilino M365 de producción y activará las licencias de prueba de E5 para evaluar M365 Defender en *el entorno actual.* Una evaluación local le permitirá mantener los métodos de seguridad con la compra de licencias después del período de evaluación.

El segundo es configurar [el entorno de Microsoft 365 Defender de prueba](setup-m365deval.md) para la evaluación. Puede que no tenga muchas señales reales de la empresa, por lo que tenga en cuenta esa advertencia.

## <a name="to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a>Para activar las licencias de prueba de E5 para evaluar Microsoft 365 Defender 
1. Inicie sesión en el portal de administración de inquilinos M365 existente.
2. Seleccione *Servicios de compra* en el menú de navegación.
3. Desplácese hacia abajo hasta *la Office 365* y seleccione el botón "Detalles" en Office 365 E5 licencia.

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="La Office 365 tiene un botón Detalles para hacer clic.":::

4. Seleccione *Iniciar vínculo de prueba* gratuita.

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Haga clic en &quot;Iniciar prueba gratuita&quot; (hay una tarifa de 35 $).":::

5. Confirme la solicitud y haga clic *en El botón Probar* ahora.

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Hay un botón &quot;Probar ahora&quot; en el panel &quot;Desproteja, confirma tu pedido&quot; (para una Office 365 E5 de prueba de un mes para 25 usuarios).":::

## <a name="next-steps"></a>Siguientes pasos
[Habilitar Microsoft 365 identidad](eval-defender-identity-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)