---
title: Administración de datos para La pizarra de Microsoft
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.service: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Obtenga información sobre la retención de datos para Microsoft Whiteboard en Azure y OneDrive para la Empresa.
ms.openlocfilehash: a43caaa9aaccff3b2a56a1c38537f80d2304358f
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598205"
---
# <a name="manage-data-for-microsoft-whiteboard"></a>Administración de datos para La pizarra de Microsoft

El contenido de pizarra se almacena en OneDrive para la Empresa y Azure. OneDrive para la Empresa es el almacenamiento predeterminado para todas las pizarras nuevas. Las pizarras que se crearon originalmente en Azure y las pizarras que se iniciaron en un dispositivo Surface Hub o en una sala de Microsoft Teams se almacenan en Azure.

Para administrar los datos, primero debe asegurarse de que Whiteboard está habilitado para su organización. Para obtener más información, vea [Administrar el acceso a Whiteboard](manage-whiteboard-access-organizations.md).

## <a name="azure-storage-overview"></a>Introducción a Azure Storage

>[!NOTE]
> La siguiente información se aplica a las pizarras que se almacenan en Azure.

Whiteboard almacena actualmente contenido de forma segura en Azure. Los datos pueden almacenarse en ubicaciones diferentes, en función del país y cuando Whiteboard cambia a almacenar contenido nuevo en esas ubicaciones. Para comprobar dónde se crean los nuevos datos, consulte [Dónde se almacenan los datos del cliente de Microsoft 365](/microsoft-365/enterprise/o365-data-locations).

El contenido de Azure no admite la prevención de pérdida de datos (DLP), la exhibición de documentos electrónicos, las directivas de retención y características similares. Este contenido se puede administrar mediante [cmdlets de PowerShell de pizarra](/powershell/module/whiteboard/). Con el tiempo, las pizarras almacenadas en Azure tendrán que migrarse a OneDrive para la Empresa o eliminarse.

### <a name="if-a-user-account-is-deleted-in-azure"></a>Si se elimina una cuenta de usuario en Azure

Estamos cambiando la forma en que se almacenan las pizarras cuando se elimina la cuenta de un usuario en Azure. Antes del cambio, también se eliminaron las pizarras que eran propiedad de la cuenta de un usuario eliminado. Sin embargo, las pizarras compartidas con otros usuarios no se eliminaron.

>[!NOTE]
> Las pizarras almacenadas en OneDrive para la Empresa se controlarán como cualquier otro contenido de OneDrive para la Empresa. Para obtener más información, vea [Establecer la retención de OneDrive para usuarios eliminados](/onedrive/set-retention).

A partir del **1 de junio de 2022**, el comportamiento de las pizarras en Azure ha cambiado. Se eliminarán las pizarras compartidas con otros usuarios.

Si desea conservar las pizarras de un usuario eliminado, *antes* de eliminar la cuenta, puede transferir la propiedad. Puede transferir una sola pizarra o todas ellas a otro usuario.

- Siga estas instrucciones para [transferir todas las pizarras](/powershell/module/whiteboard/invoke-transferallwhiteboards).

- Para obtener más información sobre cómo eliminar cuentas de usuario, consulte [Eliminación de un usuario de su organización](/microsoft-365/admin/add-users/delete-a-user).

Asegúrese de que cualquier proceso de eliminación o script controla este cambio. Si está bien con las pizarras que se van a eliminar, no se requiere ninguna acción.

## <a name="onedrive-for-business-storage-overview"></a>introducción al almacenamiento de OneDrive para la Empresa

Las pizarras se crearán en la carpeta OneDrive para la Empresa de la persona que inicia la pizarra. SharePoint aún no se admite. Este proceso se aplica a todas las pizarras creadas en las aplicaciones de pizarra independientes y en reuniones, chats y canales de Microsoft Teams. La única excepción es que las pizarras iniciadas desde un Surface Hub se almacenarán en Azure, aunque se moverán a OneDrive para la Empresa en el futuro.

Los usuarios que no tengan OneDrive para la Empresa aprovisionados ya no podrán crear nuevas pizarras cuando se implemente este cambio. Sin embargo, todavía pueden editar sus paneles creados anteriormente. También pueden colaborar en cualquier pizarra compartida con ellas por otros usuarios que hayan OneDrive para la Empresa.

Una pizarra promedio podría tener un tamaño de entre 50 KB y 1 MB y estar ubicada donde resida el contenido OneDrive para la Empresa. Para comprobar dónde se almacenan los datos del inquilino, consulte [Dónde se almacenan los datos del cliente de Microsoft 365](/microsoft-365/enterprise/o365-data-locations). A continuación, examine la ubicación de OneDrive para la Empresa.

### <a name="controls-for-onedrive-for-business-storage"></a>Controles para el almacenamiento de OneDrive para la Empresa

Puede administrar datos de Pizarra mediante controles de OneDrive para la Empresa existentes. Para obtener más información, vea [Guía de OneDrive para empresas](/onedrive/plan-onedrive-enterprise).

Puede usar las herramientas de OneDrive para la Empresa existentes para satisfacer las solicitudes del interesado (DSR) para el Reglamento general de protección de datos (RGPD). Si desea asegurarse de que todos los cambios anteriores se quitan del archivo, debe eliminar todo el archivo.

Los archivos de pizarra se pueden mover de la misma manera que otros contenidos de OneDrive para la Empresa. Sin embargo, es posible que no se muevan los vínculos y permisos de uso compartido.

Controles de datos admitidos hoy en día:

- Directivas de retención
- Quota
- Suspensión legal
- DLP
- Exhibición de documentos electrónicos básica: los archivos .whiteboard se almacenan como archivos en el OneDrive para la Empresa del creador. Se indexan para la búsqueda de palabras clave y tipos de archivo, pero no están disponibles para obtener una vista previa o revisar. Tras la exportación, un administrador debe volver a cargar el archivo en OneDrive para la Empresa para ver el contenido. Se planea más soporte técnico para el futuro.

Controles de datos planeados para futuras versiones:

- Etiquetas de confidencialidad
- Análisis
- Más compatibilidad con eDiscovery

## <a name="see-also"></a>Vea también

[Administración del acceso a Whiteboard](manage-whiteboard-access-organizations.md)

[Administración del uso compartido para Whiteboard](manage-sharing-organizations.md)

[Implementación de pizarra en Windows](deploy-on-windows-organizations.md)