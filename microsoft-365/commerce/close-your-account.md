---
title: Cerrar la cuenta
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Obtenga información sobre cómo cerrar su cuenta con Microsoft.
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376322"
---
# <a name="close-your-account"></a>Cerrar la cuenta

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Al cerrar la cuenta de Microsoft, se elimina toda la información relacionada con su cuenta. Esta información incluye suscripciones, licencias, métodos de pago, usuarios y datos de usuario.

## <a name="before-you-begin"></a>Antes de empezar

Antes de iniciar este proceso, asegúrese de realizar una copia de seguridad de los datos que desea conservar.

Debe ser administrador global o de facturación para realizar las tareas de este artículo. Para obtener más información, vea [Sobre los roles de administrador](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Paso 1: Eliminar usuarios

Elimine todos los usuarios excepto un administrador global. El administrador global completa los pasos para cerrar la cuenta. Antes de poder eliminar el directorio al final de este proceso, debe eliminar todos los demás usuarios.

Si los usuarios se sincronizan desde el entorno local, desactive primero la sincronización y, a continuación, elimine los usuarios del directorio de nube con los cmdlets de Azure Portal o Azure PowerShell.

Para eliminar usuarios, vea <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Administración de usuarios: Eliminar uno o más usuarios.</a>

También puede usar el cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell para eliminar usuarios de forma masiva.

Si su organización usa Active Directory que se sincroniza con Microsoft Azure Active Directory (Azure AD), elimine la cuenta de usuario de Active Directory. Para obtener instrucciones, <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">consulte Eliminación masiva de usuarios en Azure Active Directory.</a>

## <a name="step-2-cancel-all-active-subscriptions"></a>Paso 2: Cancelar todas las suscripciones activas

1. En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** busque una suscripción activa. Seleccione **Más acciones** (tres puntos) y luego seleccione **Cancelar suscripción**.
3. En el panel **Cancelar suscripción**, seleccione una razón por la que cancela. Opcionalmente, proporcione algún comentario.
4. Seleccione **Guardar**.
5. Repita los pasos del 1 al 4 para cancelar todas las suscripciones activas.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Paso 3: Eliminar todas las suscripciones deshabilitadas

1. En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** seleccione una suscripción deshabilitada.
3. En la página de detalles de la suscripción, en la sección Configuración de **suscripción y pago,** seleccione **Eliminar suscripción.**
4. En el **panel Eliminar suscripción,** seleccione **Eliminar suscripción.**
5. En el **cuadro de diálogo Eliminar** suscripción, seleccione **Sí**.
6. Para cada suscripción deshabilitada, repita los pasos del 3 al 5 hasta que se eliminen todas las suscripciones.

> [!NOTE]
> Si no puede eliminar inmediatamente una suscripción deshabilitada, póngase <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">en contacto con el soporte técnico</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Paso 4: Deshabilitar la autenticación multifactor

1. Inicie sesión en el centro de administración con una cuenta de administrador global. Para comprobar qué roles tiene, consulte [Comprobar roles de administrador en su organización.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)
2. Vaya a la **página**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos.</a>
3. Elija **Autenticación multifactor.**
4. En la página de autenticación multifactor, deshabilite todas las cuentas excepto la cuenta de administrador global que está usando actualmente.

También puede usar <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">PowerShell para deshabilitar la autenticación multifactor para varios usuarios.</a>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Paso 5: Eliminar el directorio en Azure Active Directory

1. Inicia sesión en el Centro <a href="https://aad.portal.azure.com/" target="_blank">de administración de Azure AD</a> con una cuenta de administrador global.
2. Seleccione **Azure Active Directory**.
3. Cambie a la organización que desea eliminar.
4. Seleccione **Eliminar inquilino.**
5. Si su organización no supera una o más comprobaciones, verá un vínculo para obtener más información sobre cómo pasar las comprobaciones. Después de pasar todas las comprobaciones, **seleccione Eliminar** para completar el proceso.

Después de completar este paso final, su cuenta con Microsoft se cerrará y eliminará.