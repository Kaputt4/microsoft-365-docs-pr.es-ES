---
title: Integración con Microsoft Defender for Cloud
description: Más información sobre Microsoft Defender para punto de conexión integración con Microsoft Defender for Cloud
keywords: integration, server, azure, 2012r2, 2016, 2019, server onboarding, device management, configure Microsoft Defender para punto de conexión servers, onboard Microsoft Defender para punto de conexión servers, onboard servidores de Microsoft Defender para punto de conexión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.service: microsoft-365-security
ms.subservice: mde
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: 65a26cf05531ecea3c5c1f95e4013d283d677adf
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68647307"
---
# <a name="integration-with-microsoft-defender-for-cloud"></a>Integración con Microsoft Defender for Cloud

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender for Cloud

Microsoft Defender para punto de conexión se puede integrar con Microsoft Defender for Cloud para proporcionar una solución de protección completa de windows server. Con esta integración, Microsoft Defender for Cloud puede usar la eficacia de Defender para punto de conexión para proporcionar una detección de amenazas mejorada para servidores Windows.

En esta integración se incluyen las siguientes funcionalidades:

- Incorporación automatizada: el sensor de Defender para punto de conexión se habilita automáticamente en servidores Windows que se incorporan a Microsoft Defender para la nube. Para obtener más información sobre Microsoft Defender para la incorporación a la nube, consulte [Uso de la licencia de Microsoft Defender para punto de conexión integrada](/azure/security-center/security-center-wdatp).

    > [!NOTE]
    > La integración entre Microsoft Defender para servidores y Microsoft Defender para punto de conexión se ha ampliado para admitir [Windows Server 2019 y Windows Virtual Desktop (WVD).](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)

- Los servidores Windows supervisados por Microsoft Defender for Cloud también estarán disponibles en Defender para punto de conexión: Microsoft Defender for Cloud se conecta sin problemas al inquilino de Defender para punto de conexión, lo que proporciona una vista única entre clientes y servidores.  Además, las alertas de Defender para punto de conexión estarán disponibles en la consola de Microsoft Defender for Cloud.
- Investigación del servidor: los clientes de Microsoft Defender for Cloud pueden acceder al portal de Microsoft 365 Defender para realizar una investigación detallada con el fin de descubrir el ámbito de una posible infracción.

> [!IMPORTANT]
> - Cuando se usa Microsoft Defender for Cloud para supervisar servidores, se crea automáticamente un inquilino de Defender para punto de conexión (en EE. UU. para usuarios de EE. UU., en la UE para usuarios europeos y británicos).<br>
Los datos recopilados por Defender para punto de conexión se almacenan en la ubicación geográfica del inquilino tal como se identifica durante el aprovisionamiento.
> - Si usa Defender para punto de conexión antes de usar Microsoft Defender for Cloud, los datos se almacenarán en la ubicación que especificó al crear el inquilino, incluso si se integra con Microsoft Defender for Cloud más adelante.
> - Una vez configurado, no se puede cambiar la ubicación donde se almacenan los datos. Si necesita mover los datos a otra ubicación, debe ponerse en contacto con el soporte técnico de Microsoft para restablecer el inquilino. <br>
La supervisión de puntos de conexión de servidor que usan esta integración se ha deshabilitado para Office 365 clientes de GCC.



## <a name="related-topics"></a>Temas relacionados
- [Incorporar versiones anteriores de Windows](onboard-downlevel.md)
- [Incorporación de Windows Server 2012 R2, 2016, SAC versión 1803 y 2019](configure-server-endpoints.md)
