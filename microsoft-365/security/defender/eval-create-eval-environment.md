---
title: Crear el entorno Microsoft 365 Defender evaluación para mayor seguridad cibernética y XDR
description: Obtenga información sobre lo que se incluye en el Microsoft 365 Defender XDR que evaluará y cree su entorno piloto o laboratorio de prueba Microsoft 365 Defender activando licencias de prueba. Inicia tu viaje de seguridad cibernética de XDR aquí y aprende a llevar esa prueba a la producción.
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 98d2ee2394e4384fbf8d7b2b3832d11a847b8521
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "63755143"
---
# <a name="step-1-create-the-microsoft-365-defender-evaluation-environment-for-greater-cyber-security"></a>Paso 1. Crear el entorno Microsoft 365 Defender evaluación para una mayor seguridad cibernética

LPuedes aprender y también crear esta Microsoft Defender XDR en los pasos que se distribuyen a través del resto de esta serie:

- [Cómo crear el entorno](eval-create-eval-environment.md)
- Configurar o aprender sobre cada tecnología de este XDR de Microsoft
    - [Microsoft Defender for Identity](eval-defender-identity-overview.md)
    - [Microsoft Defender para Office](eval-defender-office-365-overview.md)
    - [Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)
    - [Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)
- [Cómo investigar y responder con este XDR](eval-defender-investigate-respond.md)
- [Promover el entorno de prueba a la producción](eval-defender-promote-to-production.md)
- [Volver a la información general](eval-overview.md)

Los pasos de esta serie se ejecutan de un extremo a otro, desde el aprendizaje de los conceptos detrás de la XDR de Microsoft 365 Defender hasta la creación y la producción del entorno de evaluación.

Hay dos maneras comunes de realizar este siguiente paso en la evaluación. Esta serie supone que ya tiene un inquilino de Microsoft 365 producción y activará las licencias de prueba de E5 para evaluar Microsoft 365 Defender en *el entorno actual*. Una evaluación local le permitirá mantener los métodos de seguridad con la compra de licencias después del período de evaluación.

El segundo es [configurar el entorno de Microsoft 365 Defender de prueba](setup-m365deval.md) para la evaluación. Tenga en cuenta que puede que no tenga muchas señales reales de la empresa mientras está en pruebas.

## <a name="you-will-need-to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a>Deberá activar las licencias de prueba de E5 para evaluar Microsoft 365 Defender

1. Inicie sesión en el portal de administración Microsoft 365 inquilino existente.
2. Seleccione **Servicios de compra** en el menú de navegación.
3. Desplácese hacia abajo hasta la Office 365 y seleccione el botón **Detalles** en Office 365 E5 licencia.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="El botón Detalles del portal de Microsoft 365 Defender web" lightbox="../../media/mdo-eval/2_mdo-eval-license-details.png":::

4. Seleccione **Iniciar vínculo de prueba** gratuita.

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="El botón Iniciar prueba gratuita en el portal Microsoft 365 Defender prueba" lightbox="../../media/mdo-eval/3-m365-purchase-button.png":::

5. Confirme la solicitud y haga clic **en El botón Probar** ahora.

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="El botón Probar ahora en el portal de Microsoft 365 Defender web" lightbox="../../media/mdo-eval/4_mdo-trial-order.png":::

## <a name="go-to-the-next-step"></a>Vaya al paso siguiente

[Obtenga información sobre cómo habilitar Microsoft 365 para Identity](eval-defender-identity-overview.md)

O bien, vuelva a la información general sobre [evaluación y prueba Microsoft 365 Defender](eval-overview.md)