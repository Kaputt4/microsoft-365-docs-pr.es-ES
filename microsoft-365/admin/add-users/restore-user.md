---
title: Restaurar un usuario en Office 365
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Obtenga información sobre cómo restaurar cuentas de usuario de Office 365 eliminadas y todos los datos asociados.
ms.openlocfilehash: 385f7938f5e0ce1f3a580d40830124f77454f64d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245668"
---
# <a name="restore-a-user-in-office-365"></a>Restaurar un usuario en Office 365
   
Al restaurar una cuenta de usuario en un plazo de 30 días después de eliminarla, se restaurará la cuenta y todos los datos asociados. El usuario podrá iniciar sesión con la misma cuenta profesional o educativa. Su buzón se restaurará por completo. Para conocer cuánto falta para que una cuenta de usuario específica ya no se pueda restaurar, [póngase en contacto con nosotros](../contact-support-for-business-products.md).
  
Aquí tiene un par de sugerencias:
  
- Compruebe que tiene disponibles licencias de Office 365 que puede asignar a la cuenta.
    
- Si su empresa usa Active Directory, consulte [Solución de problemas de cuentas de usuario eliminadas en Office 365](https://support.microsoft.com/kb/2619308) para obtener instrucciones sobre cómo restaurar una cuenta de usuario. 
    
## <a name="restore-one-or-more-user-accounts"></a>Restaurar una o más cuentas de usuario

Para realizar estos pasos, debe ser administrador global o administrador de administración de usuarios en Office 365. 
  
 
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **la** \> página usuarios <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados</a> .

::: moniker-end

::: moniker range="o365-germany"

1. Vaya al [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=848041)y, a continuación, seleccione **usuarios** \> **eliminados**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=850627)y, a continuación, seleccione **usuarios** \> **eliminados**.

::: moniker-end

2. En la página **usuarios eliminados** , seleccione los nombres de los usuarios que desea restaurar y, a continuación, seleccione **restaurar**.
    
 
3. Siga las indicaciones para establecer su contraseña y, después, seleccione **restaurar**.
    
4. Si el usuario se ha restaurado correctamente, seleccione **Enviar correo electrónico y cerrar**. Si se produce un conflicto de nombres o un conflicto de direcciones de proxy, vea las instrucciones a continuación sobre cómo restaurar esas cuentas.
    
Una vez que haya restaurado un usuario, asegúrese de notificarle que su contraseña se ha modificado y que debe realizar el seguimiento.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Restaurar un usuario con un conflicto de nombre de usuario
<a name="RestoreUserNameConflict"> </a>

Se produce un conflicto de nombres de usuario al eliminar una cuenta de usuario, crear una nueva con el mismo nombre de usuario (para el mismo usuario o para otro con un nombre parecido) y, más tarde, intentar restaurar la cuenta eliminada.
  
Para resolverlo, puede cambiar la cuenta de usuario activa por la que vaya a restaurar. También puede asignar otro nombre de usuario a la cuenta que vaya a restaurar, de modo que no haya dos cuentas con el mismo nombre de usuario. Siga estos pasos.
  

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **la** \> página usuarios <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados</a> .

::: moniker-end

::: moniker range="o365-germany"

1. Vaya al [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=848041)y, a continuación, seleccione **usuarios** \> **eliminados**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=850627)y, a continuación, seleccione **usuarios** \> **eliminados**.

::: moniker-end

  
2. En la página **usuarios eliminados** , seleccione los nombres de los usuarios que desea restaurar y, a continuación, seleccione **restaurar**.
    
    > [!NOTE]
    > Si se produce un error al restaurar dos o más usuarios, un mensaje de error le advierte sobre ello. Vea el registro para comprobar qué usuarios no se restauraron y, después, restaure las cuentas en las que se haya producido el error de una en una. 
  
3. Siga las indicaciones para establecer la contraseña y seleccione **restaurar**.
    
4. Aparece un mensaje que le avisa de que se ha producido un problema al restaurar la cuenta. Realice una de las acciones siguientes:
    
  - Cancele la restauración, cambie el nombre del usuario activo y vuelva a intentar la restauración.
    
  - O bien, escriba una nueva dirección de correo electrónico principal para el usuario y seleccione **restaurar**.
    
5. Después de revisar los resultados, seleccione **Cerrar**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Restaurar un usuario que tenga un conflicto de dirección del proxy

Se produce un conflicto de direcciones de proxy al eliminar una cuenta de usuario que contiene una dirección de proxy, asignar la misma dirección de proxy a otra cuenta y, después, intentar restaurar la cuenta eliminada. Siga los pasos que se indican a continuación para solucionar este problema.
  
Debe tener [permisos de administrador](about-admin-roles.md) en Office 365 para realizar esta acción. 
  

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a **la** \> página usuarios <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminados</a> .

::: moniker-end

::: moniker range="o365-germany"

Vaya al [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=848041)y, a continuación, seleccione **usuarios** \> **eliminados**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=850627)y, a continuación, seleccione **usuarios** \> **eliminados**.

::: moniker-end

2. En la página **Usuarios eliminados**, seleccione los usuarios que quiere restaurar y luego seleccione **Restaurar**. 
    
3. En la página **restaurar** , siga las instrucciones para establecer la contraseña y seleccione **restaurar**. Las direcciones del proxy que estén en conflicto se eliminan automáticamente del usuario que vaya a restaurar.
    
4. Después de revisar los resultados, seleccione **Cerrar**.

## <a name="related-articles"></a>Artículos relacionados

[Eliminar un usuario](delete-a-user.md)
  

