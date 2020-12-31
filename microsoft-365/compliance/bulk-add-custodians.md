---
title: Importar custodios a un caso de eDiscovery avanzado
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
description: Use la herramienta de importación dto rápidamente para agregar varios custodios y sus orígenes de datos asociados a un caso en eDiscovery avanzado.
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740307"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>Importar custodios a un caso de eDiscovery avanzado

Para los casos de eDiscovery avanzados que involucran muchos custodios, puede importar varios custodios a la vez mediante un archivo CSV que contenga la información necesaria para agregarlos a un caso.

## <a name="import-custodians"></a>Importación de custodios

1. Abra el caso de exhibición avanzada de documentos electrónicos y seleccione la pestaña **orígenes de datos** .

2. Haga clic en **Agregar**  >  **custodios de importación** de origen de datos.

3. En la página de control flotante **importar administradores** , haga clic en **descargar una plantilla en blanco** para descargar un archivo CSV de plantilla de custodio.

   ![Descargar una plantilla CSV desde la página de control de custodios para importación](../media/ImportCustodians1.png)

4. Agregue la información de la Private al archivo CSV y guárdelo en su equipo local. Consulte la sección [archivo CSV de custodio](#custodian-csv-file) para obtener información sobre las propiedades necesarias en el archivo CSV.

5. Una vez que haya preparado el archivo CSV con la información de custodios, vuelva a la pestaña **orígenes de datos** y haga clic en **Agregar**  >  **custodios de importación** de origen de datos de nuevo.

6. En la página de control flotante **importar administradores** , haga clic en **examinar** y, a continuación, cargue el archivo CSV que contiene la información de custodios.

   Una vez cargado el archivo CSV, se crea un trabajo denominado **BulkAddCustodian** y se muestra en la pestaña **trabajos** . El trabajo valida los custodios y sus orígenes de datos asociados y, a continuación, los agrega a la página de **orígenes de datos** del caso.

## <a name="custodian-csv-file"></a>Archivo CSV de custodio

Una vez que haya descargado la plantilla de custodio de CSV, puede Agregar custodios y su origen de datos en cada fila. Asegúrese de no cambiar los nombres de columna de la fila de encabezado. Use las columnas tipo de carga de trabajo y ubicación de carga de trabajo para asociar otros orígenes de datos a un custodio.

| Nombre de columna|Descripción|
|:------- |:------------------------------------------------------------|
|**Asociada de custodios**     |La dirección de correo electrónico UPN del custodio. Por ejemplo, sarad@contoso.onmicrosoft.com.           |
|**Exchange habilitado** | Valor TRUE/FALSE para incluir o no el buzón del custodio.      |
|**OneDrive habilitado** | Valor TRUE/FALSE para incluir o no la cuenta de OneDrive para la empresa del custodio. |
|**Es pamantente**        | Valor TRUE/FALSE para indicar si se deben retener los orígenes de datos de custodios.       |
|**Tipo Workload1**         |Valor de cadena que indica el tipo de origen de datos que se va a asociar con el custodio. Los valores posibles son: <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Ubicación de Workload1**     | Según el tipo de carga de trabajo, sería la ubicación del origen de datos. Por ejemplo, la dirección de correo electrónico de un buzón de Exchange o la dirección URL de un sitio de SharePoint. |
|||

Este es un ejemplo de un archivo CSV con información de custodios:<br/><br/>

|Asociada de custodios      | Exchange habilitado | OneDrive habilitado | Es pamantente | Tipo Workload1 | Ubicación de Workload1             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>Validación de custodios y orígenes de datos

Después de cargar el archivo CSV de custodio, la exhibición avanzada de documentos electrónicos realiza las siguientes acciones:

1. Valida los custodios y sus orígenes de datos.

2. Indiza todos los orígenes de datos para cada custodio y los coloca en retención (si la propiedad **is alhold** en el archivo CSV se establece en true).

### <a name="custodian-validation"></a>Validación de custodios

Actualmente, solo se admite la importación de custodios que se incluyen en Azure Active Directory de la organización (Azure AD).

La herramienta de importación de custodios busca y valida a los custodios mediante el valor UPN en la columna **asociada de custodios** del archivo CSV. Los custodios que se validan se agregan automáticamente al caso y se enumeran en la ficha **orígenes de datos** del caso. Si no se puede validar un custodio, se enumeran en el registro de errores del trabajo BulkAddCustodian que aparece en la ficha **trabajos** en el caso. Los custodios no validados no se agregan al caso o aparecen en la pestaña **orígenes de datos** .

### <a name="data-source-validation"></a>Validación de origen de datos

Una vez que los custodios se validan y agregan al caso, se agregan todos los buzones de correo principales y de OneDrive asociados a un custodio.

Sin embargo, si no se encuentra alguno de los otros orígenes de datos (como sitios de SharePoint, Microsoft Teams, grupos de Microsoft 365 o grupos de Yammer) asociados a un custodio, ninguno de ellos se asigna al custodio y el valor **no validado** se muestra en la columna **Estado** junto al custodio en la pestaña **orígenes de datos** .

Para agregar orígenes de datos validados para un custodio:

1. En la pestaña **orígenes de datos** , seleccione un custodio que contenga orígenes de datos que no se validen.

2. En la página flotante de custodios, desplácese hasta la sección **ubicaciones de Private** para ver los orígenes de datos validados y no validados asociados con el custodio.

3. Haga clic en **Editar** en la parte superior de la página de control flotante para quitar orígenes de datos no válidos o agregar otros nuevos.

4. Después de quitar los orígenes de datos no validados o agregar uno nuevo, el valor **activo** se muestra en la columna **Estado** del custodio en la ficha **orígenes de datos** . Para agregar orígenes que antes aparecían como no válidos, siga los pasos de corrección que se describen a continuación para agregarlos manualmente a un custodio.

### <a name="remediating-invalid-data-sources"></a>Corregir orígenes de datos no válidos

Para agregar y asociar manualmente un origen de datos que anteriormente no era válido:

1. En la pestaña **orígenes de datos** , seleccione un custodio para agregar y asociar manualmente un origen de datos que antes no era válido.

2. Haga clic en **Editar** en la parte superior de la página de control flotante para asociar buzones de correo, sitios, equipos o grupos de Yammer al custodio. Para ello, haga clic en **Editar** junto al tipo de ubicación de datos correspondiente.

3. Haga clic en **siguiente** para mostrar la página **configuración de suspensión** y configurar la opción de suspensión para los orígenes de datos que ha agregado.

4. Haga clic en **siguiente** para mostrar la página de **revisión de custodios** y, a continuación, haga clic en **Enviar** para guardar los cambios.
