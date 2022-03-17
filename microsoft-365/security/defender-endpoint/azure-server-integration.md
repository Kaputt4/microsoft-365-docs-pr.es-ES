---
title: Integración con Microsoft Defender for Cloud
description: Obtenga información sobre la integración de Microsoft Defender para endpoints con Microsoft Defender para la nube
keywords: integración, servidor, azure, 2012r2, 2016, 2019, incorporación de servidores, administración de dispositivos, configuración de Microsoft Defender para servidores de extremo, incorporación de Servidores de Microsoft Defender para endpoints, incorporación de Microsoft Defender para servidores de extremo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2ed9d25336cd7e8162849aa5d1d1a3e3382063fc
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63526682"
---
# <a name="integration-with-microsoft-defender-for-cloud"></a>Integración con Microsoft Defender for Cloud

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender for Cloud

Microsoft Defender para endpoint se puede integrar con Microsoft Defender para la nube para proporcionar una solución completa Windows protección del servidor. Con esta integración, Microsoft Defender para la nube puede usar la potencia de Defender para Endpoint para proporcionar una mejor detección de amenazas para Windows Servidores.

En esta integración se incluyen las siguientes funcionalidades:

- Incorporación automatizada: el sensor Defender para endpoints se habilita automáticamente en servidores Windows que están incorporados a Microsoft Defender para la nube. Para obtener más información sobre la incorporación de Microsoft Defender para la nube, consulte [Use the integrated Microsoft Defender for Endpoint license](/azure/security-center/security-center-wdatp).

    > [!NOTE]
    > La integración entre Microsoft Defender para servidores y Microsoft Defender para endpoint se ha expandido para admitir [Windows Server 2019 y Windows Virtual Desktop (WVD)](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).

- Windows servidores supervisados por Microsoft Defender para la nube también estarán disponibles en Defender para endpoint: Microsoft Defender para la nube se conecta perfectamente al inquilino de Defender para endpoint, lo que proporciona una vista única entre clientes y servidores.  Además, las alertas de Defender para puntos de conexión estarán disponibles en la consola de Microsoft Defender para la nube.
- Investigación del servidor: los clientes de Microsoft Defender para la nube pueden acceder al portal de Microsoft 365 Defender para realizar una investigación detallada para descubrir el ámbito de una posible infracción.

> [!IMPORTANT]
> - Cuando usa Microsoft Defender para la nube para supervisar los servidores, se crea automáticamente un inquilino de Defender for Endpoint (en Estados Unidos para usuarios estadounidenses, en la UE para usuarios europeos y británicos).<br>
Los datos recopilados por Defender para endpoint se almacenan en la ubicación geográfica del inquilino tal como se identifica durante el aprovisionamiento.
> - Si usa Defender para endpoint antes de usar Microsoft Defender para la nube, los datos se almacenarán en la ubicación que especificó al crear el inquilino, incluso si se integra con Microsoft Defender para la nube más adelante.
> - Una vez configurado, no se puede cambiar la ubicación donde se almacenan los datos. Si necesita mover los datos a otra ubicación, póngase en contacto con el soporte técnico de Microsoft para restablecer el espacio empresarial. <br>
La supervisión de extremos de servidor que utiliza esta integración se ha deshabilitado para Office 365 GCC clientes.



## <a name="related-topics"></a>Temas relacionados
- [Incorporar versiones anteriores de Windows](onboard-downlevel.md)
- [Onboard Windows Server 2012 R2, 2016, SAC version 1803, and 2019](configure-server-endpoints.md)
