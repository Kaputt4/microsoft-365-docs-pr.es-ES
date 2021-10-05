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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a07bd5cf5d3c3a021811841ccf3fffe054823ffa
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124726"
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

Se admiten las siguientes herramientas y métodos de implementación:


Tema|Descripción
:---|:---
[Incorporar dispositivos con la directiva de grupo](configure-endpoints-gp.md)|Use la directiva de grupo para implementar el paquete de configuración en dispositivos.
[Incorporar dispositivos con el Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)|Puede usar Microsoft Endpoint Manager (rama actual) versión 1606 o Microsoft Endpoint Manager (rama actual) versión 1602 o anterior para implementar el paquete de configuración en dispositivos.
[Incorporar dispositivos con las herramientas de administración de dispositivos móviles](configure-endpoints-mdm.md)|Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.
[Incorporar dispositivos con un script local](configure-endpoints-script.md)|Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.
[Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)|Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpoints-belowfoldlink)


Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que un dispositivo está correctamente incorporado al servicio. Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint](run-detection-test.md)recién incorporado.