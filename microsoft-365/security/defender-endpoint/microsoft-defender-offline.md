---
title: Microsoft Defender sin Conexión en Windows 10
description: Puedes usar Microsoft Defender sin Conexión directamente desde la Antivirus de Windows Defender aplicación. También puede administrar cómo se implementa en la red.
keywords: examinar, defender, sin conexión
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a25a2ec513cd7c25f9f6ddf3d5e328928837bf2d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275149"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Ejecutar y revisar los resultados de un análisis de Microsoft Defender sin Conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Microsoft Defender sin Conexión es una herramienta de análisis de antimalware que le permite arrancar y ejecutar un examen desde un entorno de confianza. El examen se ejecuta desde fuera del kernel de Windows normal para que pueda dirigirse a malware que intente omitir el shell de Windows, como virus y rootkits que infectan o sobrescriben el registro de arranque maestro (MBR).

Puede usar Microsoft Defender sin Conexión si sospecha que hay una infección de malware o si desea confirmar una limpieza exhaustiva del extremo después de un brote de malware.

En Windows 10, Microsoft Defender sin Conexión se puede ejecutar con un solo clic directamente desde la [Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md). En versiones anteriores de Windows, un usuario tenía que instalar Microsoft Defender sin Conexión en medios de arranque, reiniciar el extremo y cargar los medios de arranque.

## <a name="prerequisites-and-requirements"></a>requisitos previos y requisitos

Microsoft Defender sin Conexión en Windows 10 tiene los mismos requisitos de hardware que Windows 10. 

Para obtener más información acerca Windows 10 requisitos, consulte los siguientes temas:

- [Requisitos mínimos de hardware](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Directrices de componentes de hardware](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender sin Conexión no se admite en máquinas con procesadores ARM o en Windows unidades de mantenimiento de stock del servidor.

Para ejecutar Microsoft Defender sin Conexión desde el punto de conexión, el usuario debe haber iniciado sesión con privilegios de administrador.
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender sin Conexión actualizaciones

Microsoft Defender sin Conexión las actualizaciones de protección más recientes disponibles en el punto de conexión; se actualiza siempre que Antivirus de Windows Defender se actualiza. 

> [!NOTE]
> Antes de ejecutar un examen sin conexión, debes intentar actualizar la protección antivirus de Microsoft Defender. Puede forzar una actualización con la directiva de grupo o, como es habitual, implementar actualizaciones en los puntos de conexión, o puede descargar e instalar manualmente las actualizaciones de protección más recientes de [la Centro de protección contra malware de Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx).

Consulte el [tema Manage Antivirus de Microsoft Defender Security intelligence updates](manage-protection-updates-microsoft-defender-antivirus.md) para obtener más información.

## <a name="usage-scenarios"></a>Escenarios de uso

En Windows 10, versión 1607, puede forzar manualmente un examen sin conexión. Como alternativa, si Windows Defender determina que Microsoft Defender sin Conexión debe ejecutarse, se le pedirá al usuario en el extremo. 

La necesidad de realizar un examen sin conexión también se mostrará en Microsoft Endpoint Manager si lo usa para administrar los puntos de conexión.

El mensaje puede producirse a través de una notificación, de forma similar a la siguiente:

![Windows notificación que muestra el requisito de ejecutar Microsoft Defender sin Conexión](images/defender/notification.png)

También se notificará al usuario en el Windows Defender cliente.

En Configuration Manager, puede identificar el estado de los puntos de conexión navegando a Monitoring **> Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**. 

Microsoft Defender sin Conexión los exámenes se indican en Estado de corrección **de malware** como examen sin **conexión requerido.**

![Microsoft Endpoint Manager que se requiere Microsoft Defender sin Conexión examen](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Configurar notificaciones

Microsoft Defender sin Conexión las notificaciones se configuran en la misma configuración de directiva que otras notificaciones AV de Microsoft Defender.

Para obtener más información acerca de las notificaciones en Windows Defender, vea el tema Configurar las notificaciones que [aparecen en los puntos de conexión.](configure-notifications-microsoft-defender-antivirus.md)

## <a name="run-a-scan"></a>Ejecutar un examen 

> [!IMPORTANT]
> Antes de usar Microsoft Defender sin Conexión, asegúrese de guardar los archivos y apagar los programas en ejecución. El Microsoft Defender sin Conexión de prueba tarda unos 15 minutos en ejecutarse. Reiniciará el punto de conexión cuando se complete el examen. El examen se realiza fuera del entorno Windows operativo habitual. La interfaz de usuario aparecerá diferente a un examen normal realizado por Windows Defender. Una vez completado el examen, el punto de conexión se reiniciará y Windows se cargará normalmente.

Puede ejecutar un examen Microsoft Defender sin Conexión con lo siguiente:

- PowerShell
- Instrumental de administración de Windows (WMI)
- La Seguridad de Windows aplicación



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Usar cmdlets de PowerShell para ejecutar un examen sin conexión

Use los cmdlets siguientes:

```PowerShell
Start-MpWDOScan
```

Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Usar Windows instrucción de administración de archivos (WMI) para ejecutar un examen sin conexión

Use la [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para ejecutar un examen sin conexión.

El siguiente fragmento de código de script WMI ejecutará inmediatamente un examen de Microsoft Defender sin Conexión, lo que hará que el extremo se reinicie, ejecute el examen sin conexión y, a continuación, reinicie y arranque en Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Vea lo siguiente para obtener más información:
- [Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Usar la aplicación Windows Defender seguridad para ejecutar un examen sin conexión

1. Abra la Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio de **Defender**.

2. Haga clic **en el icono protección contra &** virus (o en el icono de escudo de la barra de menús izquierda) y, a continuación, en la etiqueta **Examen** avanzado:
    
3. Seleccione **Microsoft Defender sin Conexión y haga** clic en Examinar **ahora**.

    > [!NOTE]
    > En Windows 10, versión 1607, el examen sin conexión podría ejecutarse desde Windows Configuración Actualizar & seguridad Windows Defender o desde el  >    >   cliente Windows Defender.


## <a name="review-scan-results"></a>Revisar los resultados del examen

Microsoft Defender sin Conexión resultados del examen se mostrarán en la sección Historial [de análisis de la Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md). 


## <a name="related-articles"></a>Artículos relacionados

- [Personalizar, iniciar y revisar los resultados de los exámenes y la corrección](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)