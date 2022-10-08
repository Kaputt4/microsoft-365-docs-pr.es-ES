---
title: Microsoft Defender para punto de conexión herramienta de prueba de acceso controlado a carpetas (CFA)
description: Vea cómo Microsoft Defender Antivirus evalúa y contrarreste las amenazas y las aplicaciones malintencionadas.
keywords: Microsoft Defender para punto de conexión, acceso a carpetas protegidas bloqueadas, detectar archivos sospechosos, detectar aplicaciones sospechosas,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: a1b5548b47c9bd60764d988235999f76349e7db6
ms.sourcegitcommit: 55672e44de74209f2e23b4bd9ca74a2ee7e88cd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2022
ms.locfileid: "68319599"
---
# <a name="controlled-folder-access-cfa-demonstration-test-tool-block-script"></a>Herramienta de prueba de demostración de acceso controlado a carpetas (CFA) (script de bloque)

El acceso controlado a carpetas le ayuda a proteger datos valiosos de aplicaciones y amenazas malintencionadas, como ransomware. Todas las aplicaciones (cualquier archivo ejecutable, incluidos .exe, .scr, archivos .dll y otros) se evalúan mediante Microsoft Defender Antivirus, que luego determina si la aplicación es malintencionada o segura. Si se determina que la aplicación es malintencionada o sospechosa, no se permitirá realizar cambios en los archivos de ninguna carpeta protegida.

## <a name="scenario-requirements-and-setup"></a>Requisitos y configuración del escenario

- Windows 10 1709 compilación 16273
- Microsoft Defender Antivirus (modo activo)

## <a name="powershell-commands"></a>Comandos de PowerShell

```powershell
Set-MpPreference -EnableControlledFolderAccess <State>
```

Estados:
- Habilitado = Modo de bloque (1)
- AuditMode = Modo de auditoría (2)
- Disabled = Off (0)

### <a name="verify-configuration"></a>Comprobación de la configuración

```powershell
Get-MpPreference
```
## <a name="scenario"></a>Escenario

### <a name="setup"></a>Instalación

Descargue y ejecute este [script de instalación](https://demo.wd.microsoft.com/Content/CFA_SetupScript.zip). Antes de ejecutar el script, establezca la directiva de ejecución en Sin restricciones mediante este comando de PowerShell: Set-ExecutionPolicy Sin restricciones

En su lugar, puede realizar estos pasos manuales:
1. Activar CFA mediante el comando de PowerShell: Set-MpPreference -EnableControlledFolderAccess Enabled
2. Descarga de la [herramienta de prueba](https://demo.wd.microsoft.com/Content/CFAtool.exe) de CFA
3. Ejecución de los comandos de PowerShell anteriores


## <a name="scenario-use-the-cfa-test-tool-to-simulate-an-untrusted-process-writing-to-a-protected-folder"></a>Escenario: Uso de la herramienta de prueba de CFA para simular un proceso que no es de confianza al escribir en una carpeta protegida
1. Iniciar la herramienta de prueba de CFA
2. Seleccione la carpeta deseada y cree el archivo.
- Puede encontrar más información [aquí.](/windows/threat-protection/windows-defender-exploit-guard/evaluate-controlled-folder-access.md)

## <a name="clean-up"></a>Limpiar

Descargue y ejecute este [script de limpieza](https://demo.wd.microsoft.com/Content/ASR_CFA_CleanupScript.zip). En su lugar, puede realizar estos pasos manuales:

- Set-MpPreference -EnableControlledFolderAccess Deshabilitado

## <a name="see-also"></a>Vea también
[Acceso controlado a carpetas](/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
