---
title: Restaurar un usuario
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
ms.openlocfilehash: e37f913bcc6a54bdcc1e0f52168fe1aab0c8afdd
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394272"
---
# <a name="restore-a-user"></a><span data-ttu-id="b5c5c-103">Restaurar un usuario</span><span class="sxs-lookup"><span data-stu-id="b5c5c-103">Restore a user</span></span>
   
<span data-ttu-id="b5c5c-p101">Al restaurar una cuenta de usuario en un plazo de 30 días después de eliminarla, se restaurará la cuenta y todos los datos asociados. El usuario podrá iniciar sesión con la misma cuenta profesional o educativa. Su buzón se restaurará por completo. Para conocer cuánto falta para que una cuenta de usuario específica ya no se pueda restaurar, [póngase en contacto con nosotros](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="b5c5c-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).</span></span>
  
<span data-ttu-id="b5c5c-108">Aquí tiene un par de sugerencias:</span><span class="sxs-lookup"><span data-stu-id="b5c5c-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="b5c5c-109">Asegúrese de que las licencias están disponibles para asignar a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="b5c5c-110">Si su empresa usa Active Directory, para obtener información sobre cómo restaurar una cuenta de usuario, vea How [to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="b5c5c-110">If your business uses Active Directory, for instrutcions on restoring a user account, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts).</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="b5c5c-111">Restaurar una o más cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="b5c5c-111">Restore one or more user accounts</span></span>

<span data-ttu-id="b5c5c-112">Debe ser un administrador Microsoft 365 global o administrador de administración de usuarios para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="b5c5c-113">En el Centro de administración, vaya a la **página Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados usuarios.</a></span><span class="sxs-lookup"><span data-stu-id="b5c5c-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="b5c5c-114">En la **página Usuarios eliminados,** seleccione los nombres de los usuarios que desea restaurar y, a continuación, **seleccione Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="b5c5c-115">Siga las indicaciones para establecer su contraseña y, a continuación, seleccione **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="b5c5c-116">Si el usuario se restaura correctamente, seleccione **Enviar correo electrónico y cierre**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="b5c5c-117">Si se produce un conflicto de nombres o un conflicto de direcciones de proxy, vea las instrucciones a continuación sobre cómo restaurar esas cuentas.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="b5c5c-118">Después de restaurar un usuario, asegúrate de notificarles que su contraseña cambió y sigues con ellos.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="b5c5c-119">Restaurar un usuario con un conflicto de nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="b5c5c-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="b5c5c-120">Se produce un conflicto de nombres de usuario al eliminar una cuenta de usuario, crear una nueva con el mismo nombre de usuario (para el mismo usuario o para otro con un nombre parecido) y, más tarde, intentar restaurar la cuenta eliminada.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="b5c5c-p103">Para resolverlo, puede cambiar la cuenta de usuario activa por la que vaya a restaurar. También puede asignar otro nombre de usuario a la cuenta que vaya a restaurar, de modo que no haya dos cuentas con el mismo nombre de usuario. Siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="b5c5c-124">En el Centro de administración, vaya a la **página Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados usuarios.</a></span><span class="sxs-lookup"><span data-stu-id="b5c5c-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="b5c5c-125">En la **página Usuarios eliminados,** seleccione los nombres de los usuarios que desea restaurar y, a continuación, **seleccione Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b5c5c-p104">Si se produce un error al restaurar dos o más usuarios, un mensaje de error le advierte sobre ello. Vea el registro para comprobar qué usuarios no se restauraron y, después, restaure las cuentas en las que se haya producido el error de una en una.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="b5c5c-128">Siga las indicaciones para establecer la contraseña y seleccione **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="b5c5c-p105">Aparece un mensaje que le avisa de que se ha producido un problema al restaurar la cuenta. Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b5c5c-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="b5c5c-p106">Cancele la restauración, cambie el nombre del usuario activo y vuelva a intentar la restauración.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="b5c5c-133">O bien, escriba una nueva dirección de correo electrónico principal para el usuario y seleccione **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="b5c5c-134">Después de revisar los resultados, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="b5c5c-135">Restaurar un usuario que tenga un conflicto de dirección del proxy</span><span class="sxs-lookup"><span data-stu-id="b5c5c-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="b5c5c-p107">Se produce un conflicto de direcciones de proxy al eliminar una cuenta de usuario que contiene una dirección de proxy, asignar la misma dirección de proxy a otra cuenta y, después, intentar restaurar la cuenta eliminada. Siga los pasos que se indican a continuación para solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="b5c5c-138">Debe tener permisos [de administrador en](about-admin-roles.md) Microsoft 365 para ello.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="b5c5c-139">En el Centro de administración, vaya a la **página Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados usuarios.</a></span><span class="sxs-lookup"><span data-stu-id="b5c5c-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="b5c5c-140">En la página **Usuarios eliminados**, seleccione los usuarios que quiere restaurar y luego seleccione **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="b5c5c-141">En la **página Restaurar,** siga las instrucciones para establecer la contraseña y seleccione **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="b5c5c-142">Las direcciones del proxy que estén en conflicto se eliminan automáticamente del usuario que vaya a restaurar.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="b5c5c-143">Después de revisar los resultados, seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b5c5c-143">Review the results, and then select **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="b5c5c-144">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="b5c5c-144">Related content</span></span>

<span data-ttu-id="b5c5c-145">[Eliminar un usuario](delete-a-user.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="b5c5c-145">[Delete a user](delete-a-user.md) (article)</span></span>\
<span data-ttu-id="b5c5c-146">[Asignar roles de administrador](assign-admin-roles.md) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="b5c5c-146">[Assign admin roles](assign-admin-roles.md) (video)</span></span>\
<span data-ttu-id="b5c5c-147">[Asignar licencias a usuarios](../manage/assign-licenses-to-users.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="b5c5c-147">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>
