---
title: Eliminación de contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Supervise y administre la eliminación de contenido, independientemente de si usa una revisión para eliminación o el contenido se elimina automáticamente de acuerdo con la configuración que haya establecido.
ms.openlocfilehash: d9786b5e93801153e168784d51e37a00ee1822bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051932"
---
# <a name="disposition-of-content"></a>Eliminación de contenido

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Use la pestaña **Eliminación** de **Administración de registros** en el Centro de cumplimiento de Microsoft 365 para administrar las revisiones de eliminación y ver [registros](records-management.md#records) que se hayan eliminado automáticamente al final de su período de retención. 

## <a name="prerequisites-for-viewing-content-dispositions"></a>Requisitos previos para ver las eliminaciones de contenido

Para administrar las revisiones de eliminación y confirmar que los registros se han eliminado, debe tener los permisos necesarios y la auditoría debe estar habilitada.

### <a name="permissions-for-disposition"></a>Permisos para la eliminación

Para acceder de forma satisfactoria a la pestaña **Eliminación** en el Centro de cumplimiento de Microsoft 365, los usuarios deben tener el rol de administrador de **Administración de eliminación**. Desde diciembre de 2020, este rol está ahora incluido en el grupo de roles de administrador predeterminado **Administración de registros**.

> [!NOTE]
> De lmanera predeterminada, un administrador global no tiene concedido el rol de **Administración de eliminación**. 

Para conceder a los usuarios solo los permisos que necesitan para las revisiones de disposición sin concederles permisos para ver y configurar otras características para la retención y la gestión de registros, cree un grupo de funciones personalizado (por ejemplo, denominado "Revisores de disposición") y conceda a este grupo la función de gestión de disposición.

Además, para ver el contenido de los elementos durante el proceso de eliminación, agregue usuarios a los dos grupos de roles siguientes: **Visor de contenido del explorador de contenido** y **Visor de listas del explorador de contenido**. Si los usuarios no tienen los permisos para estos grupos de roles, aún pueden seleccionar una acción de revisión de eliminación para completar la revisión de eliminación, pero deberán hacerlo sin poder ver el contenido del elemento desde el centro de cumplimiento.

Para obtener instrucciones sobre la configuración de estos permisos, consulte [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento de Office 365](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md).

### <a name="enable-auditing"></a>Habilitar auditoría

Asegúrese de que la auditoría está activada al menos un día antes de la primera acción de eliminación. Para más información, vea [Buscar en el registro de auditoría del Centro de seguridad &amp; cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md). 

## <a name="disposition-reviews"></a>Revisiones para eliminación

Cuando el contenido llega al final de su período de retención, hay varios motivos por los que es posible que quiera revisar el contenido y confirmar si se puede borrar de forma permanente ("eliminar"). Por ejemplo, en vez de borrar el contenido, podría necesitar:
  
- Suspender la eliminación de contenido relevante en caso de litigio o una auditoría.

- Asignar un periodo de retención diferente al contenido, por ejemplo, porque las configuraciones de retención originales eran una solución temporal o provisional.

- Mover el contenido desde su ubicación existente a una ubicación de archivo. Por ejemplo, si ese contenido tiene valor histórico o de investigación.

Cuando se activa una revisión para eliminación al final del período de retención:
  
- Las personas que elija recibirán una notificación por correo electrónico de que tienen contenido para revisar. Estos revisores pueden ser usuarios individuales o grupos de seguridad habilitados para correo. Tenga en cuenta que las notificaciones se envían cada semana.
    
- Los revisores pueden ir a la pestaña **Eliminación** en el Centro de cumplimiento de Microsoft 365 para revisar el contenido y decidir si se elimina de forma permanente, se amplía el período de retención o se aplica una etiqueta de retención diferente.

Una revisión para eliminación puede incluir contenido en buzones de Exchange, sitios de SharePoint, cuentas de OneDrive y grupos de Microsoft 365. El contenido pendiente de una revisión para eliminación en esas ubicaciones se eliminará solo después de que un revisor elija eliminar el contenido de forma permanente.

> [!NOTE]
> Un buzón debe tener al menos 10 MB de datos para admitir las revisiones para eliminación.

Puede ver una descripción general de todas las eliminaciones pendientes en la pestaña **Información general**. Por ejemplo:

![Disposiciones pendientes en la información general de Administración de registros](../media/dispositions-overview.png)

Al seleccionar **Ver todas las eliminaciones pendientes**, se le dirigirá a la página **Eliminación**. Por ejemplo:

![Página Eliminaciones en el Centro de cumplimiento de Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a>Flujo de trabajo para una revisión para eliminación

El siguiente diagrama muestra el flujo de trabajo básico de una revisión para eliminación cuando se publica una etiqueta de retención y un usuario la aplica de forma manual. Como alternativa, puede aplicar automáticamente la etiqueta de retención configurada para una revisión para eliminación al contenido.
  
![Gráfico que muestra el flujo de trabajo de eliminación](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Desencadenar una revisión para eliminación al final del período de retención es una opción de configuración que solo está disponible con una etiqueta de retención. Esta opción no está disponible para una directiva de retención. Para más información sobre estas dos soluciones de retención, consulte [Obtener información sobre las directivas de retención y las etiquetas de retención](retention.md).

En la página **Definir la configuración de retención** de una etiqueta de retención:

![Configuración de retención para una etiqueta](../media/disposition-review-option.png)
 
Después de seleccionar la opción **Desencadenar una revisión para eliminación**, especifique los revisores de eliminación en la siguiente página del asistente:

![Especificar revisores de eliminación](../media/disposition-reviewers.png)

Para los revisores, especifique un usuario o un grupo de seguridad habilitado para correo. En esta opción no se admiten los grupos de Microsoft 365 ([anteriormente llamados grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).

### <a name="viewing-and-disposing-of-content"></a>Visualización y eliminación de contenido

Cuando un revisor recibe una notificación por correo electrónico de que el contenido está listo para su revisión, puede ir a la pestaña **Eliminación** de **Administración de registros** en el Centro de cumplimiento de Microsoft 365. Los revisores pueden ver cuántos elementos están esperando la eliminación para cada etiqueta de retención y seleccionar una etiqueta de retención para ver todo el contenido con esa etiqueta.

Después de seleccionar una etiqueta de retención, verá todas las eliminaciones pendientes para dicha etiqueta en la pestaña **Pendiente de eliminación**. Seleccione uno o más elementos, en los que puede elegir una acción y escribir un comentario de justificación:

![Opciones de eliminación](../media/retention-disposition-options.png)

Como puede ver en la imagen, las acciones compatibles son las siguientes: 
  
- Eliminar permanentemente el elemento
- Extender el período de retención
- Aplicar una etiqueta de retención diferente

Siempre que disponga de permisos para la ubicación y el contenido, puede usar el vínculo de la columna **Ubicación** para ver los documentos en su ubicación original. Durante una revisión para eliminación, el contenido nunca se mueve de su ubicación original y nunca se elimina hasta que el revisor elija hacerlo.

Las notificaciones por correo electrónico se envían automáticamente a los revisores cada semana. Este proceso programado significa que cuando el contenido llega al final de su período de retención, es posible que los revisores tarden hasta siete días en recibir la notificación por correo electrónico de que el contenido está esperando la eliminación.
  
Se pueden auditar todas las acciones de eliminación. Además, el texto de justificación introducido por el revisor se guarda y se muestra en la columna **Comentario** de la página **Elementos eliminados**.
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Cuánto tiempo tarda el contenido eliminado en borrarse permanentemente

El contenido que espera una revisión para eliminación solo se elimina después de que un revisor elija eliminar el contenido de forma permanente. Cuando el revisor elige esta opción, el contenido en el sitio de SharePoint o en la cuenta de OneDrive pasa a ser apto para el proceso de limpieza estándar descrito en [Cómo funciona la configuración de retención con el contenido local](retention.md#how-retention-settings-work-with-content-in-place).

## <a name="disposition-of-records"></a>Eliminación de registros

Use la pestaña **Eliminación** en la página **Administración de registros** para identificar registros ya eliminados, ya sea automáticamente o después de una revisión para eliminación. Estos elementos muestran **Registros eliminados** en la columna **Tipo**. Por ejemplo:

![Elementos que se eliminaron sin una revisión para eliminación](../media/records-disposed2.png)

Los elementos que se muestran en la pestaña **Elementos eliminados** para etiquetas de registro se guardan hasta siete años después de que se elimine el elemento, con un límite de un millón artículos por registro para ese período. Si ve que el número de **Recuento** está a punto de alcanzar este límite de un millón y necesita una prueba de eliminación de los registros, póngase en contacto con el [Soporte técnico de Microsoft](/office365/admin/contact-support-for-business-products).

> [!NOTE]
> Esta funcionalidad se basa en la información del [registro de auditoría unificado](search-the-audit-log-in-security-and-compliance.md) y, por lo tanto, requiere que la auditoría se [habilite y se pueda buscar](turn-audit-log-search-on-or-off.md) para que se puedan capturar los eventos correspondientes.

En el caso de la auditoría, se debe buscar **Archivo eliminado marcado como registro** en la categoría **Actividades de archivos y páginas**. Este evento de auditoría se aplica a documentos y mensajes de correo electrónico.

## <a name="filter-and-export-the-views"></a>Filtrar y exportar las vistas

Al seleccionar una etiqueta de retención de la página **Eliminación**, la pestaña **Pendiente de eliminación** (si procede) y la pestaña **Elementos eliminados** le permiten filtrar las vistas para facilitar la búsqueda de elementos. 

Para las eliminaciones pendientes, el intervalo de tiempo se basa en la fecha de expiración. En el caso de los elementos eliminados, el intervalo de tiempo se basa en la fecha de eliminación.
  
Puede exportar información acerca de los elementos de cualquier vista como un archivo .csv que puede ordenar y administrar con Excel:

![Opción de exportación para la eliminación](../media/retention-export-option.png)