---
title: Exportar un informe de búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: En lugar de exportar los resultados reales de una búsqueda de contenido en el portal de cumplimiento Microsoft Purview, puede exportar un informe de resultados de búsqueda. El informe contiene un resumen de los resultados de la búsqueda y un documento con información detallada sobre cada elemento que se exportaría.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9695c6bda600dae37c9ee8def435813240a828f
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67821107"
---
# <a name="export-a-content-search-report"></a>Exportar un informe de búsqueda de contenido

En lugar de exportar el conjunto completo de resultados de búsqueda de una búsqueda de contenido en el portal de cumplimiento Microsoft Purview (o de una búsqueda asociada a un caso de Microsoft Purview eDiscovery (estándar), puede exportar los mismos informes que se generan al exportar los resultados reales de la búsqueda.
  
Al exportar un informe, los archivos de informe se descargan en una carpeta del equipo local que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly*. Por ejemplo, si la búsqueda de contenido se denomina  *ContosoCase0815*, el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly*. Para obtener una lista de los documentos que se incluyen en el informe, vea [What's included in the report(Qué se incluye en el informe](#whats-included-in-the-report)).

## <a name="before-you-export-a-search-report"></a>Antes de exportar un informe de búsqueda

- Para exportar un informe de búsqueda, debe tener asignado el rol de administración búsqueda de cumplimiento en el portal de cumplimiento. Este rol se asigna de forma predeterminada a los grupos de roles integrados eDiscovery Manager y Organization Management. Para más información, consulte [Asignar permisos de eDiscovery](assign-ediscovery-permissions.md).

- Al exportar un informe, los datos se almacenan temporalmente en una ubicación de Azure Storage en la nube de Microsoft antes de descargarlos en el equipo local. Asegúrese de que su organización puede conectarse al punto de conexión en Azure, que es **\*.blob.core.windows.net** (el carácter comodín representa un identificador único para la exportación). Los datos de resultados de búsqueda se eliminan de la ubicación de Azure Storage dos semanas después de su creación.

- El equipo que use para exportar el informe de búsqueda debe cumplir los siguientes requisitos del sistema:
  
  - Versión más reciente de Windows (32 bits o 64 bits)
  
  - Microsoft .NET Framework 4.7 o superior
  
- Tiene que usar Microsoft Edge<sup>1</sup> para ejecutar la herramienta de exportación de exhibición de documentos electrónicos. El uso de Internet Explorer 11 para exportar los resultados de búsqueda ya no es compatible con<sup>2</sup>.
  
  > [!NOTE]
  > <sup>1</sup> Como resultado de los cambios recientes en Microsoft Edge, la compatibilidad con ClickOnce ya no está habilitada de forma predeterminada. Para obtener instrucciones sobre cómo habilitar la compatibilidad con ClickOnce en Edge, vea [Usar la herramienta de exportación de exhibición de documentos electrónicos en Microsoft Edge](configure-edge-to-export-search-results.md). Además, Microsoft no fabrica extensiones ni complementos de terceros para aplicaciones ClickOnce. No se admite la exportación de resultados de búsqueda mediante un explorador no compatible con extensiones o complementos de terceros.
  > 
  > <sup>2</sup> A partir de agosto de 2021, las aplicaciones y servicios de Microsoft 365 ya no admitirán Internet Explorer 11 (IE11) y es posible que los usuarios tengan una experiencia degradada o no puedan conectarse a esas aplicaciones y servicios. Estas aplicaciones y servicios se eliminarán gradualmente en las próximas semanas y meses para garantizar un fin sin problemas del soporte técnico. Cada aplicación y servicio se están eliminando gradualmente según programaciones independientes. Para obtener más información, consulte esta [entrada de blog](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666).

- Si el tamaño total estimado de los resultados devueltos por la búsqueda supera los 2 TB, se produce un error al exportar los informes. Para exportar correctamente los informes, intente restringir el ámbito y volver a ejecutar la búsqueda para que el tamaño estimado de los resultados sea inferior a 2 TB.

- Si los resultados de una búsqueda son anteriores a 7 días y envía un trabajo de informe de exportación, se muestra un mensaje de error que le pide que vuelva a ejecutar la búsqueda para actualizar los resultados de la búsqueda. Si esto sucede, cancele la exportación, vuelva a ejecutar la búsqueda y vuelva a iniciar la exportación.

- La exportación de informes de búsqueda cuenta con el número máximo de exportaciones que se ejecutan al mismo tiempo y el número máximo de exportaciones que puede ejecutar un solo usuario. Para obtener más información sobre los límites de exportación, vea [Exportar resultados de búsqueda de contenido](export-search-results.md#export-limits).
  
## <a name="step-1-generate-the-report-for-export"></a>Paso 1: Generar el informe para la exportación

El primer paso consiste en preparar el informe para su descarga en el equipo que exporta. Al exportar el informe, los documentos del informe se cargan en un área de Azure Storage en la nube de Microsoft.
  
1. En el portal de cumplimiento, seleccione la búsqueda de contenido desde la que desea exportar el informe.
  
2. En el menú **Acciones** de la parte inferior de la página desplegable de búsqueda, haga clic en **Exportar informe**.

   ![Opción Exportar informe en el menú Acciones.](../media/ActionMenuExportReport.png)

   Se muestra la página de control flotante **Exportar informe** . Las opciones del informe de exportación disponibles para exportar información sobre la búsqueda dependen de si los resultados de la búsqueda se encuentran en buzones o sitios o en una combinación de ambos.
  
3. En **Opciones de salida**, elija una de las siguientes opciones:
  
   ![Opciones de salida de exportación.](../media/ExportOutputOptions.png)

    - **Todos los elementos, excepto los que tienen formato no reconocido, se cifran o no se indexan por otros motivos**. Esta opción solo exporta información sobre los elementos indexados.
  
    - **Todos los elementos, incluidos los que tienen formato no reconocido, se cifran o no se indexan por otros motivos**. Esta opción exporta información sobre los elementos indexados y sin indexar.
  
    - **Solo los elementos que tienen un formato no reconocido, se cifran o no se indexan por otros motivos**. Esta opción solo exporta información sobre elementos no indexados.

4. Configure la opción **Habilitar desduplicación para contenido de Exchange** .
  
   - Si selecciona esta opción, el recuento de mensajes duplicados (antes de la desduplicación y después de la desduplicación) se incluye en el informe de resumen de exportación. Además, solo se incluirá una copia de un mensaje en el archivo manifest.xml. Pero el informe de resultados de exportación contendrá una fila para cada copia de un mensaje duplicado para que pueda identificar los buzones que contienen una copia del mensaje duplicado. Para obtener más información sobre los informes exportados, vea [What's included in the report(Qué se incluye en el informe](#whats-included-in-the-report)).

   - Si no selecciona esta opción, los informes de exportación contendrán información sobre todos los mensajes devueltos por la búsqueda, incluidos los duplicados.

     Para obtener más información sobre la desduplicación y cómo se identifican los elementos duplicados, vea [Desduplicación en los resultados de búsqueda de eDiscovery](de-duplication-in-ediscovery-search-results.md).

5. Haga clic en **Generar informe**.

   Los informes de búsqueda están preparados para su descarga, lo que significa que los documentos del informe se cargan en una ubicación de Azure Storage en la nube de Microsoft. Esto podría llevar varios minutos.

Consulte la sección siguiente para obtener instrucciones para descargar los informes de búsqueda exportados.
  
## <a name="step-2-download-the-report"></a>Paso 2: Descargar el informe

El siguiente paso consiste en descargar el informe del área de Azure Storage en el equipo local.

> [!NOTE]
> El informe de búsqueda exportado se debe descargar en un plazo de 14 días después de generar el informe en el paso 1.

1. En la página **Búsqueda de contenido** del portal de cumplimiento, seleccione la pestaña **Exportaciones** .
  
   Es posible que tenga que hacer clic en **Actualizar** para actualizar la lista de trabajos de exportación para que muestre el trabajo de exportación que ha creado. Los trabajos de exportación del informe tienen el mismo nombre que la búsqueda correspondiente con **_ReportsOnly** anexados al nombre de la búsqueda.
  
2. Seleccione el trabajo de exportación que creó en el paso 1.

3. En la página desplegable **Exportar informe** , en **Clave de exportación**, haga clic en **Copiar en el Portapapeles**. Use esta clave en el paso 6 para descargar los resultados de la búsqueda.
  
   > [!IMPORTANT]
   > Dado que cualquier usuario puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, usar esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave al igual que protegería contraseñas u otra información relacionada con la seguridad.

4. En la parte superior de la página de control flotante, haga clic en **Descargar resultados**.

5. Si se le pide que instale la herramienta de **exportación de exhibición de documentos electrónicos**, haga clic en **Instalar**.

6. En la **herramienta de exportación de eDiscovery**, haga lo siguiente:

   ![Herramienta de exportación de eDiscovery.](../media/eDiscoveryExportTool.png)

   1. Pegue la clave de exportación que copió en el paso 3 en el cuadro adecuado.
  
   2. Haga clic en **Examinar** para especificar la ubicación donde desea descargar los archivos de informe de búsqueda.

7. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo.
  
    La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar. Cuando el proceso de exportación se completa, puede acceder a los archivos en la ubicación donde se descargaron.
  
## <a name="whats-included-in-the-report"></a>Qué se incluye en el informe

Al generar y exportar un informe sobre los resultados de una búsqueda de contenido, se descargan los siguientes documentos:
  
- **Resumen de exportación:** Documento de Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se buscaron, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se exportarían y el tamaño estimado y real de los elementos que se exportarían.

   Si incluye elementos no indexados al exportar el informe, el número de elementos no indexados se incluye en el número total de resultados de búsqueda estimados y en el número total de resultados de búsqueda descargados (si desea exportar los resultados de búsqueda) que se enumeran en el informe de resumen de exportación. En otras palabras, el número total de elementos que se descargarían es igual al número total de resultados estimados y al número total de elementos sin indexar.
  
- **Manifiesto:** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda. Si ha habilitado la opción de desduplicación, los mensajes duplicados no se incluyen en el archivo de manifiesto.

- **Resultados:** Documento de Excel que contiene una fila con información sobre cada elemento indexado que se exportaría con los resultados de la búsqueda. Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos: 

  - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).

  - La fecha en que se envió o se recibió el mensaje.

  - La línea Asunto del mensaje.

  - El remitente y los destinatarios del mensaje.

  Para los documentos de SharePoint y OneDrive para la Empresa sitios, el registro de resultados contiene información sobre cada documento, incluidos:

  - La dirección URL del documento.

  - La dirección URL de la colección de sitio donde se ubica el documento.

  - La fecha en la que el documento se modificó por última vez.

  - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).

  > [!NOTE]
  > El número de filas del informe **Resultados** debe ser igual al número total de resultados de búsqueda menos el número total de elementos enumerados en el informe **Elementos sin indexar** .
  
- **Trace.log:** Un registro de seguimiento que contiene información de registro detallada sobre el proceso de exportación y puede ayudar a descubrir problemas durante la exportación. Si abre un vale con Soporte técnico de Microsoft sobre un problema relacionado con la exportación de informes de búsqueda, es posible que se le pida que proporcione este registro de seguimiento.

- **Elementos sin indexar:** Documento de Excel que contiene información sobre los elementos no indexados incluidos en los resultados de la búsqueda. Si no incluye elementos sin indexar al generar el informe de resultados de búsqueda, este informe se seguirá descargando, pero estará vacío.
