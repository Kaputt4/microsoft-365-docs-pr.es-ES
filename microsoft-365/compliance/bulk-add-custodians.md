---
title: Importar custodios a un caso de exhibición de documentos electrónicos (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Use la herramienta de importación masiva para agregar rápidamente varios custodios y sus orígenes de datos asociados a un caso en Microsoft Purview eDiscovery (Premium).
ms.openlocfilehash: a9274ebd01a034af82eec510b4e16534150e2216
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097808"
---
# <a name="import-custodians-to-an-ediscovery-premium-case"></a>Importar custodios a un caso de exhibición de documentos electrónicos (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Para los casos de exhibición de documentos electrónicos (Premium) de Microsoft Purview que implican a muchos custodios, puede importar varios custodios a la vez mediante un archivo CSV que contenga la información necesaria para agregarlos a un caso. La herramienta importar custodios también validará el archivo CSV antes de crear el trabajo de importación. Esto significa que puede corregir los errores en el archivo CSV en lugar de tener que esperar a que se complete el trabajo de importación antes de aprender que hay errores que impiden que un custodio se agregue al caso.

## <a name="before-you-import-custodians"></a>Antes de importar custodios

- Puede importar un máximo de 1000 custodios (filas) por archivo CSV.

- Puede asociar hasta 500 orígenes de datos para cada custodio.  

- Solo puede importar custodios que formen parte de la Azure Active Directory de su organización.

- Cada custodio debe tener una dirección de correo electrónico única.

- Para importar un buzón inactivo como custodio o para asociar un buzón inactivo a otro custodio, agregue un prefijo "." a la dirección de correo electrónico del buzón inactivo (por ejemplo, .sarad@contoso.onmmicrosoft.com).

## <a name="import-custodians"></a>Importar custodios

1. Abra el caso de eDiscovery (Premium) y seleccione la pestaña **Orígenes de datos**.

2. Haga clic en **Agregar origen de** >  **datosImportar custodios**.

3. En la página Obtener asistente para **plantillas** , haga clic en **Descargar la plantilla CSV** para descargar un archivo CSV de plantilla de custodio.

   ![Descargue una plantilla CSV desde la página desplegable Importar custodios.](../media/ImportCustodians1.png)

4. Agregue la información de custodia al archivo CSV y guárdela en el equipo local. Consulte la sección [Archivo CSV del custodio](#custodian-csv-file) para obtener información detallada sobre las propiedades necesarias en el archivo CSV.

5. Después de preparar el archivo CSV con la información del custodio, vuelva a la pestaña **Orígenes de datos** y haga clic en **Agregar origen** >  de **datosImportar custodios** de nuevo.

6. En la página Upload asistente para **archivos CSV**, haga clic en **Upload archivo csv** y, a continuación, cargue el archivo CSV que contiene la información del custodio.

   Después de cargar el archivo CSV, el asistente para importación valida el archivo CSV. Si existen errores de validación, el asistente muestra un banner de error con un vínculo para ver los errores.

   ![Banner de error de validación con vínculo a más información.](../media/ImportCustodians2.png)

   La información de error identifica la fila y la columna de la celda que contiene el error y sugiere una acción de corrección. Tiene que corregir cualquier error de validación y, a continuación, volver a cargar el archivo CSV fijo. El archivo CSV debe validarse correctamente para poder crear el trabajo de custodio de importación.

7. Una vez que el archivo CSV se haya validado correctamente, haga clic en **Siguiente** y, a continuación, haga clic en **Importar** para iniciar el trabajo de importación.

Después de iniciar el trabajo de importación, eDiscovery (Premium) hace lo siguiente:

- Crea un trabajo denominado **BulkAddCustodian** en la pestaña **Trabajos** del caso.

- Realiza la indexación avanzada de todos los orígenes de datos para cada custodio.

- Coloca todos los orígenes de datos custodios en suspensión (si la propiedad **Is OnHold** del archivo CSV está establecida en TRUE)

Una vez completado el trabajo del custodio de importación, los custodios y sus orígenes de datos asociados se agregan a la página **Orígenes de datos** del caso.

## <a name="custodian-csv-file"></a>Archivo CSV de custodio

Después de descargar la plantilla de custodio CSV, puede agregar custodios y sus orígenes de datos en cada fila. Asegúrese de no cambiar los nombres de columna de la fila de encabezado. Use el tipo de carga de trabajo y las columnas de ubicación de la carga de trabajo para asociar otros orígenes de datos a un custodio.

| Nombre de columna|Descripción|
|:------- |:------------------------------------------------------------|
|**Contacto del custodioEmail**     |Dirección de correo electrónico UPN del custodio. Por ejemplo, sarad@contoso.onmicrosoft.com.           |
|**Exchange habilitado** | Valor TRUE/FALSE para incluir o no el buzón del custodio.      |
|**OneDrive habilitado** | Valor TRUE/FALSE para incluir o no la cuenta de OneDrive para la Empresa del custodio. |
|**Is OnHold**        | Valor TRUE/FALSE para indicar si se van a poner en espera los orígenes de datos del custodio. <sup>1</sup>     |
|**Tipo Workload1**         |Valor de cadena que indica el tipo de origen de datos que se va a asociar al custodio. Los valores posibles son: <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- <sup>TeamsMailbox2</sup><br/>- YammerMailbox2.<sup></sup> Los valores anteriores de estos tipos de carga de trabajo distinguen mayúsculas de minúsculas. El archivo CSV contiene columnas para tres tipos de carga de trabajo y sus ubicaciones de carga de trabajo correspondientes. Puede agregar un total de 500 tipos de carga de trabajo y ubicaciones.|
|**Ubicación de Workload1**     | En función del tipo de carga de trabajo, esta sería la ubicación del origen de datos. Por ejemplo, la dirección de correo electrónico de un buzón de Exchange o la dirección URL de un sitio de SharePoint. |
|||

> [!NOTE]
> <sup>1</sup> Si coloca más de 1000 buzones o 100 sitios en espera en un caso, el sistema escalará automáticamente la suspensión de eDiscovery según sea necesario. Esto significa que el sistema agrega automáticamente ubicaciones de datos a varias directivas de suspensión, en lugar de agregarlas a una sola directiva. Sin embargo, todavía se aplica el límite de 10 000 directivas de suspensión de casos por organización. Para obtener más información sobre los límites de suspensión, vea [Límites en eDiscovery (Premium)](limits-ediscovery20.md#hold-limits).
<br>
> <sup>2</sup> Al incluir las cargas de trabajo TeamsMailbox y YammerMailbox en el archivo CSV, el sitio de grupo (TeamSite y YammerSite) se agrega automáticamente de forma predeterminada. No es necesario especificar TeamsSite y YammerSite por separado en el archivo CSV.

Este es un ejemplo de un archivo CSV con información del custodio:<br/><br/>

|Contacto del custodioEmail      | Exchange habilitado | OneDrive habilitado | Is OnHold | Tipo Workload1 | Ubicación de Workload1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@contoso.onmicrosoft.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@contoso.onmicrosoft.com | TRUE             | TRUE             | TRUE      | |  |
|.johnj@contoso.onmicrosoft.com|TRUE|TRUE|TRUE||
|sarad@contoso.onmicrosoft.com|TRUE|TRUE|TRUE|ExchangeMailbox|.saradavis@contoso.onmicrosoft.com
||||||

> [!NOTE]
> Como se explicó anteriormente, agregue un prefijo "." a la dirección UPN de un buzón inactivo para importar un buzón inactivo como custodio o para asociar un buzón inactivo a otro custodio.
