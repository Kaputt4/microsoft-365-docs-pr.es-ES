---
title: Solución de problemas con las herramientas de informes para Antivirus de Microsoft Defender
description: Identificar y resolver problemas comunes al intentar informar en Antivirus de Microsoft Defender estado de protección en Cumplimiento de actualizaciones
keywords: solucionar problemas, errores, corregir, actualizar el cumplimiento, oms, supervisar, informar, Antivirus de Microsoft Defender
ms.prod: m365-security
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
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: bf65bb13ab45d127bf2302464f1948437e1fe02d
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65417982"
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
> El 31 de marzo de 2020, se quitará la característica de informes Antivirus de Microsoft Defender de Cumplimiento de actualizaciones. Puede seguir definiendo y revisando las directivas de cumplimiento de seguridad mediante [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), lo que permite un control más preciso sobre las características de seguridad y las actualizaciones.

Puede usar Antivirus de Microsoft Defender con El cumplimiento de actualizaciones. Verá el estado de las licencias E3, B, F1, VL y Pro. Sin embargo, para las licencias E5, debe usar el [portal de Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Para obtener más información sobre las opciones de licencia, consulte [Windows 10 opciones de licencias de productos](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).

Al usar [Windows Cumplimiento de actualizaciones de Analytics para obtener informes sobre el estado de protección de los dispositivos o puntos de conexión de](/windows/deployment/update/update-compliance-using#wdav-assessment) la red que usan Antivirus de Microsoft Defender, es posible que encuentre problemas o problemas.

Normalmente, los indicadores más comunes de un problema son:

- Solo verá un pequeño número o subconjunto de todos los dispositivos que esperaba ver.
- No ve ningún dispositivo en absoluto
- Los informes y la información que ve no están actualizados (más de unos días)

Para obtener códigos de error comunes e identificadores de evento relacionados con el servicio de Antivirus de Microsoft Defender que no están relacionados con el cumplimiento de actualizaciones, consulte [eventos de Antivirus de Microsoft Defender](troubleshoot-microsoft-defender-antivirus.md).

Hay tres pasos para solucionar estos problemas:

1. Confirme que ha cumplido todos los requisitos previos.
2. Comprobación de la conectividad con el servicio basado en la nube de Windows Defender
3. Envío de registros de soporte técnico

> [!IMPORTANT]
> Normalmente, los dispositivos tardan 3 días en empezar a aparecer en Cumplimiento de actualizaciones.

## <a name="confirm-prerequisites"></a>Confirmación de los requisitos previos

Para que los dispositivos se muestren correctamente en Cumplimiento de actualizaciones, debe cumplir ciertos requisitos previos tanto para el servicio de cumplimiento de actualizaciones como para Antivirus de Microsoft Defender:

>[!div class="checklist"]
>
> - Los puntos de conexión usan Antivirus de Microsoft Defender como única aplicación de protección antivirus. [El uso de cualquier otra aplicación antivirus hará que Antivirus de Microsoft Defender se deshabilite](microsoft-defender-antivirus-compatibility.md) y el punto de conexión no se notificará en Cumplimiento de actualizaciones.
> - [La protección entregada en la nube está habilitada](enable-cloud-protection-microsoft-defender-antivirus.md).
> - Los puntos de conexión pueden [conectarse a la nube de Antivirus de Microsoft Defender](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Si el punto de conexión se ejecuta Windows 10 versión 1607 o anterior, [Windows 10 datos de diagnóstico deben establecerse en el nivel Mejorado](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).
> - Han pasado 3 días desde que se han cumplido todos los requisitos

"Puede usar Antivirus de Microsoft Defender con el cumplimiento de actualizaciones. Verá el estado de las licencias E3, B, F1, VL y Pro. Sin embargo, para las licencias de E5, debe usar el portal de Microsoft Defender para punto de conexión (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Para obtener más información sobre las opciones de licencia, consulte Windows 10 opciones de licencias de productos"

Si se cumplen todos los requisitos previos anteriores, es posible que tenga que continuar con el paso siguiente para recopilar información de diagnóstico y enviarla a nosotros.

> [!div class="nextstepaction"]
> [Recopilación de datos de diagnóstico para la solución de problemas de cumplimiento de actualizaciones](collect-diagnostic-data.md)

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Implementación de Antivirus de Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
