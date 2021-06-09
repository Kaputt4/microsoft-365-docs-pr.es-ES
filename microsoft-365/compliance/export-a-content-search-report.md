---
title: Exportar un informe de búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: En lugar de exportar los resultados reales de una búsqueda de contenido en el Centro de seguridad & cumplimiento en Office 365, puede exportar un informe de resultados de búsqueda. El informe contiene un resumen de los resultados de la búsqueda y un documento con información detallada sobre cada elemento que se exportaría.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311578"
---
# <a name="export-a-content-search-report"></a>Exportar un informe de búsqueda de contenido

En lugar de exportar el conjunto completo de resultados de búsqueda desde una búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 (o desde una búsqueda asociada a un caso de exhibición de documentos electrónicos principal), puede exportar los mismos informes que se generan al exportar los resultados de búsqueda reales.
  
Al exportar un informe, los archivos de informe se descargan en una carpeta del equipo local que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly*. Por ejemplo, si la búsqueda de contenido se denomina  *ContosoCase0815*, el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly*. Para obtener una lista de los documentos que se incluyen en el informe, vea [What's included in the report](#whats-included-in-the-report).

## <a name="before-you-export-a-search-report"></a>Antes de exportar un informe de búsqueda

- Para exportar un informe de búsqueda, debe tener asignado el rol de administración Búsqueda de cumplimiento en el Centro de seguridad & cumplimiento. Este rol se asigna de forma predeterminada a los grupos de roles integrados eDiscovery Manager y Organization Management. Para más información, consulte [Asignar permisos de eDiscovery](assign-ediscovery-permissions.md).

- Al exportar un informe, los datos se almacenan temporalmente en una ubicación Azure Storage en la nube de Microsoft antes de que se descarguen en el equipo local. Asegúrese de que su organización puede conectarse al punto de conexión de Azure, que **\* es .blob.core.windows.net** (el comodín representa un identificador único para la exportación). Los datos de resultados de búsqueda se eliminan de la Azure Storage dos semanas después de su creación.

- El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:

  - Versión más reciente de Windows (32 bits o 64 bits)

  - Microsoft .NET Framework 4.7

- Debe usar uno de los siguientes exploradores compatibles para ejecutar la herramienta de exportación de exhibición de documentos<sup>electrónicos 1</sup>:

  - Microsoft Edge <sup>2</sup>

    O

  - Microsoft Internet Explorer 10 y versiones posteriores

  > [!NOTE]
  > <sup>1</sup> Microsoft no fabrica extensiones de terceros ni complementos para ClickOnce aplicaciones. No se admite la exportación de resultados de búsqueda mediante un explorador no compatible con extensiones o complementos de terceros.<br/>
  > <sup>2</sup> Como resultado de los cambios recientes en Microsoft Edge, ClickOnce soporte técnico ya no está habilitado de forma predeterminada. Para obtener instrucciones sobre cómo ClickOnce compatibilidad en Edge, vea [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).

- Si el tamaño total estimado de los resultados devueltos por la búsqueda supera los 2 TB, se produce un error al exportar los informes. Para exportar correctamente los informes, intente restringir el ámbito y volver a ejecutar la búsqueda para que el tamaño estimado de los resultados sea inferior a 2 TB.

- Si los resultados de una búsqueda tienen más de 7 días y envía un trabajo de informe de exportación, se muestra un mensaje de error que le pedirá que vuelva a ejecutar la búsqueda para actualizar los resultados de la búsqueda. Si esto sucede, cancele la exportación, vuelva a ejecutar la búsqueda y vuelva a iniciar la exportación.

- La exportación de informes de búsqueda cuenta con el número máximo de exportaciones que se ejecutan al mismo tiempo y el número máximo de exportaciones que puede ejecutar un solo usuario. Para obtener más información acerca de los límites de exportación, vea [Export Content search results](export-search-results.md#export-limits).
  
## <a name="step-1-generate-the-report-for-export"></a>Paso 1: Generar el informe para exportar

El primer paso es preparar el informe para su descarga en el equipo que exporta. Al exportar el informe, los documentos del informe se cargan en un área Azure Storage en la nube de Microsoft.
  
1. En el Microsoft 365 de cumplimiento, seleccione la búsqueda de contenido desde la que desea exportar el informe.
  
2. En el **menú** Acciones de la parte inferior de la página desplegable de búsqueda, haga clic **en Exportar informe**.

   ![Opción Exportar informe en el menú Acciones](../media/ActionMenuExportReport.png)

   Se **muestra la página** desplegable Exportar informe. Las opciones de informe de exportación disponibles para exportar información sobre la búsqueda dependen de si los resultados de la búsqueda se encuentran en buzones o sitios o en una combinación de ambos.
  
3. En **Opciones de salida,** elija una de las siguientes opciones:
  
   ![Exportar opciones de salida](../media/ExportOutputOptions.png)

    - Todos los elementos, excepto los que tienen formato no reconocido, se cifran o no se **indizan por otras razones.** Esta opción solo exporta información sobre elementos indizados.
  
    - **Todos los elementos, incluidos** los que tienen formato no reconocido, se cifran o no se indizan por otros motivos. Esta opción exporta información sobre elementos indexados y no indexados.
  
    - Solo los elementos que tienen un formato no reconocido, se cifran **o no se indizan por otras razones**. Esta opción solo exporta información sobre elementos no indexados.

4. Configure la **opción Habilitar desduplicación para Exchange contenido.**
  
   - Si selecciona esta opción, el recuento de mensajes duplicados (antes de la desduplicación y después de la desduplicación) se incluye en el informe de resumen de exportación. Además, solo se incluirá una copia de un mensaje en el manifest.xml archivo. Pero el informe de resultados de exportación contendrá una fila para cada copia de un mensaje duplicado de modo que pueda identificar los buzones que contienen una copia del mensaje duplicado. Para obtener más información acerca de los informes exportados, vea [What's included in the report](#whats-included-in-the-report).

   - Si no selecciona esta opción, los informes de exportación contendrán información sobre todos los mensajes devueltos por la búsqueda, incluidos los duplicados.

     Para obtener más información sobre la desduplicación y cómo se identifican los elementos duplicados, vea [Desduplicación en](de-duplication-in-ediscovery-search-results.md)los resultados de búsqueda de exhibición de documentos electrónicos .

5. Haga clic **en Generar informe**.

   Los informes de búsqueda están preparados para su descarga, lo que significa que los documentos del informe se cargan en una Azure Storage en la nube de Microsoft. Esto podría llevar varios minutos.

Consulte la siguiente sección para obtener instrucciones para descargar los informes de búsqueda exportados.
  
## <a name="step-2-download-the-report"></a>Paso 2: Descargar el informe

El siguiente paso es descargar el informe del área Azure Storage en el equipo local.

1. En la **página Búsqueda de contenido** del Centro de Microsoft 365 cumplimiento, seleccione la **pestaña** Exportar
  
   Es posible que tenga que hacer clic **en Actualizar** para actualizar la lista de trabajos de exportación para que muestre el trabajo de exportación que creó. Los trabajos de informe de exportación tienen el mismo nombre que la búsqueda correspondiente **con _ReportsOnly** anexado al nombre de búsqueda.
  
2. Seleccione el trabajo de exportación que creó en el paso 1.

3. En la **página Exportar control** desplegable del informe en Exportar **clave**, haga clic en Copiar en **el Portapapeles.** Esta clave se usa en el paso 6 para descargar los resultados de la búsqueda.
  
   > [!IMPORTANT]
   > Dado que cualquier persona puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, usar esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave del mismo manera que protegería las contraseñas u otra información relacionada con la seguridad.

4. En la parte superior de la página desplegable, haga clic **en Descargar resultados**.

5. Si se le pide que instale la herramienta de exportación **de exhibición** de documentos electrónicos, haga clic **en Instalar**.

6. En la **herramienta de exportación de exhibición de** documentos electrónicos , haga lo siguiente:

   ![Herramienta de exportación de eDiscovery](../media/eDiscoveryExportTool.png)

   1. Pegue la clave de exportación que copió en el paso 3 en el cuadro correspondiente.
  
   2. Haga **clic en** Examinar para especificar la ubicación en la que desea descargar los archivos de informe de búsqueda.

7. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo.
  
    La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar. Cuando el proceso de exportación se completa, puede acceder a los archivos en la ubicación donde se descargaron.
  
## <a name="whats-included-in-the-report"></a>Lo que se incluye en el informe

Al generar y exportar un informe sobre los resultados de una búsqueda de contenido, se descargan los siguientes documentos:
  
- **Resumen de exportación:** Un Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se buscaron, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se exportarían y el tamaño estimado y real de los elementos que se exportarían.

   Si incluye elementos no indexados al exportar el informe, el número de elementos sin indexar se incluye en el número total de resultados de búsqueda estimados y en el número total de resultados de búsqueda descargados (si desea exportar los resultados de búsqueda) que aparecen en el informe de resumen de exportación. En otras palabras, el número total de elementos que se descargarían es igual al número total de resultados estimados y al número total de elementos no indexados.
  
- **Manifiesto:** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda. Si ha habilitado la opción de desduplicación, el mensaje duplicado no se incluye en el archivo de manifiesto.

- **Resultados:** Un Excel que contiene una fila con información sobre cada elemento indizado que se exportaría con los resultados de la búsqueda. Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos: 

  - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).

  - La fecha en que se envió o se recibió el mensaje.

  - La línea Asunto del mensaje.

  - El remitente y los destinatarios del mensaje.

  Para los documentos de SharePoint y OneDrive para la Empresa, el registro de resultados contiene información sobre cada documento, incluidos:

  - La dirección URL del documento.

  - La dirección URL de la colección de sitio donde se ubica el documento.

  - La fecha en la que el documento se modificó por última vez.

  - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).

  > [!NOTE]
  > El número de filas del informe **de** resultados debe ser igual al número total de resultados de búsqueda menos el número total de elementos enumerados en el informe **Elementos sin** indizar.
  
- **Trace.log:** un registro de seguimiento que contiene información de registro detallada sobre el proceso de exportación y puede ayudar a descubrir problemas durante la exportación. Si abre un vale con el Soporte técnico de Microsoft sobre un problema relacionado con la exportación de informes de búsqueda, es posible que se le pida que proporcione este registro de seguimiento.

- **Elementos sin indizar:** Un Excel que contiene información sobre los elementos no indexados incluidos en los resultados de la búsqueda. Si no incluye elementos sin indizar al generar el informe de resultados de búsqueda, este informe se seguirá descargando, pero estará vacío.
