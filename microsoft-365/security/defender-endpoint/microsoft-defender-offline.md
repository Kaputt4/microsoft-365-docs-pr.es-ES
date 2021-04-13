---
title: Microsoft Defender sin conexión en Windows 10
description: Puedes usar Microsoft Defender sin conexión directamente desde la Windows Defender Antivirus. También puede administrar cómo se implementa en la red.
keywords: examinar, defender, sin conexión
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
ms.openlocfilehash: 44a0e78ecfe3854a070831bf01a012c2cec06ce7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690935"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Ejecutar y revisar los resultados de un examen sin conexión de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline es una herramienta de detección de antimalware que te permite arrancar y ejecutar un examen desde un entorno de confianza. El examen se ejecuta desde fuera del kernel normal de Windows para que pueda dirigirse a malware que intente omitir el shell de Windows, como virus y rootkits que infectan o sobrescriben el registro de arranque maestro (MBR).

Puedes usar Microsoft Defender sin conexión si sospechas de una infección de malware o quieres confirmar una limpieza exhaustiva del punto de conexión después de un brote de malware.

En Windows 10, Microsoft Defender sin conexión se puede ejecutar con un solo clic directamente desde la [aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md). En versiones anteriores de Windows, un usuario tenía que instalar Microsoft Defender sin conexión en medios de arranque, reiniciar el punto de conexión y cargar los medios de arranque.

## <a name="prerequisites-and-requirements"></a>requisitos previos y requisitos

Microsoft Defender sin conexión en Windows 10 tiene los mismos requisitos de hardware que Windows 10. 

Para obtener más información acerca de los requisitos de Windows 10, consulta los siguientes temas:

- [Requisitos mínimos de hardware](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Directrices de componentes de hardware](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender sin conexión no se admite en máquinas con ARM procesadores o en unidades de mantenimiento de valores de Windows Server.

Para ejecutar Microsoft Defender sin conexión desde el punto de conexión, el usuario debe haber iniciado sesión con privilegios de administrador.
 
## <a name="microsoft-defender-offline-updates"></a>Actualizaciones sin conexión de Microsoft Defender

Microsoft Defender sin conexión usa las actualizaciones de protección más recientes disponibles en el punto de conexión; se actualiza siempre que Windows Defender antivirus se actualiza. 

> [!NOTE]
> Antes de ejecutar un examen sin conexión, debes intentar actualizar la protección antivirus de Microsoft Defender. Puede forzar una actualización con la directiva de grupo o bien implementar actualizaciones normalmente en los puntos de conexión, o puede descargar e instalar manualmente las actualizaciones de protección más recientes de [la Centro de protección contra malware de Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx).

Consulta el [tema Administrar actualizaciones de inteligencia de Seguridad antivirus de Microsoft Defender](manage-protection-updates-microsoft-defender-antivirus.md) para obtener más información.

## <a name="usage-scenarios"></a>Escenarios de uso

En Windows 10, versión 1607, puedes forzar manualmente un examen sin conexión. Como alternativa, si Windows Defender determina que Microsoft Defender sin conexión debe ejecutarse, se le pedirá al usuario en el punto de conexión. 

La necesidad de realizar un examen sin conexión también se mostrará en Microsoft Endpoint Manager si lo usa para administrar los puntos de conexión.

El mensaje puede producirse a través de una notificación, de forma similar a la siguiente:

![Notificación de Windows que muestra el requisito para ejecutar Microsoft Defender sin conexión](images/defender/notification.png)

También se notificará al usuario en el Windows Defender cliente.

En Configuration Manager, puede identificar el estado de los puntos de conexión navegando **a Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**. 

Los exámenes sin conexión de Microsoft Defender se indican en Estado de **corrección de malware** como **examen sin conexión requerido.**

![Microsoft Endpoint Manager que indica que es necesario realizar un examen sin conexión de Microsoft Defender](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Configurar notificaciones

Las notificaciones sin conexión de Microsoft Defender se configuran en la misma configuración de directiva que otras notificaciones av de Microsoft Defender.

Para obtener más información acerca de las notificaciones en Windows Defender, vea el tema Configurar las notificaciones que [aparecen en los puntos de conexión.](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>Ejecutar un examen 

> [!IMPORTANT]
> Antes de usar Microsoft Defender sin conexión, asegúrese de guardar los archivos y apagar los programas en ejecución. El examen sin conexión de Microsoft Defender tarda unos 15 minutos en ejecutarse. Reiniciará el punto de conexión cuando se complete el examen. El examen se realiza fuera del entorno operativo habitual de Windows. La interfaz de usuario aparecerá diferente a un examen normal realizado por Windows Defender. Una vez completado el examen, el punto de conexión se reiniciará y Windows se cargará normalmente.

Puede ejecutar un examen sin conexión de Microsoft Defender con lo siguiente:

- PowerShell
- Instrumental de administración de Windows (WMI)
- La aplicación Seguridad de Windows



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Usar cmdlets de PowerShell para ejecutar un examen sin conexión

Use los cmdlets siguientes:

```PowerShell
Start-MpWDOScan
```

Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Usar Windows Management Instruction (WMI) para ejecutar un examen sin conexión

Use la [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para ejecutar un examen sin conexión.

El siguiente fragmento de código de script WMI ejecutará inmediatamente un examen sin conexión de Microsoft Defender, lo que hará que el extremo se reinicie, ejecute el examen sin conexión y, a continuación, reinicie y arranque en Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Vea lo siguiente para obtener más información:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Usar la aplicación Windows Defender Seguridad para ejecutar un examen sin conexión

1. Abre la aplicación Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio de **Defender**.

2. Haga clic **en el icono protección contra &** virus (o en el icono de escudo de la barra de menús izquierda) y, a continuación, en la etiqueta **Examen** avanzado:
    
3. Seleccione **Examen sin conexión de Microsoft Defender** y haga clic en Examinar **ahora**.

    > [!NOTE]
    > En Windows 10, versión 1607, el examen sin conexión podría ejecutarse desde la sección Actualización de configuración de **Windows**& seguridad Windows Defender desde el  >    >   Windows Defender cliente.


## <a name="review-scan-results"></a>Revisar los resultados del examen

Los resultados del examen sin conexión de Microsoft Defender se mostrarán en la sección Historial [de análisis de la aplicación Seguridad de Windows.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>Artículos relacionados

- [Personalizar, iniciar y revisar los resultados de los exámenes y la corrección](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)