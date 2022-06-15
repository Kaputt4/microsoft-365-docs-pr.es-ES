---
title: Cerrar la cuenta
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: amberb, vikdesai
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- AdminTemplateSet
search.appverid: MET150
description: Al cerrar la cuenta con Microsoft, se elimina toda la información relacionada con su cuenta, incluidas las licencias, los usuarios y los datos de usuario.
ms.date: 04/02/2021
ms.openlocfilehash: c036a4cda929d58265a088b15a43772caacb0b94
ms.sourcegitcommit: 3b194dd6f9ce531ae1b33d617ab45990d48bd3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66102468"
---
# <a name="close-your-account"></a>Cerrar la cuenta

Al cerrar la cuenta de Microsoft, se elimina toda la información relacionada con su cuenta. Esta información incluye suscripciones, licencias, métodos de pago, usuarios y datos de usuario.

## <a name="before-you-begin"></a>Antes de empezar

Antes de iniciar este proceso, asegúrese de realizar una copia de seguridad de los datos que desea conservar.

Para poder realizar las tareas de este artículo, debe ser un administrador global o de facturación. Para más información, consulte[Sobre los roles de administrador](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Paso 1: Eliminar usuarios

Elimine todos los usuarios excepto un administrador global. El administrador global completa los pasos para cerrar la cuenta. Para poder eliminar el directorio al final de este proceso, debe eliminar todos los demás usuarios.

Si los usuarios se sincronizan desde el entorno local, desactive primero la sincronización y, a continuación, elimine los usuarios en el directorio en la nube mediante los cmdlets de Azure Portal o Azure PowerShell.

Para eliminar usuarios, consulte [Administración de usuarios: Eliminar uno o varios usuarios](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).

También puede usar el cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) de PowerShell para eliminar usuarios de forma masiva.

Si su organización usa Active Directory que se sincroniza con Microsoft Azure Active Directory (Azure AD), elimine la cuenta de usuario de Active Directory. Para obtener instrucciones, consulte [Eliminación masiva de usuarios en Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).

## <a name="step-2-cancel-all-active-subscriptions"></a>Paso 2: Cancelar todas las suscripciones activas

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la pestaña **Productos** , busque una suscripción activa. Seleccione los tres puntos (más acciones) y, después, seleccione **Cancelar suscripción**.
3. En el panel **Cancelar suscripción**, seleccione una razón por la que cancela. Opcionalmente, proporcione algún comentario.
4. Seleccione **Guardar**.
5. Repita los pasos del 1 al 4 para cancelar todas las suscripciones activas.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Paso 3: Eliminar todas las suscripciones deshabilitadas

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la pestaña **Productos** , seleccione una suscripción deshabilitada.
3. En la página de detalles de la suscripción, en la sección **Configuración de suscripción y pago** , seleccione **Eliminar suscripción**.
4. En el panel **Eliminar suscripción** , seleccione **Eliminar suscripción**.
5. En el cuadro de diálogo **Eliminar suscripción** , seleccione **Sí**.
6. Para cada suscripción deshabilitada, repita los pasos del 3 al 5 hasta que se eliminen todas las suscripciones.

> [!NOTE]
> Si no puede eliminar inmediatamente una suscripción deshabilitada, [póngase en contacto con el soporte técnico](../admin/get-help-support.md).

## <a name="step-4-disable-multi-factor-authentication"></a>Paso 4: Deshabilitar la autenticación multifactor

1. Inicie sesión en el centro de administración con una cuenta de Administrador global. Para comprobar qué roles tiene, consulte [Comprobación de roles de administrador en su organización](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).
2. Vaya a la página **Usuarios** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos</a> .
3. Elija **Multi-Factor Authentication**.
4. En la página Multi-Factor Authentication, deshabilite todas las cuentas excepto la cuenta de administrador global que está usando actualmente.

También puede [usar PowerShell para deshabilitar la autenticación multifactor para varios usuarios](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Paso 5: Eliminación del directorio en Azure Active Directory

1. Inicie sesión en el <a href="https://aad.portal.azure.com/" target="_blank">Centro de administración de Azure AD</a> con una cuenta de Administrador global.
2. Seleccione **Azure Active Directory**.
3. Cambie a la organización que desea eliminar.
4. Seleccione **Eliminar inquilino**.
5. Si su organización produce un error en una o varias comprobaciones, verá un vínculo para obtener más información sobre cómo pasar las comprobaciones. Después de pasar todas las comprobaciones, seleccione **Eliminar** para completar el proceso.

Después de completar este paso final, la cuenta con Microsoft se cierra y se elimina.

## <a name="related-content"></a>Contenido relacionado 

[Conozca su factura o recibo por la compra de Microsoft 365 para Empresas](./billing-and-payments/understand-your-invoice2.md) (artículo)\
[Cancelar la suscripción](./subscriptions/cancel-your-subscription.md) (artículo)

