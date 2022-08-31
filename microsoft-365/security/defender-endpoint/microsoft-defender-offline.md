---
title: Microsoft Defender sin conexión en Windows
description: Puede usar Microsoft Defender Sin conexión directamente desde la aplicación Antivirus de Microsoft Defender. También puede administrar cómo se implementa en la red.
keywords: examen, defender, sin conexión
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.date: 08/30/2022
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 350ab278281cc436bb49c6d27827ac73ae2bea43
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67476536"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Ejecutar y revisar los resultados de un análisis de Microsoft Defender sin Conexión

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Microsoft Defender Offline es una herramienta de examen antimalware que le permite arrancar y ejecutar un examen desde un entorno de confianza. El examen se ejecuta fuera del kernel normal de Windows para que pueda dirigirse al malware que intenta omitir el shell de Windows, como virus y rootkits que infectan o sobrescriben el registro de arranque maestro (MBR).

Puede usar Microsoft Defender Sin conexión si sospecha que hay una infección de malware o si desea confirmar una limpieza exhaustiva del punto de conexión después de un brote de malware.

En Windows 10 y Windows 11, Microsoft Defender Sin conexión se puede ejecutar con un solo clic directamente desde la [aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md). En versiones anteriores de Windows, un usuario tenía que instalar Microsoft Defender sin conexión en medios de arranque, reiniciar el punto de conexión y cargar los medios de arranque.

## <a name="prerequisites-and-requirements"></a>requisitos previos y requisitos

Microsoft Defender sin conexión en Windows 10 y Windows 11 tiene los mismos requisitos de hardware que Windows 10.

Para obtener más información sobre los requisitos de Windows 10 y Windows 11, consulte los temas siguientes:

- [Requisitos mínimos de hardware](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [Directrices de componentes de hardware](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender sin conexión no se admite en máquinas con procesadores ARM ni en unidades de almacenamiento de existencias de Windows Server.

Para ejecutar Microsoft Defender sin conexión desde el punto de conexión, el usuario debe iniciar sesión con privilegios de administrador.

## <a name="microsoft-defender-offline-updates"></a>Actualizaciones sin conexión de Microsoft Defender

Microsoft Defender Sin conexión usa las actualizaciones de protección más recientes disponibles en el punto de conexión; se actualiza cada vez que se actualiza el Antivirus de Microsoft Defender.

> [!NOTE]
> Antes de ejecutar un examen sin conexión, debe intentar actualizar la protección antivirus de Microsoft Defender. Puede forzar una actualización con directiva de grupo o, sin embargo, normalmente implementa actualizaciones en puntos de conexión, o puede descargar e instalar manualmente las actualizaciones de protección más recientes desde el [Centro de protección contra malware de Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx).

Consulte el tema [Administrar actualizaciones de inteligencia de seguridad del Antivirus de Microsoft Defender](manage-protection-updates-microsoft-defender-antivirus.md) para obtener más información.

## <a name="usage-scenarios"></a>Escenarios de uso

En Windows 10, versión 1607, puede forzar manualmente un examen sin conexión. Como alternativa, si Windows Defender determina que Microsoft Defender Sin conexión necesita ejecutarse, se le pedirá al usuario que se encuentra en el punto de conexión.

La necesidad de realizar un examen sin conexión también se revelará en Microsoft Endpoint Manager si lo usa para administrar los puntos de conexión.

El aviso puede producirse a través de una notificación, similar a la siguiente:

:::image type="content" source="../../media/notification.png" alt-text="Notificación para ejecutar Microsoft Defender sin conexión" lightbox="../../media/notification.png":::

El usuario también recibirá una notificación en el cliente de Windows Defender.

En Configuration Manager, puede identificar el estado de los puntos de conexión; para ello, vaya a **Supervisión > Información general > Seguridad > Estado de Endpoint Protection > System Center Endpoint Protection Estado**.

Los exámenes sin conexión de Microsoft Defender se indican en **Estado de corrección de malware** como **Examen sin conexión necesario**.

:::image type="content" source="../../media/sccm-wdo.png" alt-text="Indicador de un examen de Microsoft Defender sin conexión" lightbox="../../media/sccm-wdo.png":::

## <a name="configure-notifications"></a>Configuración de notificaciones

Las notificaciones sin conexión de Microsoft Defender se configuran en la misma configuración de directiva que otras notificaciones del Antivirus de Microsoft Defender.

Para obtener más información sobre las notificaciones en Windows Defender, vea el tema [Configurar las notificaciones que aparecen en los puntos de conexión](configure-notifications-microsoft-defender-antivirus.md).

## <a name="run-a-scan"></a>Ejecutar un examen

> [!IMPORTANT]
> Antes de usar Microsoft Defender sin conexión, asegúrese de guardar los archivos y apagar los programas en ejecución. El examen sin conexión de Microsoft Defender tarda unos 15 minutos en ejecutarse. Reiniciará el punto de conexión cuando se complete el examen. El examen se realiza fuera del entorno operativo Habitual de Windows. La interfaz de usuario aparecerá diferente a un examen normal realizado por Windows Defender. Una vez completado el examen, se reiniciará el punto de conexión y Windows se cargará con normalidad.

Puede ejecutar un examen sin conexión de Microsoft Defender con lo siguiente:

- PowerShell
- Instrumental de administración de Windows (WMI)
- La aplicación Seguridad de Windows

### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Uso de cmdlets de PowerShell para ejecutar un examen sin conexión

Use los siguientes cmdlets:

```PowerShell
Start-MpWDOScan
```

Consulte [Uso de cmdlets de PowerShell para configurar y ejecutar antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [cmdlets de Antivirus de Defender](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con el Antivirus de Microsoft Defender.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Uso de Instrucciones de administración de Windows (WMI) para ejecutar un examen sin conexión

Use la clase [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para ejecutar un examen sin conexión.

El siguiente fragmento de script WMI ejecutará inmediatamente un examen sin conexión de Microsoft Defender, lo que hará que el punto de conexión se reinicie, ejecute el examen sin conexión y, a continuación, reinicie y arranque en Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start
```

Consulte lo siguiente para obtener más información:

- [API Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Uso de la aplicación Windows Defender Security para ejecutar un examen sin conexión

1. Para abrir la aplicación Seguridad de Windows, haga clic en el icono de escudo de la barra de tareas o busque **Defender for Cloud en** el menú inicio.

2. Haga clic en el icono **de Protección contra amenazas de Virus &** (o en el icono de escudo de la barra de menús de la izquierda) y, a continuación, en la etiqueta **Análisis avanzado** :

3. Seleccione **Examen sin conexión de Microsoft Defender** y haga clic en **Examinar ahora**.

    > [!NOTE]
    > En Windows 10, versión 1607, el examen sin conexión se podría ejecutar desde **windows Settings** \> **Update &** **Windows Defender** de seguridad \> o desde el cliente de Windows Defender.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

### <a name="where-can-i-find-the-scan-results"></a>¿Dónde puedo encontrar los resultados del examen?

Para ver los resultados del examen sin conexión de Microsoft Defender:

1. Seleccione **Inicio** y, a continuación, seleccione **Configuración**  > **Actualizar & Seguridad**  >  **Seguridad de Windows**  >  **Virus & protección contra amenazas**.

2. En la pantalla **Protección contra amenazas de Virus &** , en **Amenazas actuales**, seleccione Opciones de **examen** y, a continuación, seleccione **Historial de protección**.

## <a name="related-articles"></a>Artículos relacionados

- [Personalización, inicio y revisión de los resultados de los exámenes y la corrección](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
