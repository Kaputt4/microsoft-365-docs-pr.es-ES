---
title: Solucionar problemas con herramientas de informes para Microsoft Defender AV
description: Identificar y resolver problemas comunes al intentar informar sobre el estado de protección antivirus de Microsoft Defender en Update Compliance
keywords: troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1a1c807c86aa95148300298484319001b59963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691591"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Solucionar problemas de informes de Antivirus de Microsoft Defender en Cumplimiento de actualizaciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> El 31 de marzo de 2020, se quitará la característica de informes de Antivirus de Microsoft Defender de Update Compliance. Puede seguir definiendo y revisando directivas de cumplimiento de seguridad con [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)lo que permite un control más preciso sobre las características y actualizaciones de seguridad.

Puede usar Antivirus de Microsoft Defender con cumplimiento de actualizaciones. Verás el estado de las licencias E3, B, F1, VL y Pro. Sin embargo, para las licencias de E5, debe usar [el portal de Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Para obtener más información sobre las opciones de licencias, consulta [Opciones de licencias de productos de Windows 10.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

Cuando usas El cumplimiento de Windows Analytics Update para obtener informes sobre el estado de protección de los [dispositivos](/windows/deployment/update/update-compliance-using#wdav-assessment) o puntos de conexión de la red que usan Antivirus de Microsoft Defender, es posible que encuentres problemas o problemas.

Normalmente, los indicadores más comunes de un problema son:
- Solo ves un número o subconjunto pequeño de todos los dispositivos que esperabas ver
- No ve ningún dispositivo en absoluto
- Los informes y la información que ve están obsoletos (con más de unos días)

Para obtener códigos de error comunes e IDs de eventos relacionados con el servicio antivirus de Microsoft Defender que no están relacionados con el cumplimiento de actualizaciones, vea [Eventos de Antivirus de Microsoft Defender](troubleshoot-microsoft-defender-antivirus.md). 

Hay tres pasos para solucionar estos problemas:

1. Confirmar que ha cumplido todos los requisitos previos
2. Comprobar la conectividad con el servicio Windows Defender basado en la nube
3. Enviar registros de soporte técnico

>[!IMPORTANT]
>Normalmente, los dispositivos tardan 3 días en aparecer en Update Compliance.


## <a name="confirm-prerequisites"></a>Confirmar requisitos previos

Para que los dispositivos se muestren correctamente en Update Compliance, debes cumplir ciertos requisitos previos tanto para el servicio de cumplimiento de actualizaciones como para Antivirus de Microsoft Defender:

>[!div class="checklist"]
>- Los puntos de conexión usan Antivirus de Microsoft Defender como única aplicación de protección antivirus. [El uso de cualquier otra aplicación antivirus hará](microsoft-defender-antivirus-compatibility.md) que el ANTIVIRUS de Microsoft Defender se deshabilite y el extremo no se notirá en Cumplimiento de actualizaciones.
> - [La protección entregada en la nube está habilitada.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Los puntos de conexión [pueden conectarse a la nube av de Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Si el punto de conexión ejecuta Windows 10 versión 1607 o anterior, los datos de diagnóstico de [Windows 10](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)deben establecerse en el nivel mejorado .
> - Han pasado 3 días desde que se han cumplido todos los requisitos

"Puede usar antivirus de Microsoft Defender con cumplimiento de actualizaciones. Verás el estado de las licencias E3, B, F1, VL y Pro. Sin embargo, para las licencias de E5, debe usar el portal de Microsoft Defender para endpoint ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) . Para obtener más información sobre las opciones de licencias, consulta Opciones de licencias de productos de Windows 10"

Si se han cumplido todos los requisitos previos anteriores, es posible que deba continuar con el siguiente paso para recopilar información de diagnóstico y enviarla a nosotros.

> [!div class="nextstepaction"]
> [Recopilar datos de diagnóstico para la solución de problemas de cumplimiento de actualizaciones](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementar antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)