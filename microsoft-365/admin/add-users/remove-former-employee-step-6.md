---
title: 'Paso 6: Eliminación y eliminación de la licencia de Microsoft 365 de un empleado anterior'
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
description: Puede quitar la licencia de Microsoft 365 de un empleado anterior y, a continuación, eliminarla de su suscripción o asignarla a otro usuario.
ms.openlocfilehash: 8d1c903a9f829605b15887b2b67e7ea61962cbfe
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68186115"
---
# <a name="step-6---remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Paso 6: Eliminación y eliminación de la licencia de Microsoft 365 de un empleado anterior

Si no quiere pagar una licencia después de que alguien deje la organización, debe quitar su licencia de Microsoft 365 y, a continuación, eliminarla de la suscripción. Puede asignar una licencia a otro usuario si no la elimina.

Si las personas autorizadas a las que se les han concedido permisos de exhibición de documentos electrónicos por motivos legales o de cumplimiento deben tener acceso al buzón de correo, se le debe asignar una licencia de Exchange Online Plan 2 (o una licencia de Exchange Online Plan 1 con una Archivado de Exchange Online  licencia de complemento) para que se pueda aplicar una suspensión al buzón antes de que se elimine. Una vez eliminada la cuenta de usuario, cualquier licencia de Exchange Online asociada a la cuenta de usuario estará disponible para asignarla a un nuevo usuario.
  
Al quitar la licencia, todos los datos de ese usuario se conservan durante 30 días. Puede [acceder](get-access-to-and-back-up-a-former-user-s-data.md) a los datos o [restaurar](restore-user.md) la cuenta si el usuario se vuelve a incorporar. Después de 30 días, todos los datos del usuario (excepto los documentos almacenados en SharePoint Online) se eliminan permanentemente de Microsoft 365 y no se pueden recuperar.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea bloquear y, a continuación, seleccione la pestaña **Licencias y aplicaciones** .
3. Desactive las casillas de las licencias que desea quitar y, a continuación, seleccione **Guardar cambios**.

**Para reducir el número de licencias que paga** hasta que contrate a otra persona, siga estos pasos:

1. En el centro de administración, vaya a la página **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de sus productos</a> y seleccione la pestaña **Productos** .
2. Seleccione la suscripción de la que desea quitar licencias.
3. En la página de detalles, seleccione **Quitar licencias**.
4. En el panel **Quitar licencias** , en Nueva cantidad, en el cuadro **Total de licencias** , escriba el número total de licencias que desea para esta suscripción. Por ejemplo, si tiene 25 licencias y desea quitar una de ellas, escriba 24.
5. Seleccione **Guardar**.

Cuando [agregue otra persona](add-users.md) a su empresa, se le pedirá que compre una licencia al mismo tiempo, con un solo paso.

Para obtener más información sobre cómo administrar licencias de usuario para Microsoft 365 para empresas, consulte [Asignación de licencias a usuarios de Microsoft 365 para empresas](../manage/assign-licenses-to-users.md) y [Anulación de la asignación de licencias de usuarios en Microsoft 365 para empresas](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Cómo afectan las cuentas de empleados eliminadas a Skype Empresarial

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Configuración del reenvío de llamadas a personas de la organización

Si necesita configurar el reenvío de llamadas para el número de teléfono del empleado terminado, la configuración de reenvío de llamadas en las directivas de llamada puede configurar el reenvío donde las llamadas entrantes se pueden reenviar a otros usuarios o pueden llamar a otra persona al mismo tiempo. Para obtener más información, consulte [Directivas de llamada en Microsoft Teams](/microsoftteams/teams-calling-policy).
