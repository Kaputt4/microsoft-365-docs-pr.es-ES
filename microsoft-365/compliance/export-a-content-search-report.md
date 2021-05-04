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
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760158"
---
# <a name="export-a-content-search-report"></a>Exportar un informe de búsqueda de contenido

En lugar de exportar el conjunto completo de resultados de búsqueda de una búsqueda de contenido en el Centro de seguridad y cumplimiento de & (y desde una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos), puede exportar los mismos informes que se generan al exportar resultados de búsqueda.
  
Al exportar un informe, se descarga en una carpeta que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly*. Por ejemplo, si la búsqueda de contenido se denomina  *ContosoCase0815*, el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly*. Para obtener una lista de los documentos que se incluyen en el informe, vea [What's included in the report](#whats-included-in-the-report).

## <a name="assign-roles-and-check-system-requirements"></a>Asignar roles y comprobar los requisitos del sistema

- Para exportar un informe de búsqueda de contenido, debe tener asignado el rol de administración Búsqueda de cumplimiento en el Centro de seguridad & cumplimiento. Este rol se asigna de forma predeterminada a los grupos de roles integrados eDiscovery Manager y Organization Management. Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).

- Al exportar un informe, los datos se almacenan temporalmente en un área de Azure Storage única en la nube de Microsoft antes de que se descarguen en el equipo local. Asegúrese de que su organización puede conectarse al punto de conexión de Azure, que **\* es .blob.core.windows.net** (el comodín representa un identificador único para la exportación). Los datos de resultados de búsqueda se eliminan del Azure Storage dos semanas después de su creación.

- El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:

  - Versión más reciente de Windows (32 bits o 64 bits)

  - Microsoft .NET Framework 4.7

- Debe usar uno de los siguientes exploradores compatibles para ejecutar la herramienta de exportación de exhibición de documentos<sup>electrónicos 1</sup>:

  - Microsoft Edge <sup>2</sup>

    O

  - Microsoft Internet Explorer 10 versiones posteriores

  > [!NOTE]
  > <sup>1</sup> Microsoft no fabrica extensiones de terceros ni complementos para ClickOnce aplicaciones. No se admite la exportación de resultados de búsqueda mediante un explorador no compatible con extensiones o complementos de terceros.<br/>
  > <sup>2</sup> Como resultado de los cambios recientes en Microsoft Edge, ClickOnce soporte técnico ya no está habilitado de forma predeterminada. Para obtener instrucciones sobre cómo ClickOnce compatibilidad en Edge, vea [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).

- Si el tamaño total estimado de los resultados devueltos por una búsqueda de contenido supera los 2 TB, se produce un error al exportar el informe. Para exportar correctamente el informe, intente restringir el ámbito y volver a ejecutar la búsqueda para que el tamaño estimado de los resultados sea inferior a 2 TB.

- La exportación de informes de búsqueda de contenido cuenta con el número máximo de exportaciones que se ejecutan al mismo tiempo y el número máximo de exportaciones que puede ejecutar un solo usuario. Para obtener más información acerca de los límites de exportación, [vea Exportar resultados de búsqueda de contenido](export-search-results.md#export-limits).

## <a name="generate-and-download-a-content-search-report"></a>Generar y descargar un informe de búsqueda de contenido

Los pasos para generar y descargar un informe de búsqueda de contenido son similares a exportar realmente los resultados de búsqueda.
  
## <a name="step-1-generate-the-report-for-export"></a>Paso 1: Generar el informe para exportar

El primer paso es preparar el informe para su descarga en el equipo que exporta. Al crear el informe, los documentos del informe se cargan en un área Azure Storage en la nube de Microsoft.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión con su cuenta profesional o educativa.
    
3. En el panel izquierdo del Centro de seguridad y & cumplimiento, haga clic en **Buscar** \> **en búsqueda de contenido**.
    
4. En la **página Búsqueda de contenido,** seleccione una búsqueda. 
    
5. En el panel de detalles, en **Exportar informe a un equipo,** haga clic en Generar **informe.**
    
    > [!NOTE]
    > Si los resultados de una búsqueda son de hace más de 7 días, se le solicitará que actualice los resultados de búsqueda. Si esto sucede, cancele  la exportación, haga clic en Actualizar resultados de búsqueda en el panel de detalles de la búsqueda seleccionada y, a continuación, vuelva a iniciar la exportación del informe después de actualizar los resultados. 
  
6. En la **página Exportar un informe,** en **Incluir estos elementos de** la búsqueda, elija una de las siguientes opciones:
    
    - Exportar solo los elementos indexados
    
    - Exportar los elementos indexados y sin indexar
    
    - Exportar solo los elementos sin indexar
    
    Para obtener más información acerca de los elementos sin indizar, vea [Elementos parcialmente indizados en Búsqueda de contenido](partially-indexed-items-in-content-search.md).
    
7. Elija incluir estadísticas de búsqueda para todas las versiones de SharePoint documentos. Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen sitios SharePoint o OneDrive para la Empresa búsqueda.
    
8. Haga clic **en Generar informe**.
    
    El informe de resultados de búsqueda está preparado para su descarga, lo que significa que los documentos del informe se cargarán en el área Azure Storage en la nube de Microsoft. Cuando el informe está listo para su descarga, el vínculo **Descargar informe** se muestra en Exportar informe a **un equipo** en el panel de detalles. 
    
> [!NOTE]
> También puede exportar un informe para una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos. Para ello, vaya a **eDiscovery** \> **eDiscovery**, seleccione un caso y haga clic **en Editar** icono Editar ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) . En la **página Búsquedas,** seleccione una búsqueda y, a continuación, haga clic en **Exportar** icono Exportar ![ resultados de búsqueda Exportar ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **un informe.** 
  
## <a name="step-2-download-the-report"></a>Paso 2: Descargar el informe

El siguiente paso es descargar el informe del área Azure Storage en el equipo local.
  
1. En el panel de detalles de la búsqueda para la que generó el informe, en Exportar **informe a un equipo,** haga clic **en Descargar informe**.
    
    Se **muestra la página** Descargar informe y contiene la siguiente información sobre el informe que se descarga en el equipo. 
    
    - El número de elementos que se descargarán.
    
    - El tamaño total estimado de los elementos que se descargarán.
    
    - Si los elementos indexados o sin indexar se exportarán. Los elementos no indexados son elementos que tienen un formato reconocido, están cifrados o no se indizaron por otros motivos.
    
    - Si se descargarán SharePoint de documentos.
    
    - El estado del proceso de exportación del informe. Puede empezar a descargar el informe incluso si no se ha completado la preparación del informe.
    
2. En **Clave de exportación**, haga clic en **Copiar al Portapapeles**. Use esta clave en el paso 5 para descargar el informe.
    
    > [!IMPORTANT]
    > Dado que cualquier persona puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, usar esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave del mismo manera que protegería las contraseñas u otra información relacionada con la seguridad. 
  
3. Haga clic **en Descargar informe**.
    
4. Si se le pide que instale la herramienta de exportación **de exhibición** de documentos electrónicos, haga clic **en Instalar**.
    
5. En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 2 en el cuadro correspondiente.
    
6. Haga **clic en** Examinar para especificar la ubicación donde desea descargar el informe. 
    
7. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar. Una vez completado el proceso de exportación, puede obtener acceso a los archivos en la ubicación donde se descargaron. 
    
> [!NOTE]
> Puede descargar el informe de una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos. Para ello, vaya a **eDiscovery** \> **eDiscovery**, seleccione un caso y haga clic **en Editar** icono Editar ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) . En la **página Exportaciones,** seleccione una exportación de informe y, a continuación, haga clic **en Descargar informe** en el panel de detalles. 
  
## <a name="whats-included-in-the-report"></a>Lo que se incluye en el informe

Al generar y exportar un informe sobre los resultados de una búsqueda de contenido, se descargan los siguientes documentos:
  
- **Resumen de exportación:** Un Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se buscaron, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se exportarían y el tamaño estimado y real de los elementos que se exportarían. 
    
    > [!NOTE]
    > Si incluye elementos no indexados al exportar el informe, el número de elementos sin indexar se incluye en el número total de resultados de búsqueda estimados y en el número total de resultados de búsqueda descargados (si desea exportar los resultados de búsqueda) que aparecen en el informe Exportar resumen. En otras palabras, el número total de elementos que se descargarían es igual al número total de resultados estimados y al número total de elementos no indexados. 
  
- **Manifiesto:** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda. 
    
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
  
- **Elementos sin indizar:** Un Excel que contiene información sobre los elementos no indexados incluidos en los resultados de la búsqueda. Si no incluye elementos sin indizar al generar el informe de resultados de búsqueda, este informe se seguirá descargando, pero estará vacío.
