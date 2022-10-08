---
title: Solución de problemas con las herramientas de informes para Microsoft Defender Antivirus
description: Identificar y resolver problemas comunes al intentar informar en Microsoft Defender estado de protección antivirus en Cumplimiento de actualizaciones
keywords: solución de problemas, error, corrección, cumplimiento de actualizaciones, oms, supervisión, informe, Microsoft Defender Antivirus
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier3
search.appverid: met150
ms.openlocfilehash: ec4d628d3eee6cb8331560241f008ef92168961b
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68226018"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Solucionar problemas de informes del Antivirus de Windows Defender en la comprobación de actualizaciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> [!IMPORTANT]
> El 31 de marzo de 2020, se quitará la característica de informes Microsoft Defender Antivirus de Cumplimiento de actualizaciones. Puede seguir definiendo y revisando las directivas de cumplimiento de seguridad mediante [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), lo que permite un control más preciso sobre las características de seguridad y las actualizaciones.

Puede usar Microsoft Defender Antivirus con el cumplimiento de actualizaciones. Verá el estado de las licencias E3, B, F1, VL y Pro. Sin embargo, para las licencias E5, debe usar el [portal de Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Para obtener más información sobre las opciones de licencia, consulte [Windows 10 opciones de licencias de productos](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).

Al usar [el cumplimiento de actualizaciones de Windows Analytics para obtener informes sobre el estado de protección de los dispositivos o puntos de conexión de](/windows/deployment/update/update-compliance-using#wdav-assessment) la red que usan Microsoft Defender Antivirus, es posible que encuentre problemas o problemas.

Normalmente, los indicadores más comunes de un problema son:

- Solo verá un pequeño número o subconjunto de todos los dispositivos que esperaba ver.
- No ve ningún dispositivo en absoluto
- Los informes y la información que ve no están actualizados (más de unos días)

Para obtener códigos de error comunes e identificadores de evento relacionados con el servicio antivirus de Microsoft Defender que no están relacionados con el cumplimiento de actualizaciones, consulte [Microsoft Defender Eventos de Antivirus](troubleshoot-microsoft-defender-antivirus.md).

Hay tres pasos para solucionar estos problemas:

1. Confirme que ha cumplido todos los requisitos previos.
2. Comprobación de la conectividad con el servicio basado en la nube de Windows Defender
3. Envío de registros de soporte técnico

> [!IMPORTANT]
> Normalmente, los dispositivos tardan 3 días en empezar a aparecer en Cumplimiento de actualizaciones.

## <a name="confirm-prerequisites"></a>Confirmación de los requisitos previos

Para que los dispositivos se muestren correctamente en Cumplimiento de actualizaciones, debe cumplir ciertos requisitos previos tanto para el servicio de cumplimiento de actualizaciones como para Microsoft Defender Antivirus:

>[!div class="checklist"]
>
> - Los puntos de conexión usan Microsoft Defender Antivirus como única aplicación de protección antivirus. [El uso de cualquier otra aplicación antivirus hará que Microsoft Defender Antivirus se deshabilite](microsoft-defender-antivirus-compatibility.md) y el punto de conexión no se notificará en Cumplimiento de actualizaciones.
> - [La protección entregada en la nube está habilitada](enable-cloud-protection-microsoft-defender-antivirus.md).
> - Los puntos de conexión pueden [conectarse a la nube Microsoft Defender Antivirus](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Si el punto de conexión se ejecuta Windows 10 versión 1607 o anterior, [Windows 10 datos de diagnóstico deben establecerse en el nivel Mejorado](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).
> - Han pasado 3 días desde que se han cumplido todos los requisitos

"Puede usar Microsoft Defender Antivirus con el cumplimiento de actualizaciones. Verá el estado de las licencias E3, B, F1, VL y Pro. Sin embargo, para las licencias de E5, debe usar el portal de Microsoft Defender para punto de conexión (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Para obtener más información sobre las opciones de licencia, consulte Windows 10 opciones de licencias de productos"

Si se cumplen todos los requisitos previos anteriores, es posible que tenga que continuar con el paso siguiente para recopilar información de diagnóstico y enviarla a nosotros.

> [!div class="nextstepaction"]
> [Recopilación de datos de diagnóstico para la solución de problemas de cumplimiento de actualizaciones](collect-diagnostic-data.md)

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementación de Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
