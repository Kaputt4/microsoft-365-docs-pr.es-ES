---
title: Exportar, configurar y ver registros de registro de auditoría
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: En este artículo, aprenderá a exportar, configurar y ver registros de registro de auditoría de Microsoft 365.
ms.openlocfilehash: 4cea867b46d3bda7d3b3a8cd38f3d01938da8764
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906872"
---
# <a name="export-configure-and-view-audit-log-records"></a>Exportar, configurar y ver registros de registro de auditoría

Después de buscar en el registro de auditoría y descargar los resultados de la búsqueda en un archivo CSV, el archivo contiene una columna denominada **AuditData**, que contiene información adicional sobre cada evento. Los datos de esta columna tienen formato de objeto JSON, que contiene varias propiedades configuradas como pares *property:value* separados por comas. Puede usar la característica de transformación JSON en el Editor de power query en Excel para dividir cada propiedad del objeto JSON de la columna **AuditData** en varias columnas para que cada propiedad tenga su propia columna. Esto le permite ordenar y filtrar una o varias de estas propiedades, lo que puede ayudarle a localizar rápidamente los datos de auditoría específicos que está buscando.

## <a name="step-1-export-audit-log-search-results"></a>Paso 1: Exportar resultados de búsqueda de registros de auditoría

El primer paso es buscar en el registro de auditoría y, a continuación, exportar los resultados en un archivo de valores separados por comas (CSV) al equipo local.
  
1. Ejecute una [búsqueda de registro de](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) auditoría y revise los criterios de búsqueda si es necesario hasta que tenga los resultados deseados.

2. Haga **clic en Exportar resultados** y seleccione Descargar todos los **resultados.** 

   ![Haga clic en Descargar todos los resultados](../media/ExportAuditSearchResults.png)

   Esta opción para exportar todos los registros de auditoría de la búsqueda del registro de auditoría que se ejecutó en el paso 1 y descarga los datos sin procesar del registro de auditoría a un archivo CSV. 

   Se muestra un mensaje en la parte inferior de la ventana que le pide que abra o guarde el archivo CSV. 

3. Haga **clic en > Guardar como** y guarde el archivo CSV en el equipo local. Se tarda un tiempo en descargar muchos resultados de búsqueda. Esto suele ocurrir al buscar todas las actividades o un intervalo de fechas amplio. Se muestra un mensaje en la parte inferior de las ventanas cuando el archivo CSV ha terminado de descargarse.

   ![Mensaje que se muestra cuando el archivo CSV ha terminado de descargarse](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > Puede descargar un máximo de 50 000 entradas en un archivo CSV desde una única búsqueda de registros de auditoría. Si se descargan 50 000 entradas en el archivo CSV, probablemente puede suponer que existen más de 50 000 eventos que cumplen los criterios de búsqueda. Para exportar más de este límite, intente usar un intervalo de fechas para reducir el número de registros de auditoría. Puede que tenga que ejecutar varias búsquedas con intervalos de fecha de menor tamaño para exportar más de 50 000 entradas.

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>Paso 2: Dar formato al registro de auditoría exportado con el Editor de power query

El siguiente paso es usar la característica de transformación JSON en el Editor de power query en Excel para dividir cada propiedad del objeto JSON de la columna **AuditData** en su propia columna. A continuación, se filtran columnas para ver registros en función de los valores de propiedades específicas. Esto puede ayudarle a localizar rápidamente los datos de auditoría específicos que está buscando.

1. Abra un libro en blanco en Excel para Office 365, Excel 2019 o Excel 2016.

2. En la **ficha Datos,** en el grupo obtener & **transformar** datos, haga clic en **Desde texto/CSV**.

    ![En la pestaña Datos, haga clic en Desde texto/CSV](../media/JSONTransformOpenCSVFile.png)

3. Abra el archivo CSV que descargó en el paso 1.

4. En la ventana que se muestra, haga clic **en Transformar datos**.

   ![Haga clic en Transformar datos](../media/JSONOpenPowerQuery.png)

   El archivo CSV se abre en el **Editor de consultas**. Hay cuatro columnas: **CreationDate**, **UserIds**, **Operations** y **AuditData**. La **columna AuditData** es un objeto JSON que contiene varias propiedades. El siguiente paso es crear una columna para cada propiedad del objeto JSON.

5. Haga clic con el botón secundario en el título de la **columna AuditData,** haga clic **en Transformar** y, a continuación, haga clic en **JSON**. 

   ![Haga clic con el botón secundario en la columna AuditData, haga clic en Transformar y, a continuación, seleccione JSON](../media/JSONTransform.png)

6. En la esquina superior derecha de la **columna AuditData,** haga clic en el icono expandir.

   ![En la columna AuditData, haga clic en el icono expandir](../media/JSONTransformExpandIcon.png)

   Se muestra una lista parcial de las propiedades de los objetos JSON de la **columna AuditData.**

7. Haga **clic en Cargar más** para mostrar todas las propiedades de los objetos JSON en la columna **AuditData.**

   ![Haga clic en Cargar más para mostrar todas las propiedades del objeto JSON](../media/JSONTransformLoadJSONProperties.png)

   Puedes anular la selección de la casilla junto a cualquier propiedad que no quieras incluir. Eliminar columnas que no son útiles para la investigación es una buena manera de reducir la cantidad de datos que se muestran en el registro de auditoría. 

   > [!NOTE]
   > Las propiedades JSON mostradas en la captura de pantalla anterior (después de hacer clic en Cargar más **)** se basan en las propiedades encontradas en la columna **AuditData** de las primeras 1.000 filas del archivo CSV. Si hay diferentes propiedades JSON en los registros después de las primeras 1.000 filas, estas propiedades (y una columna correspondiente) no se incluirán cuando la columna **AuditData** se divida en varias columnas. Para evitar esto, considere la posibilidad de volver a ejecutar la búsqueda del registro de auditoría y restringir los criterios de búsqueda para que se devuelvan menos registros. Otra solución alternativa es filtrar los elementos de la columna **Operaciones** para reducir el número de filas (antes de realizar el paso 5 anterior) antes de transformar el objeto JSON en la **columna AuditData.**

   > [!TIP]
   > Para ver un atributo dentro de una lista como AuditData.AffectedItems, haga clic en el icono **Expandir** de la esquina superior derecha de la columna de la que desea extraer un atributo y, a continuación, seleccione Expandir a **Nueva fila**.  Desde allí será un registro y puede hacer clic en el icono **Expandir** en la esquina superior derecha de la columna, ver los atributos y seleccionar el que desea ver o extraer.

8. Realice una de las siguientes acciones para dar formato al título de las columnas que se agregan para cada propiedad JSON seleccionada.

    - Anule la selección de la casilla Usar **nombre de columna original como** prefijo para usar el nombre de la propiedad JSON como nombres de columna; por ejemplo, **RecordType** o **SourceFileName**.

    - Deje activada **la casilla Usar nombre de columna original como** prefijo para agregar el prefijo AuditData a los nombres de columna; por ejemplo, **AuditData.RecordType** o **AuditData.SourceFileName**.

9. Haga clic en **Aceptar**.

    La **columna AuditData** se divide en varias columnas. Cada nueva columna corresponde a una propiedad del objeto JSON AuditData. Cada fila de la columna contiene el valor de la propiedad. Si la propiedad no contiene un valor, se muestra el *valor* nulo. En Excel, las celdas con valores nulos están vacías.
  
10. En la **pestaña** Inicio, haga clic **en Cerrar & cargar** para cerrar el Editor de power query y abrir el archivo CSV transformado en un libro de Excel.

## <a name="use-powershell-to-search-and-export-audit-log-records"></a>Usar PowerShell para buscar y exportar registros de registro de auditoría

En lugar de usar la herramienta de búsqueda de registro de auditoría en el Centro de seguridad y cumplimiento de &, puede usar el cmdlet [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) en Exchange Online PowerShell para exportar los resultados de una búsqueda de registro de auditoría a un archivo CSV. A continuación, puede seguir el mismo procedimiento descrito en el paso 2 para dar formato al registro de auditoría mediante el editor de Power Query. Una ventaja de usar el cmdlet de PowerShell es que puede buscar eventos de un servicio específico mediante el *parámetro RecordType.* Estos son algunos ejemplos de uso de PowerShell para exportar registros de auditoría a un archivo CSV para que pueda usar el editor de Power Query para transformar el objeto JSON en la columna **AuditData** tal como se describe en el paso 2.

En este ejemplo, ejecute los siguientes comandos para devolver todos los registros relacionados con las operaciones de uso compartido de SharePoint.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

Los resultados de la búsqueda se exportan a un archivo CSV denominado *PowerShellAuditlog* que contiene cuatro columnas: CreationDate, UserIds, RecordType, AuditData).

También puede usar el nombre o el valor de enumeración para el tipo de registro como el valor del *parámetro RecordType.* Para obtener una lista de nombres de tipo de registro y sus valores de enumeración correspondientes, vea la *tabla AuditLogRecordType* en el esquema de la API de actividad de administración [de Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).

Solo puede incluir un solo valor para el *parámetro RecordType.* Para buscar registros de auditoría para otros tipos de registros, debe volver a ejecutar los dos comandos anteriores para especificar un tipo de registro diferente y anexar esos resultados al archivo CSV original. Por ejemplo, ejecutaría los dos comandos siguientes para agregar actividades de archivo de SharePoint desde el mismo intervalo de fechas al PowerShellAuditlog.csv archivo.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>Sugerencias para exportar y ver el registro de auditoría

Estos son algunos consejos y ejemplos de exportación y visualización del registro de auditoría antes y después de usar la característica de transformación JSON para dividir la columna **AuditData** en varias columnas.

- Filtre **la columna RecordType** para mostrar solo los registros de un servicio o área funcional específicos. Por ejemplo, para mostrar eventos relacionados con el uso compartido de SharePoint, seleccionaría **14** (el valor de enumeración de los registros desencadenados por las actividades de uso compartido de SharePoint). Para obtener una lista de los servicios que corresponden a los valores de enumeración que se muestran en la **columna RecordType,** vea Propiedades detalladas [en el registro de auditoría](detailed-properties-in-the-office-365-audit-log.md).

- Filtre la **columna** Operaciones para mostrar los registros de actividades específicas. Para obtener una lista de la mayoría de las operaciones que corresponden a una actividad que se puede buscar en la herramienta de búsqueda del registro de auditoría en el Centro de cumplimiento de seguridad &, vea la sección "Actividades auditadas" en Buscar el registro de auditoría en el Centro de seguridad y cumplimiento de [&](search-the-audit-log-in-security-and-compliance.md#audited-activities).