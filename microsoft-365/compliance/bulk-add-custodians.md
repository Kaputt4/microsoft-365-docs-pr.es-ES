---
title: Importar custodios a un Advanced eDiscovery caso
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
description: Use la herramienta de importación dto agregar rápidamente varios custodios y sus orígenes de datos asociados a un caso en Advanced eDiscovery.
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421617"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Importar custodios a un Advanced eDiscovery caso

Para Advanced eDiscovery casos en los que participan muchos custodios, puede importar varios custodios a la vez mediante un archivo CSV que contiene la información necesaria para agregarlos a un caso.

## <a name="import-custodians"></a>Importar custodios

1. Abra el Advanced eDiscovery y seleccione la **pestaña Orígenes de** datos.

2. Haga **clic en Agregar orígenes de datos** Importar  >  **custodios**.

3. En la página desplegable Importar **custodios,** haga clic en **Descargar una** plantilla en blanco para descargar un archivo CSV de plantilla de custodia.

   ![Descargar una plantilla CSV desde la página desplegable Importar custodios](../media/ImportCustodians1.png)

4. Agregue la información de custodia al archivo CSV y guárdela en el equipo local. Consulte la [sección Archivo CSV de](#custodian-csv-file) custodia para obtener información sobre las propiedades necesarias en el archivo CSV.

5. Después de preparar el archivo CSV con la información  de custodia, vuelva a la pestaña Orígenes de datos y haga clic en **Agregar** orígenes de datos  >  **Importar custodios** de nuevo.

6. En la página desplegable Importar **custodios,** haga clic en **Examinar** y, a continuación, cargue el archivo CSV que contiene la información del custodio.

   Después de cargar el archivo CSV, se crea un trabajo denominado **BulkAddCustodian** y se muestra en la **pestaña** Trabajos. El trabajo valida a los custodios y sus orígenes de datos asociados y, a continuación, los agrega a la **página Orígenes** de datos del caso.

## <a name="custodian-csv-file"></a>Archivo CSV de custodia

Después de descargar la plantilla de custodia CSV, puede agregar custodios y su origen de datos en cada fila. Asegúrese de no cambiar los nombres de columna de la fila de encabezado. Use el tipo de carga de trabajo y las columnas de ubicación de carga de trabajo para asociar otros orígenes de datos a un administrador.

| Nombre de columna|Descripción|
|:------- |:------------------------------------------------------------|
|**Contacto de custodiaEmail**     |Dirección de correo electrónico UPN del custodio. Por ejemplo, sarad@contoso.onmicrosoft.com.           |
|**Exchange Habilitado** | Valor TRUE/FALSE para incluir o no incluir el buzón del custodio.      |
|**OneDrive Habilitado** | Valor TRUE/FALSE para incluir o no incluir la cuenta OneDrive para la Empresa custodia. |
|**Is OnHold**        | Valor TRUE/FALSE para indicar si se deben poner en espera los orígenes de datos de custodia. <sup>1</sup>     |
|**Tipo Workload1**         |Valor de cadena que indica el tipo de origen de datos que se asociará con el custodio. Los valores posibles son: <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Ubicación workload1**     | Según el tipo de carga de trabajo, esta sería la ubicación del origen de datos. Por ejemplo, la dirección de correo electrónico de un buzón Exchange o la dirección URL de un SharePoint sitio. |
|||

> [!NOTE]
> <sup>1</sup> Puede poner un máximo de 1.000 buzones y 100 sitios en espera mediante el proceso de importación de custodia y el archivo CSV. Puede usar este proceso para agregar más de 1.000 custodios a un caso, pero aún se aplican los límites de retención. Para obtener más información acerca de los límites de retención, vea [Limits in Advanced eDiscovery](limits-ediscovery20.md#hold-limits).

Este es un ejemplo de un archivo CSV con información de custodia:<br/><br/>

|Contacto de custodiaEmail      | Exchange Habilitado | OneDrive Habilitado | Is OnHold | Tipo Workload1 | Ubicación workload1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Validación de custodia y origen de datos

Después de cargar el archivo CSV de custodia, Advanced eDiscovery las siguientes acciones:

1. Valida los custodios y sus orígenes de datos.

2. Indiza todos los orígenes de datos de cada custodio y los pone en espera (si la propiedad **Is OnHold** del archivo CSV está establecida en TRUE).

### <a name="custodian-validation"></a>Validación de custodia

Actualmente, solo se admite la importación de custodios que se incluyen en la organización Azure Active Directory (Azure AD).

La herramienta de importación de custodia busca y valida a los custodios mediante el valor UPN de la columna **ContactEmail** de custodia del archivo CSV. Los custodios validados se agregan automáticamente al caso y se enumeran en la **pestaña Orígenes de** datos del caso. Si no se puede validar un custodio, aparecen en el registro de errores  del trabajo BulkAddCustodian que aparece en la pestaña Trabajos en el caso. Los custodios no confirmados no se agregan al caso ni aparecen en la **pestaña Orígenes de** datos.

### <a name="data-source-validation"></a>Validación del origen de datos

Después de que los custodios se validan y se agregan al caso, se agregan cada buzón principal y OneDrive cuenta asociada a un custodio.

Sin embargo, si no se encuentra ninguno de los otros orígenes de datos (como sitios de SharePoint, Microsoft Teams, grupos de Microsoft 365 o grupos de Yammer) asociados con  un custodio, ninguno de ellos se asigna al custodio y el valor No validado se muestra en la columna Estado situada junto al custodio en la ficha **Orígenes** de datos. 

Para agregar orígenes de datos validados para un custodio:

1. En la **pestaña Orígenes de** datos, seleccione un custodio que contenga orígenes de datos que no se validan.

2. En la página desplegable de custodia, desplácese hasta la sección Ubicaciones de custodia para ver los orígenes de datos validados y no validados asociados con el custodio. 

3. Haga **clic en** Editar en la parte superior de la página desplegable para quitar orígenes de datos no válidos o agregar otros nuevos.

4. Después de quitar orígenes de datos sin validar o agregar uno  nuevo, el valor **Active** se muestra en la columna Estado del custodio en la **pestaña Orígenes de** datos. Para agregar orígenes que anteriormente parecían no válidos, siga los pasos de corrección siguientes para agregarlos manualmente a un custodio.

### <a name="remediating-invalid-data-sources"></a>Corrección de orígenes de datos no válidos

Para agregar y asociar manualmente un origen de datos que no era válido anteriormente:

1. En la **pestaña Orígenes de** datos, seleccione un custodio para agregar y asociar manualmente un origen de datos que no era válido anteriormente.

2. Haga **clic en** Editar en la parte superior de la página desplegable para asociar buzones, sitios, Teams o Yammer grupos al custodio. Para ello, haga clic **en Editar** junto al tipo de ubicación de datos correspondiente.

3. Haga **clic en** Siguiente para mostrar la página Configuración **de** retención y configurar la configuración de retención para los orígenes de datos que agregó.

4. Haga **clic en** Siguiente para mostrar la página Revisar **custodios** y, a continuación, haga clic en **Enviar** para guardar los cambios.
