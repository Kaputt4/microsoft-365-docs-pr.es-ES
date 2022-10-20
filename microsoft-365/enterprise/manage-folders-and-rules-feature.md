---
title: Característica Administrar carpetas y reglas en Grupos de Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkEXCHANGE
search.appverid: ''
ms.assetid: ''
description: En este artículo, aprenderá a administrar la característica de carpetas y reglas en grupos de Microsoft 365.
ms.openlocfilehash: 470f8569cc064053b96ab1d39b318d875451267a
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631377"
---
# <a name="manage-folders-and-rules-feature-in-microsoft-365-groups"></a>Característica Administrar carpetas y reglas en Grupos de Microsoft 365

Los usuarios pueden organizar los correos electrónicos de grupos de forma eficaz mediante la creación de carpetas y la configuración de reglas dentro del buzón de grupos. Una vez creadas las carpetas en el buzón de grupos, los usuarios pueden mover y copiar mensajes a diferentes carpetas manualmente, así como mediante **reglas**.

Esta funcionalidad solo está disponible actualmente en Outlook Web Application.

## <a name="enable-folders-and-rules-feature-for-microsoft-365-groups-in-outlook"></a>Característica Habilitar carpetas y reglas para Grupos de Microsoft 365 en Outlook

Administración puede habilitar la característica con la ayuda del cmdlet `Set-OrganizationConfig -IsGroupFoldersAndRulesEnabled`.

 - `[-IsGroupFoldersAndRulesEnabled<Boolean>]` -Opcional

   El `IsGroupFoldersAndRulesEnabled` parámetro especifica si la característica Carpetas y reglas está habilitada para el inquilino.

   Valores posibles: true/false

   Valor predeterminado: false

> [!NOTE]
> Una vez que el `IsGroupFoldersAndRulesEnabled` parámetro está desactivado después de crear algunas carpetas y reglas,
  > 
  > - Las carpetas y reglas existentes se seguirán representando.
  > 
  > - Las reglas existentes seguirán ejecutándose.
  > 
  > - Se bloqueará la creación, la creación y la eliminación de carpetas.
  > 
  > - Se bloquearán las acciones de nivel de mensaje Copiar o Mover.

Una vez habilitada la característica, de forma predeterminada, solo el propietario del grupo tiene permiso para crear carpetas, cambiar el nombre de carpeta, mover y copiar mensajes entre carpetas.
  
## <a name="enable-member-permission-option"></a>Habilitar la opción de permiso de miembro

Si es necesario que los miembros del grupo creen carpetas y triagen mensajes en el buzón de grupos, el administrador debe habilitar el permiso de miembro para editar el contenido de grupos en el nivel de inquilino y el propietario del grupo en el nivel de grupo respectivamente.

De forma predeterminada, esta configuración se **desactiva** en el nivel de inquilino y en el nivel de grupo.
  
Administración puede habilitar el permiso de miembro para el inquilino mediante el cmdlet `IsGroupMemberAllowedToEditContent`.

 - `[-IsGroupMemberAllowedToEditContent<Boolean>]`-Opcional

   El `IsGroupMemberAllowedToEditContent` parámetro especifica si el propietario del grupo puede conceder permiso a los miembros para la edición de contenido de la característica Carpetas y reglas.

   Valores posibles: True/False

   Valor predeterminado: false

Una vez habilitado esto, los propietarios del grupo pueden proporcionar a los miembros del grupo la capacidad de crear carpetas, cambiar el nombre de las carpetas, copiar, mover y eliminar mensajes. Los propietarios del grupo controlan el permiso de miembro de nivel de grupo.

> [!NOTE]
> Los administradores pueden ver el valor actual de la configuración mediante `Get-OrganizationConfig` el cmdlet .

## <a name="block-move-message-capability"></a>Bloquear la funcionalidad de mensaje "Mover"

Los administradores pueden bloquear la opción **Mover** mensaje para todos los grupos de Microsoft 365 dentro de un inquilino mediante el cmdlet `Set-OrganizationConfig -BlockMoveMessagesForGroupFold`.

 - `[-BlockMoveMessagesForGroupFolders<Boolean>]` –Opcional

   El `BlockMoveMessagesForGroupFolders` parámetro especifica si el mensaje la acción **Mover** está deshabilitada.

   Valores posibles: True/False

   Valor predeterminado: false

> [!NOTE]
> La creación de **la regla Mover** también está deshabilitada cuando `BlockMoveMessagesForGroupFolders` está habilitada.

> [!NOTE]
> Esto resulta útil si hay un conjunto mixto de usuarios que usan Outlook en Web y Outlook Desktop App. Para los usuarios de la aplicación de escritorio de Outlook, donde las carpetas no están disponibles, pueden obtener los mensajes de la bandeja de entrada del grupo. 
  
  
  
