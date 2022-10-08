---
title: Uso de cmdlets de PowerShell para configurar y ejecutar Microsoft Defender Antivirus
description: En Windows 10 y Windows 11, puede usar cmdlets de PowerShell para ejecutar exámenes, actualizar inteligencia de seguridad y cambiar la configuración en Microsoft Defender Antivirus.
keywords: scan, command line, mpcmdrun, defender
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/06/2022
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
audience: ITPro
ms.topic: how-to
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 217f7e06fa7ded119750611197147bb1610902f6
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227028"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Uso de cmdlets de PowerShell para configurar y administrar Microsoft Defender Antivirus

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede usar PowerShell para realizar varias funciones en Windows Defender. De forma similar al símbolo del sistema o la línea de comandos, PowerShell es un shell de línea de comandos basado en tareas y un lenguaje de scripting diseñado especialmente para la administración del sistema. Puede obtener más información al respecto en la [documentación de PowerShell](/powershell/scripting/overview).

Para obtener una lista de los cmdlets y sus funciones y parámetros disponibles, consulte el tema [Cmdlets del Antivirus de Defender](/powershell/module/defender) .

Los cmdlets de PowerShell son más útiles en entornos de Windows Server que no dependen de una interfaz gráfica de usuario (GUI) para configurar el software.

> [!NOTE]
> Los cmdlets de PowerShell no deben usarse como reemplazo de una infraestructura de administración de directivas de red completa, como [Microsoft Endpoint Configuration Manager](/configmgr), [directiva de grupo Management Console](use-group-policy-microsoft-defender-antivirus.md) o [Microsoft Defender Antivirus directiva de grupo Plantillas de ADMX](https://www.microsoft.com/download/101445).

Los cambios realizados con PowerShell afectarán a la configuración local en el punto de conexión donde se implementan o realizan los cambios. Esto significa que las implementaciones de directiva con directiva de grupo, Configuration Manager de punto de conexión de Microsoft o Microsoft Intune pueden sobrescribir los cambios realizados con PowerShell.

Puede [configurar qué opciones se pueden invalidar localmente con invalidaciones de directiva local](configure-local-policy-overrides-microsoft-defender-antivirus.md).

PowerShell se instala normalmente en la carpeta `%SystemRoot%\system32\WindowsPowerShell`.

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Uso de cmdlets de PowerShell Microsoft Defender Antivirus

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
- [Cmdlets de antivirus de Microsoft Defender](/powershell/module/defender)
