---
title: Herramientas y métodos de incorporación para dispositivos Windows 10
description: Incorporar dispositivos Windows 10 para que puedan enviar datos del sensor al sensor atp de Microsoft Defender
keywords: Incorporación de dispositivos Windows 10, directiva de grupo, administrador de configuración de extremo, administración de dispositivos móviles, script local, gp, sccm, mdm, intune
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
ms.openlocfilehash: 77b843f9526d8b100845403bc8d2df4bf3259471
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760217"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Herramientas y métodos de incorporación para dispositivos Windows 10

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Prevención de pérdida de datos del extremo de Microsoft 365 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Administración de riesgos de Microsoft 365 Insider](/microsoft-365/compliance/insider-risk-management)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Los dispositivos de la organización deben configurarse para que el servicio Defender for Endpoint pueda obtener datos de sensores de ellos. Existen varios métodos y herramientas de implementación que puede usar para configurar los dispositivos de la organización.

Se admiten las siguientes herramientas y métodos de implementación:

- Directiva de grupo
- Microsoft Endpoint Configuration Manager
- Administración de dispositivos móviles (incluido Microsoft Intune)
- Script local

## <a name="in-this-section"></a>En esta sección
Tema | Descripción
:---|:---
[Incorporación de dispositivos Windows 10 con la directiva de grupo](configure-endpoints-gp.md) | Use la directiva de grupo para implementar el paquete de configuración en dispositivos.
[Incorporación de dispositivos Windows con Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) | Puede usar Microsoft Endpoint Manager (rama actual) versión 1606 o Microsoft Endpoint Manager (rama actual) versión 1602 o versiones anteriores para implementar el paquete de configuración en dispositivos.
[Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles](configure-endpoints-mdm.md) | Usa las herramientas de administración de dispositivos móviles o Microsoft Intune para implementar el paquete de configuración en el dispositivo.
[Incorporar dispositivos Windows 10 mediante un script local](configure-endpoints-script.md) | Obtenga información sobre cómo usar el script local para implementar el paquete de configuración en puntos de conexión.
[Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md) | Obtenga información sobre cómo usar el paquete de configuración para configurar dispositivos VDI.


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
