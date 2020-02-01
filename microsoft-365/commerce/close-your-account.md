---
title: Cerrar la cuenta
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
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Obtenga información sobre cómo cerrar su cuenta con Microsoft.
ms.openlocfilehash: bbb3b56d72c0f67e7771c9a188df751aa3dd95ed
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594144"
---
# <a name="close-your-account"></a>Cerrar la cuenta

Al cerrar la cuenta con Microsoft, se elimina toda la información relacionada con su cuenta. Esta información incluye las suscripciones, las licencias, los métodos de pago, los usuarios y los datos de usuario. Antes de iniciar este proceso, asegúrese de hacer una copia de seguridad de los datos que desee conservar.

## <a name="step-1-delete-users"></a>Paso 1: eliminar usuarios

Elimine todos los usuarios excepto un administrador global que complete los pasos para cerrar la cuenta. Antes de poder eliminar el directorio al final de este proceso, debe eliminar todos los demás usuarios.

Si los usuarios están sincronizados desde una ubicación local, primero desactive la sincronización y, a continuación, elimine los usuarios en el directorio de nube con los cmdlets de Azure portal o Azure PowerShell.

Para eliminar usuarios, consulte <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Administrador de administración de usuarios: eliminar uno o más usuarios</a>.

También puede usar el cmdlet de PowerShell <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> para eliminar usuarios de forma masiva.

Si su organización usa Active Directory que se sincroniza con Azure AD, elimine la cuenta de usuario de Active Directory en su lugar. Para obtener instrucciones, consulte <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">bulk Delete users in Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Paso 2: cancelar todas las suscripciones activas

1. En el centro de administración, vaya a la página productos de **facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& Services</a> .

2. Si la lista de suscripciones está en la vista de **tabla** , a la derecha, seleccione **tarjetas**.

3. Busque una suscripción activa y, en la sección **configuración & acciones** , seleccione **Cancelar suscripción**.

4. Siga las indicaciones para finalizar el proceso.

5. Repita los pasos del 1 al 4 para cancelar todas las suscripciones activas.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Paso 3: eliminar todas las suscripciones deshabilitadas

1. En el centro de administración, vaya a la página productos de **facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">& Services</a> .

2. Si la lista de suscripciones está en la vista de **tabla** , a la derecha, seleccione **tarjetas**.

3. Junto a **Estado de suscripción**, seleccione **deshabilitado**.

4. Busque una suscripción deshabilitada y, en la sección **configuración & acciones** , seleccione **eliminar**.

5. En el cuadro de diálogo **eliminar suscripción** , active la casilla de verificación **entiendo el impacto** y, a continuación, seleccione **eliminar suscripción**.

6. Para cada suscripción deshabilitada, repita los pasos 4 y 5 hasta que se hayan eliminado todas las suscripciones.

## <a name="step-4-disable-multi-factor-authentication"></a>Paso 4: deshabilitar multi-factor Authentication

1. En el centro de administración, vaya a **la** > página usuarios<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">activos</a> .

2. Elija **multi-factor Authentication**.

3. En la página autenticación multifactor, deshabilite todas las cuentas excepto la cuenta de administrador global que está usando actualmente.

También puede <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">usar PowerShell para deshabilitar multi-factor Authentication para varios usuarios</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Paso 5: eliminar el directorio en Azure Active Directory

1. Inicie sesión en el <a href="https://aad.portal.azure.com/" target="_blank">centro de administración de Azure ad</a> con una cuenta de administrador global.

2. Seleccione **Azure Active Directory**.

3. Cambie al directorio que desee eliminar.

4. Seleccione **eliminar directorio**.

5. Si el directorio produce un error en una o más comprobaciones, verá un vínculo para obtener más información sobre cómo pasar las comprobaciones. Después de pasar todas las comprobaciones, seleccione **eliminar** para completar el proceso.

Después de completar este paso final, su cuenta con Microsoft se cierra y se elimina.