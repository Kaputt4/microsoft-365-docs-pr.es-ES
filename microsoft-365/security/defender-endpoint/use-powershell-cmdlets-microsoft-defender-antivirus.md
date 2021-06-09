---
title: Usar cmdlets de PowerShell para configurar y ejecutar MICROSOFT Defender AV
description: En Windows 10, puede usar cmdlets de PowerShell para ejecutar exámenes, actualizar inteligencia de seguridad y cambiar la configuración en Antivirus de Microsoft Defender.
keywords: scan, línea de comandos, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: d6fb8dc510e004fa88bf99583cc2cc33ae8c63bb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765304"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>Use cmdlets de PowerShell para configurar y administrar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Puede usar PowerShell para realizar varias funciones en Windows Defender. Al igual que el símbolo del sistema o la línea de comandos, PowerShell es un shell de línea de comandos basado en tareas y un lenguaje de scripting diseñado especialmente para la administración del sistema. Puede leer más sobre él en el centro [de PowerShell en MSDN](/previous-versions/msdn10/mt173057(v=msdn.10)).

Para obtener una lista de los cmdlets y sus funciones y parámetros disponibles, consulte el [tema Cmdlets de](/powershell/module/defender) Defender.

Los cmdlets de PowerShell son más útiles Windows entornos de servidor que no dependen de una interfaz gráfica de usuario (GUI) para configurar software.

> [!NOTE]
> Los cmdlets de PowerShell no deben usarse como reemplazo de una infraestructura [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))de administración de directivas de red completa, como [Microsoft Endpoint Configuration Manager,](/configmgr)consola de administración de directivas de grupo o plantillas [ADMX](https://www.microsoft.com/download/101445)de directiva de grupo Antivirus de Microsoft Defender .

Los cambios realizados con PowerShell afectarán a la configuración local en el punto de conexión donde se implementan o realizan los cambios. Esto significa que las implementaciones de directivas con directiva de grupo, Microsoft Endpoint Configuration Manager o Microsoft Intune pueden sobrescribir los cambios realizados con PowerShell.

Puede configurar [qué opciones se pueden invalidar localmente con invalidaciones de directiva local.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

PowerShell normalmente se instala en la carpeta `%SystemRoot%\system32\WindowsPowerShell` .

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>Usar Antivirus de Microsoft Defender cmdlets de PowerShell

1. En la barra Windows búsqueda, escriba **powershell**.
2. Seleccione **Windows PowerShell** de los resultados para abrir la interfaz.
3. Escriba el comando de PowerShell y los parámetros.

> [!NOTE]
> Es posible que necesite abrir PowerShell en modo de administrador. Haga clic con el botón secundario en el elemento del menú Inicio, haga clic **en Ejecutar como administrador** y haga clic en Sí **en** el símbolo del sistema de permisos.

Para abrir la ayuda en línea para cualquiera de los cmdlets, escriba lo siguiente:

```PowerShell
Get-Help <cmdlet> -Online
```

Omita el `-online` parámetro para obtener ayuda almacenada localmente en caché.

## <a name="related-topics"></a>Temas relacionados

- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Antivirus de Microsoft Defender Cmdlets](/powershell/module/defender)