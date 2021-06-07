---
title: 'Paso 7: Eliminar la cuenta de usuario de un antiguo empleado'
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga estos pasos para eliminar la cuenta de usuario de un antiguo empleado.
ms.openlocfilehash: e9f87f68650394a81c735346db929bf592e91d18
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779836"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>Paso 7: Eliminar la cuenta de usuario de un antiguo empleado

Después de haber guardado y accedido a todos los datos de usuario del antiguo empleado, puede suprimir su cuenta.

> [!IMPORTANT]
> No elimine la cuenta si ha configurado el reenvío de correo electrónico o la ha convertido en un buzón compartido. En ambos casos se necesita la cuenta para anclar el reenvío de correo o el buzón compartido.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea eliminar.
3. En el nombre del usuario, seleccione **Eliminar usuario**. Elija las opciones que desee para este usuario y, a continuación, **seleccione Eliminar usuario**. Si ya ha concedido a otro usuario acceso al correo electrónico y al OneDrive, no tiene que volver a hacerlo aquí.

Al eliminar un usuario, la cuenta se vuelve inactiva durante aproximadamente 30 días. Tiene tiempo hasta ese momento para restaurar la cuenta antes de que se elimine de forma permanente.

## <a name="watch-delete-a-former-employees-user-account"></a>Watch: Delete a former employee's user account

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

## <a name="does-your-organization-use-active-directory"></a>¿Su organización utiliza Active Directory?

Si su organización sincroniza las cuentas de usuario Microsoft 365 desde un entorno local de Active Directory, debe eliminar y restaurar esas cuentas de usuario en el servicio de Active Directory local. No puede suprimirlas ni restaurarlas en Office 365.

Para obtener información sobre cómo eliminar y restaurar una cuenta de usuario en Active Directory, vea [Eliminar una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).
  
Si usas Azure Active Directory, consulta el cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Todo lo que debe saber sobre el cierre de la sesión de un empleado

Aquí tiene información sobre cómo quitar a un empleado del correo electrónico (Exchange).
  
|||
|:-----|:-----|
|**Qué puede hacer** <br/> |**Cómo debe hacerlo** <br/> |
|Cerrar una sesión (de Outlook en la Web, Outlook, Exchange Active Sync, etc.) y forzar el inicio de una sesión nueva  <br/> |Restablecer la contraseña  <br/> |
|Cerrar una sesión y bloquear el acceso a sesiones futuras (para todos los protocolos)  <br/> |Deshabilite la cuenta. Por ejemplo, (en el centro Exchange administración o mediante PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Cerrar la sesión de un protocolo en particular (como ActiveSync)  <br/> |Deshabilite el protocolo. Por ejemplo, (en el centro Exchange administración o mediante PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

Las operaciones anteriores se pueden realizar en tres lugares:
  
|||
|:-----|:-----|
|**Si cierra la sesión aquí** <br/> |**Cuánto tiempo se tarda** <br/> |
|En el centro de administración de Exchange o usando PowerShell  <br/> |La duración estimada es de 30 minutos  <br/> |
|En el centro de administración de Azure Active Directory  <br/> |La duración estimada es de 60 minutos  <br/> |
|En un entorno local  <br/> |La duración estimada es de 3 horas o más  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>Procedimiento para obtener una respuesta más rápida para la eliminación de la cuenta

 **Más rápida**: use el Centro de administración de Exchange (use PowerShell) o el Centro de administración de Azure Active Directory. En un entorno local, el cambio mediante DirSync puede tardar varias horas en sincronizarse.
  
 **Más rápida para un usuario con presencia local y en el centro de datos de Exchange**: finalice la sesión mediante el Centro de administración de Azure Active Directory o el Centro de administración de Exchange Y efectúe también el cambio en el entorno local. En caso contrario, DirSync sobrescribirá el cambio realizado en el Centro de administración de Exchange o el Centro de administración Azure Active Directory.
  
## <a name="related-articles"></a>Artículos relacionados

[Restaurar un usuario](restore-user.md)

[Restablecer contraseñas](reset-passwords.md)
