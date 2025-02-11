---
title: Buscar ransomware con la búsqueda avanzada de amenazas
description: Use la búsqueda avanzada para localizar dispositivos potencialmente afectados por ransomware.
keywords: búsqueda avanzada, ransomware, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-ransomware
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: 0decdcf0302b9cd3ea7db3aeda53a1d15d49c61d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68640750"
---
# <a name="hunt-for-ransomware"></a>Buscar ransomware

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Ransomware ha evolucionado rápidamente de ser malware simple mercancía que afecta a usuarios de equipos individuales a una amenaza empresarial que está afectando gravemente a los sectores e instituciones gubernamentales. Aunque [Microsoft 365 Defender](microsoft-365-defender.md) proporciona muchas funcionalidades que detectan y bloquean el ransomware y las actividades de intrusiones asociadas, realizar comprobaciones proactivas para detectar signos de peligro puede ayudar a mantener la red protegida.

> [Leer sobre ransomware operado por humanos](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

Con [la búsqueda avanzada](advanced-hunting-overview.md) en Microsoft 365 Defender, puede crear consultas que busquen artefactos individuales asociados a la actividad de ransomware. También puede ejecutar consultas más sofisticadas que puedan buscar signos de actividad y sopesar esos signos para encontrar dispositivos que requieran atención inmediata.

## <a name="signs-of-ransomware-activity"></a>Signos de actividad de ransomware
Los investigadores de seguridad de Microsoft han observado varios artefactos comunes pero sutiles en muchas campañas de ransomware lanzadas por intrusos sofisticados. Estos signos implican principalmente el uso de herramientas del sistema para prepararse para el cifrado, evitar la detección y evidencia forense clara.

| Actividad de ransomware | Herramientas comunes | Intent |
|--|--|--|
| Detener procesos | _taskkill.exe_, _net stop_ | Asegúrese de que las distintas aplicaciones no bloquean los archivos destinados al cifrado. |
| Desactivar servicios | _sc.exe_ | - Asegúrese de que los archivos destinados al cifrado no están bloqueados por varias aplicaciones.<br>- Impedir que el software de seguridad interrumpa el cifrado y otra actividad ransomware.<br>- Impedir que el software de copia de seguridad cree copias recuperables.  |
| Eliminación de registros y archivos | _cipher.exe_, _wevtutil__,fsutil.exe_ | Quite las pruebas forenses. |
| Eliminar instantáneas  | _vsadmin.exe_, _wmic.exe_ | Quite las instantáneas de unidad que se pueden usar para recuperar archivos cifrados. |
| Eliminación y detención de copias de seguridad | _wbadmin.exe_ | Elimine las copias de seguridad existentes y detenga las tareas de copia de seguridad programadas, lo que impide la recuperación después del cifrado. |
| Modificación de la configuración de arranque | _bcdedit.exe_ | Desactive las advertencias y las reparaciones automáticas después de errores de arranque que puedan deberse al proceso de cifrado. |
| Desactivar las herramientas de recuperación | _schtasks.exe_, _regedit.exe_, | Desactive La restauración del sistema y otras opciones de recuperación del sistema. |

## <a name="check-for-individual-signs-of-ransomware-activity"></a>Comprobar si hay signos individuales de actividad de ransomware
Muchas actividades que constituyen un comportamiento ransomware, incluidas las actividades descritas en la sección anterior, pueden ser benignas. Al usar las siguientes consultas para localizar ransomware, ejecute más de una consulta para comprobar si los mismos dispositivos muestran varios signos de posible actividad de ransomware.

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a>Detener varios procesos mediante _taskkill.exe_
Esta consulta comprueba si hay intentos de detener al menos 10 procesos independientes mediante la utilidad _taskkill.exe_ . [Ejecutar consulta](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a>Detención de procesos mediante _net stop_
Esta consulta comprueba si hay intentos de detener al menos 10 procesos independientes mediante el comando _net stop_ . [Ejecutar consulta](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a>Eliminación de datos en varias unidades mediante _cipher.exe_
Esta consulta comprueba si hay intentos de eliminar datos en varias unidades mediante _cipher.exe_. Esta actividad se realiza normalmente mediante ransomware para evitar la recuperación de datos después del cifrado. [Ejecutar consulta](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for cipher.exe deleting data from multiple drives
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine),
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1
```

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a>Eliminación de pruebas forenses de registros de eventos mediante _wevtutil_
Esta consulta comprueba si hay intentos de borrar al menos 10 entradas de registro de registros de eventos mediante _wevtutil_. [Ejecutar consulta](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a>Desactivación de servicios mediante _sc.exe_
Esta consulta comprueba si hay intentos de desactivar al menos 10 servicios existentes mediante _sc.exe_. [Ejecutar consulta](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a>Desactivar la restauración del sistema
Esta consulta identifica los intentos de detener la restauración del sistema e impedir que el sistema cree puntos de restauración, que se pueden usar para recuperar datos cifrados por ransomware. [Ejecutar consulta](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
//Pivoting for rundll32  
| where InitiatingProcessFileName =~ 'rundll32.exe'   
//Looking for empty command line   
and InitiatingProcessCommandLine !contains " " and InitiatingProcessCommandLine != ""  
//Looking for schtasks.exe as the created process  
and FileName in~ ('schtasks.exe')  
//Disabling system restore   
and ProcessCommandLine has 'Change' and ProcessCommandLine has 'SystemRestore' 
and ProcessCommandLine has 'disable'
```

### <a name="backup-deletion"></a>Eliminación de copia de seguridad
Esta consulta identifica el uso de _wmic.exe_ para eliminar instantáneas de instantáneas antes del cifrado. [Ejecutar consulta](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a>Comprobar si hay varios signos de actividad de ransomware
En lugar de ejecutar varias consultas por separado, también puede usar una consulta completa que compruebe si hay varios signos de actividad de ransomware para identificar los dispositivos afectados. La siguiente consulta consolidada:
- Busca signos relativamente concretos y sutiles de actividad ransomware
- Sopesa la presencia de estos signos
- Identifica los dispositivos con una mayor probabilidad de ser destinos de ransomware 

Cuando se ejecuta, esta consulta consolidada devuelve una lista de dispositivos que han mostrado varios signos de ataque. También se muestra el recuento de cada tipo de actividad de ransomware. Para ejecutar esta consulta consolidada, cópiela directamente en el [editor de consultas de búsqueda avanzada](https://security.microsoft.com/advanced-hunting). 

```kusto
// Find attempts to stop processes using taskkill.exe
let taskKill = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10;
// Find attempts to stop processes using net stop
let netStop = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10;
// Look for cipher.exe deleting data from multiple drives
let cipher = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine), 
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1;
// Look for use of wevtutil to clear multiple logs
let wevtutilClear = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10;
// Look for sc.exe disabling services
let scDisable = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10;
// Main query for counting and aggregating evidence
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "vssadmin.exe" and ProcessCommandLine has_any("list shadows", "delete shadows")
or FileName =~ "fsutil.exe" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal"
or ProcessCommandLine has("bcdedit") and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures")
or ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup")
or (ProcessCommandLine has "wevtutil" and ProcessCommandLine has "cl") 
or (ProcessCommandLine has "wmic" and ProcessCommandLine has "shadowcopy delete")
or (ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled")
| extend Bcdedit = iff(ProcessCommandLine has "bcdedit" and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures"), 1, 0)
| extend ShadowCopyDelete = iff (ProcessCommandLine has "shadowcopy delete", 1, 0)
| extend VssAdminShadows = iff(ProcessCommandLine has "vssadmin" and ProcessCommandLine has_any("list shadows", "delete shadows"), 1, 0)
| extend Wbadmin = iff(ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup"), 1,0)
| extend Fsutil = iff(ProcessCommandLine has "fsutil" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal", 1, 0)
| summarize FirstActivity = min(Timestamp), ReportId = any(ReportId), Commands = make_set(ProcessCommandLine) by DeviceId, Fsutil, Wbadmin, ShadowCopyDelete, Bcdedit, VssAdminShadows, bin(Timestamp, 6h)
// Joining extra evidence
| join kind=leftouter (wevtutilClear) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (cipher) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (netStop) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (taskKill) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (scDisable) on $left.DeviceId == $right.DeviceId
| extend WevtutilUse = iff(LogClearCount > 10, 1, 0)
| extend CipherUse = iff(CipherCount > 1, 1, 0)
| extend NetStopUse = iff(netStopCount > 10, 1, 0)
| extend TaskkillUse = iff(taskKillCount > 10, 1, 0)
| extend ScDisableUse = iff(ScDisableCount > 10, 1, 0)
// Adding up all evidence
| mv-expand CommandList = NetStopList, TaskKillList, ClearedLogList, CipherList, Commands, ScDisableList
// Format results
| summarize BcdEdit = iff(make_set(Bcdedit) contains "1" , 1, 0), NetStop10PlusCommands = iff(make_set(NetStopUse) contains "1", 1, 0), Wevtutil10PlusLogsCleared = iff(make_set(WevtutilUse) contains "1", 1, 0),
CipherMultipleDrives = iff(make_set(CipherUse) contains "1", 1, 0), Fsutil = iff(make_set(Fsutil) contains "1", 1, 0), ShadowCopyDelete = iff(make_set(ShadowCopyDelete) contains "1", 1, 0),
Wbadmin = iff(make_set(Wbadmin) contains "1", 1, 0), TaskKill10PlusCommand = iff(make_set(TaskkillUse) contains "1", 1, 0), VssAdminShadow = iff(make_set(VssAdminShadows) contains "1", 1, 0), 
ScDisable = iff(make_set(ScDisableUse) contains "1", 1, 0), TotalEvidenceCount = count(CommandList), EvidenceList = make_set(Commands), StartofBehavior = min(FirstActivity) by DeviceId, bin(Timestamp, 1d)
| extend UniqueEvidenceCount = BcdEdit + NetStop10PlusCommands + Wevtutil10PlusLogsCleared + CipherMultipleDrives + Wbadmin + Fsutil + TaskKill10PlusCommand + VssAdminShadow + ScDisable + ShadowCopyDelete
| where UniqueEvidenceCount > 2
```
### <a name="understand-and-tweak-the-query-results"></a>Descripción y ajuste de los resultados de la consulta
La consulta consolidada devuelve los resultados siguientes:

- **DeviceId**: identifica el dispositivo afectado. 
- **TimeStamp**: la primera vez que se observó cualquier signo de actividad de ransomware en el dispositivo
- **Signos específicos de actividad**: el recuento de cada signo que se muestra en varias columnas, como _BcdEdit_ o _FsUtil_
- **TotalEvidenceCount**: número de signos observados
- **UniqueEvidenceCount**: número de tipos de signos observados

:::image type="content" source="../../media/advanced-hunting-ransomware-query.png" alt-text="Ejemplo de una consulta consolidada para una actividad de ransomware en el portal de Microsoft 365 Defender" lightbox="../../media/advanced-hunting-ransomware-query.png":::

*Resultados de la consulta que muestran los dispositivos afectados y recuentos de varios signos de actividad de ransomware*

De forma predeterminada, el resultado de la consulta enumera solo los dispositivos que tienen más de dos tipos de actividad de ransomware. Para ver todos los dispositivos con cualquier signo de actividad de ransomware, modifique el siguiente `where` operador y establezca el número en cero (0). Para ver menos dispositivos, establezca un número mayor. 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)

## <a name="more-ransomware-resources"></a>Más recursos de ransomware

Información clave de Microsoft:

- [La creciente amenaza de ransomware](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/), entrada de blog de Microsoft On the Issues del 20 de julio de 2021
- [Ransomware operado por humanos](/security/compass/human-operated-ransomware)
- [Protéjase contra ransomware y extorsión de manera rápida](/security/compass/protect-against-ransomware)
- [Informe de Microsoft Digital Defense 2021](https://www.microsoft.com/security/business/microsoft-digital-defense-report) (vea las páginas 10-19)
- [Ransomware: informe de análisis de amenazas generalizado y continuo](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview) en el portal de Microsoft 365 Defender

Microsoft 365:

- [Implementar la protección contra ransomware para el inquilino de Microsoft 365](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Maximizar la resistencia de ransomware con Azure y Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Recuperarse de un ataque de ransomware](/microsoft-365/security/office-365-security/recover-from-ransomware)
- [Protección de malware y ransomware](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [Proteger su PC Windows de ransomware](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [Control de ransomware en SharePoint Online](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- [Informes de análisis de amenazas para ransomware](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag) en el portal de Microsoft 365 Defender

Microsoft Azure:

- [Defensas de Azure para los ataques de ransomware](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Maximizar la resistencia de ransomware con Azure y Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Plan de restauración y copia de seguridad para la protección contra ransomware](/security/compass/backup-plan-to-protect-against-ransomware)
- [Ayuda para la protección contra ransomware con Microsoft Azure Backup](https://www.youtube.com/watch?v=VhLOr2_1MCg) (vídeo de 26 minutos)
- [Recuperación de una identidad en peligro](/azure/security/fundamentals/recover-from-identity-compromise)
- [Detección avanzada de ataques de varias fases en Microsoft Sentinel](/azure/sentinel/fusion#ransomware)
- [Detección de difusión para ransomware en Microsoft Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Defender for Cloud Apps:

-  [Crear directivas de detección de anomalías en Defender para aplicaciones en la nube](/cloud-app-security/anomaly-detection-policy)

Entradas de blog del equipo de Seguridad de Microsoft:

- [Tres pasos para prevenir y recuperarse del ransomware (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [Una guía para combatir el ransomware operado por personas: Parte 1 (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/)

  Pasos clave sobre cómo el equipo de detección y respuesta de Microsoft (DART) lleva a cabo investigaciones de incidentes de ransomware.

- [Una guía para combatir el ransomware operado por personas: Parte 2 (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/)

  Recomendaciones y procedimientos recomendados.

- [Camino a la resistencia al comprender los riesgos de ciberseguridad: Parte 4 — Navegación por las amenazas actuales (mayo de 2021)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  Consulte la sección **Ransomware**.

- [Ataques de ransomware operados por humanos: Un desastre evitable (marzo de 2020)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  Incluye análisis de cadenas de ataques, de ataques reales.

- [Respuesta frente a ransomware: ¿pagar o no pagar? (diciembre de 2019)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro responde ante ataques de ransomware con transparencia (diciembre de 2019)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
