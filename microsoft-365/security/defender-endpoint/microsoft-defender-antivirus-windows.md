---
title: Antivirus de Microsoft Defender en Windows
description: Información sobre cómo administrar, configurar y usar Antivirus de Microsoft Defender, una protección integrada antimalware y antivirus.
keywords: Antivirus de Microsoft Defender, windows defender, antimalware, scep, protección de punto de conexión del centro del sistema, administrador de configuración del centro del sistema, virus, malware, amenazas, detección, protección, seguridad
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
ms.date: 10/03/2022
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 27d7665fb275531457e90b418a2053fb978d7ead
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2022
ms.locfileid: "68537102"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Antivirus de Microsoft Defender en Windows

**Se aplica a:**

- Microsoft Defender para punto de conexión, planes 1 y 2
- Microsoft Defender para Empresas
- Antivirus de Microsoft Defender

**Plataformas**
- Windows 

Antivirus de Microsoft Defender está disponible en Windows 10, Windows 11 y en versiones de Windows Server.

Antivirus de Microsoft Defender es el mayor componente de protección de nueva generación en Microsoft Defender para punto de conexión. Esta protección reúne el aprendizaje automático, el análisis de macrodatos, la investigación de resistencia contra amenazas en profundidad y la infraestructura de nube de Microsoft para proteger a los dispositivos (o puntos de conexión) en la organización. El antivirus de Microsoft Defender está integrado en Windows y funciona con Microsoft Defender para punto de conexión para proporcionar protección en el dispositivo y en la nube.

## <a name="compatibility-with-other-antivirus-products"></a>Compatibilidad con otros productos antivirus

Si usa un producto antimalware o antivirus que no es de Microsoft en el dispositivo, es posible que pueda ejecutar el Antivirus de Microsoft Defender en modo pasivo junto con la solución antivirus que no es de Microsoft. Depende del sistema operativo usado y de si el dispositivo está incorporado a Defender para punto de conexión. Para más información, consulte [Compatibilidad con Antivirus de Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>Comparación del modo activo, el modo pasivo y el modo deshabilitado

En la tabla siguiente se describe qué esperar cuando el Antivirus de Microsoft Defender está en modo activo, en modo pasivo o deshabilitado.

| Modo | Qué ocurre |
|---|---|
| Modo activo | En modo activo, el Antivirus de Microsoft Defender se usa como la aplicación antivirus principal en el dispositivo. Los archivos se examinan, se corrigen las amenazas y las amenazas detectadas se enumeran en los informes de seguridad de la organización y en la aplicación de Seguridad de Windows. |
| Modo pasivo | En modo pasivo, el Antivirus de Microsoft Defender no se usa como la aplicación antivirus principal en el dispositivo. Los archivos se examinan y se notifican las amenazas detectadas, pero el Antivirus de Microsoft Defender no corrige las amenazas. <br/><br/> **IMPORTANTE**: El Antivirus de Microsoft Defender solo se puede ejecutar en modo pasivo en los puntos de conexión que se incorporan a Microsoft Defender para punto de conexión. Consulte [Requisitos para que el Antivirus de Microsoft Defender se ejecute en modo pasivo](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode). |
| Deshabilitado o desinstalado | Cuando se deshabilita o desinstala, no se usa el Antivirus de Microsoft Defender. Los archivos no se examinan y las amenazas no se corrigen. En general, no se recomienda deshabilitar o desinstalar el Antivirus de Microsoft Defender. |

Para más información, consulte [Compatibilidad con Antivirus de Microsoft Defender](microsoft-defender-antivirus-compatibility.md).

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>Comprobar el estado del Antivirus de Microsoft Defender en el dispositivo

Puede usar uno de varios métodos, como la aplicación Seguridad de Windows o Windows PowerShell, para comprobar el estado de Antivirus de Microsoft Defender en el dispositivo.

> [!IMPORTANT]
> A partir de la [versión de la plataforma 4.18.2208.0 y versiones posteriores](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions): si un servidor se ha incorporado a Microsoft Defender para punto de conexión, la configuración de directiva de [grupo](configure-endpoints-gp.md#update-endpoint-protection-configuration) "Desactivar Windows Defender" ya no deshabilitará completamente Windows Defender Antivirus activado. Windows Server 2012 R2 y versiones posteriores. En su lugar, lo colocará en modo pasivo. Además, la característica de [protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md) permitirá cambiar al modo activo, pero no al modo pasivo.
> 
> - Si ya se ha implementado "Desactivar Windows Defender" antes de incorporarse a Microsoft Defender para punto de conexión, no habrá ningún cambio y Antivirus de Defender permanecerá deshabilitado.
> - Para cambiar antivirus de Defender al modo pasivo, incluso si se deshabilitó antes de la incorporación, puede aplicar la [configuración de ForceDefenderPassiveMode](switch-to-mde-phase-2.md#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server) con un valor de `1`. Para colocarlo en modo activo, cambie este valor a `0` en su lugar.
> 
> Tenga en cuenta la lógica modificada para `ForceDefenderPassiveMode` cuando se habilita la protección contra alteraciones: una vez que Microsoft Defender Antivirus cambia al modo activo, la protección contra alteraciones impedirá que vuelva al modo pasivo incluso cuando `ForceDefenderPassiveMode` se establezca en `1`.

### <a name="use-the-windows-security-app-to-check-the-status-of-microsoft-defender-antivirus"></a>Usar la aplicación Seguridad de Windows para comprobar el estado del Antivirus de Microsoft Defender

1. En el dispositivo Windows, seleccione el menú **Inicio** y empiece a escribir `Security`. A continuación, abra la aplicación Seguridad de Windows en los resultados.

2. Seleccione **Protección antivirus y contra amenazas**.

3. En **¿Quién me protege?**, elija **Administrar proveedores**.

Verá el nombre de la solución antivirus o antimalware en la página de proveedores de seguridad.

### <a name="use-powershell-to-check-the-status-of-microsoft-defender-antivirus"></a>Usar PowerShell para comprobar el estado del Antivirus de Microsoft Defender

1. Seleccione el menú **Inicio** y empiece a escribir `PowerShell`. A continuación, abra Windows PowerShell en los resultados.

2. Tipo `Get-MpComputerStatus`.

3. En la lista de resultados, examine la fila **AMRunningMode**.

   - **Normal** significa que el Antivirus de Microsoft Defender se ejecuta en modo activo.

   - **Modo pasivo** significa que el Antivirus de Microsoft Defender está ejecución, pero no es el producto antivirus/antimalware principal del dispositivo. El modo pasivo solo está disponible para los dispositivos que se incorporan a Microsoft Defender para punto de conexión y que cumplen determinados requisitos. Consulte [Requisitos para que el Antivirus de Microsoft Defender se ejecute en modo pasivo](microsoft-defender-antivirus-compatibility.md#requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode).

   - **Modo de bloqueo de EDR**: significa que el Antivirus de Microsoft Defender se está ejecutando y que está habilitada la [Detección y respuesta de puntos de conexión (EDR) en modo de bloqueo](edr-in-block-mode.md), una funcionalidad de Microsoft Defender para punto de conexión. Compruebe la clave del Registro **ForceDefenderPassiveMode** . Si su valor es 0, se ejecuta en modo normal; De lo contrario, se ejecuta en modo pasivo.

   - **El modo pasivo SxS** significa Microsoft Defender Antivirus se ejecuta junto con otro producto antivirus o antimalware y [se usa un examen periódico limitado](limited-periodic-scanning-microsoft-defender-antivirus.md).

> [!TIP]
> Para obtener más información sobre el cmdlet de Get-MpComputerStatus PowerShell, consulte el artículo de referencia [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

## <a name="get-your-antivirusantimalware-platform-updates"></a>Obtener actualizaciones de la plataforma malware/antivirus

Es importante mantener actualizado el Antivirus de Microsoft Defender, o cualquier solución antivirus/antimalware. Microsoft publica actualizaciones periódicas para ayudar a garantizar que los dispositivos tengan la última tecnología  para protegerse contra nuevas técnicas de ataque y malware. Para obtener más información, consulte [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia](manage-updates-baselines-microsoft-defender-antivirus.md).

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

- [Administración y configuración de Antivirus de Microsoft Defender](configuration-management-reference-microsoft-defender-antivirus.md)
- [Evaluar la protección de Antivirus de Microsoft Defender](evaluate-microsoft-defender-antivirus.md)
