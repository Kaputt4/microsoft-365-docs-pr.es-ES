---
title: Analizador de rendimiento para Antivirus de Microsoft Defender
description: Describe el procedimiento para ajustar el rendimiento de Antivirus de Microsoft Defender.
keywords: tune, performance, microsoft defender for endpoint, defender antivirus
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6350b91a700000a5d8fecec90462d53721d2f1ca
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61936022"
---
# <a name="performance-analyzer-for-microsoft-defender-antivirus"></a>Analizador de rendimiento para Antivirus de Microsoft Defender

**Se aplica a**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**¿Qué es Antivirus de Microsoft Defender de rendimiento?**

En algunos casos, es posible que deba ajustar el rendimiento de Antivirus de Microsoft Defender a medida que examina archivos y carpetas específicos. El analizador de rendimiento es una herramienta de línea de comandos de PowerShell que ayuda a determinar qué archivos, extensiones de archivo y procesos pueden estar causando problemas de rendimiento en puntos de conexión individuales. Esta información se puede usar para evaluar mejor los problemas de rendimiento y aplicar acciones de corrección.

Algunas opciones para analizar incluyen:

- Archivos principales que afectan al tiempo de examen
- Procesos principales que afectan al tiempo de examen
- Extensiones de archivo principales que afectan al tiempo de examen
- Combinaciones: por ejemplo, los archivos principales por extensión, los exámenes superiores por archivo, los exámenes superiores por archivo por proceso

## <a name="running-performance-analyzer"></a>Ejecución del analizador de rendimiento

El proceso de alto nivel para ejecutar el analizador de rendimiento implica los siguientes pasos:

1. Ejecute el analizador de rendimiento para recopilar una grabación de rendimiento de Antivirus de Microsoft Defender eventos en el punto de conexión.

   > [!NOTE]
   > El rendimiento de Antivirus de Microsoft Defender eventos del tipo **Microsoft-Antimalware-Engine** se registran a través del analizador de rendimiento.

2. Analice los resultados del examen con diferentes informes de grabación.

## <a name="using-performance-analyzer"></a>Uso del analizador de rendimiento

Para iniciar la grabación de eventos del sistema, abra PowerShell en modo administrativo y siga estos pasos:

1. Ejecute el siguiente comando para iniciar la grabación:

   `New-MpPerformanceRecording -RecordTo <recording.etl>`
 
    donde parámetro especifica la ubicación de ruta de acceso completa en la que se guarda `-RecordTo` el archivo de seguimiento. Para obtener más información sobre los [cmdlets, vea Antivirus de Microsoft Defender cmdlets](/powershell/module/defender).

2. Si se cree que hay procesos o servicios que afectan al rendimiento, reproduzca la situación llevando a cabo las tareas pertinentes.

3. Presione **ENTRAR** para detener y guardar la grabación, o **Ctrl+C para** cancelar la grabación.

4. Analice los resultados con el parámetro del analizador de `Get-MpPerformanceReport` rendimiento. Por ejemplo, al ejecutar el comando, se proporciona al usuario una lista de los diez primeros exámenes para los 3 archivos principales que afectan `Get-MpPerformanceReport -Path <recording.etl> -TopFiles 3 -TopScansPerFile 10` al rendimiento. 

Para obtener más información sobre parámetros y opciones de línea de comandos, vea [New-MpPerformanceRecording](#new-mpperformancerecording) y [Get-MpPerformanceReport](#get-mpperformancereport).

> [!NOTE]
> Al ejecutar una grabación, si recibe el error "No se puede iniciar la grabación de rendimiento porque la grabadora de rendimiento de Windows ya está grabando", ejecute el siguiente comando para detener el seguimiento existente con el nuevo comando: **wpr -cancel -instancename MSFT_MpPerformanceRecording**

### <a name="performance-tuning-data-and-information"></a>Información y datos de ajuste de rendimiento

En función de la consulta, el usuario podrá ver datos para los recuentos de examen, la duración (total/min/average/max/median), la ruta de acceso, el proceso y el motivo del examen. La imagen siguiente muestra el resultado de ejemplo de una consulta sencilla de los 10 archivos principales para el impacto del examen. 

:::image type="content" source="images/example-output.png" alt-text="Resultado de ejemplo para una consulta básica de TopFiles":::

### <a name="additional-functionality-exporting-and-converting-to-csv-and-json"></a>Funcionalidad adicional: exportar y convertir a CSV y JSON

Los resultados del analizador de rendimiento también se pueden exportar y convertir a un archivo CSV o JSON.
Para ver ejemplos que describen el proceso de "exportación" y "conversión" a través de códigos de ejemplo, vea a continuación.

#### <a name="for-csv"></a>Para CSV

- **Para exportar**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | Export-CSV -Path:.\Repro-Install-Scans.csv -Encoding:UTF8 -NoTypeInformation`

- **Para convertir**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:100). TopScans | ConvertTo-Csv -NoTypeInformation`

#### <a name="for-json"></a>Para JSON

- **Para convertir**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | ConvertTo-Json -Depth:1`

### <a name="requirements"></a>Requisitos
Antivirus de Microsoft Defender analizador de rendimiento tiene los siguientes requisitos previos:

- Versiones Windows compatibles: Windows 10, Windows 11 y Windows Server 2016 versiones posteriores
- Versión de la plataforma: 4.18.2108.7+
- Versión de PowerShell: PowerShell versión 5.1, PowerShell ISE

## <a name="powershell-reference"></a>Referencia de PowerShell
Hay dos cmdlets de PowerShell nuevos que se usan para ajustar el rendimiento de Antivirus de Microsoft Defender: 

- [New-MpPerformanceRecording](#new-mpperformancerecording)
- [Get-MpPerformanceReport](#get-mpperformancereport)


### <a name="new-mpperformancerecording"></a>New-MpPerformanceRecording

En la siguiente sección se describe la referencia del nuevo cmdlet de PowerShell New-MpPerformanceRecording. Este cmdlet recopila una grabación de rendimiento de Antivirus de Microsoft Defender exámenes.

#### <a name="syntax-new-mpperformancerecording"></a>Sintaxis: New-MpPerformanceRecording

```powershell
New-MpPerformanceRecording -RecordTo <String >
```

#### <a name="description-new-mpperformancerecording"></a>Descripción: New-MpPerformanceRecording
El `New-MpPerformanceRecording` cmdlet recopila una grabación de rendimiento de Antivirus de Microsoft Defender exámenes. Estas grabaciones de rendimiento contienen eventos de proceso del kernel de Microsoft-Antimalware-Engine y NT y se pueden analizar después de la recopilación mediante el cmdlet [Get-MpPerformanceReport.](#get-mpperformancereport)

Este cmdlet proporciona información sobre los archivos problemáticos que podrían causar una degradación `New-MpPerformanceRecording` en el rendimiento de Antivirus de Microsoft Defender. Esta herramienta se proporciona "AS IS" y no está diseñada para proporcionar sugerencias sobre exclusiones. Las exclusiones pueden reducir el nivel de protección en los puntos de conexión. Las exclusiones, si las hay, deben definirse con precaución.

Para obtener más información sobre el analizador de rendimiento, consulte [Documentos del analizador de](/windows-hardware/test/wpt/windows-performance-analyzer) rendimiento.

> [!IMPORTANT]
> Este cmdlet requiere privilegios de administrador elevados.

**Versiones del sistema operativo compatibles**

Windows versión 10 y posterior.

> [!NOTE]
> Esta característica está disponible a partir de la versión 4.18.2108.X de la plataforma y versiones posteriores.

#### <a name="examples-new-mpperformancerecording"></a>Ejemplos: New-MpPerformanceRecording

##### <a name="example-1-collect-a-performance-recording-and-save-it"></a>Ejemplo 1: Recopilar una grabación de rendimiento y guardarla

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

El comando anterior recopila una grabación de rendimiento y la guarda en la ruta de acceso especificada: **.\Defender-scans.etl**.

#### <a name="parameters-new-mpperformancerecording"></a>Parámetros: New-MpPerformanceRecording

##### <a name="-recordto"></a>-RecordTo
Especifica la ubicación en la que se guardará la grabación de rendimiento de Antimalware de Microsoft Defender.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False
```

### <a name="get-mpperformancereport"></a>Get-MpPerformanceReport

En la siguiente sección se describe el Get-MpPerformanceReport cmdlet de PowerShell. Analiza e informa sobre el Antivirus de Microsoft Defender de rendimiento (MDAV).

#### <a name="syntax-get-mpperformancereport"></a>Sintaxis: Get-MpPerformanceReport

```powershell
Get-MpPerformanceReport    [-Path] <String>
[-TopScans <Int32>]
[-TopFiles  <Int32>
    [-TopScansPerFile <Int32>]
    [-TopProcessesPerFile  <Int32>  
        [-TopScansPerProcessPerFile <Int32>]
    ]
] 
[-TopExtensions  <Int32>
    [-TopScansPerExtension <Int32>]
    [-TopProcessesPerExtension <Int32>
        [-TopScansPerProcessPerExtension <Int32>]
        ]
    [-TopFilesPerExtension  <Int32>
        [-TopScansPerFilePerExtension <Int32>]
        ]
    ] 
]
[-TopProcesses  <Int32>
    [-TopScansPerProcess <Int32>]
    [-TopExtensionsPerProcess <Int32>
        [-TopScansPerExtensionPerProcess <Int32>]
    ]
]
[-TopFilesPerProcess  <Int32>
    [-TopScansPerFilePerProcess <Int32>]
]
[-MinDuration <String>]
```

#### <a name="description-get-mpperformancereport"></a>Descripción: Get-MpPerformanceReport
El cmdlet analiza una grabación de rendimiento de Antivirus de Microsoft Defender recopilada anteriormente `Get-MpPerformanceReport` ([New-MpPerformanceRecording](#new-mpperformancerecording)) e informa de las rutas de acceso de archivo, las extensiones de archivo y los procesos que causan el mayor impacto en Antivirus de Microsoft Defender exámenes.

El analizador de rendimiento proporciona información sobre los archivos problemáticos que podrían causar una degradación en el rendimiento de Antivirus de Microsoft Defender. Esta herramienta se proporciona "AS IS" y no está diseñada para proporcionar sugerencias sobre exclusiones. Las exclusiones pueden reducir el nivel de protección en los puntos de conexión. Las exclusiones, si las hay, deben definirse con precaución.

Para obtener más información sobre el analizador de rendimiento, consulte [Documentos del analizador de](/windows-hardware/test/wpt/windows-performance-analyzer) rendimiento.

**Versiones del sistema operativo compatibles**

Windows versión 10 y posterior.

> [!NOTE]
> Esta característica está disponible a partir de la versión 4.18.2108.X de la plataforma y versiones posteriores.

#### <a name="examples-get-mpperformancereport"></a>Ejemplos: Get-MpPerformanceReport

##### <a name="example-1-single-query"></a>Ejemplo 1: Consulta única 

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:20
```

##### <a name="example-2-multiple-queries"></a>Ejemplo 2: Varias consultas 

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10
```

##### <a name="example-3-nested-queries"></a>Ejemplo 3: Consultas anidadas 

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopProcesses:10 -TopExtensionsPerProcess:3 -TopScansPerExtensionPerProcess:3
```

##### <a name="example-4-using--minduration-parameter"></a>Ejemplo 4: Uso del parámetro -MinDuration

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopScans:100 -MinDuration:100ms
```

#### <a name="parameters-get-mpperformancereport"></a>Parámetros: Get-MpPerformanceReport

##### <a name="-minduration"></a>-MinDuration
Especifica la duración mínima de cualquier examen o duración total del examen de archivos, extensiones y procesos incluidos en el informe; acepta valores como  **0,1234567sec**, **0,1234ms**, **0,1us** o un TimeSpan válido.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False 
Accept wildcard characters: False
```

##### <a name="-path"></a>-Path
Especifica las rutas de acceso a una o más ubicaciones.

```yaml
Type: String
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

### <a name="-topextensions"></a>-TopExtensions 
Especifica cuántas extensiones superiores se va a generar, ordenadas por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topextensionsperprocess"></a>-TopExtensionsPerProcess 
Especifica cuántas extensiones superiores se va a generar para cada proceso superior, ordenadas por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfiles"></a>-TopFiles
Solicita un informe de archivos superiores y especifica cuántos archivos principales se va a generar, ordenados por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperextension"></a>-TopFilesPerExtension 
Especifica cuántos archivos principales se va a generar para cada extensión superior, ordenada por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topfilesperprocess"></a>-TopFilesPerProcess
Especifica cuántos archivos principales se va a generar para cada proceso superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocesses"></a>-TopProcesses
Solicita un informe de procesos superiores y especifica cuántos de los procesos superiores se va a generar, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topprocessesperextension"></a>-TopProcessesPerExtension 
Especifica cuántos procesos principales se va a generar para cada extensión superior, ordenada por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topprocessesperfile"></a>-TopProcessesPerFile
Especifica cuántos procesos principales se va a generar para cada archivo superior, ordenados por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscans"></a>-TopScans
Solicita un informe de exámenes superiores y especifica cuántos exámenes superiores se va a obtener, ordenados por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperextension"></a>-TopScansPerExtension
Especifica el número de exámenes superiores que se va a generar para cada extensión superior, ordenada por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperextensionperprocess"></a>-TopScansPerExtensionPerProcess 
Especifica el número de exámenes superiores que se va a generar para cada extensión superior para cada proceso superior, ordenado por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperfile"></a>-TopScansPerFile
Especifica el número de exámenes superiores que se va a generar para cada archivo superior, ordenado por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperfileperextension"></a>-TopScansPerFilePerExtension 
Especifica el número de exámenes principales que se va a generar para cada archivo superior de cada extensión superior, ordenado por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperfileperprocess"></a>-TopScansPerFilePerProcess 
Especifica el número de exámenes principales para cada archivo superior de cada proceso superior, ordenado por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```


### <a name="-topscansperprocess"></a>-TopScansPerProcess 
Especifica el número de exámenes superiores que se va a generar para cada proceso superior en el informe Procesos principales, ordenado por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperextension"></a>-TopScansPerProcessPerExtension
Especifica cuántos exámenes superiores de salida para cada proceso superior de cada extensión superior, ordenados por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="-topscansperprocessperfile"></a>-TopScansPerProcessPerFile
Especifica el número de exámenes principales para cada proceso superior de cada archivo superior, ordenado por "Duración".


```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```
