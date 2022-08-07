---
title: Administración de datos para La pizarra de Microsoft
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Obtenga información sobre la retención de datos para Microsoft Whiteboard en Azure y OneDrive Entreprise.
ms.openlocfilehash: e79c0250d896d479047ec4465a81643dd2ba26d5
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276096"
---
# <a name="manage-data-for-microsoft-whiteboard"></a>Administración de datos para La pizarra de Microsoft

El contenido de pizarra se almacena en Azure y OneDrive Entreprise. Las nuevas pizarras se almacenarán en OneDrive Entreprise; la única excepción son las pizarras iniciadas desde un Surface Hub se almacenarán en Azure (que se moverán a OneDrive Entreprise en el futuro). Para obtener más información, vea [Administrar el uso compartido en la pizarra](manage-sharing-organizations.md).

## <a name="azure-storage-overview"></a>Introducción a Azure Storage

Whiteboard almacena actualmente contenido de forma segura en Azure. Los datos pueden almacenarse en ubicaciones diferentes, en función del país y cuando Whiteboard cambia a almacenar contenido nuevo en esas ubicaciones. Para comprobar dónde se crean los nuevos datos, consulte [Dónde se almacenan los datos del cliente de Microsoft 365](/microsoft-365/enterprise/o365-data-locations).

El contenido de Azure no admite la prevención de pérdida de datos (DLP), la exhibición de documentos electrónicos, las directivas de retención y características similares. El contenido se puede administrar mediante [cmdlets de PowerShell de Pizarra](/powershell/module/whiteboard/) y, con el tiempo, este contenido deberá migrarse a OneDrive Entreprise o eliminarse.

### <a name="if-a-user-account-is-deleted-in-azure"></a>Si se elimina una cuenta de usuario en Azure

Estamos cambiando la forma en que se almacenan las pizarras cuando se elimina la cuenta de un usuario en Azure. Antes del cambio, cuando se eliminó la cuenta de un usuario, también se eliminaron las pizarras que era propiedad del usuario, pero las pizarras que se compartieron con otros usuarios no se eliminaron.

>[!NOTE]
> Las pizarras almacenadas en OneDrive Entreprise se controlarán como cualquier otro contenido de OneDrive Entreprise. Para obtener más información, vea [Establecer la retención de OneDrive para usuarios eliminados](/onedrive/set-retention).

A partir del **1 de junio de 2022**, el comportamiento de las pizarras en Azure ha cambiado. Se eliminarán las pizarras compartidas con otros usuarios.

Si desea conservar las pizarras de un usuario eliminado, *antes* de eliminar la cuenta, puede transferir la propiedad. Puede transferir una sola pizarra o todas ellas a otro usuario.

- Siga estas instrucciones para [transferir todas las pizarras](/powershell/module/whiteboard/invoke-transferallwhiteboards).

- Para obtener más información sobre cómo eliminar cuentas de usuario, consulte [Eliminación de un usuario de su organización](/microsoft-365/admin/add-users/delete-a-user).

Asegúrese de que cualquier proceso de eliminación o script controla este cambio. Si está bien con las pizarras que se van a eliminar, no se requiere ninguna acción.

## <a name="onedrive-for-business-storage-overview"></a>introducción al almacenamiento de OneDrive Entreprise

Las pizarras se crearán en la carpeta OneDrive Entreprise de la persona que inicia la pizarra (SharePoint aún no se admite). Este proceso se aplica a todas las pizarras creadas en las aplicaciones de pizarra independientes y en reuniones, chats y canales de Microsoft Teams. La única excepción son las pizarras iniciadas desde un Surface Hub que se almacenarán en Azure (que se moverán a OneDrive Entreprise en el futuro).

Los usuarios que no tengan OneDrive Entreprise aprovisionados ya no podrán crear nuevas pizarras cuando se implemente este cambio. Sin embargo, todavía pueden editar sus paneles creados anteriormente. También pueden colaborar en cualquier pizarra compartida con ellas por otros usuarios que hayan OneDrive Entreprise.

Una pizarra promedio podría tener un tamaño de entre 50 KB y 1 MB y estar ubicada donde resida el contenido OneDrive Entreprise. Para comprobar dónde se almacenan los datos del inquilino, consulte [Dónde se almacenan los datos del cliente de Microsoft 365](/microsoft-365/enterprise/o365-data-locations). A continuación, examine la ubicación de OneDrive Entreprise.

### <a name="controls-for-onedrive-for-business-storage"></a>Controles para el almacenamiento de OneDrive Entreprise

Puede administrar datos de Pizarra mediante controles de OneDrive Entreprise existentes. Para obtener más información, vea [Guía de OneDrive para empresas](/onedrive/plan-onedrive-enterprise).

Puede usar las herramientas de OneDrive Entreprise existentes para satisfacer las solicitudes del interesado (DSR) para el Reglamento general de protección de datos (RGPD). Si desea asegurarse de que todos los cambios anteriores se quitan del archivo, debe eliminar todo el archivo.

Los archivos de pizarra se pueden mover de la misma manera que otros contenidos de OneDrive Entreprise. Sin embargo, es posible que no se muevan los vínculos y permisos de uso compartido.

Controles de datos admitidos hoy en día:

- Directivas de retención
- Quota
- Suspensión legal
- DLP
- Exhibición de documentos electrónicos básica: los archivos .whiteboard se almacenan como archivos en el OneDrive Entreprise del creador. Se indexan para la búsqueda de palabras clave y tipos de archivo, pero no están disponibles para obtener una vista previa o revisar. Tras la exportación, un administrador debe volver a cargar el archivo en OneDrive Entreprise para ver el contenido. Para el futuro está previsto soporte técnico adicional.

Controles de datos planeados para futuras versiones:

- Etiquetas de confidencialidad
- Análisis
- Compatibilidad adicional con eDiscovery

## <a name="see-also"></a>Ver también

[Administración del acceso a Whiteboard](manage-whiteboard-access-organizations.md)

[Administración del uso compartido para Whiteboard](manage-sharing-organizations.md)

[Implementación de pizarra en Windows](deploy-on-windows-organizations.md)