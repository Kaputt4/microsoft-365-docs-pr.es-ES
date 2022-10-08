---
title: Microsoft Defender para punto de conexión demostraciones de acceso controlado a carpetas (CFA)
description: Muestra cómo control de acceso a carpetas protege datos valiosos de aplicaciones malintencionadas y amenazas, como ransomware.
keywords: Microsoft Defender para punto de conexión, Protección de acceso controlado a carpetas, Demostración de acceso controlado a carpetas
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
ms.openlocfilehash: e5a83446613b28b633472f5c6368d92d5e850049
ms.sourcegitcommit: 55672e44de74209f2e23b4bd9ca74a2ee7e88cd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2022
ms.locfileid: "68319669"
---
# <a name="controlled-folder-access-cfa-demonstrations-block-ransomware"></a>Demostraciones de acceso controlado a carpetas (CFA) (bloquear ransomware)

El acceso controlado a carpetas le ayuda a proteger datos valiosos de aplicaciones y amenazas malintencionadas, como ransomware. Todas las aplicaciones (cualquier archivo ejecutable, incluidos .exe, .scr, archivos .dll y otros) se evalúan mediante Microsoft Defender Antivirus, que luego determina si la aplicación es malintencionada o segura. Si se determina que la aplicación es malintencionada o sospechosa, no se permitirá realizar cambios en los archivos de ninguna carpeta protegida.

## <a name="scenario-requirements-and-setup"></a>Requisitos y configuración del escenario

- Windows 10 1709 compilación 16273
- Microsoft Defender Antivirus (modo activo)

## <a name="powershell-commands"></a>Comandos de PowerShell

- Set-MpPreference -EnableControlledFolderAccess (Estado)
- Set-MpPreference -ControlledFolderAccessProtectedFolders C:\demo\

Estados
- Habilitado = Modo de bloque (1)
- AuditMode = Modo de auditoría (2)
- Disabled = Off (0)

## <a name="verify-configuration"></a>Comprobación de la configuración

Get-MpPreference

## <a name="test-file"></a>Archivo de prueba
[Archivo de prueba de ransomware CFA](https://demo.wd.microsoft.com/Content/ransomware_testfile_unsigned.exe)

## <a name="scenarios"></a>Escenarios

### <a name="setup"></a>Instalación

Descargue y ejecute este [script de instalación](https://demo.wd.microsoft.com/Content/CFA_SetupScript.zip). Antes de ejecutar el script, establezca la directiva de ejecución en Sin restricciones mediante este comando de PowerShell: Set-ExecutionPolicy Sin restricciones

En su lugar, puede realizar estos pasos manuales:

1. Cree una carpeta en c: denominada demo, "c:\demo"
2. Guarde este [archivo limpio](https://demo.wd.microsoft.com/Content/testfile_safe.txt) en c:\demo (necesitamos algo para cifrar)
3. Ejecución de comandos de PowerShell anteriores

### <a name="scenario-1-cfa-blocks-ransomware-test-file"></a>Escenario 1: CFA bloquea el archivo de prueba de ransomware

1. Activar CFA mediante el comando de PowerShell: Set-MpPreference -EnableControlledFolderAccess Enabled
2. Agregue la carpeta de demostración a la lista de carpetas protegidas mediante el comando de PowerShell: Set-MpPreference -ControlledFolderAccessProtectedFolders C:\demo\
3. Descargar el [archivo de prueba](https://demo.wd.microsoft.com/Content/ransomware_testfile_unsigned.exe) de ransomware
4. Ejecutar el archivo de prueba ransomware *esto no es ransomware, lo sencillo intenta cifrar c:\demo

#### <a name="scenario-1-expected-results"></a>Resultados esperados del escenario 1

5 segundos después de ejecutar el archivo de prueba ransomware debería ver una notificación CFA bloqueado

### <a name="scenario-2-what-would-happen-without-cfa"></a>Escenario 2: Lo que sucedería sin CFA

1. Desactivar CFA mediante este comando de PowerShell: Set-MpPreference -EnableControlledFolderAccess Disabled
2. Ejecución del [archivo de prueba](https://demo.wd.microsoft.com/Content/ransomware_testfile_unsigned.exe) de ransomware

#### <a name="scenario-2-expected-results"></a>Resultados esperados del escenario 2

- Los archivos de c:\demo se cifrarán y debería recibir un mensaje de advertencia.
- Ejecute de nuevo el archivo de prueba ransomware para descifrar los archivos.

## <a name="clean-up"></a>Limpiar

Descargue y ejecute este [script de limpieza](https://demo.wd.microsoft.com/Content/ASR_CFA_CleanupScript.zip). En su lugar, puede realizar estos pasos manuales:

- Set-MpPreference -EnableControlledFolderAccess Deshabilitado
- El cifrado de limpieza c:\demo ejecuta el [archivo encrypt/decrypt](https://demo.wd.microsoft.com/Content/ransomware_cleanup_encrypt_decrypt.exe).

## <a name="see-also"></a>Vea también
[Acceso controlado a carpetas](/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard?ocid=wd-av-demo-cfa-bottom)