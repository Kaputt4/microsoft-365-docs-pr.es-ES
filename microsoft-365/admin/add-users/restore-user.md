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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Obtenga información sobre cómo restaurar cuentas de usuario eliminadas y todos los datos asociados.
ms.openlocfilehash: 9cdc4100f963ed450b50caa0f07a3863bc87992d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244037"
---
# <a name="restore-a-user"></a>Restaurar un usuario
   
Al restaurar una cuenta de usuario en un plazo de 30 días después de eliminarla, se restaurará la cuenta y todos los datos asociados. El usuario podrá iniciar sesión con la misma cuenta profesional o educativa. Su buzón se restaurará por completo. Para conocer cuánto falta para que una cuenta de usuario específica ya no se pueda restaurar, [póngase en contacto con nosotros](../contact-support-for-business-products.md).
  
Aquí tiene un par de sugerencias:
  
- Asegúrese de que las licencias están disponibles para asignar a la cuenta.
    
- Si su empresa usa Active Directory, consulte [Solución de problemas de cuentas de usuario eliminadas en Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) para obtener instrucciones sobre cómo restaurar una cuenta de usuario. 
    
## <a name="restore-one-or-more-user-accounts"></a>Restaurar una o más cuentas de usuario

Debe ser un administrador Microsoft 365 global o administrador de administración de usuarios para realizar estos pasos. 

1. En el Centro de administración, vaya a la **página Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados usuarios.</a>

2. En la **página Usuarios eliminados,** seleccione los nombres de los usuarios que desea restaurar y, a continuación, **seleccione Restaurar**.
    
3. Siga las indicaciones para establecer su contraseña y, a continuación, seleccione **Restaurar**.
    
4. Si el usuario se restaura correctamente, seleccione **Enviar correo electrónico y cierre**. Si se produce un conflicto de nombres o un conflicto de direcciones de proxy, vea las instrucciones a continuación sobre cómo restaurar esas cuentas.
    
Después de restaurar un usuario, asegúrate de notificarles que su contraseña cambió y sigues con ellos.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Restaurar un usuario con un conflicto de nombre de usuario

Se produce un conflicto de nombres de usuario al eliminar una cuenta de usuario, crear una nueva con el mismo nombre de usuario (para el mismo usuario o para otro con un nombre parecido) y, más tarde, intentar restaurar la cuenta eliminada.
  
Para resolverlo, puede cambiar la cuenta de usuario activa por la que vaya a restaurar. También puede asignar otro nombre de usuario a la cuenta que vaya a restaurar, de modo que no haya dos cuentas con el mismo nombre de usuario. Siga estos pasos.

1. En el Centro de administración, vaya a la **página Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados usuarios.</a>
  
2. En la **página Usuarios eliminados,** seleccione los nombres de los usuarios que desea restaurar y, a continuación, **seleccione Restaurar**.
    
    > [!NOTE]
    > Si se produce un error al restaurar dos o más usuarios, un mensaje de error le advierte sobre ello. Vea el registro para comprobar qué usuarios no se restauraron y, después, restaure las cuentas en las que se haya producido el error de una en una. 
  
3. Siga las indicaciones para establecer la contraseña y seleccione **Restaurar**.
    
4. Aparece un mensaje que le avisa de que se ha producido un problema al restaurar la cuenta. Realice una de las acciones siguientes:
    
  - Cancele la restauración, cambie el nombre del usuario activo y vuelva a intentar la restauración.
    
  - O bien, escriba una nueva dirección de correo electrónico principal para el usuario y seleccione **Restaurar**.
    
5. Después de revisar los resultados, seleccione **Cerrar**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Restaurar un usuario que tenga un conflicto de dirección del proxy

Se produce un conflicto de direcciones de proxy al eliminar una cuenta de usuario que contiene una dirección de proxy, asignar la misma dirección de proxy a otra cuenta y, después, intentar restaurar la cuenta eliminada. Siga los pasos que se indican a continuación para solucionar este problema.
  
Debe tener permisos [de administrador en](about-admin-roles.md) Microsoft 365 para ello. 

1. En el Centro de administración, vaya a la **página Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados usuarios.</a>

2. En la página **Usuarios eliminados**, seleccione los usuarios que quiere restaurar y luego seleccione **Restaurar**. 
    
3. En la **página Restaurar,** siga las instrucciones para establecer la contraseña y seleccione **Restaurar**. Las direcciones del proxy que estén en conflicto se eliminan automáticamente del usuario que vaya a restaurar.
    
4. Después de revisar los resultados, seleccione **Cerrar**.

## <a name="related-articles"></a>Artículos relacionados

[Eliminar un usuario](delete-a-user.md)
