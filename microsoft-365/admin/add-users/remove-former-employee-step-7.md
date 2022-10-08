---
title: 'Paso 7: Eliminación de la cuenta de usuario de un antiguo empleado'
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- m365solution-removeemployee
search.appverid:
- BCS160
- MET150
- MOE150
description: Después de guardar y acceder a todos los datos de usuario de un empleado anterior, puede eliminar la cuenta del empleado anterior en el Centro de administración de Microsoft 365.
ms.openlocfilehash: ad3d40aada0b73f82ffad702aebbbea3605b985d
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68205253"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>Paso 7: Eliminación de la cuenta de usuario de un antiguo empleado

Después de haber guardado y accedido a todos los datos de usuario del antiguo empleado, puede suprimir su cuenta.

> [!IMPORTANT]
> Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea eliminar.
3. En el nombre del usuario, seleccione **Eliminar usuario**. Elija las opciones que desee para este usuario y, a continuación, seleccione **Eliminar usuario**. Si ya ha dado acceso a otro usuario al correo electrónico de este usuario y a OneDrive, no tiene que volver a hacerlo aquí.

Al eliminar un usuario, la cuenta se vuelve inactiva durante aproximadamente 30 días. Hasta entonces, tiene que restaurar la cuenta antes de que se elimine permanentemente.

## <a name="watch-delete-a-former-employees-user-account"></a>Inspección: Eliminación de la cuenta de usuario de un antiguo empleado

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

## <a name="does-your-organization-use-active-directory"></a>¿Su organización utiliza Active Directory?

Si su organización sincroniza las cuentas de usuario con Microsoft 365 desde un entorno local de Active Directory, debe eliminar y restaurar esas cuentas de usuario en el servicio local de Active Directory. No puede suprimirlas ni restaurarlas en Office 365.

Para obtener información sobre cómo eliminar y restaurar una cuenta de usuario en Active Directory, consulte [Eliminación de una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).
  
Si usa Azure Active Directory, consulte el cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) de PowerShell.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Todo lo que debe saber sobre el cierre de la sesión de un empleado

Aquí tiene información sobre cómo quitar a un empleado del correo electrónico (Exchange).

<br>

****

|Qué puede hacer|Cómo debe hacerlo|
|:-----|:-----|
|Cerrar una sesión (de Outlook en la Web, Outlook, Exchange Active Sync, etc.) y forzar el inicio de una sesión nueva|Restablecer la contraseña|
|Cerrar una sesión y bloquear el acceso a sesiones futuras (para todos los protocolos)|Deshabilite la cuenta. Por ejemplo, en el Centro de administración de Exchange o mediante PowerShell: <p>  `Set-Mailbox user@contoso.com -AccountDisabled:$true`|
|Cerrar la sesión de un protocolo en particular (como ActiveSync)|Deshabilite el protocolo. Por ejemplo, en el Centro de administración de Exchange o mediante PowerShell: <p>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false`|
|

Las operaciones anteriores se pueden realizar en tres lugares:
  
<br>

****

|Si cierra la sesión aquí|Cuánto tiempo se tarda|
|---|---|
|En el centro de administración de Exchange o usando PowerShell|La duración estimada es de 30 minutos|
|En el centro de administración de Azure Active Directory|La duración estimada es de 60 minutos|
|En un entorno local|La duración estimada es de 3 horas o más|
|

### <a name="how-to-get-fastest-response-for-account-termination"></a>Procedimiento para obtener una respuesta más rápida para la eliminación de la cuenta

**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.
  
**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.
  
## <a name="related-content"></a>Contenido relacionado

[Restauración de un usuario](restore-user.md) (artículo)

[Restablecer contraseñas](reset-passwords.md) (artículo)
