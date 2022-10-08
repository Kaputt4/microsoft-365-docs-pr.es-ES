---
title: Corregir la detección de correcciones para el Antivirus de Windows Defender
description: Configure lo que Microsoft Defender Antivirus debe hacer cuando detecte una amenaza y cuánto tiempo deben conservarse los archivos en cuarentena en la carpeta de cuarentena.
keywords: corrección, corrección, eliminación, amenazas, cuarentena, examen, restauración
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: m365-security
search.appverid: met150
ms.openlocfilehash: 30c21e93f4370025a3dd4dba9bd14d96a2deeaae
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68061734"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Corregir la detección de correcciones para el Antivirus de Windows Defender


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Cuando Microsoft Defender Antivirus ejecuta un examen, intenta corregir o quitar las amenazas detectadas. Puede configurar cómo Microsoft Defender Antivirus debe abordar determinadas amenazas, si se debe crear un punto de restauración antes de corregirlo y cuándo se deben quitar las amenazas.

En este artículo se describe cómo configurar estas opciones mediante directiva de grupo, pero también puede usar Configuration Manager y [Microsoft Intune](/intune/device-restrictions-configure) de [punto de conexión de Microsoft](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings).

También puede usar el [cmdlet de PowerShell o la`Set-MpPreference` clase](/powershell/module/defender/set-mppreference) WMI para configurar estas opciones.[`MSFT_MpPreference`](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="configure-remediation-options"></a>Configuración de opciones de corrección

1. En el equipo de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol a **componentes** \> **de Windows Microsoft Defender Antivirus**.

4. Con la tabla siguiente, seleccione una ubicación y, a continuación, edite la directiva según sea necesario.

5. Seleccione **Aceptar**.

<br/><br/>

|Ubicación|Configuración|Descripción|Configuración predeterminada (si no está configurada)|
|---|---|---|---|
|Examinar|Creación de un punto de restauración del sistema|Se creará un punto de restauración del sistema cada día antes de que se intente limpiar o escanear.|Deshabilitada|
|Examinar|Activar la eliminación de elementos de la carpeta del historial de exámenes|Especificar cuántos días deben conservarse los elementos en el historial de exámenes|30 días|
|Raíz|Desactivar la corrección rutinaria|Puede especificar si Microsoft Defender Antivirus corrige automáticamente las amenazas o si debe preguntar al usuario del punto de conexión qué hacer.|Deshabilitado (las amenazas se corrigen automáticamente)|
|Quarantine|Configuración de la eliminación de elementos de la carpeta Cuarentena|Especificar cuántos días deben mantenerse los elementos en cuarentena antes de quitarlos|90 días|
|Amenazas|Especificar los niveles de alerta de amenaza en los que no se debe realizar una acción predeterminada cuando se detecte|A cada amenaza detectada por Microsoft Defender Antivirus se le asigna un nivel de amenaza (bajo, medio, alto o grave). Puede usar esta configuración para definir cómo se deben corregir todas las amenazas de cada uno de los niveles de amenazas (ponerlas en cuarentena, quitarlas o omitirlas).|No aplicable|
|Amenazas|Especificar amenazas en las que no se debe realizar una acción predeterminada cuando se detecte|Especifique cómo deben corregirse amenazas específicas (con su identificador de amenaza). Puede especificar si se debe poner en cuarentena, quitar o omitir la amenaza específica.|No aplicable|

> [!IMPORTANT]
> Microsoft Defender Antivirus detecta y corrige los archivos en función de muchos factores. A veces, completar una corrección requiere un reinicio. Incluso si más adelante se determina que la detección es un falso positivo, el reinicio debe completarse para asegurarse de que se han completado todos los pasos de corrección adicionales.
>
> Si está seguro Microsoft Defender Antivirus pone en cuarentena un archivo en función de un falso positivo, puede restaurar el archivo de la cuarentena después de reiniciar el dispositivo. Consulte [Restauración de archivos en cuarentena en Microsoft Defender Antivirus](restore-quarantined-files-microsoft-defender-antivirus.md).
>
> Para evitar este problema en el futuro, puede excluir archivos de los exámenes. Consulte [Configure and validate exclusions for Microsoft Defender Antivirus scans (Configurar y validar exclusiones para los exámenes de antivirus de Microsoft Defender](configure-exclusions-microsoft-defender-antivirus.md)).

Consulte también [Configuración de exámenes de antivirus de Microsoft Defender completos programados necesarios](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) para la corrección para obtener más opciones relacionadas con la corrección.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

- [Configurar opciones de análisis del Antivirus de Microsoft Defender](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Configuración de exámenes programados Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Configurar y ejecutar análisis bajo petición en el Antivirus de Microsoft Defender](run-scan-microsoft-defender-antivirus.md)
- [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md)
- [Configuración de la interacción del usuario final Microsoft Defender antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Personalización, inicio y revisión de los resultados de los exámenes y correcciones de Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
