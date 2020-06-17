---
title: Adición de custodios en masa a un caso de eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Use la herramienta de adición en masa para agregar rápidamente varios custodios y sus orígenes de datos asociados a un caso en eDiscovery avanzado.
ms.openlocfilehash: 921d4a1616d97f2adde7e40baa5c73f607c849b6
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741643"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case"></a>Adición de custodios en masa a un caso de eDiscovery avanzado

Para los casos de eDiscovery avanzados que implican un gran número de custodios, puede importar varios custodios a la vez mediante un archivo CSV que contenga toda la información necesaria para agregarlos a un caso.

## <a name="bulk-add-custodians"></a>Custodios de adición en masa

1. Escriba mayúsculas y navegue a la pestaña **orígenes** .

2. Haga clic en **importar custodios**

3. En la página de flotante, haga clic en **descargar una plantilla en blanco** para descargar un archivo de plantilla de custodio de CSV.

4. Agregue la información de la Private al archivo CSV y guárdelo en el equipo local. Consulte la sección siguiente para obtener información sobre las propiedades del archivo CSV.

5. En la pestaña **orígenes** , haga clic en **importar custodios** nuevamente. 
6. En la página de flotante, haga clic en **examinar** y en cargar el archivo CSV.

   Una vez cargado el archivo CSV, se crea un trabajo de BulkAddCustodian y se muestra en la pestaña **trabajos** . El trabajo valida los custodios y sus orígenes de datos correspondientes y, a continuación, los agrega a la ficha **custodios** de la página **orígenes** del caso.

## <a name="custodian-csv-file"></a>Archivo CSV de custodio

Una vez que haya descargado la plantilla CSV, puede Agregar custodios y su origen de datos en cada fila. Asegúrese de no cambiar los nombres de columna en la fila de encabezado.

| Nombre de columna|Descripción|
|:------- |:------------------------------------------------------------|
|**Asociada de custodios**     | Correo electrónico UPN de custodio. Ejemplo: sarad@onmicrosoft.contoso.com           |
|**Exchange habilitado** | Valor TRUE/FALSE si se va a agregar el buzón de custodio.      |
|**OneDrive habilitado** | Valor TRUE/FALSE si se va a agregar la cuenta de OneDrive para la empresa de custodio. |
|**Es pamantente**        | Valor verdadero/falso si desea poner la custodia en espera.       |
|**Tipo Workload1**         | Valor de cadena que indica el tipo de origen de datos que se va a asociar con el custodio. <br />Los valores posibles son: <br />ExchangeMailbox, SharePointSite, TeamsMailbox, TeamsSite, YammerMailbox, YammerSite |
|**Ubicación de Workload1**     | Según el tipo de carga de trabajo, sería la ubicación de los datos de la carga de trabajo (por ejemplo, la dirección de correo electrónico de un buzón de Exchange o la dirección URL de un sitio de SharePoint). |
|||

Este es un ejemplo de un archivo CSV con información de custodios:  

| ContactEmail      | Exchange habilitado | OneDrive habilitado | Es pamantente | Tipo Workload1 | Ubicación de Workload1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|sarad@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Validación de custodios y orígenes de datos

Cuando se carga el archivo CSV de custodio, la exhibición avanzada de documentos electrónicos realiza las siguientes acciones:

1. Valida los custodios y sus orígenes de datos. 

2. Indiza todos los orígenes de datos para cada custodio y los coloca en retención (si la propiedad is alhold se establece en TRUE).

### <a name="custodian-validation"></a>Validación de custodios

Actualmente, solo se admite la importación de custodios que estén en Azure Active Directory (AAD).

Validamos y buscamos custodios mediante el valor UPN en la columna de **correo electrónico del contacto** en el archivo CSV. Los custodios que se validan se agregan automáticamente al caso y se enumeran en la ficha **custodio** en la página **orígenes** del caso. Si no se puede validar un custodio, se enumeran en el registro de errores del trabajo BulkAddCustodian que aparece en la ficha **trabajos** en el caso. Los custodios no validados no se agregan al caso.

### <a name="data-source-validation"></a>Validación de origen de datos

Una vez validados y agregados los custodios al caso, se validan todos los orígenes de datos asociados con un custodio. Si no se encuentra ningún origen de datos para un custodio, el valor **no validado** se mostraría en la columna **validada** en la ficha **custodio** de ese custodio.

### <a name="remediating-unvalidated-data-sources"></a>Corrección de orígenes de datos no validados

Para corregir los custodios con orígenes de datos no validados: 

1. En la ficha **custodio** , seleccione un custodio que no se haya validado.

2. En la página flotante de custodios, desplácese hasta la sección **orígenes de datos** para ver los orígenes de datos asociados con custodio. Se enumeran los orígenes de datos validados y no validados.

3. En la sección **orígenes de datos** , haga clic en **Editar**.

4. En la página **elegir ubicaciones de apoyo** , quite un origen de datos no validado.

5. En la página **seleccionar ubicaciones adicionales** , haga clic en **Actualizar** para agregar más orígenes de datos para un custodio.
