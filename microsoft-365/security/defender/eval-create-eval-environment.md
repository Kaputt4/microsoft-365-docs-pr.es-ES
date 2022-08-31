---
title: Creación del entorno de evaluación de Microsoft 365 Defender para una mayor ciberseguridad y XDR
description: Obtenga información sobre lo que se incluye en el Microsoft 365 Defender XDR que evaluará y obtenga información sobre el laboratorio de prueba o el entorno piloto de Microsoft 365 Defender activando licencias de prueba. Inicie el recorrido de ciberseguridad de XDR aquí y aprenda a llevar esa prueba a producción.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: how-to
ms.openlocfilehash: 31254fac4b56da65469fac56320440bfd0e487c3
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67470561"
---
# <a name="step-1-create-the-microsoft-365-defender-evaluation-environment-for-greater-cyber-security"></a>Paso 1. Creación del entorno de evaluación de Microsoft 365 Defender para una mayor ciberseguridad

Puede obtener información sobre esta solución Microsoft Defender XDR y compilarla en los pasos que se distribuyen en el resto de esta serie:

- [Creación del entorno](eval-create-eval-environment.md)
- Configuración o información sobre cada tecnología de este XDR de Microsoft
    - [Microsoft Defender for Identity](eval-defender-identity-overview.md)
    - [Microsoft Defender para Office](eval-defender-office-365-overview.md)
    - [Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)
    - [Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)
- [Cómo investigar y responder con este XDR](eval-defender-investigate-respond.md)
- [Promover el entorno de prueba a producción](eval-defender-promote-to-production.md)
- [Volver a la información general](eval-overview.md)

Los pasos de esta serie se ejecutan de un extremo a otro, desde el aprendizaje de los conceptos detrás de la Microsoft 365 Defender XDR hasta la compilación y la puesta en marcha del entorno de evaluación en producción.

Hay dos maneras comunes de realizar este paso siguiente en la evaluación. En esta serie se supone que ya tiene un inquilino de Producción de Microsoft 365 y activará licencias de prueba de E5 para evaluar Microsoft 365 Defender en *el entorno actual*. Una evaluación local le permitirá mantener los métodos de seguridad con la compra de licencias después del período de evaluación.

La segunda consiste en [configurar el entorno de laboratorio de prueba de Microsoft 365 Defender](setup-m365deval.md) con fines de evaluación. Tenga en cuenta que es posible que no tenga muchas señales reales de la empresa durante las pruebas.

## <a name="you-will-need-to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a>Tendrá que activar licencias de prueba de E5 para evaluar Microsoft 365 Defender

1. Inicie sesión en el portal de administración de inquilinos de Microsoft 365 existente.
2. Seleccione **Comprar servicios** en el menú de navegación.
3. Desplácese hacia abajo hasta la sección Office 365 y seleccione **el botón Detalles** en Office 365 E5 licencia.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Botón Detalles del portal de Microsoft 365 Defender" lightbox="../../media/mdo-eval/2_mdo-eval-license-details.png":::

4. Seleccione **Iniciar vínculo de evaluación gratuita** .

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Botón Iniciar evaluación gratuita en el portal de Microsoft 365 Defender" lightbox="../../media/mdo-eval/3-m365-purchase-button.png":::

5. Confirme la solicitud y haga clic en **el botón Probar ahora** .

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Botón Probar ahora en el portal de Microsoft 365 Defender" lightbox="../../media/mdo-eval/4_mdo-trial-order.png":::

## <a name="go-to-the-next-step"></a>Vaya al paso siguiente.

[Aprenda a habilitar Microsoft 365 for Identity](eval-defender-identity-overview.md)

O bien, vuelva a información general para [evaluar y probar Microsoft 365 Defender](eval-overview.md)
