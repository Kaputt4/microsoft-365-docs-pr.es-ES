---
title: Herramientas y métodos de incorporación para Windows dispositivos
description: Incorporar Windows dispositivos para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint
keywords: Incorporación Windows, directiva de grupo, administrador de configuración de extremo, administración de dispositivos móviles, script local, gp, sccm, mdm, intune
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26f4789ed5c44a2a3380476c78cea67daab84917
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240516"
---
# <a name="onboarding-tools-and-methods-for-windows-devices-in-defender-for-endpoint"></a>Herramientas y métodos de incorporación para Windows dispositivos en Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft 365 Prevención de pérdida de datos de extremo (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Microsoft 365 Administración de riesgos de Insider](/microsoft-365/compliance/insider-risk-management)

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Los dispositivos de la organización deben configurarse para que el servicio Defender for Endpoint pueda obtener datos de sensores de ellos. Existen varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de la organización.

En general, identificarás el dispositivo Windows que estás incorporando y, a continuación, sigue la herramienta correspondiente adecuada para el dispositivo o el entorno.

![Imagen de herramientas y métodos de incorporación](images/onboarding-config-tools.png)

## <a name="endpoint-onboarding-tools"></a>Herramientas de incorporación de puntos de conexión
En función del Windows de conexión que desee incorporar, use la herramienta o el método correspondiente que se describe en la tabla siguiente.

Windows dispositivo | Herramienta o método de incorporación
:---|:---
|<ul><li> Windows 10</li> <li>Windows Server 1803 y 2019 y 2022</li> <li>Windows Server 2012 R2 y 2016 <sup> [[1](#fn1)]<sup></li></ul>  |   [Script local (hasta 10 dispositivos)](configure-endpoints-script.md)<br>   [Directiva de grupo](configure-endpoints-gp.md)<br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Microsoft Endpoint Manager/ Administración de dispositivos móviles (Intune)](configure-endpoints-mdm.md)<br>    [Scripts VDI](configure-endpoints-vdi.md) <br><br> **NOTA:** Un script local es adecuado para una prueba de concepto, pero no debe usarse para la implementación de producción. Para una implementación de producción, se recomienda usar la directiva de grupo, Microsoft Endpoint Configuration Manager o Intune.
|<ul><li> Windows Server 2008 R2 SP1 </li></ul>| [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br>[Incorporar versiones anteriores de Windows](onboard-downlevel.md) o Azure [Defender](/azure/security-center/security-center-wdatp) <br><br> **NOTA:** Microsoft Monitoring Agent es ahora agente de Azure Log Analytics. Para obtener más información, consulte [Log Analytics agent overview](/azure/azure-monitor/platform/log-analytics-agent).  
|<ul><li> Windows 7 SP1 </li> <li>  Windows 7 SP1 Pro </li> <li>  Windows 8.1 Pro </li> <li> Windows 8.1 Enterprise</li></ul>  | [Microsoft Monitoring Agent (MMA)](onboard-downlevel.md) <br><br> **NOTA:** Microsoft Monitoring Agent es ahora agente de Azure Log Analytics. Para obtener más información, consulte [Log Analytics agent overview](/azure/azure-monitor/platform/log-analytics-agent).



(<a id="fn1">1</a>) Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse con las instrucciones de [Onboard Windows servers](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016).

Tema|Descripción
:---|:---
[Incorporar dispositivos con la directiva de grupo](configure-endpoints-gp.md)|Use la directiva de grupo para implementar el paquete de configuración en dispositivos.
[Incorporar dispositivos con el Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)|Puede usar Microsoft Endpoint Manager (rama actual) versión 1606 o Microsoft Endpoint Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en dispositivos.
[Incorporar dispositivos con las herramientas de administración de dispositivos móviles](configure-endpoints-mdm.md)|Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.
[Incorporar dispositivos con un script local](configure-endpoints-script.md)|Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.
[Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)|Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpoints-belowfoldlink)


Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio. Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint](run-detection-test.md)recién incorporado.