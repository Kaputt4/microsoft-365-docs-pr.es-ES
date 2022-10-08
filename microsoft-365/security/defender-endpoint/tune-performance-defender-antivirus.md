---
title: Analizador de rendimiento para Microsoft Defender Antivirus
description: Describe el procedimiento para ajustar el rendimiento de Microsoft Defender Antivirus.
keywords: tune, performance, microsoft defender for endpoint, defender antivirus
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.date: 08/13/2022
manager: dansimp
ms.collection:
- m365-security
- tier2
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 4d7dbcd7199d7318243a5c1733303d24b494c5c8
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232592"
---
# <a name="performance-analyzer-for-microsoft-defender-antivirus"></a>Analizador de rendimiento para Microsoft Defender Antivirus

**Se aplica a**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**

- Windows

## <a name="what-is-microsoft-defender-antivirus-performance-analyzer"></a>¿Qué es Microsoft Defender analizador de rendimiento de Antivirus?

En algunos casos, es posible que tenga que ajustar el rendimiento de Microsoft Defender Antivirus a medida que examina archivos y carpetas específicos. El analizador de rendimiento es una herramienta de línea de comandos de PowerShell que ayuda a determinar qué archivos, extensiones de archivo y procesos podrían estar causando problemas de rendimiento en puntos de conexión individuales. Esta información se puede usar para evaluar mejor los problemas de rendimiento y aplicar acciones de corrección.

Algunas opciones para analizar incluyen:

- Rutas de acceso principales que afectan al tiempo de examen
- Archivos principales que afectan al tiempo de examen
- Principales procesos que afectan al tiempo de examen
- Extensiones de archivo principales que afectan al tiempo de examen
- Combinaciones: por ejemplo:
  - archivos principales por extensión
  - rutas de acceso superiores por extensión
  - procesos principales por ruta de acceso
  - exámenes superiores por archivo
  - exámenes superiores por archivo por proceso
  
## <a name="running-performance-analyzer"></a>Ejecución del analizador de rendimiento

El proceso de alto nivel para ejecutar el analizador de rendimiento implica los pasos siguientes:

1. Ejecute el analizador de rendimiento para recopilar una grabación de rendimiento de Microsoft Defender eventos antivirus en el punto de conexión.

   > [!NOTE]
   > El rendimiento de Microsoft Defender eventos antivirus del tipo **Microsoft-Antimalware-Engine** se registra a través del analizador de rendimiento.

2. Analice los resultados del examen mediante diferentes informes de grabación.

## <a name="using-performance-analyzer"></a>Uso del analizador de rendimiento

Para iniciar la grabación de eventos del sistema, abra PowerShell en modo administrativo y realice los pasos siguientes:

1. Ejecute el siguiente comando para iniciar la grabación:

   `New-MpPerformanceRecording -RecordTo <recording.etl>`

    donde `-RecordTo` el parámetro especifica la ubicación de ruta de acceso completa en la que se guarda el archivo de seguimiento. Para obtener más información sobre los [cmdlets, consulte cmdlets Microsoft Defender Antivirus](/powershell/module/defender).

2. Si hay procesos o servicios que se cree que afectan al rendimiento, reproduzca la situación realizando las tareas pertinentes.

3. Presione **ENTRAR** para detener y guardar la grabación o **Ctrl+C** para cancelar la grabación.

4. Analice los resultados con el parámetro del analizador de `Get-MpPerformanceReport`rendimiento. Por ejemplo, al ejecutar el comando `Get-MpPerformanceReport -Path <recording.etl> -TopFiles 3 -TopScansPerFile 10`, se proporciona al usuario una lista de los diez primeros exámenes de los tres primeros archivos que afectan al rendimiento.

Para obtener más información sobre los parámetros y las opciones de la línea de comandos, vea [New-MpPerformanceRecording](#new-mpperformancerecording) y [Get-MpPerformanceReport](#get-mpperformancereport).

> [!NOTE]
> Al ejecutar una grabación, si aparece el error "No se puede iniciar la grabación de rendimiento porque Windows Performance Recorder ya está grabando", ejecute el siguiente comando para detener el seguimiento existente con el nuevo comando: **wpr -cancel -instancename MSFT_MpPerformanceRecording**

## <a name="performance-tuning-data-and-information"></a>Datos e información de optimización del rendimiento

En función de la consulta, el usuario podrá ver los datos de los recuentos de exámenes, la duración (total/min/average/max/median), la ruta de acceso, el proceso y **el motivo del examen**. En la imagen siguiente se muestra la salida de ejemplo de una consulta simple de los 10 archivos principales para el impacto en el examen.

:::image type="content" source="images/example-output.png" alt-text="Salida de ejemplo para una consulta TopFiles básica" lightbox="images/example-output.png":::

## <a name="additional-functionality-exporting-and-converting-to-csv-and-json"></a>Funcionalidad adicional: exportación y conversión a CSV y JSON

Los resultados del analizador de rendimiento también se pueden exportar y convertir a un archivo CSV o JSON.
Para obtener ejemplos que describen el proceso de "exportación" y "conversión" a través de códigos de ejemplo, vea a continuación.

A partir de la versión 4.18.2206.X de Defender, los usuarios podrán ver la información de omitir motivos en la columna "SkipReason". Los valores posibles son:

1. No omitido
1. Optimización (normalmente debido a motivos de rendimiento)
1. Usuario omitido (normalmente debido a exclusiones del conjunto de usuarios)

### <a name="for-csv"></a>Para CSV

- **Para exportar**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | Export-CSV -Path:.\Repro-Install-Scans.csv -Encoding:UTF8 -NoTypeInformation`

- **Para convertir**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:100). TopScans | ConvertTo-Csv -NoTypeInformation`

### <a name="for-json"></a>Para JSON

- **Para convertir**: `(Get-MpPerformanceReport -Path:.\Repro-Install.etl -Topscans:1000). TopScans | ConvertTo-Json -Depth:1`

Para garantizar una salida legible para la máquina para la exportación con otros sistemas de procesamiento de datos, se recomienda usar el parámetro -Raw para Get-MpPerformanceReport. Consulte a continuación para obtener más información.

## <a name="requirements"></a>Requisitos

Microsoft Defender Analizador de rendimiento de Antivirus tiene los siguientes requisitos previos:

- Versiones compatibles de Windows: Windows 10, Windows 11 y Windows Server 2016 y versiones posteriores
- Versión de la plataforma: 4.18.2108.7+
- Versión de PowerShell: PowerShell versión 5.1, PowerShell ISE, PowerShell remoto (4.18.2201.10+), PowerShell 7.x (4.18.2201.10+)

## <a name="powershell-reference"></a>Referencia de PowerShell

Hay dos nuevos cmdlets de PowerShell que se usan para optimizar el rendimiento de Microsoft Defender Antivirus:

- [New-MpPerformanceRecording](#new-mpperformancerecording)
- [Get-MpPerformanceReport](#get-mpperformancereport)

### <a name="new-mpperformancerecording"></a>New-MpPerformanceRecording

En la sección siguiente se describe la referencia del nuevo cmdlet de PowerShell New-MpPerformanceRecording. Este cmdlet recopila una grabación de rendimiento de los exámenes de Microsoft Defender Antivirus.

#### <a name="syntax-new-mpperformancerecording"></a>Sintaxis: New-MpPerformanceRecording

```powershell
New-MpPerformanceRecording -RecordTo <String >
```

#### <a name="description-new-mpperformancerecording"></a>Descripción: New-MpPerformanceRecording

El `New-MpPerformanceRecording` cmdlet recopila una grabación de rendimiento de los exámenes de Microsoft Defender Antivirus. Estas grabaciones de rendimiento contienen eventos de proceso de kernel de Microsoft-Antimalware-Engine y NT y se pueden analizar después de la recopilación mediante el cmdlet [Get-MpPerformanceReport](#get-mpperformancereport) .

Este `New-MpPerformanceRecording` cmdlet proporciona información sobre los archivos problemáticos que podrían provocar una degradación en el rendimiento de Microsoft Defender Antivirus. Esta herramienta se proporciona "AS IS" y no está pensada para proporcionar sugerencias sobre exclusiones. Las exclusiones pueden reducir el nivel de protección en los puntos de conexión. Las exclusiones, si las hubiera, deben definirse con precaución.

Para obtener más información sobre el analizador de rendimiento, consulte [Analizador de rendimiento](/windows-hardware/test/wpt/windows-performance-analyzer) documentos.

> [!IMPORTANT]
> Este cmdlet requiere privilegios de administrador con privilegios elevados.

**Versiones admitidas del sistema operativo**:

Windows versión 10 y versiones posteriores.

> [!NOTE]
> Esta característica está disponible a partir de la versión 4.18.2108.X de la plataforma y versiones posteriores.

#### <a name="examples-new-mpperformancerecording"></a>Ejemplos: New-MpPerformanceRecording

##### <a name="example-1-collect-a-performance-recording-and-save-it"></a>Ejemplo 1: Recopilar una grabación de rendimiento y guardarla

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl
```

El comando anterior recopila una grabación de rendimiento y la guarda en la ruta de acceso especificada: **.\Defender-scans.etl**.

##### <a name="example-2-collect-a-performance-recording-for-remote-powershell-session"></a>Ejemplo 2: Recopilación de una grabación de rendimiento para una sesión remota de PowerShell

```powershell
$s = New-PSSession -ComputerName Server02 -Credential Domain01\User01
New-MpPerformanceRecording -RecordTo C:\LocalPathOnServer02\trace.etl -Session $s
```

El comando anterior recopila una grabación de rendimiento en Server02 (según lo especificado por el argumento $s del parámetro Session) y lo guarda en la ruta de acceso especificada: **C:\LocalPathOnServer02\trace.etl** en Server02.

##### <a name="example-3-collect-a-performance-recording-in-non-interactive-mode"></a>Ejemplo 3: Recopilación de una grabación de rendimiento en modo no interactivo

```powershell
New-MpPerformanceRecording -RecordTo:.\Defender-scans.etl -Seconds 60
```

El comando anterior recopila una grabación de rendimiento durante los segundos especificados por el parámetro -Seconds. Esto se recomienda para los usuarios que realizan colecciones por lotes que no requieren ninguna interacción o solicitud.

#### <a name="parameters-new-mpperformancerecording"></a>Parámetros: New-MpPerformanceRecording

##### <a name="-recordto"></a>-RecordTo

Especifica la ubicación en la que se va a guardar el Microsoft Defender grabación de rendimiento de Antimalware.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-session"></a>-Sesión

Especifica el objeto PSSession en el que se va a crear y guardar la grabación de rendimiento Microsoft Defender Antivirus. Cuando se usa este parámetro, el parámetro RecordTo hace referencia a la ruta de acceso local en el equipo remoto. Disponible con la versión 4.18.2201.10 de la plataforma Defender.

```yaml
Type: PSSession[]
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-seconds"></a>-Segundos

Especifica la duración de la grabación de rendimiento en segundos. Esto se recomienda para los usuarios que realizan colecciones por lotes que no requieren ninguna interacción o solicitud.

```yaml
Type: Int32
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### <a name="get-mpperformancereport"></a>Get-MpPerformanceReport

En la sección siguiente se describe el cmdlet de PowerShell Get-MpPerformanceReport. Analiza e informa sobre Microsoft Defender grabación de rendimiento del antivirus.

#### <a name="syntax-get-mpperformancereport"></a>Sintaxis: Get-MpPerformanceReport

```powershell
Get-MpPerformanceReport    [-Path] <String>
    [-TopScans [<Int32>]]
    [-TopPaths [<Int32>] [-TopPathsDepth [<Int32>]]]
            [-TopScansPerPath [<Int32>]]
            [-TopFilesPerPath [<Int32>]
                    [-TopScansPerFilePerPath [<Int32>]]
                    ]
            [-TopExtensionsPerPath [<Int32>]
                    [-TopScansPerExtensionPerPath [<Int32>]]
                    ]
            [-TopProcessesPerPath [<Int32>]
                    [-TopScansPerProcessPerPath [<Int32>]]
                    ]
            ]
    [-TopFiles [<Int32>]
            [-TopScansPerFile [<Int32>]]
            [-TopProcessesPerFile [<Int32>]
                    [-TopScansPerProcessPerFile [<Int32>]]
                    ]
            ]
    [-TopExtensions [<Int32>]
            [-TopScansPerExtension [<Int32>]
            [-TopPathsPerExtension [<Int32>] [-TopPathsDepth [<Int32>]]
                    [-TopScansPerPathPerExtension [<Int32>]]
                    ]
            [-TopProcessesPerExtension [<Int32>]
                    [-TopScansPerProcessPerExtension [<Int32>]]
                    ]
            [-TopFilesPerExtension [<Int32>]
                    [-TopScansPerFilePerExtension [<Int32>]]
                    ]
            ]
    [-TopProcesses [<Int32>]
            [-TopScansPerProcess [<Int32>]]
            [-TopExtensionsPerProcess [<Int32>]
                    [-TopScansPerExtensionPerProcess [<Int32>]]
                    ]
            [-TopPathsPerProcess [<Int32>] [-TopPathsDepth [<Int32>]]
                    [-TopScansPerPathPerProcess [<Int32>]]
                    ]
            [-TopFilesPerProcess [<Int32>]
                    [-TopScansPerFilePerProcess [<Int32>]]
                    ]
            ]
    [-MinDuration <String>]
    [-Raw]

```

#### <a name="description-get-mpperformancereport"></a>Descripción: Get-MpPerformanceReport

El `Get-MpPerformanceReport` cmdlet analiza una grabación de rendimiento de antivirus Microsoft Defender previamente recopilada ([New-MpPerformanceRecording](#new-mpperformancerecording)) e informa de las rutas de acceso de archivo, las extensiones de archivo y los procesos que provocan el mayor impacto en los exámenes Microsoft Defender Antivirus.

El analizador de rendimiento proporciona información sobre los archivos problemáticos que podrían provocar una degradación en el rendimiento de Microsoft Defender Antivirus. Esta herramienta se proporciona "AS IS" y no está pensada para proporcionar sugerencias sobre exclusiones. Las exclusiones pueden reducir el nivel de protección en los puntos de conexión. Las exclusiones, si las hubiera, deben definirse con precaución.

Para obtener más información sobre el analizador de rendimiento, consulte [Analizador de rendimiento](/windows-hardware/test/wpt/windows-performance-analyzer) documentos.

**Versiones admitidas del sistema operativo**:

Windows versión 10 y versiones posteriores.

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

##### <a name="example-5-using--raw-parameter"></a>Ejemplo 5: Uso del parámetro -Raw

```powershell
Get-MpPerformanceReport -Path:.\Defender-scans.etl -TopFiles:10 -TopExtensions:10 -TopProcesses:10 -TopScans:10 -Raw | ConvertTo-Json
```

El uso \-de Raw en el comando anterior especifica que la salida debe ser legible y fácilmente convertible a formatos de serialización como JSON.

#### <a name="parameters-get-mpperformancereport"></a>Parámetros: Get-MpPerformanceReport

##### <a name="-toppaths"></a>-TopPaths

Solicita un informe de rutas de acceso superiores y especifica cuántas rutas de acceso superiores se van a generar, ordenadas por "Duración". Agrega los exámenes en función de su ruta de acceso y directorio. El usuario puede especificar cuántos directorios se deben mostrar en cada nivel y la profundidad de la selección.

- Tipo: Int32
- Posición: con nombre
- Valor predeterminado: Ninguno
- Aceptar entrada de canalización: False
- Aceptar caracteres comodín: False

##### <a name="-toppathsdepth"></a>-TopPathsDepth

Especifica la profundidad recursiva que se usará para agrupar y mostrar los resultados de la ruta de acceso agregada. Por ejemplo, "C:\" corresponde a una profundidad de 1, "C:\Users\Foo" corresponde a una profundidad de 3.

Esta marca puede acompañar todas las demás opciones de Ruta de acceso superior. Si falta, se supone un valor predeterminado de 3. El valor no puede ser 0.

- Tipo: Int32
- Posición: con nombre
- Valor predeterminado: 3
- Aceptar entrada de canalización: False
- Aceptar caracteres comodín: False

| flag | Definición |
|:---|:---|  
|  -**TopScansPerPath** | Especifica cómo se pueden realizar exámenes superiores para especificar para cada ruta de acceso superior. |
|  -**TopFilesPerPath** | Especifica cómo se pueden especificar los archivos superiores para cada ruta de acceso superior. |
|  -**TopScansPerFilePerPath** | Especifica cuántos exámenes superiores se van a generar para cada archivo superior de cada ruta de acceso superior, ordenados por "Duración" |
|  -**TopExtensionsPerPath** | Especifica cuántas extensiones superiores se van a generar para cada ruta de acceso superior. |
|  -**TopScansPerExtensionPerPath** | Especifica cuántos exámenes superiores se van a generar para cada extensión superior para cada ruta de acceso superior. |
|  -**TopProcessesPerPath** | Especifica cuántos procesos principales se van a generar para cada ruta de acceso superior |
|  -**TopScansPerProcessPerPath** | Especifica cuántos exámenes superiores se van a generar para cada proceso superior para cada ruta de acceso superior |
|  -**TopPathsPerExtension** | Especifica cuántas rutas de acceso superiores se van a generar para cada extensión superior |
|  -**TopScansPerPathPerExtension** | Especifica cuántos exámenes superiores se van a generar para cada ruta de acceso superior para cada extensión superior. |
|  -**TopPathsPerProcess** | Especifica cuántas rutas de acceso superiores se van a generar para cada proceso superior |
|  -**TopScansPerPathPerProcess** | Especifica cuántos exámenes superiores se van a generar para cada ruta de acceso superior para cada proceso superior. |

##### <a name="-minduration"></a>-MinDuration

Especifica la duración mínima de cualquier examen o duración total del examen de archivos, extensiones y procesos incluidos en el informe; acepta valores como  **0,1234567sec**, **0,1234 ms**, **0,1us** o un TimeSpan válido.

```yaml
Type: String
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-path"></a>-Camino

Especifica las rutas de acceso a una o varias ubicaciones.

```yaml
Type: String
Position: 0
Default value: None
Accept pipeline input: True
Accept wildcard characters: False
```

##### <a name="-raw"></a>-Crudo

Especifica que la salida de la grabación de rendimiento debe ser legible y fácilmente convertible a formatos de serialización como JSON (por ejemplo, mediante el comando Convertir a JSON). Esto se recomienda para los usuarios interesados en el procesamiento por lotes con otros sistemas de procesamiento de datos.

```yaml
Type: <SwitchParameter>
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topextensions"></a>-TopExtensions

Especifica cuántas extensiones superiores se van a generar, ordenadas por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topextensionsperprocess"></a>-TopExtensionsPerProcess

Especifica cuántas extensiones superiores se van a generar para cada proceso superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topfiles"></a>-TopFiles

Solicita un informe de archivos superiores y especifica cuántos archivos principales se van a generar, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topfilesperextension"></a>-TopFilesPerExtension

Especifica cuántos archivos superiores se van a generar para cada extensión superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topfilesperprocess"></a>-TopFilesPerProcess

Especifica cuántos archivos principales se van a generar para cada proceso superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topprocesses"></a>-TopProcesses

Solicita un informe de procesos superiores y especifica cuántos de los procesos principales se van a generar, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topprocessesperextension"></a>-TopProcessesPerExtension

Especifica cuántos procesos superiores se van a generar para cada extensión superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topprocessesperfile"></a>-TopProcessesPerFile

Especifica cuántos procesos superiores se van a generar para cada archivo superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscans"></a>-TopScans

Solicita un informe de exámenes superiores y especifica cuántos exámenes superiores se van a generar, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperextension"></a>-TopScansPerExtension

Especifica cuántos exámenes superiores se van a generar para cada extensión superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperextensionperprocess"></a>-TopScansPerExtensionPerProcess

Especifica cuántos exámenes superiores se van a generar para cada extensión superior de cada proceso superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperfile"></a>-TopScansPerFile

Especifica cuántos exámenes superiores se van a generar para cada archivo superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperfileperextension"></a>-TopScansPerFilePerExtension

Especifica cuántos exámenes superiores se van a generar para cada archivo superior de cada extensión superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperfileperprocess"></a>-TopScansPerFilePerProcess

Especifica cuántos exámenes superiores de salida hay para cada archivo superior de cada proceso superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperprocess"></a>-TopScansPerProcess

Especifica cuántos exámenes superiores se van a generar para cada proceso superior en el informe Procesos principales, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperprocessperextension"></a>-TopScansPerProcessPerExtension

Especifica cuántos exámenes superiores de salida hay para cada proceso superior de cada extensión superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

##### <a name="-topscansperprocessperfile"></a>-TopScansPerProcessPerFile

Especifica cuántos exámenes superiores de salida hay para cada proceso superior de cada archivo superior, ordenados por "Duración".

```yaml
Type: Int32
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## <a name="additional-resources"></a>Recursos adicionales

Si busca información relacionada con antivirus para otras plataformas, consulte:

- [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
- [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
- [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
- [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
- [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
- [Configuración de características de Defender para punto de conexión en Android](android-configure.md)-  [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
