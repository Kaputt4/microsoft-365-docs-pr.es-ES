---
title: Restaurar un usuario
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: En un plazo de 30 días después de eliminar una cuenta de usuario, puede restaurar la cuenta y todos los datos, y el usuario puede iniciar sesión con la misma cuenta.
ms.openlocfilehash: 126cb9ca4a9b74445aad2cc3f7cec4f6feab8eb7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68200107"
---
# <a name="restore-a-user-in-the-microsoft-365-admin-center"></a>Restauración de un usuario en el Centro de administración de Microsoft 365
   
When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).
  
Aquí tiene un par de sugerencias:
  
- Asegúrese de que las licencias están disponibles para asignarlas a la cuenta.
    
- Si su empresa usa Active Directory, para obtener instrucciones sobre cómo restaurar una cuenta de usuario, consulte [Solución de problemas de cuentas de usuario eliminadas en Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts). 
    
## <a name="restore-one-or-more-user-accounts"></a>Restaurar una o más cuentas de usuario

Debe ser administrador global de Microsoft 365 o administrador de administración de usuarios para realizar estos pasos. 

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados</a> .

2. En la página **Usuarios eliminados** , seleccione los nombres de los usuarios que desea restaurar y, a continuación, seleccione **Restaurar**.
    
3. Siga las indicaciones para establecer su contraseña y, a continuación, seleccione **Restaurar**.
    
4. Si el usuario se ha restaurado correctamente, seleccione **Enviar correo electrónico y cerrar**. Si se produce un conflicto de nombres o un conflicto de direcciones de proxy, vea las instrucciones a continuación sobre cómo restaurar esas cuentas.
    
Después de restaurar un usuario, asegúrese de notificarle que ha cambiado la contraseña y de realizar un seguimiento con ellos.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Restaurar un usuario con un conflicto de nombre de usuario

Se produce un conflicto de nombres de usuario al eliminar una cuenta de usuario, crear una nueva con el mismo nombre de usuario (para el mismo usuario o para otro con un nombre parecido) y, más tarde, intentar restaurar la cuenta eliminada.
  
To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados</a> .
  
2. En la página **Usuarios eliminados** , seleccione los nombres de los usuarios que desea restaurar y, a continuación, seleccione **Restaurar**.
    
    > [!NOTE]
    > If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time. 
  
3. Siga las indicaciones para establecer la contraseña y seleccione **Restaurar**.
    
4. Aparece un mensaje que le avisa de que se ha producido un problema al restaurar la cuenta. Realice una de las acciones siguientes:
    
     - Cancele la restauración y cambie el nombre del usuario activo actual. A continuación, vuelva a intentar la restauración.
    
     - O bien, escriba una nueva dirección de correo electrónico principal para el usuario y seleccione **Restaurar**.
    
5. Después de revisar los resultados, seleccione **Cerrar**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Restaurar un usuario que tenga un conflicto de dirección del proxy

A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.
  
Para ello, debe tener [permisos de administrador](about-admin-roles.md) en Microsoft 365. 

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados</a> .

2. En la página **Usuarios eliminados**, seleccione los usuarios que quiere restaurar y luego seleccione **Restaurar**. 
    
3. En la página **Restaurar** , siga las instrucciones para establecer la contraseña y seleccione **Restaurar**. Las direcciones del proxy que estén en conflicto se eliminan automáticamente del usuario que vaya a restaurar.
    
4. Después de revisar los resultados, seleccione **Cerrar**.

## <a name="related-content"></a>Contenido relacionado

[Eliminar un usuario](delete-a-user.md) (artículo)\
[Asignar roles de administrador](assign-admin-roles.md) (vídeo)\
[Asignación de licencias a usuarios](../manage/assign-licenses-to-users.md) (artículo)
