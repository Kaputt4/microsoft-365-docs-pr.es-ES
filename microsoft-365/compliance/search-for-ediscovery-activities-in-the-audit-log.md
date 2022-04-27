---
title: Buscar actividades de eDiscovery en el registro de auditoría
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Obtenga información sobre los eventos que se registran cuando los usuarios asignados a los permisos de exhibición de documentos electrónicos realizan tareas de búsqueda de contenido, eDiscovery (estándar) y eDiscovery (Premium) en el portal de cumplimiento de Microsoft Purview.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6a11c8a939954b7319b88b45ea8f0d43b1b72442
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090869"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Buscar actividades de eDiscovery en el registro de auditoría

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Las actividades relacionadas con la búsqueda de contenido y eDiscovery (para microsoft Purview eDiscovery (estándar) y microsoft Purview eDiscovery (Premium)) que se realizan en el portal de cumplimiento de Microsoft Purview o mediante la ejecución de los cmdlets de PowerShell correspondientes se registran en el registro de auditoría. Los eventos se registran cuando los administradores o administradores de eDiscovery (o los permisos de exhibición de documentos electrónicos asignados por el usuario) realizan las siguientes tareas de búsqueda de contenido y exhibición de contenido (estándar) en el portal de cumplimiento:
  
- Creación y administración de casos principales y eDiscovery (Premium)

- Creación, inicio y edición de búsquedas de contenido

- Realizar acciones de búsqueda, como obtener una vista previa, exportar y eliminar resultados de búsqueda

- Administración de custodios y conjuntos de revisión en eDiscovery (Premium)

- Configuración del filtrado de permisos para la búsqueda de contenido

- Administrar el rol de administrador de la exhibición de documentos electrónicos
  
Para obtener más información sobre cómo buscar en el registro de auditoría, los permisos necesarios y exportar los resultados de búsqueda, consulte [Búsqueda en el registro de auditoría en el portal de cumplimiento](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Búsqueda y visualización de actividades de exhibición de documentos electrónicos

Actualmente, tiene que hacer algunas cosas específicas para ver las actividades de exhibición de documentos electrónicos en el registro de auditoría. Aquí se muestra cómo hacerlo.
  
1. Vaya a <https://compliance.microsoft.com> e inicie sesión con su cuenta profesional o educativa.

2. En el panel de navegación izquierdo del portal de cumplimiento, haga clic en **Auditar**.

3. En la lista desplegable **Actividades**, en **actividades de exhibición de documentos electrónicos** o **actividades de exhibición de documentos electrónicos (Premium),** haga clic en una o varias actividades para buscar.

    > [!NOTE]
    > La lista desplegable **Actividades** también incluye un grupo de actividades denominadas **actividades de cmdlet de eDiscovery** que devolverán registros del registro de auditoría de cmdlets.
  
4. Seleccione un intervalo de fecha y hora para mostrar los eventos de exhibición de documentos electrónicos que se produjeron en ese período.

5. En el cuadro **Usuarios** , seleccione uno o varios usuarios para mostrar los resultados de búsqueda. Deje este cuadro en blanco para devolver entradas para todos los usuarios.

6. Haga clic en **Búsqueda** para ejecutar la búsqueda mediante sus criterios de búsqueda. 

7. Una vez que se muestran los resultados de la búsqueda, puede hacer clic en **Filtrar resultados** para filtrar u ordenar los registros de actividad resultantes. Desafortunadamente, no puede usar el filtrado para excluir explícitamente determinadas actividades. 

8. Para ver detalles sobre una actividad, haga clic en el registro de actividad en la lista de resultados de búsqueda. 

    Se muestra una página desplegable **Detalles** que contiene las propiedades detalladas del registro de eventos. Para mostrar detalles adicionales, haga clic en **Más información**. Para obtener una descripción de estas propiedades, vea la sección [Propiedades detalladas para actividades de exhibición de documentos electrónicos](#detailed-properties-for-ediscovery-activities) .

9. Si lo desea, puede exportar los resultados de la búsqueda de registros de auditoría a un archivo CSV y, a continuación, usar la característica Excel Power Query para dar formato y filtrar estos registros. Para más información, consulte[Exportar, configurar y ver registros de auditoría](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>Actividades de eDiscovery

En la tabla siguiente se describen las actividades búsqueda de contenido y exhibición de documentos electrónicos (estándar) que se registran cuando un administrador o administrador de eDiscovery realiza una actividad relacionada con eDiscovery mediante el portal de cumplimiento. Algunas actividades realizadas en eDiscovery (Premium) pueden devolverse al buscar actividades en esta lista.
  
> [!NOTE]
> Las actividades de eDiscovery descritas en esta sección proporcionan información similar a las actividades de cmdlet de eDiscovery descritas en la sección siguiente. Se recomienda usar las actividades de exhibición de documentos electrónicos que se describen en esta sección, ya que aparecerán en los resultados de la búsqueda del registro de auditoría en un plazo de 30 minutos. Las actividades de cmdlet de eDiscovery pueden tardar hasta 24 horas en aparecer en los resultados de la búsqueda de registros de auditoría.
  
|**Nombre descriptivo**|**Operación**|**Cmdlet correspondiente**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Se ha agregado un miembro al caso de eDiscovery  <br/> |CaseMemberAdded  <br/> |Add-ComplianceCaseMember  <br/> |Se agregó un usuario como miembro de un caso de exhibición de documentos electrónicos. Como miembro de un caso, un usuario puede realizar varias tareas relacionadas con casos en función de si se le han asignado los permisos necesarios.  <br/> |
|Búsqueda de contenido modificada  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |Se ha cambiado una búsqueda de contenido existente. Los cambios pueden incluir la adición o eliminación de ubicaciones de contenido o la edición de la consulta de búsqueda.  <br/> |
|Se ha cambiado la pertenencia al administrador de eDiscovery  <br/> |CaseAdminUpdated  <br/> |Update-eDiscoveryCaseAdmin  <br/> |Se ha cambiado la lista de administradores de exhibición de documentos electrónicos de la organización. Esta actividad se registra cuando la lista de administradores de exhibición de documentos electrónicos se reemplaza por un grupo de nuevos usuarios. Si se agrega o quita un único usuario, se registra la operación CaseAdminAdded.  <br/> |
|Se ha cambiado el caso de eDiscovery  <br/> |CaseUpdated  <br/> |Set-ComplianceCase  <br/> |Se cambió un caso de eDiscovery. Los cambios incluyen el cierre de un caso abierto o la reapertura de un caso cerrado.  <br/> |
|Se ha cambiado la pertenencia a casos de exhibición de documentos electrónicos  <br/> |CaseMemberUpdated  <br/> |Update-ComplianceCaseMember  <br/> |Se cambió la lista de pertenencia de un caso de exhibición de documentos electrónicos. Esta actividad se registra cuando todos los miembros se reemplazan por un grupo de nuevos usuarios. Si se agrega o quita un solo miembro, se registra la operación CaseMemberAdded o CaseMemberRemoved.  <br/> |
|Filtro de permisos de búsqueda modificado  <br/> |SearchPermissionUpdated  <br/> |Set-ComplianceSecurityFilter  <br/> |Se ha cambiado un filtro de permisos de búsqueda.  <br/> |
|Se ha cambiado la consulta de búsqueda para la suspensión de mayúsculas y minúsculas de eDiscovery  <br/> |HoldUpdated  <br/> |Set-CaseHoldRule  <br/> |Se cambió una suspensión basada en consultas asociada a un caso de exhibición de documentos electrónicos. Los posibles cambios incluyen la edición de la consulta o el intervalo de fechas para una retención basada en consultas.  <br/> |
|Elemento de vista previa de búsqueda de contenido descargado  <br/> |PreviewItemDownloaded  <br/> |N/D  <br/> |Un usuario descargó un elemento en su equipo local (haciendo clic en el vínculo **Descargar elemento original** ) al obtener una vista previa de los resultados de la búsqueda.  <br/> |
|Elemento de vista previa de búsqueda de contenido enumerado  <br/> |PreviewItemListed  <br/> |N/D  <br/> |Un usuario ha hecho clic en **Vista previa de los resultados de la búsqueda** para mostrar la página de resultados de búsqueda de vista previa, que muestra hasta 1000 elementos a partir de los resultados de una búsqueda.  <br/> |
|Elemento de vista previa de búsqueda de contenido visto  <br/> |PreviewItemRendered  <br/> |N/D  <br/> |Un administrador de eDiscovery ha visto un elemento haciendo clic en él al obtener una vista previa de los resultados de la búsqueda.  <br/> |
|Búsqueda de contenido creada  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |Se creó una nueva búsqueda de contenido.  <br/> |
|Administrador de eDiscovery creado  <br/> |CaseAdminAdded  <br/> |Add-eDiscoveryCaseAdmin  <br/> |Se agregó un usuario como administrador de exhibición de documentos electrónicos en la organización.  <br/> |
|Caso de eDiscovery creado  <br/> |CaseAdded  <br/> |New-ComplianceCase  <br/> |Se creó un caso de eDiscovery. Cuando se crea un caso, solo tiene que darle un nombre. Otras tareas relacionadas con casos, como agregar miembros, crear retenciones y crear búsquedas de contenido asociadas al caso, provocan que se registren eventos adicionales.  <br/> |
|Filtro de permisos de búsqueda creado  <br/> |SearchPermissionCreated  <br/> |New-ComplianceSecurityFilter  <br/> |Se creó un filtro de permisos de búsqueda.  <br/> |
|Consulta de búsqueda creada para la suspensión de casos de eDiscovery  <br/> |HoldCreated  <br/> |New-CaseHoldRule  <br/> |Se creó una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos.  <br/> |
|Búsqueda de contenido eliminado  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |Se eliminó una búsqueda de contenido existente.  <br/> |
|Administrador de eDiscovery eliminado  <br/> |CaseAdminRemoved  <br/> |Remove-eDiscoveryCaseAdmin  <br/> |Se eliminó un administrador de exhibición de documentos electrónicos de la organización.  <br/> |
|Caso de eDiscovery eliminado  <br/> |CaseRemoved  <br/> |Remove-ComplianceCase  <br/> |Se eliminó un caso de eDiscovery. Cualquier retención asociada al caso debe quitarse antes de que se pueda eliminar el caso.  <br/> |
|Filtro de permisos de búsqueda eliminados  <br/> |SearchPermissionRemoved  <br/> |Remove-ComplianceSecurityFilter  <br/> |Se eliminó un filtro de permisos de búsqueda.  <br/> |
|Consulta de búsqueda eliminada para la suspensión de casos de eDiscovery  <br/> |HoldRemoved  <br/> |Remove-CaseHoldRule  <br/> |Se eliminó una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos. La eliminación de la consulta de la suspensión suele ser el resultado de eliminar una suspensión. Cuando se elimina una consulta de suspensión o suspensión, se liberan las ubicaciones de contenido que estaban en espera.  <br/> |
|Exportación descargada de la búsqueda de contenido  <br/> |SearchExportDownloaded  <br/> |N/D  <br/> |Un usuario descargó los resultados de una búsqueda de contenido en su equipo local. Se debe iniciar una **exportación iniciada de la actividad de búsqueda de contenido** antes de que se puedan descargar los resultados de la búsqueda.  <br/> |
|Resultados en vista previa de la búsqueda de contenido  <br/> |SearchPreviewed  <br/> |N/D  <br/> |Un usuario ha obtenido una vista previa de los resultados de una búsqueda de contenido.  <br/> |
|Resultados purgados de la búsqueda de contenido  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |Un usuario purgue los resultados de una búsqueda de contenido mediante la ejecución del comando **New-ComplianceSearchAction -Purge** .  <br/> |
|Se ha quitado el análisis de la búsqueda de contenido.  <br/> |RemovedSearchResultsSentToZoom  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de preparación de búsqueda de contenido (para preparar los resultados de búsqueda para eDiscovery (Premium)). Si la acción de preparación tenía menos de dos semanas de antigüedad, los resultados de búsqueda que se prepararon para eDiscovery (Premium) se eliminaron del área de almacenamiento de Microsoft Azure. Si la acción de preparación era anterior a 2 semanas, este evento indica que solo se eliminó la acción de preparación correspondiente.  <br/> |
|Se ha quitado la exportación de la búsqueda de contenido  <br/> |RemovedSearchExported  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de exportación de búsqueda de contenido. Si la acción de exportación tenía menos de dos semanas de antigüedad, se eliminaron los resultados de búsqueda que se cargaron en el área de almacenamiento Microsoft Azure. Si la acción de exportación era anterior a 2 semanas, este evento indica que solo se eliminó la acción de exportación correspondiente.  <br/> |
|Se quitó el miembro del caso de eDiscovery  <br/> |CaseMemberRemoved  <br/> |Remove-ComplianceCaseMember  <br/> |Un usuario se quitó como miembro de un caso de exhibición de documentos electrónicos.  <br/> |
|Se han quitado los resultados de la vista previa de la búsqueda de contenido  <br/> |RemovedSearchPreviewed  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de vista previa de búsqueda de contenido.  <br/> |
|Acción de purga eliminada realizada en la búsqueda de contenido  <br/> |RemovedSearchResultsPurged  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de purga de búsqueda de contenido.  <br/> |
|Informe de búsqueda eliminado  <br/> |SearchReportRemoved  <br/> |Remove-ComplianceSearchAction  <br/> |Se eliminó una acción de informe de exportación de búsqueda de contenido.  <br/> |
|Análisis iniciado de la búsqueda de contenido  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |Los resultados de una búsqueda de contenido se prepararon para su análisis en eDiscovery (Premium).  <br/> |
|Búsqueda de contenido iniciada  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |Se inició una búsqueda de contenido. Al crear o cambiar una búsqueda de contenido mediante el portal de cumplimiento, la búsqueda se inicia automáticamente.<br/> |
|Exportación iniciada de la búsqueda de contenido  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |Un usuario exportó los resultados de una búsqueda de contenido.  <br/> |
|Informe de exportación iniciado  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |Un usuario exportó un informe de búsqueda de contenido.  <br/> |
|Búsqueda de contenido detenida  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |Un usuario detuvo una búsqueda de contenido.  <br/> |
|(ninguno)|CaseViewed|Get-ComplianceCase|Un usuario ha visto un caso de exhibición de documentos electrónicos (estándar) en el centro de cumplimiento. El registro de auditoría de este evento incluye el nombre del caso que se ha visto. |
|(ninguno)|SearchViewed|Get-ComplianceSearch|Un usuario ha visto una búsqueda de contenido en el centro de cumplimiento accediendo a la búsqueda en la pestaña **Búsquedas** en un caso de exhibición de documentos electrónicos (estándar) o accediendo a ella en la página **Búsqueda de contenido** . El registro de auditoría de este evento incluye la identidad de la búsqueda que se ha visto.|
|(ninguno)|ViewedSearchExported|Get-ComplianceSearchAction -Export|Un usuario ha visto una exportación de búsqueda de contenido en el centro de cumplimiento accediendo a la exportación en la pestaña **Exportaciones** de la página **Búsqueda de contenido** . Esta actividad también se registra cuando un usuario ve una exportación asociada a un caso de exhibición de documentos electrónicos (estándar).|
|(ninguno)|ViewedSearchPreviewed|Get-ComplianceSearchAction -Preview|Un usuario ha obtenido una vista previa de los resultados de una búsqueda de contenido en el centro de cumplimiento. Esta actividad también se registra cuando un usuario obtiene una vista previa de los resultados de una búsqueda asociada a un caso de exhibición de documentos electrónicos (estándar).|
|||||
  
## <a name="ediscovery-premium-activities"></a>Actividades de eDiscovery (Premium)

En la tabla siguiente se describen las actividades de eDiscovery (Premium) registradas en el registro de auditoría. Estas actividades se pueden usar para ayudarle a realizar un seguimiento de la progresión de la actividad en un caso de exhibición de documentos electrónicos (Premium).

|**Nombre descriptivo**|**Operación**|**Descripción**|
|:-----|:-----|:-----|
|Agregar datos a otro conjunto de revisión|AddWorkingSetQueryToWorkingSet|El usuario ha agregado documentos de un conjunto de revisiones a un conjunto de revisiones diferente.|
|Datos agregados a otro conjunto de revisión|AddQueryToWorkingSet|El usuario agregó los resultados de búsqueda de una búsqueda de contenido asociada a un caso de exhibición de documentos electrónicos (Premium) a un conjunto de revisión.|
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

## <a name="ediscovery-cmdlet-activities"></a>Actividades de cmdlet de eDiscovery

En la tabla siguiente se enumeran los registros de auditoría de cmdlets que se registran cuando un administrador o usuario realiza una actividad relacionada con eDiscovery mediante el centro de cumplimiento o mediante la ejecución del cmdlet correspondiente en PowerShell del Centro de seguridad & cumplimiento. La información detallada del registro de auditoría es diferente para las actividades de cmdlet enumeradas en esta tabla y las actividades de exhibición de documentos electrónicos descritas en la sección anterior.
  
Como se indicó anteriormente, las actividades de cmdlet de eDiscovery pueden tardar hasta 24 horas en aparecer en los resultados de la búsqueda del registro de auditoría.
  
> [!TIP]
> Los cmdlets de la columna **Operation** de la tabla siguiente están vinculados al tema de ayuda de cmdlet correspondiente en TechNet. Vaya al tema de ayuda del cmdlet para obtener una descripción de los parámetros disponibles para cada cmdlet. El parámetro y el valor del parámetro que se usaron con un cmdlet se incluyen en la entrada de registro de auditoría para cada actividad de cmdlet de eDiscovery que se registra. 
  
|**Nombre descriptivo**|**Operación (cmdlet)**|**Descripción**|
|:-----|:-----|:-----|
|Suspensión creada en el caso de eDiscovery  <br/> |[New-CaseHoldPolicy](/powershell/module/exchange/new-caseholdpolicy) <br/> |Se creó una suspensión para un caso de exhibición de documentos electrónicos. Se puede crear una suspensión con o sin especificar un origen de contenido. Si se especifican orígenes de contenido, se identificarán en la entrada del registro de auditoría.  <br/> |
|Suspensión eliminada del caso de eDiscovery  <br/> |[Remove-CaseHoldPolicy](/powershell/module/exchange/remove-caseholdpolicy) <br/> |Se eliminó una suspensión asociada a un caso de exhibición de documentos electrónicos. Al eliminar una suspensión, se liberan todas las ubicaciones de contenido de la suspensión. La eliminación de la suspensión también da como resultado la eliminación de las reglas de suspensión de casos asociadas a la suspensión (vea **Remove-CaseHoldRule** a continuación).  <br/> |
|Se ha cambiado la suspensión en el caso de eDiscovery  <br/> |[Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) <br/> |Se ha cambiado una suspensión asociada a una exhibición de documentos electrónicos. Los posibles cambios incluyen agregar o quitar ubicaciones de contenido o desactivar (deshabilitar) la suspensión.  <br/> |
|Consulta de búsqueda creada para la suspensión de casos de eDiscovery  <br/> |[New-CaseHoldRule](/powershell/module/exchange/new-caseholdrule) <br/> |Se creó una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos.  <br/> |
|Consulta de búsqueda eliminada para la suspensión de casos de eDiscovery  <br/> |[Remove-CaseHoldRule](/powershell/module/exchange/remove-caseholdrule) <br/> |Se eliminó una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos. La eliminación de la consulta de la suspensión suele ser el resultado de eliminar una suspensión. Cuando se elimina una consulta de suspensión o suspensión, se liberan las ubicaciones de contenido que estaban en espera.  <br/> |
|Se ha cambiado la consulta de búsqueda para la suspensión de mayúsculas y minúsculas de eDiscovery  <br/> |[Set-CaseHoldRule](/powershell/module/exchange/set-caseholdrule) <br/> |Se cambió una suspensión basada en consultas asociada a un caso de exhibición de documentos electrónicos. Los posibles cambios incluyen la edición de la consulta o el intervalo de fechas para una retención basada en consultas.  <br/> |
|Caso de eDiscovery creado  <br/> |[New-ComplianceCase](/powershell/module/exchange/new-compliancecase) <br/> |Se creó un caso de eDiscovery. Cuando se crea un caso, solo tiene que darle un nombre. Otras tareas relacionadas con casos, como agregar miembros, crear retenciones y crear búsquedas de contenido asociadas al caso, provocan que se registren eventos adicionales.  <br/> |
|Caso de eDiscovery eliminado  <br/> |[Remove-ComplianceCase](/powershell/module/exchange/remove-compliancecase) <br/> |Se eliminó un caso de eDiscovery. Cualquier retención asociada al caso debe quitarse antes de que se pueda eliminar el caso.  <br/> |
|Se ha cambiado el caso de eDiscovery  <br/> |[Set-ComplianceCase](/powershell/module/exchange/set-compliancecase) <br/> |Se cambió un caso de eDiscovery. Los cambios incluyen el cierre de un caso abierto o la reapertura de un caso cerrado.  <br/> |
|Se ha agregado un miembro al caso de eDiscovery  <br/> |[Add-ComplianceCaseMember](/powershell/module/exchange/add-compliancecasemember) <br/> |Se agregó un usuario como miembro de un caso de exhibición de documentos electrónicos. Como miembro de un caso, un usuario puede realizar varias tareas relacionadas con casos en función de si se le han asignado los permisos necesarios.  <br/> |
|Se quitó el miembro del caso de eDiscovery  <br/> |[Remove-ComplianceCaseMember](/powershell/module/exchange/remove-compliancecasemember) <br/> |Un usuario se quitó como miembro de un caso de exhibición de documentos electrónicos.  <br/> |
|Se ha cambiado la pertenencia a casos de exhibición de documentos electrónicos  <br/> |[Update-ComplianceCaseMember](/powershell/module/exchange/update-compliancecasemember) <br/> |Se cambió la lista de pertenencia de un caso de exhibición de documentos electrónicos. Esta actividad se registra cuando todos los miembros se reemplazan por un grupo de nuevos usuarios. Si se agrega o quita un solo miembro, se registra la operación **Add-ComplianceCaseMember** o **Remove-ComplianceCaseMember** .  <br/> |
|Búsqueda de contenido creada  <br/> |[New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch) <br/> |Se creó una nueva búsqueda de contenido.  <br/> |
|Búsqueda de contenido eliminado  <br/> |[Remove-ComplianceSearch](/powershell/module/exchange/remove-compliancesearch) <br/> |Se eliminó una búsqueda de contenido existente.  <br/> |
|Búsqueda de contenido modificada  <br/> |[Set-ComplianceSearch](/powershell/module/exchange/set-compliancesearch) <br/> |Se ha cambiado una búsqueda de contenido existente. Los cambios pueden incluir la adición o eliminación de ubicaciones de contenido que se buscan y la edición de la consulta de búsqueda.  <br/> |
|Búsqueda de contenido iniciada  <br/> |[Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch) <br/> |Se inició una búsqueda de contenido. Al crear o cambiar una búsqueda de contenido mediante la GUI del Centro de cumplimiento, la búsqueda se inicia automáticamente. Si crea o cambia una búsqueda mediante el cmdlet **New-ComplianceSearch** o **Set-ComplianceSearch** , debe ejecutar el cmdlet **Start-ComplianceSearch** para iniciar la búsqueda.  <br/> |
|Búsqueda de contenido detenida  <br/> |[Stop-ComplianceSearch](/powershell/module/exchange/stop-compliancesearch) <br/> |Se detuvo una búsqueda de contenido que se estaba ejecutando.  <br/> |
|Acción de búsqueda de contenido creada  <br/> |[New-ComplianceSearchAction](/powershell/module/exchange/new-compliancesearchaction) <br/> |Se creó una acción de búsqueda de contenido. Las acciones de búsqueda de contenido incluyen la vista previa de los resultados de búsqueda, la exportación de resultados de búsqueda, la preparación de los resultados de búsqueda para su análisis en eDiscovery (Premium) y la eliminación permanente de elementos que coinciden con los criterios de búsqueda de una búsqueda de contenido.  <br/> |
|Acción de búsqueda de contenido eliminado  <br/> |[Remove-ComplianceSearchAction](/powershell/module/exchange/remove-compliancesearchaction) <br/> |Se eliminó una acción de búsqueda de contenido.  <br/> |
|Filtro de permisos de búsqueda creado  <br/> |[New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) <br/> |Se creó un filtro de permisos de búsqueda.  <br/> |
|Filtro de permisos de búsqueda eliminados  <br/> |[Remove-ComplianceSecurityFilter](/powershell/module/exchange/remove-compliancesecurityfilter) <br/> |Se eliminó un filtro de permisos de búsqueda.  <br/> |
|Filtro de permisos de búsqueda modificado  <br/> |[Set-ComplianceSecurityFilter](/powershell/module/exchange/set-compliancesecurityfilter) <br/> |Se ha cambiado un filtro de permisos de búsqueda.  <br/> |
|Administrador de eDiscovery creado  <br/> |[Add-eDiscoveryCaseAdmin](/powershell/module/exchange/add-ediscoverycaseadmin) <br/> |Se agregó un usuario como administrador de exhibición de documentos electrónicos en su organización.  <br/> |
|Administrador de eDiscovery eliminado  <br/> |[Remove-eDiscoveryCaseAdmin](/powershell/module/exchange/remove-ediscoverycaseadmin) <br/> |Se eliminó un administrador de exhibición de documentos electrónicos de la organización.  <br/> |
|Se ha cambiado la pertenencia al administrador de eDiscovery  <br/> |[Update-eDiscoveryCaseAdmin](/powershell/module/exchange/update-ediscoverycaseadmin) <br/> |Se ha cambiado la lista de administradores de exhibición de documentos electrónicos de la organización. Esta actividad se registra cuando la lista de administradores de exhibición de documentos electrónicos se reemplaza por un grupo de nuevos usuarios. Si se agrega o quita un único usuario, se registra la operación **Add-eDiscoveryCaseAdmin** o **Remove-eDiscoveryCaseAdmin** .  <br/> |
|(ninguno)|[Get-ComplianceCase](/powershell/module/exchange/get-compliancecase) <br/>|Esta actividad se registra cuando un usuario ha visto una lista de casos de exhibición de documentos electrónicos (estándar) o eDiscovery (Premium). Esta actividad también se registra cuando un usuario ve un caso específico en eDiscovery (Estándar). Cuando un usuario ve un caso específico, el registro de auditoría incluye la identidad del caso que se ha visto. Si el usuario solo ha visto una lista de casos, el registro de auditoría no contiene una identidad de caso.|
|(ninguno)|[Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)|Esta actividad se registra cuando un usuario ha visto una lista de búsquedas de contenido o búsquedas asociadas a un caso de exhibición de documentos electrónicos (estándar). Esta actividad también se registra cuando un usuario ve una búsqueda de contenido específica o ve una búsqueda específica asociada a un caso de exhibición de documentos electrónicos (estándar). Cuando un usuario ve una búsqueda específica, el registro de auditoría incluye la identidad de la búsqueda que se ha visto. Si el usuario solo ha visto una lista de búsquedas, el registro de auditoría no contiene una identidad de búsqueda.
|(ninguno)|[Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)|Esta actividad se registra cuando un usuario ha visto una lista de acciones de búsqueda de cumplimiento (como exportaciones, vistas previas o purgas) o acciones asociadas a un caso de exhibición de documentos electrónicos (estándar). Esta actividad también se registra cuando un usuario ve una acción de búsqueda de cumplimiento específica (como una exportación) o ve una acción específica asociada a un caso de exhibición de documentos electrónicos (estándar). Cuando un usuario ve una acción de búsqueda, el registro de auditoría incluye la identidad de la acción de búsqueda que se ha visto. Si el usuario solo ha visto una lista de acciones, el registro de auditoría no contiene una identidad de acción.|
||||

## <a name="detailed-properties-for-ediscovery-activities"></a>Propiedades detalladas de las actividades de eDiscovery

En la tabla siguiente se describen las propiedades que se incluyen en la página de control flotante de una actividad de exhibición de documentos electrónicos enumerada en los resultados de la búsqueda. Estas propiedades también se incluyen en el archivo CSV al exportar los resultados de la búsqueda de registros de auditoría. Un registro de auditoría para una actividad de exhibición de documentos electrónicos no incluirá todas las propiedades detalladas que se enumeran a continuación.
  
> [!TIP]
> Al exportar los resultados de la búsqueda, el archivo CSV contiene una columna denominada **AudtiData**, que contiene las propiedades detalladas descritas en la tabla siguiente en una propiedad de varios valores. Puede usar la característica Power Query en Excel para dividir esta columna en varias columnas de modo que cada propiedad tenga su propia columna. Esto le permitirá ordenar y filtrar una o varias de estas propiedades. Para obtener más información, vea la sección "Exportar los resultados de búsqueda a un archivo" en [Buscar en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md#step-3-export-the-search-results-to-a-file). 
  
|**Propiedad**|**Descripción**|
|:-----|:-----|
|Case  <br/> |Identidad (GUID) del caso de exhibición de documentos electrónicos que se creó, cambió o eliminó.  <br/> |
|ClientApplication  <br/> |Las actividades de cmdlets de eDiscovery tienen un valor de **EMC** para esta propiedad. Esto indica que la actividad se realizó mediante la GUI del Centro de cumplimiento o ejecutando el cmdlet en PowerShell.  <br/> |
|ClientIP  <br/> |La dirección IP del dispositivo que se ha usado cuando la actividad se ha registrado. La dirección IP se muestra en el formato de dirección IPv4 o IPv6.  <br/> |
|ClientRequestId  <br/> | Para las actividades de exhibición de documentos electrónicos, esta propiedad suele estar en blanco.  <br/> |
|CmdletVersion  <br/> |Número de compilación de la versión del centro de cumplimiento que se ejecuta en su organización.  <br/> |
|CreationTime  <br/> |Fecha y hora de la hora universal coordinada (UTC) cuando se completó la actividad de exhibición de documentos electrónicos.  <br/> |
|EffectiveOrganization  <br/> |Nombre de la organización de Microsoft 365.  <br/> |
|ExchangeLocations  <br/> |Los Exchange Online buzones que se incluyen en una búsqueda de contenido o se colocan en espera en un caso de exhibición de documentos electrónicos.  <br/> |
|Exclusiones  <br/> |Ubicaciones de buzón o sitio que se excluyen de una búsqueda de contenido o una suspensión en un caso de exhibición de documentos electrónicos.  <br/> |
|ExtendedProperties  <br/> |Propiedades adicionales de una búsqueda de contenido, una acción de búsqueda de contenido o una suspensión en un caso de exhibición de documentos electrónicos, como el GUID del objeto y los parámetros de cmdlet y cmdlet correspondientes que se usaron cuando se realizó la actividad.  <br/> |
|Id  <br/> |Identificador de la entrada del informe. El identificador identifica de forma única la entrada del registro de auditoría.  <br/> |
|NonPIIParameters  <br/> |Una lista de los parámetros (sin ningún valor) que se usaron con el cmdlet identificado en la propiedad Operation. Los parámetros enumerados en esta propiedad son los mismos que los que aparecen en la propiedad Parameters.  <br/> |
|ObjectId  <br/> |GUID o nombre del objeto (por ejemplo, una búsqueda de contenido o un caso de exhibición de documentos electrónicos (estándar) que la actividad enumerada en la propiedad Operation creó, obtuvo acceso, cambió o eliminó. Este objeto también se identifica en la columna Item de los resultados de búsqueda del registro de auditoría.  <br/> |
|ObjectType  <br/> |Tipo de objeto eDiscovery que el usuario creó, eliminó o modificó; por ejemplo, una acción de búsqueda de contenido (vista previa, exportación o purga), un caso de exhibición de documentos electrónicos o una búsqueda de contenido.  <br/> |
|Operación  <br/> |Nombre de la operación que corresponde a la actividad eDiscovery que se realizó.  <br/> |
|OrganizationId  <br/> |GUID de la organización Microsoft 365.  <br/> |
|Parámetros  <br/> |Nombre y valor de los parámetros que se usaron con el cmdlet correspondiente.  <br/> |
|PublicFolderLocations  <br/> |Las ubicaciones de carpetas públicas de Exchange Online que se incluyen en una búsqueda de contenido o se colocan en espera en un caso de exhibición de documentos electrónicos.  <br/> |
|Consulta  <br/> |Consulta de búsqueda asociada a la actividad, como una búsqueda de contenido o una retención basada en consultas.  <br/> |
|RecordType  <br/> |El tipo de operación indicado por el registro. El valor **de 18** indica un evento relacionado con una actividad enumerada en la sección [de actividades de cmdlets de eDiscovery](#ediscovery-cmdlet-activities) . Un valor de **24** indica un evento relacionado con una actividad que se muestra en la sección [Búsqueda y visualización de actividades de eDiscovery](#how-to-search-for-and-view-ediscovery-activities) .  <br/> |
|ResultStatus  <br/> |Indica si la acción (especificada en la propiedad Operation) se completó correctamente o no.  <br/> |
|SecurityComplianceCenterEventType  <br/> |Indica que la actividad era un evento del centro de cumplimiento. Todas las actividades de eDiscovery tendrán un valor de **0** para esta propiedad.  <br/> |
|SharepointLocations  <br/> |Los SharePoint sitios en línea que se incluyen en una búsqueda de contenido o se colocan en espera en un caso de exhibición de documentos electrónicos.  <br/> |
|StartTime  <br/> |Fecha y hora de la hora universal coordinada (UTC) cuando se inició la actividad de exhibición de documentos electrónicos.  <br/> |
|UserId  <br/> |El usuario que realizó la actividad (especificada en la propiedad Operation) que provocó que se registrara el registro. Los registros de la actividad de exhibición de documentos electrónicos realizadas por cuentas del sistema (como NT AUTHORITY\SYSTEM) también se incluyen en el registro de auditoría.  <br/> |
|UserKey  <br/> |Un id. alternativo para el usuario identificado en la propiedad id. de usuario. En el caso de las actividades de eDiscovery, el valor de esta propiedad suele ser el mismo que la propiedad UserId.  <br/> |
|UserServicePlan  <br/> |La suscripción que usa la organización. Para las actividades de exhibición de documentos electrónicos, esta propiedad suele estar en blanco.  <br/> |
|UserType  <br/> |El tipo de usuario que llevó a cabo la operación. Los siguientes valores indican el tipo de usuario.  <br/> 0 Un usuario normal. 2 Administrador de la organización. 3 Una cuenta de sistema de centro de datos o administrador del centro de datos de Microsoft. 4 Una cuenta del sistema. 5 Una aplicación. 6 Una entidad de servicio. |
|Versión  <br/> |Indica el número de versión de la actividad (identificada por la propiedad Operation) que se registra.  <br/> |
|Carga de trabajo  <br/> |El servicio donde se produjo la actividad. Para las actividades de eDiscovery, el valor es **SecurityComplianceCenter**.  <br/> |
