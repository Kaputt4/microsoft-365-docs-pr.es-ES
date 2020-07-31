---
title: Disposición del contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Supervisar y administrar la eliminación de contenido, independientemente de si usa una revisión de disposición o el contenido se elimina automáticamente de acuerdo con la configuración que haya configurado.
ms.openlocfilehash: 938d530447d1a798e5a2d6d4c2f622a04827bf1c
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529605"
---
# <a name="disposition-of-content"></a>Disposición del contenido

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Use la pestaña **disposición** de la **Administración de registros** en el centro de cumplimiento de Microsoft 365 para administrar las revisiones de disposición y ver [los registros](records.md) que se han eliminado automáticamente al final del período de retención. 

## <a name="prerequisites-for-viewing-content-dispositions"></a>Requisitos previos para ver las disposiciones de contenido

Para administrar las revisiones de disposición y confirmar que los registros se han eliminado, debe tener permisos suficientes y la auditoría debe estar habilitada.

### <a name="permissions-for-disposition"></a>Permisos para disposición

Para obtener acceso correctamente a la pestaña **disposición** del centro de cumplimiento de Microsoft 365, los usuarios deben tener el rol de **Administración de disposición** y el rol **registros de auditoría con permiso de vista** . Aunque el aviso estándar es agregar usuarios a los grupos de roles predeterminados, en este caso, se recomienda crear un nuevo grupo de funciones denominado **revisores de disposición** con estos dos roles y agregar usuarios a este grupo según sea necesario. Un solo grupo de roles para la disposición reduce los gastos generales de administración y facilita a los usuarios los permisos combinados que necesitan.

> [!NOTE]
> Incluso un administrador global debe recibir la función de **Administración de disposición** . Por lo tanto, los administradores globales deben tener acceso a la ficha disposición como miembros del grupo de roles **Reviewers de disposición** . 

Específica del rol **registros de auditoría con permiso de vista** :

- Dado que el cmdlet subyacente que se usa para buscar en el registro de auditoría es un cmdlet de Exchange Online, debe asignar a los usuarios este rol mediante el [centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), en lugar de usar la página **permisos** del centro de seguridad & cumplimiento. Para obtener instrucciones, vea [administrar grupos de roles en Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Los grupos de 365 de Microsoft ([anteriormente los grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) no se admiten para este rol. En su lugar, asigne buzones de usuario, usuarios de correo o grupos de seguridad habilitados para correo.

Para obtener instrucciones sobre cómo conceder a los usuarios la función de **Administración de disposición** y crear su nueva función de **revisores de disposición** , vea [conceder acceso a los usuarios al &amp; centro de seguridad y cumplimiento de Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

### <a name="enable-auditing"></a>Habilitar la auditoría

Asegúrese de que la auditoría esté habilitada al menos un día antes de la primera acción de disposición. Para obtener más información, vea [Buscar en el registro de auditoría del &amp; centro de seguridad y cumplimiento de Office 365](search-the-audit-log-in-security-and-compliance.md). 

## <a name="disposition-reviews"></a>Revisiones para eliminación

Cuando el contenido alcanza el final de su período de retención, existen varios motivos por los que puede que desee revisar el contenido para decidir si se puede eliminar de forma segura ("eliminado"). Por ejemplo, es posible que deba:
  
- Suspender la eliminación del contenido relevante en caso de litigio o una auditoría.
    
- Quitar contenido de la lista de disposición para almacenarla en un archivo, si el contenido tiene un valor histórico o de investigación.
    
- Asigne un período de retención diferente al contenido, quizá porque la configuración de retención original era una solución temporal o provisional.
    
- Devolver el contenido a los clientes o transferirlo a otra organización.

Cuando se activa una revisión de disposición al final del período de retención:
  
- Las personas que elija reciben una notificación por correo electrónico de que tienen contenido que revisar. Estos revisores pueden ser usuarios individuales, grupos de distribución o de seguridad o grupos de 365 de Microsoft ([anteriormente grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)). Tenga en cuenta que las notificaciones se envían cada semana.
    
- Los revisores van a la pestaña **disposición** del centro de cumplimiento de Microsoft 365 para revisar el contenido y decidir si desea eliminarlo permanentemente, ampliar el período de retención o aplicar una etiqueta de retención diferente.

Una revisión de disposición puede incluir contenido en buzones de Exchange, sitios de SharePoint, cuentas de OneDrive y grupos de Microsoft 365. El contenido que espera una revisión de disposición en esas ubicaciones se elimina solo después de que un revisor elige eliminar el contenido de forma permanente.

> [!NOTE]
> Un buzón de correo debe tener al menos 10 MB de datos para admitir revisiones de disposición.

Puede ver una descripción general de todas las disposiciones pendientes en la ficha **información general** . Por ejemplo:

![Información general sobre las disposiciones pendientes en la administración de registros](../media/dispositions-overview.png)

Al seleccionar **ver todas las disposiciones pendientes**, se le lleva a la página de **disposición** . Por ejemplo:

![Página disposiciones del centro de cumplimiento de Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a>Flujo de trabajo para una revisión de disposición

El siguiente diagrama muestra el flujo de trabajo básico para una revisión de disposición cuando una etiqueta de retención se publica y, a continuación, un usuario la aplica manualmente. Como alternativa, una etiqueta de retención configurada para una revisión de disposición se puede aplicar automáticamente al contenido.
  
![Gráfico que muestra el flujo de trabajo de disposición](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Desencadenar una revisión de disposición al final del período de retención es una opción de configuración que solo está disponible con una etiqueta de retención. Esta opción no está disponible para una directiva de retención. Para obtener más información acerca de estas dos soluciones de retención, consulte [información sobre las directivas de retención y las etiquetas de retención](retention.md).
  
![Configuración de retención de una etiqueta](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> Cuando seleccione la opción **notificar a estas personas cuando hay elementos listos para revisar**, especifique un usuario o un grupo de seguridad habilitado para correo. Para esta opción no se admiten grupos de 365 de Microsoft ([anteriormente los grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).

### <a name="viewing-and-disposing-of-content"></a>Visualización y eliminación de contenido

Cuando se notifica a un revisor por correo electrónico que el contenido está preparado para revisarlo, se dirige a la pestaña **disposición** de **Administración de registros** en el centro de cumplimiento de Microsoft 365. Los revisores pueden ver cuántos elementos tiene la etiqueta de retención en espera de disposición y, a continuación, seleccionar una etiqueta de retención para ver todo el contenido con esa etiqueta.

Después de seleccionar una etiqueta de retención, verá todas las coposiciones pendientes para esa etiqueta de la pestaña de **disposición pendiente** . Seleccione uno o más elementos en los que podrá elegir una acción y escriba un Comentario de justificación:

![Opciones de disposición](../media/retention-disposition-options.png)

Como puede ver en la imagen, las acciones admitidas son las siguientes: 
  
- Eliminar permanentemente el elemento
- Ampliación del período de retención
- Aplicar una etiqueta de retención diferente

Siempre que tenga permisos para la ubicación y el contenido, puede usar el vínculo de la columna **Ubicación** para ver los documentos en su ubicación original. Durante una revisión de disposición, el contenido nunca se mueve desde su ubicación original, y nunca se elimina hasta que el revisor elige hacerlo.

Las notificaciones por correo electrónico se envían de forma automática a los revisores cada semana. Este proceso programado significa que cuando el contenido alcanza el final de su período de retención, los revisores pueden tardar hasta siete días en recibir la notificación por correo electrónico de que el contenido espera la disposición.
  
Todas las acciones de disposición se pueden auditar y el texto de justificación escrito por el revisor se guarda y se muestra en la columna **Comentario** de la página **elementos desechados** .
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Cuánto tiempo se eliminará permanentemente el contenido desechado

El contenido que espera una revisión de disposición se elimina solo después de que un revisor elige eliminar el contenido de forma permanente. Cuando el revisor elige esta opción, el contenido en el sitio de SharePoint o la cuenta de OneDrive pasa a ser apto para el proceso de limpieza estándar descrito en [Cómo funciona la configuración de retención con el contenido en su lugar](retention.md#how-retention-settings-work-with-content-in-place).

## <a name="disposition-of-records"></a>Eliminación de registros

> [!NOTE]
>Se ha completado la implementación de la prueba de eliminación de registros en SharePoint y OneDrive. Verá la lista de etiquetas de retención que marcan contenido como registros para SharePoint y OneDrive en la sección disposición de la página Administración de registros en el centro de cumplimiento de Microsoft 365. En estas etiquetas, puede ver la lista de elementos de SharePoint y OneDrive que se eliminaron automáticamente o después de una revisión de disposición.

La prueba de eliminación de registros de Exchange todavía no está activa. Cuando este lanzamiento se inicie y una vez que se haya completado, actualizaremos esta nota.

Use la pestaña **disposición** de la página **Administración de registros** para identificar los registros que se eliminan automáticamente. Estos elementos muestran **los registros eliminados** en la columna **tipo** . Por ejemplo:

![Elementos eliminados sin una revisión de disposición](../media/records-disposed2.png)

Los elementos que se muestran en la ficha **elementos desechados** para las etiquetas de registro se conservan hasta siete años después de que se eliminó el elemento, con un límite de 1 millón elementos por registro para ese período. Si ve el número de **recuento** cerca de este límite de 1 millón y necesita probar la disposición de sus registros, póngase en contacto [con el soporte técnico de Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

> [!NOTE]
> Esta funcionalidad se basa en la información del [registro de auditoría unificado](search-the-audit-log-in-security-and-compliance.md) y, por lo tanto, requiere que la auditoría esté [habilitada y sea buscada](turn-audit-log-search-on-or-off.md) para que se capturen los eventos correspondientes.
    
## <a name="filter-and-export-the-views"></a>Filtrar y exportar las vistas

Cuando se selecciona una etiqueta de retención de la página de **disposición** , la ficha de **disposición pendiente** (si procede) y la ficha **elementos desechados** le permiten filtrar las vistas para facilitar la búsqueda de elementos. 

Para las disposiciones pendientes, el intervalo de tiempo se basa en la fecha de expiración. Para los elementos eliminados, el intervalo de tiempo se basa en la fecha de eliminación.
  
Puede exportar la información sobre los elementos en cualquiera de las vistas como un archivo. csv que puede ordenar y administrar mediante Excel:

![Opción de exportación para la disposición](../media/retention-export-option.png)
  
![Datos de disposición exportados en Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


