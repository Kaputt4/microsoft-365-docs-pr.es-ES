---
title: Integración con Azure Defender
description: Obtenga información sobre la integración de Microsoft Defender para endpoints con Azure Defender
keywords: integración, servidor, azure, 2012r2, 2016, 2019, incorporación de servidores, administración de dispositivos, configuración de Microsoft Defender para servidores de extremo, incorporación de Servidores de Microsoft Defender para endpoints, incorporación de Microsoft Defender para servidores de extremo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a702585a558cf6754cbd2eaf23d5061879120ac8
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240626"
---
# <a name="integration-with-azure-defender"></a>Integración con Azure Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft Defender para punto de conexión
- Azure Defender

Microsoft Defender para endpoint se puede integrar con Azure Defender para proporcionar una solución completa Windows protección de servidores. Con esta integración, Azure Defender puede usar la potencia de Defender para endpoint para proporcionar una mejor detección de amenazas para Windows servidores.

En esta integración se incluyen las siguientes funcionalidades:

- Incorporación automatizada: el sensor Defender for Endpoint se habilita automáticamente en los servidores Windows que están incorporados a Azure Defender. Para obtener más información sobre la incorporación de Azure Defender, consulte [Use the integrated Microsoft Defender for Endpoint license](/azure/security-center/security-center-wdatp).

    > [!NOTE]
    > La integración entre Azure Defender para servidores y Microsoft Defender para endpoint se ha expandido para admitir [Windows Server 2019 y Windows Virtual Desktop (WVD).](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)

- Windows servidores supervisados por Azure Defender también estarán disponibles en Defender para endpoint: Azure Defender se conecta perfectamente al inquilino de Defender para endpoint, lo que proporciona una vista única entre clientes y servidores.  Además, las alertas de Defender para extremo estarán disponibles en la consola de Azure Defender.
- Investigación del servidor: los clientes de Azure Defender pueden acceder a Centro de seguridad de Microsoft Defender realizar una investigación detallada para descubrir el ámbito de una posible infracción.

> [!IMPORTANT]
> - Cuando usa Azure Defender para supervisar los servidores, se crea automáticamente un inquilino de Defender for Endpoint (en Estados Unidos para usuarios estadounidenses, en la UE para usuarios europeos y británicos).<br>
Los datos recopilados por Defender para endpoint se almacenan en la ubicación geográfica del inquilino tal como se identifica durante el aprovisionamiento.
> - Si usa Defender para endpoint antes de usar Azure Defender, los datos se almacenarán en la ubicación que especificó al crear el inquilino, incluso si se integra con Azure Defender más adelante.
> - Una vez configurado, no se puede cambiar la ubicación donde se almacenan los datos. Si necesita mover los datos a otra ubicación, póngase en contacto con el soporte técnico de Microsoft para restablecer el espacio empresarial. <br>
La supervisión de extremos de servidor que utiliza esta integración se ha deshabilitado para Office 365 GCC clientes.



## <a name="related-topics"></a>Temas relacionados
- [Incorporar versiones anteriores de Windows](onboard-downlevel.md)
- [Onboard Windows Server 2012 R2, 2016, SAC version 1803, and 2019](configure-server-endpoints.md)