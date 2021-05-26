---
title: Buscar actividades de eDiscovery en el registro de auditoría
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Obtenga información sobre qué eventos se registran cuando los usuarios asignados a permisos de exhibición de documentos electrónicos realizan búsquedas de contenido, exhibición de documentos electrónicos principales y Advanced eDiscovery tareas en el centro de Microsoft 365 cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b1f3f235f3411e2f637e4e32104c6179643757d
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657698"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Buscar actividades de eDiscovery en el registro de auditoría

Las actividades relacionadas con la búsqueda de contenido y la exhibición de documentos electrónicos (para eDiscovery y Advanced eDiscovery principales) que se realizan en el centro de cumplimiento de Microsoft 365 o ejecutando los cmdlets de PowerShell correspondientes se registran en el registro de auditoría. Los eventos se registran cuando los administradores o administradores de exhibición de documentos electrónicos (o cualquier usuario asignado a permisos de exhibición de documentos electrónicos) realizan las siguientes tareas de búsqueda de contenido y exhibición de documentos electrónicos principales en el centro de Microsoft 365 cumplimiento:
  
- Creación y administración de casos Advanced eDiscovery principales

- Creación, inicio y edición de búsquedas de contenido

- Realizar acciones de búsqueda, como obtener una vista previa, exportar y eliminar resultados de búsqueda

- Administración de custodias y conjuntos de revisión en Advanced eDiscovery

- Configuración del filtrado de permisos para la búsqueda de contenido

- Administrar el rol de administrador de la exhibición de documentos electrónicos
  
Para obtener más información acerca de la búsqueda en el registro de auditoría, los permisos necesarios y la exportación de resultados de búsqueda, vea [Search the audit log in the Microsoft 365 compliance center](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Cómo buscar y ver actividades de exhibición de documentos electrónicos

Actualmente, debe hacer algunas cosas específicas para ver las actividades de exhibición de documentos electrónicos en el registro de auditoría. Aquí se muestra cómo hacerlo.
  
1. Vaya a <https://compliance.microsoft.com> e inicie sesión con su cuenta laboral o educativa.

2. En el panel de navegación izquierdo del centro de Microsoft 365 cumplimiento, haga clic en **Mostrar todo** y, a continuación, haga clic en **Auditar**.

3. En la **lista** desplegable Actividades, en **Actividades** de exhibición de documentos electrónicos **o** Advanced eDiscovery, haga clic en una o más actividades para buscar.

    > [!NOTE]
    > La **lista** desplegable Actividades también incluye un grupo de actividades denominadas actividades **del cmdlet eDiscovery** que devolverán registros del registro de auditoría del cmdlet.
  
4. Seleccione un intervalo de fecha y hora para mostrar los eventos de exhibición de documentos electrónicos que se produjeron en ese período.

5. En el **cuadro Usuarios,** seleccione uno o varios usuarios para los que mostrar los resultados de la búsqueda. Deje este cuadro en blanco para devolver entradas para todos los usuarios.

6. Haga clic en **Búsqueda** para ejecutar la búsqueda mediante sus criterios de búsqueda. 

7. Después de mostrar los resultados de la búsqueda, puede hacer clic en **Filtrar** resultados para filtrar o ordenar los registros de actividad resultantes. Desafortunadamente, no puede usar el filtrado para excluir explícitamente determinadas actividades. 

8. Para ver detalles sobre una actividad, haga clic en el registro de actividad de la lista de resultados de búsqueda. 

    Se **muestra** una página desplegable Detalles que contiene las propiedades detalladas del registro de eventos. Para mostrar detalles adicionales, haga clic **en Más información**. Para obtener una descripción de estas propiedades, vea la [sección Propiedades detalladas para actividades de exhibición de documentos electrónicos.](#detailed-properties-for-ediscovery-activities)

9. Si lo desea, puede exportar los resultados de la búsqueda del registro de auditoría a un archivo CSV y, a continuación, usar la característica Excel Power Query para dar formato y filtrar estos registros. Para más información, consulte[Exportar, configurar y ver registros de auditoría](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>Actividades de eDiscovery

En la tabla siguiente se describen las actividades de búsqueda de contenido y exhibición de documentos electrónicos principales que se registran cuando un administrador o administrador de exhibición de documentos electrónicos realiza una actividad relacionada con la exhibición de documentos electrónicos mediante el centro de cumplimiento o ejecutando el cmdlet correspondiente en PowerShell del Centro de seguridad & cumplimiento. Tenga en cuenta también que algunas actividades realizadas en Advanced eDiscovery pueden devolverse al buscar actividades en esta lista.
  
> [!NOTE]
> Las actividades de exhibición de documentos electrónicos descritas en esta sección proporcionan información similar a las actividades del cmdlet eDiscovery descritas en la sección siguiente. Se recomienda usar las actividades de exhibición de documentos electrónicos que se describen en esta sección porque aparecerán en los resultados de búsqueda del registro de auditoría en 30 minutos. Las actividades del cmdlet eDiscovery tardan hasta 24 horas en aparecer en los resultados de búsqueda del registro de auditoría.
  
|**Nombre descriptivo**|**Operación**|**Cmdlet correspondiente**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Miembro agregado al caso de exhibición de documentos electrónicos  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Se agregó un usuario como miembro de un caso de exhibición de documentos electrónicos. Como miembro de un caso, un usuario puede realizar varias tareas relacionadas con casos en función de si se les han asignado los permisos necesarios.  <br/> |
|Búsqueda de contenido modificado  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Se ha cambiado una búsqueda de contenido existente. Los cambios pueden incluir agregar o quitar ubicaciones de contenido o editar la consulta de búsqueda.  <br/> |
|Pertenencia de administrador de exhibición de documentos electrónicos modificada  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |Se cambió la lista de administradores de exhibición de documentos electrónicos de la organización. Esta actividad se registra cuando la lista de administradores de exhibición de documentos electrónicos se reemplaza por un grupo de nuevos usuarios. Si se agrega o quita un solo usuario, se registra la operación CaseAdminAdded.  <br/> |
|Caso de exhibición de documentos electrónicos modificado  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Se cambió un caso de exhibición de documentos electrónicos. Los cambios incluyen cerrar un caso abierto o volver a abrir un caso cerrado.  <br/> |
|Pertenencia a casos de exhibición de documentos electrónicos modificados  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |Se cambió la lista de pertenencia de un caso de exhibición de documentos electrónicos. Esta actividad se registra cuando todos los miembros se reemplazan por un grupo de nuevos usuarios. Si se agrega o quita un solo miembro, se registra la operación CaseMemberAdded o CaseMemberRemoved.  <br/> |
|Filtro de permisos de búsqueda modificado  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Se cambió un filtro de permisos de búsqueda.  <br/> |
|Consulta de búsqueda modificada para retención de casos de exhibición de documentos electrónicos  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Se cambió una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos. Los posibles cambios incluyen la edición de la consulta o el intervalo de fechas de una retención basada en consulta.  <br/> |
|Elemento de vista previa de búsqueda de contenido descargado  <br/> |PreviewItemDownloaded  <br/> |N/D  <br/> |Un usuario descargó un elemento en su equipo local (haciendo clic en el vínculo **Descargar elemento original)** al obtener una vista previa de los resultados de la búsqueda.  <br/> |
|Elemento de vista previa de búsqueda de contenido enumerado  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Un usuario hizo clic en **Vista** previa de resultados de búsqueda para mostrar la página de resultados de búsqueda de vista previa, que enumera hasta 1000 elementos de los resultados de una búsqueda de contenido.  <br/> |
|Elemento de vista previa de búsqueda de contenido visto  <br/> |PreviewItemRendered  <br/> |N/D  <br/> |Un administrador de exhibición de documentos electrónicos ha visto un elemento haciendo clic en él al obtener una vista previa de los resultados de la búsqueda.  <br/> |
|Búsqueda de contenido creada  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Se creó una nueva búsqueda de contenido.  <br/> |
|Administrador de exhibición de documentos electrónicos creado  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Se agregó un usuario como administrador de exhibición de documentos electrónicos en la organización.  <br/> |
|Caso de exhibición de documentos electrónicos creado  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Se creó un caso de exhibición de documentos electrónicos. Cuando se crea un caso, solo tiene que darle un nombre. Otras tareas relacionadas con casos, como agregar miembros, crear retenciones y crear búsquedas de contenido asociadas con el caso, darán como resultado eventos adicionales que se registran.  <br/> |
|Filtro de permisos de búsqueda creado  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Se creó un filtro de permisos de búsqueda.  <br/> |
|Consulta de búsqueda creada para retención de casos de exhibición de documentos electrónicos  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Se creó una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos.  <br/> |
|Búsqueda de contenido eliminado  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Se eliminó una búsqueda de contenido existente.  <br/> |
|Administrador de exhibición de documentos electrónicos eliminado  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Se eliminó un administrador de exhibición de documentos electrónicos de la organización.  <br/> |
|Caso de exhibición de documentos electrónicos eliminado  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Se eliminó un caso de exhibición de documentos electrónicos. Cualquier retención asociada con el caso debe quitarse antes de que se pueda eliminar el caso.  <br/> |
|Filtro de permisos de búsqueda eliminados  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Se eliminó un filtro de permisos de búsqueda.  <br/> |
|Consulta de búsqueda eliminada para retención de casos de exhibición de documentos electrónicos  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Se eliminó una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos. La eliminación de la consulta de la retención suele ser el resultado de eliminar una retención. Cuando se elimina una retención o una consulta de retención, se liberan las ubicaciones de contenido que estaban en espera.  <br/> |
|Exportación descargada de búsqueda de contenido  <br/> |SearchExportDownloaded  <br/> |N/D  <br/> |Un usuario descargó los resultados de una búsqueda de contenido en su equipo local. Debe **iniciarse una exportación** iniciada de la actividad de búsqueda de contenido antes de poder descargar los resultados de la búsqueda.  <br/> |
|Resultados preliminares de la búsqueda de contenido  <br/> |SearchPreviewed  <br/> |N/D  <br/> |Un usuario ha obtenido una vista previa de los resultados de una búsqueda de contenido.  <br/> |
|Resultados purgados de búsqueda de contenido  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Un usuario purgó los resultados de una búsqueda de contenido ejecutando el **comando New-ComplianceSearchAction -Purge.**  <br/> |
|Análisis quitado de la búsqueda de contenido  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de preparación de búsqueda de contenido (para preparar los resultados de Advanced eDiscovery). Si la acción de preparación tenía menos de dos semanas de antigüedad, los resultados de búsqueda que se prepararon para Advanced eDiscovery se eliminaron del Microsoft Azure de almacenamiento. Si la acción de preparación tenía más de 2 semanas, este evento indica que solo se eliminó la acción de preparación correspondiente.  <br/> |
|Exportación eliminada de búsqueda de contenido  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de exportación de búsqueda de contenido. Si la acción de exportación tenía menos de dos semanas de antigüedad, se eliminaron los resultados de búsqueda que se cargaron en el Microsoft Azure de almacenamiento. Si la acción de exportación tenía más de 2 semanas, este evento indica que solo se eliminó la acción de exportación correspondiente.  <br/> |
|Miembro eliminado del caso de exhibición de documentos electrónicos  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Un usuario se quitó como miembro de un caso de exhibición de documentos electrónicos.  <br/> |
|Resultados de vista previa eliminados de la búsqueda de contenido  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de vista previa de búsqueda de contenido.  <br/> |
|Se quitó la acción de purga realizada en la búsqueda de contenido  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de purga de búsqueda de contenido.  <br/> |
|Informe de búsqueda quitado  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de informe de exportación de búsqueda de contenido.  <br/> |
|Análisis iniciado de búsqueda de contenido  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Los resultados de una búsqueda de contenido se prepararon para el análisis en Advanced eDiscovery.  <br/> |
|Búsqueda de contenido iniciada  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Se inició una búsqueda de contenido. Al crear o cambiar una búsqueda de contenido mediante la GUI Microsoft 365 centro de cumplimiento, la búsqueda se inicia automáticamente. Si crea o cambia una búsqueda mediante el cmdlet **New-ComplianceSearch** o **Set-ComplianceSearch,** debe ejecutar el cmdlet **Start-ComplianceSearch** para iniciar la búsqueda.  <br/> |
|Exportación iniciada de búsqueda de contenido  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Un usuario exportó los resultados de una búsqueda de contenido.  <br/> |
|Informe de exportación iniciado  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Un usuario exportó un informe de búsqueda de contenido.  <br/> |
|Búsqueda de contenido detenida  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Un usuario detuvo una búsqueda de contenido.  <br/> |
|(ninguno)|CaseViewed|Get-ComplianceCase|Un usuario ha visto la lista de casos en la página **eDiscovery** principal o en la página **Advanced eDiscovery** en el centro de cumplimiento o ejecutando el cmdlet Get-ComplianceCase web.|
|(ninguno)|SearchViewed|Get-ComplianceSearch|Un usuario ha visto la lista en  búsquedas de contenido (enumeradas en la pestaña Búsquedas) en el centro de cumplimiento o ejecutando el cmdlet. Esta actividad también se registra cuando un usuario ve la lista de búsquedas de contenido asociadas con un caso de exhibición de documentos electrónicos (haciendo clic en la pestaña Búsquedas en un caso) o ejecutando el comando **Get-ComplianceSearch -Case.** |
|(ninguno)|ViewedSearchExported|Get-ComplianceSearchAction -Export|Un usuario ha visto la lista de trabajos  de exportación de búsqueda de contenido (enumerados en la pestaña Exportaciones) en el centro de cumplimiento o ejecutando el cmdlet. Esta actividad también se registra cuando un usuario ve la lista de  trabajos de exportación en un caso de exhibición de documentos electrónicos (enumerado en la pestaña Exportaciones en un caso) o ejecutando el comando **Get-ComplianceSearchAction -Case -Export.**|
|(ninguno)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|Un usuario obtiene una vista previa de los resultados de una búsqueda de contenido en el centro de cumplimiento o ejecutando el cmdlet.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Actividades de eDiscovery avanzado

En la tabla siguiente se describen las Advanced eDiscovery registradas en el registro de auditoría. Estas actividades se pueden usar para ayudarle a realizar un seguimiento de la progresión de la actividad en un Advanced eDiscovery caso.

|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Agregar datos a otro conjunto de revisión|AddWorkingSetQueryToWorkingSet|El usuario ha agregado documentos de un conjunto de revisiones a un conjunto de revisiones diferente.|
|Datos agregados a otro conjunto de revisión|AddQueryToWorkingSet|El usuario agregó los resultados de una búsqueda de contenido asociada con un caso de eDiscovery avanzado a un conjunto de revisiones.|
|Se han agregado datos que no son de Microsoft 365 a un conjunto de revisión|AddNonOffice365DataToWorkingSet|Un usuario ha agregado datos que no son de Microsoft 365 a un conjunto de revisión.|
|Documentos corregidos agregados para revisar el conjunto|AddRemediatedData|El usuario carga documentos que tuvieron errores de indexación corregidos para un conjunto de revisiones.|
|Datos analizados en el conjunto de revisiones|RunAlgo|El usuario ejecuta el análisis en los documentos de un conjunto de revisiones.|
|Documento anotados en el conjunto de revisiones|AnnotateDocument|El usuario anotó un documento en un conjunto de revisiones. La anotación incluye contenido redactado en un documento.|
|Conjuntos de carga comparados|LoadComparisonJob|El usuario comparó dos conjuntos de carga distintos en un conjunto de revisiones. Un conjunto de carga es cuando los datos de una búsqueda de contenido asociados al caso se agregan a un conjunto de revisiones.|
|Documentos redactados convertidos en PDF|BurnJob|El usuario convirtió todos los documentos redactados en un conjunto de revisión en archivos PDF.|
|Creado el conjunto de revisiones|CreateWorkingSet|El usuario creó un conjunto de revisiones.|
|Conjunto de búsqueda de revisiones creado|CreateWorkingSetSearch|El usuario creó una consulta de búsqueda para buscar en los documentos de un conjunto de revisiones.|
|Etiqueta creada|CreateTag|El usuario creó un grupo de etiquetas en un conjunto de revisiones. Un grupo de etiquetas puede contener una o más etiquetas pequeñas. Las etiquetas se usan para etiquetar documentos en el conjunto de revisiones.|
|Conjunto de búsqueda de revisiones creado|DeleteWorkingSetSearch|El usuario eliminó una consulta de búsqueda en un conjunto de revisiones.|
|Etiquetas eliminadas|DeleteTag|El usuario eliminó un grupo de etiquetas en un conjunto de revisiones.|
|Documento descargado|DownloadDocument|El usuario ha descargado un documento de un conjunto de revisiones.|
|Etiqueta editada|UpdateTag|El usuario cambió una etiqueta en un conjunto de revisiones.|
|Documentos exportados desde un conjunto de revisión|ExportJob|Documentos de usuario exportados desde un conjunto de revisión.|
|Configuración de carcaza modificados|UpdateCaseSettings|Los usuarios modificaron la configuración de una carcaza. Las opciones de configuración de carcazas incluyen información de casos, permisos de acceso y configuraciones que controlan el comportamiento de búsqueda y análisis.|
|Conjunto de búsqueda de revisiones modificado|UpdateWorkingSetSearch|El usuario editó una consulta de búsqueda en un conjunto de revisiones.|
|Conjunto de búsqueda de revisiones previstas|PreviewWorkingSetSearch|Usuario obtiene una vista previa de los resultados de una consulta de búsqueda en un conjunto de revisiones.|
|Documentos erróneos corregidos|ErrorRemediationJob|El usuario corrige los archivos que contienen errores de escritura..|
|Documento etiquetado|TagFiles|El usuario etiquetó un documento en un conjunto de revisiones.|
|Resultados etiquetados de una consulta|TagJob|EL usuario etiqueta todos los documentos que coinciden con los criterios de la consulta de búsqueda en un conjunto de revisiones.|
|Documento anotados en el conjunto de revisiones|ViewDocument|El usuario visualizó un documento en un conjunto de revisiones.|
|||

## <a name="ediscovery-cmdlet-activities"></a>Actividades del cmdlet eDiscovery

En la tabla siguiente se enumeran los registros de registro de auditoría del cmdlet que se registran cuando un administrador o usuario realiza una actividad relacionada con la exhibición de documentos electrónicos mediante el centro de cumplimiento o ejecutando el cmdlet correspondiente en PowerShell del Centro de seguridad & cumplimiento. La información detallada del registro de auditoría es diferente para las actividades de cmdlet que se enumeran en esta tabla y las actividades de exhibición de documentos electrónicos descritas en la sección anterior.
  
Como se ha indicado anteriormente, las actividades del cmdlet eDiscovery tardan hasta 24 horas en aparecer en los resultados de búsqueda del registro de auditoría.
  
> [!TIP]
> Los cmdlets de la **columna Operación** de la tabla siguiente están vinculados al tema de ayuda del cmdlet correspondiente en TechNet. Vaya al tema de ayuda del cmdlet para obtener una descripción de los parámetros disponibles para cada cmdlet. El parámetro y el valor del parámetro que se usaron con un cmdlet se incluyen en la entrada del registro de auditoría para cada actividad del cmdlet de exhibición de documentos electrónicos que se registra. 
  
|**Nombre descriptivo**|**Operación (cmdlet)**|**Descripción**|
|:-----|:-----|:-----|
|Retención creada en caso de exhibición de documentos electrónicos  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |Se creó una retención para un caso de exhibición de documentos electrónicos. Se puede crear una retención con o sin especificar un origen de contenido. Si se especifican orígenes de contenido, se identificarán en la entrada del registro de auditoría.  <br/> |
|Retención eliminada del caso de exhibición de documentos electrónicos  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |Se eliminó una retención asociada a un caso de exhibición de documentos electrónicos. Al eliminar una retención, se liberan todas las ubicaciones de contenido de la retención. Al eliminar la retención, también se eliminan las reglas de retención de mayúsculas y minúsculas asociadas con la retención (vea **Remove-CaseHoldRule** a continuación).  <br/> |
|Retención modificada en caso de exhibición de documentos electrónicos  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |Se cambió una retención asociada a una exhibición de documentos electrónicos. Los posibles cambios incluyen agregar o quitar ubicaciones de contenido o desactivar (deshabilitar) la retención.  <br/> |
|Consulta de búsqueda creada para retención de casos de exhibición de documentos electrónicos  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |Se creó una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos.  <br/> |
|Consulta de búsqueda eliminada para retención de casos de exhibición de documentos electrónicos  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |Se eliminó una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos. La eliminación de la consulta de la retención suele ser el resultado de eliminar una retención. Cuando se elimina una retención o una consulta de retención, se liberan las ubicaciones de contenido que estaban en espera.  <br/> |
|Consulta de búsqueda modificada para retención de casos de exhibición de documentos electrónicos  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |Se cambió una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos. Los posibles cambios incluyen la edición de la consulta o el intervalo de fechas de una retención basada en consulta.  <br/> |
|Caso de exhibición de documentos electrónicos creado  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |Se creó un caso de exhibición de documentos electrónicos. Cuando se crea un caso, solo tiene que darle un nombre. Otras tareas relacionadas con casos, como agregar miembros, crear retenciones y crear búsquedas de contenido asociadas con el caso, darán como resultado eventos adicionales que se registran.  <br/> |
|Caso de exhibición de documentos electrónicos eliminado  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |Se eliminó un caso de exhibición de documentos electrónicos. Cualquier retención asociada con el caso debe quitarse antes de que se pueda eliminar el caso.  <br/> |
|Caso de exhibición de documentos electrónicos modificado  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |Se cambió un caso de exhibición de documentos electrónicos. Los cambios incluyen cerrar un caso abierto o volver a abrir un caso cerrado.  <br/> |
|Miembro agregado al caso de exhibición de documentos electrónicos  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |Se agregó un usuario como miembro de un caso de exhibición de documentos electrónicos. Como miembro de un caso, un usuario puede realizar varias tareas relacionadas con casos en función de si se les han asignado los permisos necesarios.  <br/> |
|Miembro eliminado del caso de exhibición de documentos electrónicos  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |Un usuario se quitó como miembro de un caso de exhibición de documentos electrónicos.  <br/> |
|Pertenencia a casos de exhibición de documentos electrónicos modificados  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |Se cambió la lista de pertenencia de un caso de exhibición de documentos electrónicos. Esta actividad se registra cuando todos los miembros se reemplazan por un grupo de nuevos usuarios. Si se agrega o quita un solo miembro, se registra la operación **Add-ComplianceCaseMember** o **Remove-ComplianceCaseMember.**  <br/> |
|Búsqueda de contenido creada  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |Se creó una nueva búsqueda de contenido.  <br/> |
|Búsqueda de contenido eliminado  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |Se eliminó una búsqueda de contenido existente.  <br/> |
|Búsqueda de contenido modificado  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |Se ha cambiado una búsqueda de contenido existente. Los cambios pueden incluir agregar o quitar ubicaciones de contenido que se buscan y editar la consulta de búsqueda.  <br/> |
|Búsqueda de contenido iniciada  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |Se inició una búsqueda de contenido. Al crear o cambiar una búsqueda de contenido mediante la GUI del centro de cumplimiento, la búsqueda se inicia automáticamente. Si crea o cambia una búsqueda mediante el cmdlet **New-ComplianceSearch** o **Set-ComplianceSearch,** debe ejecutar el cmdlet **Start-ComplianceSearch** para iniciar la búsqueda.  <br/> |
|Búsqueda de contenido detenida  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |Se detuvo una búsqueda de contenido que se estaba ejecutando.  <br/> |
|Acción de búsqueda de contenido creado  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |Se creó una acción de búsqueda de contenido. Las acciones de búsqueda de contenido incluyen la vista previa de los resultados de búsqueda, la exportación de resultados de búsqueda, la preparación de resultados de búsqueda para el análisis en Advanced eDiscovery y la eliminación permanente de elementos que coincidan con los criterios de búsqueda de una búsqueda de contenido.  <br/> |
|Acción de búsqueda de contenido eliminado  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |Se eliminó una acción de búsqueda de contenido.  <br/> |
|Filtro de permisos de búsqueda creado  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |Se creó un filtro de permisos de búsqueda.  <br/> |
|Filtro de permisos de búsqueda eliminados  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |Se eliminó un filtro de permisos de búsqueda.  <br/> |
|Filtro de permisos de búsqueda modificado  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |Se cambió un filtro de permisos de búsqueda.  <br/> |
|Administrador de exhibición de documentos electrónicos creado  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |Se agregó un usuario como administrador de exhibición de documentos electrónicos en la organización.  <br/> |
|Administrador de exhibición de documentos electrónicos eliminado  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |Se eliminó un administrador de exhibición de documentos electrónicos de la organización.  <br/> |
|Pertenencia de administrador de exhibición de documentos electrónicos modificada  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |Se cambió la lista de administradores de exhibición de documentos electrónicos de la organización. Esta actividad se registra cuando la lista de administradores de exhibición de documentos electrónicos se reemplaza por un grupo de nuevos usuarios. Si se agrega o quita un solo usuario, se registra la operación **Add-eDiscoveryCaseAdmin** o **Remove-eDiscoveryCaseAdmin.**  <br/> |

## <a name="detailed-properties-for-ediscovery-activities"></a>Propiedades detalladas para actividades de exhibición de documentos electrónicos

En la tabla siguiente se describen  las propiedades  que se incluyen al hacer clic en Más información en la página Detalles de una actividad de exhibición de documentos electrónicos que aparece en los resultados de la búsqueda. Estas propiedades también se incluyen en el archivo CSV al exportar los resultados de búsqueda del registro de auditoría. Un registro de registro de auditoría para una actividad de exhibición de documentos electrónicos no incluirá todas las propiedades detalladas que se enumeran a continuación.
  
> [!TIP]
> Al exportar los resultados de búsqueda, el archivo CSV contiene una columna denominada **Detail**, que contiene las propiedades detalladas descritas en la tabla siguiente en una propiedad de varios valores. Puede usar la característica Power Query en Excel dividir esta columna en varias columnas para que cada propiedad tenga su propia columna. Esto le permitirá ordenar y filtrar en una o varias de estas propiedades. Para obtener más información, vea la sección "Exportar los resultados de búsqueda a un archivo" [en Buscar en el registro de auditoría.](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file) 
  
|**Propiedad**|**Descripción**|
|:-----|:-----|
|Case  <br/> |La identidad (GUID) del caso de exhibición de documentos electrónicos que se creó, cambió o eliminó.  <br/> |
|ClientApplication  <br/> |Las actividades del cmdlet eDiscovery tienen un valor de **EMC** para esta propiedad. Esto indica que la actividad se realizó con la GUI del centro de cumplimiento o ejecutando el cmdlet en PowerShell.  <br/> |
|ClientIP  <br/> |La dirección IP del dispositivo que se ha usado cuando la actividad se ha registrado. La dirección IP se muestra en el formato de dirección IPv4 o IPv6.  <br/> |
|ClientRequestId  <br/> | Para las actividades de exhibición de documentos electrónicos, esta propiedad suele estar en blanco.  <br/> |
|CmdletVersion  <br/> |Número de compilación de la versión del centro de cumplimiento que se ejecuta en la organización.  <br/> |
|CreationTime  <br/> |Fecha y hora en la hora universal coordinada (UTC) cuando se completó la actividad de exhibición de documentos electrónicos.  <br/> |
|EffectiveOrganization  <br/> |Nombre de la organización de Microsoft 365.  <br/> |
|ExchangeLocations  <br/> |Los Exchange Online que se incluyen en una búsqueda de contenido o se colocan en espera en un caso de exhibición de documentos electrónicos.  <br/> |
|Exclusiones  <br/> |Ubicaciones de buzones o sitios que se excluyen de una búsqueda de contenido o de una retención en un caso de exhibición de documentos electrónicos.  <br/> |
|ExtendedProperties  <br/> |Propiedades adicionales de una búsqueda de contenido, una acción de búsqueda de contenido o retención en un caso de exhibición de documentos electrónicos, como el GUID del objeto y los parámetros de cmdlet y cmdlet correspondientes que se usaron cuando se realizó la actividad.  <br/> |
|Id  <br/> |El identificador de la entrada del informe. El identificador identifica de forma única la entrada del registro de auditoría.  <br/> |
|NonPIIParameters  <br/> |Una lista de los parámetros (sin valores) que se usaron con el cmdlet identificado en la propiedad Operation. Los parámetros enumerados en esta propiedad son los mismos que los enumerados en la propiedad Parameters.  <br/> |
|ObjectId  <br/> |Guid o nombre del objeto (por ejemplo, una búsqueda de contenido o un caso de exhibición de documentos electrónicos) que la actividad enumera en la propiedad Operation creó, cambió o eliminó. Este objeto también se identifica en la columna Elemento de los resultados de búsqueda del registro de auditoría.  <br/> |
|ObjectType  <br/> |El tipo de objeto de exhibición de documentos electrónicos que el usuario creó, eliminó o modificó; por ejemplo, una acción de búsqueda de contenido (vista previa, exportación o purga), un caso de exhibición de documentos electrónicos o una búsqueda de contenido.  <br/> |
|Operación  <br/> |Nombre de la operación que corresponde a la actividad de exhibición de documentos electrónicos que se realizó.  <br/> |
|OrganizationId  <br/> |GUID de la Microsoft 365 organización.  <br/> |
|Parameters  <br/> |Nombre y valor de los parámetros que se usaron con el cmdlet correspondiente.  <br/> |
|PublicFolderLocations  <br/> |Las ubicaciones de carpetas públicas Exchange Online que se incluyen en una búsqueda de contenido o se colocan en espera en un caso de exhibición de documentos electrónicos.  <br/> |
|Consulta  <br/> |Consulta de búsqueda asociada a la actividad, como una búsqueda de contenido o una retención basada en consulta.  <br/> |
|RecordType  <br/> |El tipo de operación indicado por el registro. El valor **de 18** indica un evento relacionado con una actividad enumerada en la sección actividades [del cmdlet eDiscovery.](#ediscovery-cmdlet-activities) Un valor de **24** indica un evento relacionado con una actividad enumerada en la sección Cómo buscar y ver actividades [de exhibición de documentos electrónicos.](#how-to-search-for-and-view-ediscovery-activities)  <br/> |
|ResultStatus  <br/> |Indica si la acción (especificada en la propiedad Operation) se completó correctamente o no.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica que la actividad era un evento del centro de cumplimiento. Todas las actividades de exhibición de documentos electrónicos tendrán un valor **de 0** para esta propiedad.  <br/> |
|SharepointLocations  <br/> |Los SharePoint online que se incluyen en una búsqueda de contenido o se colocan en espera en un caso de exhibición de documentos electrónicos.  <br/> |
|StartTime  <br/> |Fecha y hora en la hora universal coordinada (UTC) cuando se inició la actividad de exhibición de documentos electrónicos.  <br/> |
|UserId  <br/> |El usuario que realizó la actividad (especificada en la propiedad Operation) que hizo que se registrara el registro. Los registros de actividad de exhibición de documentos electrónicos realizados por cuentas del sistema (como NT AUTHORITY\SYSTEM) también se incluyen en el registro de auditoría.  <br/> |
|UserKey  <br/> |Un id. alternativo para el usuario identificado en la propiedad id. de usuario. Para las actividades de exhibición de documentos electrónicos, el valor de esta propiedad suele ser el mismo que la propiedad UserId.  <br/> |
|UserServicePlan  <br/> |La suscripción que usa la organización. Para las actividades de exhibición de documentos electrónicos, esta propiedad suele estar en blanco.  <br/> |
|UserType  <br/> |El tipo de usuario que llevó a cabo la operación. Los siguientes valores indican el tipo de usuario.  <br/> 0 Un usuario normal. 2 Un administrador de la organización. 3 Una cuenta de sistema de centro de datos o administrador de centros de datos de Microsoft. 4 Una cuenta del sistema. 5 Una aplicación. 6 Una entidad de servicio. |
|Versión  <br/> |Indica el número de versión de la actividad (identificada por la propiedad Operation) que se registra.  <br/> |
|Carga de trabajo  <br/> |El servicio donde se produjo la actividad. Para las actividades de exhibición de documentos electrónicos, el valor **es SecurityComplianceCenter**.  <br/> |
