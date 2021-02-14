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
description: En lugar de exportar los resultados reales de una búsqueda de contenido en el Centro de seguridad y cumplimiento de & en Office 365, puede exportar un informe de resultados de búsqueda. El informe contiene un resumen de los resultados de la búsqueda y un documento con información detallada sobre cada elemento que se exportaría.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de27e25945f14f6a6119b4c1776eebca5e84d8ce
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358306"
---
# <a name="export-a-content-search-report"></a>Exportar un informe de búsqueda de contenido

En lugar de exportar el conjunto completo de resultados de búsqueda desde una búsqueda de contenido en el Centro de seguridad y cumplimiento de & (y desde una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos), puede exportar los mismos informes que se generan al exportar los resultados de la búsqueda.
  
Al exportar un informe, se descarga en una carpeta que tiene el mismo nombre que la búsqueda de contenido, pero que se anexa con *_ReportsOnly*. Por ejemplo, si la búsqueda de contenido se denomina  *ContosoCase0815*, el informe se descarga en una carpeta denominada *ContosoCase0815_ReportsOnly*. Para obtener una lista de los documentos que se incluyen en el informe, vea Lo [que se incluye en el informe.](#whats-included-in-the-report)

## <a name="assign-roles-and-check-system-requirements"></a>Asignar roles y comprobar los requisitos del sistema

- Para exportar un informe de búsqueda de contenido, debe tener asignado el rol de administración búsqueda de cumplimiento en el Centro de & cumplimiento. Este rol se asigna de forma predeterminada a los grupos de roles integrados administrador de exhibición de documentos electrónicos y administración de la organización. Para obtener más información, consulte [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).

- Al exportar un informe, los datos se almacenan temporalmente en un área única de Azure Storage en la nube de Microsoft antes de que se descarguen en el equipo local. Asegúrese de que su organización puede conectarse al punto de conexión de Azure, que es **\* .blob.core.windows.net** (el carácter comodín representa un identificador único para la exportación). Los datos de los resultados de la búsqueda se eliminan del área de Azure Storage dos semanas después de su creación. 
    
- El equipo que use para exportar los resultados de búsqueda debe cumplir los siguientes requisitos del sistema:
    
  - Versiones de 32 o 64 bits de Windows 7 y versiones posteriores
    
  - Microsoft .NET Framework 4.7
    
- Debe usar uno de los siguientes exploradores compatibles para ejecutar la herramienta de exportación de exhibición de documentos electrónicos<sup>1:</sup>

  - Microsoft Edge <sup>2</sup>

    O

  - Microsoft Internet Explorer 10 y versiones posteriores

  > [!NOTE]
  > <sup>1</sup> Microsoft no fabrica extensiones ni complementos de terceros para ClickOnce aplicaciones. No se admite la exportación de resultados de búsqueda mediante un explorador no compatible con extensiones o complementos de terceros.<br/>
  > <sup>2</sup> Como resultado de los cambios recientes en Microsoft Edge, ClickOnce soporte técnico ya no está habilitado de forma predeterminada. Para obtener instrucciones sobre cómo habilitar ClickOnce en Edge, vea Usar la herramienta de exportación de exhibición de documentos [electrónicos en Microsoft Edge.](configure-edge-to-export-search-results.md)

- Si el tamaño total estimado de los resultados devueltos por una búsqueda de contenido supera los 2 TB, se produce un error al exportar el informe. Para exportar correctamente el informe, intente restringir el ámbito y volver a ejecutar la búsqueda para que el tamaño estimado de los resultados sea inferior a 2 TB.

- La exportación de informes de búsqueda de contenido tiene en cuenta el número máximo de exportaciones que se ejecutan al mismo tiempo y el número máximo de exportaciones que puede ejecutar un solo usuario. Para obtener más información acerca de los límites de exportación, vea [Exportar resultados de búsqueda de contenido.](export-search-results.md#export-limits)

## <a name="generate-and-download-a-content-search-report"></a>Generar y descargar un informe de búsqueda de contenido

Los pasos para generar y descargar un informe de búsqueda de contenido son similares a exportar realmente los resultados de la búsqueda.
  
## <a name="step-1-generate-the-report-for-export"></a>Paso 1: Generar el informe para exportar

El primer paso es preparar el informe para la descarga en el equipo que se exporta. Cuando el informe se usa, los documentos del informe se cargan en un área de Azure Storage en la nube de Microsoft.
  
1. Vaya a [https://protection.office.com](https://protection.office.com).
    
2. Inicie sesión con su cuenta profesional o educativa.
    
3. En el panel izquierdo del Centro de seguridad & cumplimiento, haga clic en **Buscar** \> **contenido.**
    
4. En la **página Búsqueda de** contenido, seleccione una búsqueda. 
    
5. En el panel de detalles, en **Exportar informe a un equipo,** haga clic en Generar **informe.**
    
    > [!NOTE]
    > Si los resultados de una búsqueda son de hace más de 7 días, se le solicitará que actualice los resultados de búsqueda. Si esto ocurre, cancele  la exportación, haga clic en Actualizar resultados de búsqueda en el panel de detalles de la búsqueda seleccionada y, a continuación, vuelva a iniciar la exportación del informe después de actualizar los resultados. 
  
6. En la **página Exportar un informe,** en **Incluir estos elementos** de la búsqueda, elija una de las siguientes opciones:
    
    - Exportar solo los elementos indexados
    
    - Exportar los elementos indexados y sin indexar
    
    - Exportar solo los elementos sin indexar
    
    Para obtener más información acerca de los elementos no indexados, vea [Elementos parcialmente indizados en la búsqueda de contenido.](partially-indexed-items-in-content-search.md)
    
7. Elija incluir estadísticas de búsqueda para todas las versiones de documentos de SharePoint. Esta opción solo aparece si los orígenes de contenido de la búsqueda incluyen sitios de SharePoint o OneDrive para la Empresa.
    
8. Haga clic **en Generar informe.**
    
    El informe de resultados de búsqueda está preparado para su descarga, lo que significa que los documentos del informe se cargarán en el área de Azure Storage en la nube de Microsoft. Cuando el informe está listo  para su descarga, el vínculo Descargar informe se muestra en Exportar informe **a un equipo** en el panel de detalles. 
    
> [!NOTE]
> También puede exportar un informe para una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos. Para ello, vaya a **eDiscovery eDiscovery,** seleccione un caso y haga clic \> en **el icono** ![ Editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) edición. En la **página Búsquedas,** seleccione  una búsqueda y, a continuación, haga clic en exportar el icono Exportar ![ resultados de búsqueda Exportar ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **un informe.** 
  
## <a name="step-2-download-the-report"></a>Paso 2: Descargar el informe

El siguiente paso es descargar el informe desde el área de Azure Storage en el equipo local.
  
1. En el panel de detalles de la búsqueda para la que generó el informe, en Exportar informe **a un** equipo, haga clic en **Descargar informe.**
    
    Se **muestra la página** Descargar informe y contiene la siguiente información sobre el informe que se descarga en el equipo. 
    
    - El número de elementos que se descargarán.
    
    - El tamaño total estimado de los elementos que se descargarán.
    
    - Si los elementos indexados o sin indexar se exportarán. Los elementos no indexados son elementos que tienen un formato reconocido, están cifrados o no se indizaron por otros motivos.
    
    - Indica si se descargarán las versiones de los documentos de SharePoint.
    
    - El estado del proceso de exportación del informe. Puede empezar a descargar el informe incluso si no se ha completado la preparación del informe.
    
2. En **Clave de exportación**, haga clic en **Copiar al Portapapeles**. Use esta clave en el paso 5 para descargar el informe.
    
    > [!IMPORTANT]
    > Dado que cualquiera puede instalar e iniciar la herramienta de exportación de exhibición de documentos electrónicos y, a continuación, usar esta clave para descargar el informe de búsqueda, asegúrese de tomar precauciones para proteger esta clave de la forma que protegería las contraseñas u otra información relacionada con la seguridad. 
  
3. Haga clic **en Descargar informe.**
    
4. Si se le pide que instale la herramienta de exportación de **exhibición** de documentos electrónicos, haga clic **en Instalar.**
    
5. En la **Herramienta de exportación de exhibición de documentos electrónicos**, pegue la clave de exportación que ha copiado en el paso 2 en el cuadro correspondiente.
    
6. Haga **clic en** Examinar para especificar la ubicación donde desea descargar el informe. 
    
7. Haga clic en **Iniciar** para descargar los resultados de la búsqueda en el equipo. 
    
    La **Herramienta de exportación de exhibición de documentos electrónicos** muestra información del estado acerca del proceso de exportación, incluida una estimación del número (y tamaño) de los elementos restantes que se van a descargar. Una vez completado el proceso de exportación, puede obtener acceso a los archivos en la ubicación donde se descargaron. 
    
> [!NOTE]
> Puede descargar el informe para una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos. Para ello, vaya a **eDiscovery eDiscovery,** seleccione un caso y haga clic \> en **el icono** ![ Editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) edición. En la **página Exportaciones,** seleccione una exportación de informe y, a continuación, haga clic **en Descargar informe** en el panel de detalles. 
  
## <a name="whats-included-in-the-report"></a>Lo que se incluye en el informe

Al generar y exportar un informe sobre los resultados de una búsqueda de contenido, se descargan los siguientes documentos:
  
- **Resumen de exportación:** Documento de Excel que contiene un resumen de la exportación. Esto incluye información como el número de orígenes de contenido que se buscaron, el número de resultados de búsqueda de cada ubicación de contenido, el número estimado de elementos, el número real de elementos que se exportarían y el tamaño estimado y real de los elementos que se exportarían. 
    
    > [!NOTE]
    > Si incluye elementos no indexados al exportar el informe, el número de elementos no indexados se incluye en el número total de resultados de búsqueda estimados y en el número total de resultados de búsqueda descargados (si desea exportar los resultados de la búsqueda) que aparecen en el informe de resumen de exportación. En otras palabras, el número total de elementos que se descargarían es igual al número total de resultados estimados y al número total de elementos no indexados. 
  
- **Manifiesto:** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda. 
    
- **Resultados:** Documento de Excel que contiene una fila con información sobre cada elemento indizado que se exportaría con los resultados de la búsqueda. Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos: 
    
  - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
    
  - La fecha en que se envió o se recibió el mensaje.
    
  - La línea Asunto del mensaje.
    
  - El remitente y los destinatarios del mensaje.
    
    Para documentos de sitios de SharePoint y OneDrive para la Empresa, el registro de resultados contiene información sobre cada documento, incluidos:
    
  - La dirección URL del documento.
    
  - La dirección URL de la colección de sitio donde se ubica el documento.
    
  - La fecha en la que el documento se modificó por última vez.
    
  - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).
    
    > [!NOTE]
    > El número de  filas del informe de resultados debe ser igual al número total de resultados de búsqueda menos el número total de elementos enumerados en el informe Elementos **no** indexados. 
  
- **Elementos no indexados:** Documento de Excel que contiene información sobre los elementos no indexados incluidos en los resultados de la búsqueda. Si no incluye elementos no indexados al generar el informe de resultados de búsqueda, este informe se seguirá descargando, pero estará vacío.
