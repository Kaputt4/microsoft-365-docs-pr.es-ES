---
title: Incorporación de Cliente windows de Defender para punto de conexión
description: Incorporación del cliente de Windows.
keywords: onboarding, Microsoft Defender para punto de conexión onboarding, sccm, group policy, mdm, local script, detection test
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 60b7e78902dff29278e3fe960e016e38c10cf296
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822165"
---
# <a name="defender-for-endpoint-onboarding-windows-client"></a>Incorporación de Cliente windows de Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Prevención de perdida de datos en el punto de conexión (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Administración de riesgos internos](/microsoft-365/compliance/insider-risk-management)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https:%2F%2Faka.ms%2FMDEp2OpenTrial)

Tendrá que pasar por la sección de incorporación del portal de Defender para punto de conexión para incorporar cualquiera de los dispositivos admitidos. En función del dispositivo, se le guiará con los pasos adecuados y se le proporcionarán opciones de herramientas de administración e implementación adecuadas para el dispositivo.

Los dispositivos de su organización deben configurarse para que el servicio Defender para punto de conexión pueda obtener datos del sensor de ellos. Hay varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de su organización.

En general, identificará el cliente que va a incorporar y, a continuación, seguirá la herramienta correspondiente adecuada para el dispositivo o el entorno.

:::image type="content" source="images/onboarddevices.png" alt-text="Incorporación de dispositivos" lightbox="images/onboarddevices.png":::

## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows mediante Microsoft Intune](configure-endpoints-mdm.md)
- [Incorporar dispositivos Windows mediante directiva de grupo](configure-endpoints-gp.md)
- [Incorporar dispositivos Windows mediante un script local](configure-endpoints-script.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)