---
title: Configurar la corrección para las detecciones de Antivirus de Microsoft Defender
description: Configurar lo que antivirus de Microsoft Defender debe hacer cuando detecte una amenaza y cuánto tiempo deben conservarse los archivos en cuarentena en la carpeta de cuarentena
keywords: corrección, corrección, eliminación, amenazas, cuarentena, examen, restauración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98bc079bcfd772ada52d699d5f873a187d4ab4c1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765064"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Configurar la corrección para las detecciones de Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Cuando Antivirus de Microsoft Defender ejecuta un examen, intenta corregir o quitar las amenazas que se detectan. Puede configurar cómo antivirus de Microsoft Defender debe abordar determinadas amenazas, si se debe crear un punto de restauración antes de corregir y cuándo deben quitarse las amenazas.

En este artículo se describe cómo configurar estas opciones mediante la directiva de grupo, pero también puede usar [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) y Microsoft [Intune](/intune/device-restrictions-configure). 

También puede usar el [ `Set-MpPreference` cmdlet de PowerShell](/powershell/module/defender/set-mppreference) o la [ `MSFT_MpPreference` clase WMI](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) para configurar estas opciones.

## <a name="configure-remediation-options"></a>Configurar opciones de corrección

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo** y seleccione **Plantillas administrativas.**

3. Expande el árbol a **Componentes de Windows** Antivirus de Microsoft  >  **Defender**. 

4. Con la tabla siguiente, seleccione una ubicación y, a continuación, edite la directiva según sea necesario. 

5. Elija **Aceptar**.

|Ubicación | Configuración | Descripción | Configuración predeterminada (si no está configurada) |
|:---|:---|:---|:---|
|Examinar | Crear un punto de restauración del sistema | Se creará un punto de restauración del sistema cada día antes de intentar limpiar o examinar | Deshabilitada|
|Examinar | Activar la eliminación de elementos de la carpeta historial de examen | Especificar cuántos días deben mantenerse los elementos en el historial de examen | 30 días |
|Raíz | Desactivar la corrección rutinaria | Puede especificar si Antivirus de Microsoft Defender corrige automáticamente las amenazas o si debe preguntar al usuario del extremo qué hacer. | Deshabilitado (las amenazas se corrigen automáticamente) |
|Cuarentena | Configurar la eliminación de elementos de la carpeta cuarentena | Especificar cuántos días deben mantenerse en cuarentena los elementos antes de quitarse | 90 días |
|Amenazas | Especificar niveles de alerta de amenazas en los que no se debe realizar ninguna acción predeterminada cuando se detecte | Cada amenaza detectada por Antivirus de Microsoft Defender tiene asignado un nivel de amenaza (bajo, medio, alto o grave). Puede usar esta configuración para definir cómo deben corregirse todas las amenazas de cada uno de los niveles de amenaza (en cuarentena, eliminados o omitidos) | No disponible |
|Amenazas | Especificar amenazas en las que no se debe realizar una acción predeterminada cuando se detecte | Especifique cómo deben corregirse las amenazas específicas (mediante su identificador de amenaza). Puede especificar si la amenaza específica debe ponerse en cuarentena, quitarse o omitirse. | No disponible |

> [!IMPORTANT]
> Antivirus de Microsoft Defender detecta y corrige archivos en función de muchos factores. A veces, completar una corrección requiere un reinicio. Incluso si más adelante se determina que la detección es un falso positivo, el reinicio debe completarse para garantizar que se hayan completado todos los pasos de corrección adicionales.
>
> Si estás seguro de que Antivirus de Microsoft Defender ha puesto en cuarentena un archivo basado en un falso positivo, puedes restaurar el archivo desde la cuarentena después de reiniciar el dispositivo. Consulte [Restaurar archivos en cuarentena en Antivirus de Microsoft Defender](restore-quarantined-files-microsoft-defender-antivirus.md).
> 
> Para evitar este problema en el futuro, puede excluir archivos de los exámenes. Consulte [Configure and validate exclusions for Microsoft Defender Antivirus scans](configure-exclusions-microsoft-defender-antivirus.md).

Vea también [Configure remediation-required scheduled full Microsoft Defender Antivirus scans for](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) more remediation-related settings.

## <a name="see-also"></a>Vea también

- [Configurar opciones de análisis de Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Configurar exámenes programados de Antivirus de Microsoft Defender](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Configurar y ejecutar exámenes de Antivirus de Microsoft Defender a petición](run-scan-microsoft-defender-antivirus.md)
- [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)
- [Configurar la interacción del antivirus de Microsoft Defender para el usuario final](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Personalizar, iniciar y revisar los resultados de los exámenes y la corrección del Antivirus de Microsoft Defender](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)