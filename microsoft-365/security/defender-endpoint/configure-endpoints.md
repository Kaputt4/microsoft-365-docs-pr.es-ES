---
title: Incorporación de herramientas y métodos para dispositivos Windows
description: Incorporación de dispositivos Windows para que puedan enviar datos del sensor al sensor de Microsoft Defender para punto de conexión
keywords: Incorporación de dispositivos Windows, directiva de grupo, administrador de configuración de puntos de conexión, administración de dispositivos móviles, script local, gp, sccm, mdm, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: fbc5a0981a6318d767252e968e45874d889aee85
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64949109"
---
# <a name="onboarding-tools-and-methods-for-windows-devices-in-defender-for-endpoint"></a>Incorporación de herramientas y métodos para dispositivos Windows en Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Prevención de perdida de datos en el punto de conexión (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Administración de riesgos internos](/microsoft-365/compliance/insider-risk-management)

> ¿Desea experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Los dispositivos de su organización deben configurarse para que el servicio Defender para punto de conexión pueda obtener datos del sensor de ellos. Hay varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de su organización.

En general, identificará el dispositivo Windows que va a incorporar y, a continuación, seguirá la herramienta correspondiente adecuada para el dispositivo o el entorno.

:::image type="content" source="images/onboarding-config-tools.png" alt-text="Herramientas y métodos de incorporación" lightbox="images/onboarding-config-tools.png":::

## <a name="endpoint-onboarding-tools"></a>Herramientas de incorporación de puntos de conexión

En función del punto de conexión de Windows que quiera incorporar, use la herramienta o el método correspondiente descritos en la tabla siguiente.

dispositivo Windows | Herramienta o método de incorporación
:---|:---
|<ul><li> Windows 10</li> <li>Windows Server 1803 y 2019 y 2022</li> <li>Windows Server 2012 R2 y 2016<sup>[[1](#fn1)]<sup></li></ul>  |   [Script local (hasta 10 dispositivos)](configure-endpoints-script.md)<br>   [Directiva de grupo](configure-endpoints-gp.md)<br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Microsoft Endpoint Manager/Mobile Administración de dispositivos (Intune)](configure-endpoints-mdm.md)<br>    [Scripts de VDI](configure-endpoints-vdi.md) <br><br> **NOTA**: Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.
|<ul><li> Windows Server 2008 R2 SP1 </li></ul>| [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br>[Incorporación de versiones anteriores de Windows](onboard-downlevel.md) o [Microsoft Defender for Cloud](/azure/security-center/security-center-wdatp) <br><br> **NOTA**: Microsoft Monitoring Agent ahora es agente de Azure Log Analytics. Para más información, consulte [Introducción al agente de Log Analytics](/azure/azure-monitor/platform/log-analytics-agent).  
|<ul><li> Windows 7 SP1 </li> <li>  Windows 7 SP1 Pro </li> <li>  Windows 8.1 Pro </li> <li> Windows 8,1 Enterprise</li></ul>  | [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br><br> **NOTA**: Microsoft Monitoring Agent ahora es agente de Azure Log Analytics. Para más información, consulte [Introducción al agente de Log Analytics](/azure/azure-monitor/platform/log-analytics-agent).

(<a id="fn1">1</a>) Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse mediante las instrucciones de [Incorporación de servidores Windows](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016).

>[!IMPORTANT]
>Para poder comprar Microsoft Defender para punto de conexión SKU de servidor, debe haber adquirido ya un mínimo combinado de cualquiera de los siguientes elementos, Windows E5/A5, Microsoft 365 E5/A5 o Seguridad de Microsoft 365 E5 licencias de suscripción.  Para obtener más información sobre las licencias, consulte los [Términos del producto](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/all).  

Tema|Descripción
:---|:---
[Incorporar dispositivos con la directiva de grupo](configure-endpoints-gp.md)|Utilice Directiva de grupo para implementar el paquete de configuración en los dispositivos.
[Incorporar dispositivos con el Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)|Puede usar Microsoft Endpoint Manager (rama actual) versión 1606 o Microsoft Endpoint Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en los dispositivos.
[Incorporar dispositivos con las herramientas de administración de dispositivos móviles](configure-endpoints-mdm.md)|Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.
[Incorporar dispositivos con un script local](configure-endpoints-script.md)|Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.
[Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)|Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.

> ¿Desea experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpoints-belowfoldlink)

Después de incorporar el dispositivo, puede optar por ejecutar una prueba de detección para comprobar que un dispositivo está incorporado correctamente al servicio. Para obtener más información, consulte [Ejecución de una prueba de detección en un dispositivo Microsoft Defender para punto de conexión recién incorporado](run-detection-test.md).
