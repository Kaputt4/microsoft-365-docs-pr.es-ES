---
title: Uso de cmdlets de PowerShell para configurar y ejecutar el Antivirus de Microsoft Defender
description: En Windows 10 y Windows 11, puede usar cmdlets de PowerShell para ejecutar exámenes, actualizar la inteligencia de seguridad y cambiar la configuración en antivirus de Microsoft Defender.
keywords: scan, command line, mpcmdrun, defender
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2020
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: bb63bb3ec898e7ba6f7b957288e95da7ec49f17c
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585892"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Uso de cmdlets de PowerShell para configurar y administrar el Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede usar PowerShell para realizar varias funciones en Windows Defender. De forma similar al símbolo del sistema o la línea de comandos, PowerShell es un shell de línea de comandos basado en tareas y un lenguaje de scripting diseñado especialmente para la administración del sistema. Puede obtener más información al respecto en el [centro de PowerShell en MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).

Para obtener una lista de los cmdlets y sus funciones y parámetros disponibles, consulte el tema [Cmdlets del Antivirus de Defender](/powershell/module/defender) .

Los cmdlets de PowerShell son más útiles en entornos de Windows Server que no dependen de una interfaz gráfica de usuario (GUI) para configurar el software.

> [!NOTE]
> Los cmdlets de PowerShell no deben usarse como reemplazo de una infraestructura de administración de directivas de red completa, como [Microsoft Endpoint Configuration Manager](/configmgr), [directiva de grupo Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) o [Antivirus de Microsoft Defender directiva de grupo plantillas ADMX](https://www.microsoft.com/download/101445).

Los cambios realizados con PowerShell afectarán a la configuración local en el punto de conexión donde se implementan o realizan los cambios. Esto significa que las implementaciones de directiva con directiva de grupo, Configuration Manager de punto de conexión de Microsoft o Microsoft Intune pueden sobrescribir los cambios realizados con PowerShell.

Puede [configurar qué opciones se pueden invalidar localmente con invalidaciones de directiva local](configure-local-policy-overrides-microsoft-defender-antivirus.md).

PowerShell se instala normalmente en la carpeta `%SystemRoot%\system32\WindowsPowerShell`.

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Uso de cmdlets de PowerShell del Antivirus de Microsoft Defender

1. En la barra de búsqueda de Windows, escriba **powershell**.
2. Seleccione **Windows PowerShell** de los resultados para abrir la interfaz.
3. Escriba el comando de PowerShell y los parámetros.

> [!NOTE]
> Es posible que tenga que abrir PowerShell en modo de administrador. Haga clic con el botón derecho en el elemento en el menú Inicio, haga clic en **Ejecutar como administrador** y haga clic en **Sí** en el símbolo del sistema de permisos.

Para abrir la ayuda en línea para cualquiera de los cmdlets, escriba lo siguiente:

```PowerShell
Get-Help <cmdlet> -Online
```

Omita el `-online` parámetro para obtener ayuda almacenada localmente en caché.

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

- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus Cmdlets](/powershell/module/defender)
