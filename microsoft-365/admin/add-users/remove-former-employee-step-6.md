---
title: 'Paso 6: Quitar y eliminar la Microsoft 365 de un antiguo empleado'
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
description: Siga estos pasos para quitar la Microsoft 365 de un antiguo empleado.
ms.openlocfilehash: ed86eb28cc6d4996f7def8cb567f0e4085e67624
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244277"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a>Paso 6: Quitar la licencia Microsoft 365 de un antiguo empleado

Si no quieres pagar una licencia después de que alguien abandone la organización, debes quitar su licencia Microsoft 365 y, a continuación, eliminarla de la suscripción. Puedes asignar una licencia a otro usuario si no la eliminas.
  
Al quitar la licencia, todos los datos de ese usuario se conservan durante 30 días. Puede [acceder](get-access-to-and-back-up-a-former-user-s-data.md) a los datos o [restaurar](restore-user.md) la cuenta si el usuario se vuelve a incorporar. Después de 30 días, todos los datos del usuario (excepto los documentos almacenados en SharePoint Online) se eliminan permanentemente de Microsoft 365 y no se pueden recuperar.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea bloquear y, a continuación, seleccione la pestaña **Licencias y** aplicaciones.
3. Desactive las casillas de las licencias que desea quitar y, a continuación, **seleccione Guardar cambios**.

**Para reducir el número de licencias que está pagando** hasta que contrate a otra persona, siga estos pasos:

1. En el Centro de  administración, vaya a la página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Facturación de sus productos</a> y seleccione la **pestaña** Productos.
2. Seleccione la suscripción de la que desea quitar licencias.
3. En la página de detalles, seleccione **Quitar licencias**.
4. En el **panel Quitar licencias,** en Nueva cantidad, en el cuadro **Total** de licencias, escriba el número total de licencias que desea para esta suscripción. Por ejemplo, si tiene 25 licencias y desea quitar una de ellas, escriba 24.
5. Seleccione **Guardar**.

Cuando [agregues otra persona](add-users.md) a tu empresa, se te pedirá que compres una licencia al mismo tiempo, con un solo paso.

Para obtener más información acerca de la administración de licencias de usuario para Microsoft 365 para empresas, vea Asignar licencias a usuarios de [Microsoft 365](../manage/assign-licenses-to-users.md)para empresas y [Unassign licenses from users in Microsoft 365 for business](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Cómo afectan las cuentas de empleados eliminadas a Skype Empresarial

Al quitar una licencia de usuario de Office 365, el número de RTC asociado con este se liberará. Puede asignarlo a otro usuario.
  
Si el usuario pertenece a un grupo de cola, ya no será un destino apto de los agentes de cola de llamadas. Por lo tanto, le recomendamos quitar también al usuario de los grupos asociados con la cola de llamadas.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Configurar el reenvío de llamadas a personas de la organización

Si necesita configurar el reenvío de llamadas para el número de teléfono del empleado terminado, la configuración de reenvío de llamadas en las directivas de llamadas puede configurar el reenvío donde las llamadas entrantes se pueden reenviar a otros usuarios o pueden llamar a otra persona al mismo tiempo. Para obtener más información, vea [Calling policies in Microsoft Teams](/microsoftteams/teams-calling-policy).
