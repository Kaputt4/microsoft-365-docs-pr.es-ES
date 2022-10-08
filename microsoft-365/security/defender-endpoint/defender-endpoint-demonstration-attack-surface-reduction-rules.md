---
title: demostraciones de reglas de reducción de superficie expuesta a ataques Microsoft Defender para punto de conexión
description: Vea cómo las reglas de reducción de superficie expuesta a ataques bloquean varios tipos de amenazas conocidos.
keywords: Microsoft Defender para punto de conexión demostración, demostración de reglas de reducción de superficie expuesta a ataques, reglas de ASR, demostración
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
ms.openlocfilehash: 01acb6b31a6d67ca826c3a47a10b40ccb82e8092
ms.sourcegitcommit: 55672e44de74209f2e23b4bd9ca74a2ee7e88cd9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2022
ms.locfileid: "68319570"
---
# <a name="attack-surface-reduction-rules-demonstrations"></a>Demostraciones de reglas de reducción de superficie expuesta a ataques

Las reglas de reducción de superficie expuesta a ataques (ASR) tienen como destino comportamientos específicos que suelen usar el malware y las aplicaciones malintencionadas para infectar máquinas, como:

- Archivos ejecutables y scripts usados en aplicaciones de Office o correo web que intentan descargar o ejecutar archivos
- Scripts ofuscados o sospechosos
- Comportamientos que realizan las aplicaciones que no se incitan durante el trabajo diario normal

## <a name="scenario-requirements-and-setup"></a>Requisitos y configuración del escenario

- Windows 10 1709 compilación 16273
- Windows 10 compilación 1803 (reglas de 1803)
- Microsoft Defender AV
- Microsoft Office (se requiere para las reglas y el ejemplo de Office)
- [Descarga de scripts de PowerShell de ASR](https://demo.wd.microsoft.com/Content/WindowsDefender_ASR_scripts.zip)

## <a name="powershell-commands"></a>Comandos de PowerShell

```powershell
Add-MpPreference -AttackSurfaceReductionRules_Ids BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D4F940AB-401B-4EfC-AADC-AD5F3C50688A -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 3B576869-A4EC-4529-8536-B80A7769E899 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D3E037E1-3EB8-44C8-A917-57927947596D -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D1E49AAC-8F56-4280-B9BA-993A6D77406C -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids C1DB55AB-C21A-4637-BB3F-A12568109D35 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 01443614-CD74-433A-B99E-2ECDC07BFC25 -AttackSurfaceReductionRules_Actions Enabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 26190899-1602-49E8-8B27-EB1D0A1CE869 -AttackSurfaceReductionRules_Actions AuditMode
Add-MpPreference -AttackSurfaceReductionRules_Ids 7674BA52-37EB-4A4F-A9A1-F0F9A1619A2C -AttackSurfaceReductionRules_Actions AuditMode
```
### <a name="states"></a>Estados
- Habilitado = Modo de bloque (1)
- AuditMode = Modo de auditoría (2)
- Disabled = Off (0)

### <a name="verify-configuration"></a>Comprobación de la configuración

- Get-MpPreference

## <a name="test-files"></a>Archivos de prueba

Nota: algunos archivos de prueba tienen varias vulnerabilidades de seguridad incrustadas y desencadenarán varias reglas.

| Nombre de regla | GUID de regla | Versión de Windows |
|:---|:---|:---|
| Bloquear el contenido ejecutable del cliente de correo electrónico y el correo web | BE9BA2D9-53EA-4CDC-84E5-9B1EE46550 | 1709 |
| [Impedir que las aplicaciones de Office creen procesos secundarios](https://demo.wd.microsoft.com/Content/TestFile_OfficeChildProcess_D4F940AB-401B-4EFC-AADC-AD5F3C50688A.docm) | D4F940AB-401B-4EFC-AADC-AD5F3C50688A | 1709 |
| [Impedir que las aplicaciones de Office creen contenido ejecutable](https://demo.wd.microsoft.com/Content/TestFile_Block_Office_applications_from_creating_executable_content_3B576869-A4EC-4529-8536-B80A7769E899.docm) | 3B576869-A4EC-4529-8536-B80A7769E899 | 1709 |
| Impedir que las aplicaciones de Office se inserten en otros procesos | 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84 | 1709 |
| [Impedir que JavaScript y VBScript inicien ejecutables](https://demo.wd.microsoft.com/Content/TestFile_Impede_JavaScript_and_VBScript_to_launch_executables_D3E037E1-3EB8-44C8-A917-57927947596D.js) | D3E037E1-3EB8-44C8-A917-57927947596D | 1709 |
| Bloquear la ejecución de scripts potencialmente ofuscados | 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC | 1709 |
| [Bloquear importaciones de Win32 desde código de macro en Office](https://demo.wd.microsoft.com/Content/Block_Win32_imports_from_Macro_code_in_Office_92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B.docm) | 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDDC7B | 1709 |
|[{Block Process Creations origining from PSExec & wmi commands](https://demo.wd.microsoft.com/Content/TestFile_PsexecAndWMICreateProcess_D1E49AAC-8F56-4280-B9BA-993A6D77406C.vbs) | D1E49AAC-8F56-4280-B9BA-993A6D77406C | 1803 |
| [Bloquear la ejecución de archivos ejecutables que no son de confianza o no firmados dentro de medios USB extraíbles](https://demo.wd.microsoft.com/Content/UNSIGNED_ransomware_test_exe.exe) | B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4 | 1803 |
| Prevención agresiva de ransomware | C1DB55AB-C21A-4637-BB3F-A12568109D35 | 1803 |
| Impedir que los archivos ejecutables se ejecuten a menos que cumplan un criterio de prevalencia, edad o lista de confianza | 01443614-CD74-433A-B99E-2ECDC07BFC25 | 1803 |
| Impedir que Adobe Reader cree procesos secundarios | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c | 1803 |

## <a name="scenarios"></a>Escenarios

### <a name="setup"></a>Instalación

Descargue y ejecute este [script de instalación](https://demo.wd.microsoft.com/Content/ASR_SetupScript.zip). Antes de ejecutar el script, establezca la directiva de ejecución en Sin restricciones mediante este comando de PowerShell: Set-ExecutionPolicy Sin restricciones

En su lugar, puede realizar estos pasos manuales:

1. Cree una carpeta en c: denominada demo, "c:\demo"
2. Guarde este [archivo limpio](https://demo.wd.microsoft.com/Content/testfile_safe.txt) en c:\demo (necesitamos algo para cifrar)
3. Habilite todas las reglas mediante los comandos de PowerShell anteriores.

### <a name="scenario-1-asr-blocks-a-test-file-with-multiple-vulnerabilities"></a>Escenario 1: ASR bloquea un archivo de prueba con varias vulnerabilidades

1. Habilitar todas las reglas en modo de bloque mediante los comandos de PowerShell anteriores (puede copiar pegar todo)
2. Descargue y abra cualquiera de los archivos o documentos de prueba vinculados anteriormente, habilite la edición y el contenido si se le solicita.

#### <a name="scenario-1-expected-results"></a>Resultados esperados del escenario 1

Debería ver inmediatamente una notificación "Acción bloqueada".

### <a name="scenario-2-asr-rule-blocks-the-test-file-with-the-corresponding-vulnerability"></a>Escenario 2: la regla ASR bloquea el archivo de prueba con la vulnerabilidad correspondiente

1. Configure la regla que desea probar con el comando de PowerShell anterior.
2. Ejemplo: Add-MpPreference -AttackSurfaceReductionRules_Ids D4F940AB-401B-4EfC-AADC-AD5F3C50688A -AttackSurfaceReductionRules_Actions Habilitado
3. Descargue y abra el archivo o documento de prueba de la regla que desea probar vinculada anteriormente, habilite la edición y el contenido si se le solicita
4. Ejemplo: [Impedir que las aplicaciones de Office creen procesos secundarios](https://demo.wd.microsoft.com/Content/ransomware_testfile_doc.docm) D4F940AB-401B-4EFC-AADC-AD5F3C50688A

#### <a name="scenario-2-expected-results"></a>Resultados esperados del escenario 2

Debería ver inmediatamente una notificación "Acción bloqueada".

### <a name="scenario-3-1803-asr-rule-blocks-unsigned-usb-content-from-executing"></a>Escenario 3 (1803): la regla ASR impide que se ejecute contenido USB sin signo

1. Configure la regla para la protección usb (B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4).

```powershell
Add-MpPreference -AttackSurfaceReductionRules_Ids B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4 -AttackSurfaceReductionRules_Actions Enabled
```

3. Descargue el archivo y colóquelo en un stick USB y ejecútelo [bloquear la ejecución de archivos ejecutables que no son de confianza o no firmados dentro de medios USB extraíbles](https://demo.wd.microsoft.com/Content/UNSIGNED_ransomware_test_exe.exe).

#### <a name="scenario-3-expected-results"></a>Resultados esperados del escenario 3

Debería ver inmediatamente una notificación "Acción bloqueada".

### <a name="scenario-4-what-would-happen-without-asr"></a>Escenario 4: ¿Qué sucedería sin ASR?

1. Desactive todas las reglas de ASR mediante los comandos de PowerShell que aparecen a continuación en la sección de limpieza.
2. Descargue cualquier archivo o documento de prueba vinculado anteriormente, habilite la edición y el contenido si se le solicita

#### <a name="scenario-4-expected-results"></a>Resultados esperados del escenario 4

- Los archivos de c:\demo se cifrarán y debería recibir un mensaje de advertencia.
- Vuelva a ejecutar el archivo de prueba para descifrar los archivos.

## <a name="clean-up"></a>Limpiar

Descarga y ejecución [de este script de limpieza](https://demo.wd.microsoft.com/Content/ASR_CFA_CleanupScript.zip)

Como alternativa, puede realizar estos pasos manuales:

```powershell
Add-MpPreference -AttackSurfaceReductionRules_Ids BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D4F940AB-401B-4EfC-AADC-AD5F3C50688A -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 3B576869-A4EC-4529-8536-B80A7769E899 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D3E037E1-3EB8-44C8-A917-57927947596D -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids D1E49AAC-8F56-4280-B9BA-993A6D77406C -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids B2B3F03D-6A65-4F7B-A9C7-1C7EF74A9BA4 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids C1DB55AB-C21A-4637-BB3F-A12568109D35 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 01443614-CD74-433A-B99E-2ECDC07BFC25 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 26190899-1602-49E8-8B27-EB1D0A1CE869 -AttackSurfaceReductionRules_Actions Disabled
Add-MpPreference -AttackSurfaceReductionRules_Ids 7674BA52-37EB-4A4F-A9A1-F0F9A1619A2C -AttackSurfaceReductionRules_Actions Disabled
```

El cifrado de limpieza c:\demo ejecuta el [archivo encrypt/decrypt](https://demo.wd.microsoft.com/Content/ransomware_cleanup_encrypt_decrypt.exe).

## <a name="see-also"></a>Vea también

[Guía de implementación de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-deployment.md)

[Referencia de reglas de reducción de superficie expuesta a ataques](attack-surface-reduction-rules-reference.md)

[Microsoft Defender para punto de conexión: escenarios de demostración](defender-endpoint-demonstrations.md)
