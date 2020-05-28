---
title: Agregar usuarios individualmente o de forma masiva
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: Obtenga información sobre cómo agregar usuarios a Microsoft 365, uno por vez o varios usuarios al mismo tiempo desde un archivo CSV.
ms.openlocfilehash: 1b63f09bf34f5ca54be83eedfac9188251578a05
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387266"
---
# <a name="add-users-individually-or-in-bulk"></a>Agregar usuarios individualmente o de forma masiva

Los usuarios de su equipo necesitan una cuenta de usuario para poder iniciar sesión y obtener acceso a [Microsoft 365 para la empresa](https://go.microsoft.com/fwlink/?LinkID=519395). La forma más sencilla de agregar cuentas de usuario es agregarlas de una en una a la vez en el centro de administración de 365 de Microsoft. Después de realizar este paso, los usuarios tendrán licencias de 365 de Microsoft, credenciales de inicio de sesión y buzones de correo de 365 de Microsoft.

::: moniker range="o365-worldwide"

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

1. Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Vaya a **usuarios** > **activos**y seleccione **Agregar un usuario**.
   
3. En el panel **configurar los conceptos básicos** , rellene la información siguiente y, a continuación, seleccione **siguiente**. 
  
- **Nombre** de Rellene primero, último, nombre para mostrar y nombre de usuario. 
    
- **Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y su dominio es contoso.com, tendrá que iniciar sesión escribiendo jakob@contoso.com. 
    
- **Configuración de contraseña** Elija usar contraseña generada automáticamente o crear su propia contraseña segura para el usuario. 
    
    - Necesitará cambiar su contraseña después de 90 días. O bien, puede optar por **requerir que este usuario cambie su contraseña la primera vez que inicie sesión**.
    
    - Elija si desea enviar la contraseña por correo electrónico cuando se haya agregado al usuario. 
    
4. En el panel **asignar licencias de producto** , seleccione la ubicación y la licencia correspondiente para el usuario. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales. Seleccione **Siguiente**.

5. En la página **configuración opcional** , expanda **roles** si desea que el usuario sea administrador y expanda **información de perfil** si desea agregar información adicional sobre el usuario. 

6. Seleccione **siguiente**, revise la configuración del nuevo usuario, realice los cambios que desee y, a continuación, seleccione **terminar de agregar**. 

::: moniker-end


::: moniker range="o365-germany"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

2. Vaya a **usuarios** > **activos**y seleccione **Agregar un usuario**.
   
  
   En el panel **nuevo usuario** , rellene la siguiente información. Seleccione **Agregar** cuando haya terminado. 
  
- **Nombre** Rellene el nombre, apellido, nombre para mostrar y nombre de usuario. 
    
- **Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y su dominio es contoso.com, tendrá que iniciar sesión escribiendo jakob@contoso.com. 
    
- **Información de contacto** Expándala para rellenar el número de teléfono móvil, la dirección y demás datos similares. 
    
- **Contraseña** Use la contraseña generada automáticamente o expándala para especificar una contraseña segura para el usuario. 
    
    Necesitará cambiar su contraseña después de 90 días. También puede elegir la opción **Solicitar a este usuario que cambie su contraseña la primera vez que inicie sesión**.
    
- **Roles** Expándala si necesita hacer que este usuario sea administrador. 
    
- **Licencias de producto** Expanda esta sección y seleccione la licencia adecuada. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

2. Vaya a **usuarios** > **activos**y seleccione **Agregar un usuario**.
   
  
   En el panel **nuevo usuario** , rellene la siguiente información. Seleccione **Agregar** cuando haya terminado. 
  
- **Nombre** Rellene el nombre, apellido, nombre para mostrar y nombre de usuario. 
    
- **Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y su dominio es contoso.com, tendrá que iniciar sesión escribiendo jakob@contoso.com. 
    
- **Información de contacto** Expándala para rellenar el número de teléfono móvil, la dirección y demás datos similares. 
    
- **Contraseña** Use la contraseña generada automáticamente o expándala para especificar una contraseña segura para el usuario. 
    
    Necesitará cambiar su contraseña después de 90 días. También puede elegir la opción **Solicitar a este usuario que cambie su contraseña la primera vez que inicie sesión**.
    
- **Roles** Expándala si necesita hacer que este usuario sea administrador. 
    
- **Licencias de producto** Expanda esta sección y seleccione la licencia adecuada. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales. 

::: moniker-end 
  
Después de agregar un usuario, recibirá una notificación del equipo de Microsoft Online Services. El correo electrónico contendrá el identificador de usuario y la contraseña de la persona para que puedan iniciar sesión en Microsoft 365. Debe informar a su nuevo usuario sobre la información de inicio de sesión de 365 de Microsoft. Use el proceso habitual para comunicar nuevas contraseñas.

> [!NOTE]
>Si crea usuarios mediante la migración de buzones de correo, tendrá que activar las cuentas de usuario mediante la asignación de licencias. Si no asigna una licencia a un usuario, su buzón se deshabilitará después de un período de gracia de 30 días. Consulte cómo [asignar licencias a usuarios](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) mediante el centro de administración de Microsoft 365.

### <a name="video-add-and-manage-users-in-the-admin-center"></a>Vídeo: agregar y administrar usuarios en el centro de administración

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a>Pasos siguientes

Comparta la [Guía de inicio rápido de empleado](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) con los nuevos usuarios para realizar la configuración, como [Office en un equipo PC o Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) y [Aplicaciones móviles de Office](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).
  
## <a name="need-help"></a>¿Necesita ayuda?

[Póngase en contacto con el soporte técnico de Microsoft 365 para empresas](../contact-support-for-business-products.md).  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a>¿Tiene cientos o miles de usuarios que agregar?


Para agregar varios usuarios al mismo tiempo, siga estos pasos:
  
- **Use una hoja de cálculo para agregar usuarios en masa.** Consulte [agregar varios usuarios al mismo tiempo](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).
    
- **Automatice la agregación de cuentas y la asignación de licencias.** Consulte [Create User accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell). Seleccione este método si ya está familiarizado con el uso de cmdlets de Windows PowerShell.
    
- **¿Usa ActiveDirectory?** [Configurar la sincronización de directorios para Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization). Use la herramienta Azure AD Connect para replicar cuentas de usuario de Active Directory (y otros objetos de Active Directory) en Office 365. La sincronización solo agrega las cuentas de usuario. Deberá asignar licencias a los usuarios sincronizados para que puedan usar el correo electrónico y otras aplicaciones de Office.
    
- **¿Va a migrar desde Exchange?** [Formas de migrar varias cuentas de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration). Al migrar varios buzones de correo a Microsoft 365 mediante transferencia, preconfigurada o un método de Exchange híbrido, agregará usuarios automáticamente como parte de la migración. La migración solo agrega las cuentas de usuario. Deberá asignar licencias a los usuarios para que puedan usar el correo electrónico y las aplicaciones de Office.

## <a name="related-articles"></a>Artículos relacionados

[Agregar un nuevo empleado a Microsoft 365](add-new-employee.md)

[Eliminar un usuario de la organización](delete-a-user.md)

[Restaurar un usuario en Microsoft 365](restore-user.md)

[Agregar varios usuarios al mismo tiempo a Microsoft 365](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)

