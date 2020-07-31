---
title: Proteger las cuentas de administrador
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Obtenga información sobre cómo configurar y proteger las cuentas de administrador.
ms.openlocfilehash: dc5f72cda0255641d7d2407d266a6ae584560733
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527191"
---
# <a name="protect-your-administrator-accounts"></a>Proteger las cuentas de administrador

Como las cuentas de administrador tienen privilegios elevados, son objetivos muy valiosos para los hackers y los delincuentes cibernéticos. Este artículo describe:

- Cómo configurar una cuenta de administrador adicional para las emergencias.
- Cómo proteger estas cuentas.
 
Cuando se suscriba a Microsoft 365 y escriba la información, se convertirá automáticamente en el administrador global. Un administrador global tiene el control final de las cuentas de usuario y el resto de la configuración en el centro de administración de Microsoft, pero hay muchos tipos diferentes de cuentas de administrador con distintos grados de acceso. Consulte [acerca](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) de los roles de administrador para obtener información sobre los diferentes niveles de acceso para cada tipo de rol de administrador.


## <a name="create-additional-admin-accounts"></a>Crear cuentas de administrador adicionales

Use cuentas de administrador solo para la administración. Los administradores deben tener una cuenta de usuario independiente para el uso normal de las aplicaciones de Office y solo usar su cuenta administrativa cuando sea necesario para administrar cuentas y dispositivos, y mientras se trabaja en otras funciones de administración. También es una buena idea quitar la licencia de Microsoft 365 de las cuentas de administrador para que no tenga que pagar por ellas.

Querrá configurar al menos una cuenta de administrador global adicional para conceder acceso de administrador a otro empleado de confianza. También puede crear cuentas de administrador independientes para la administración de usuarios (este rol se denomina **Administrador de administración de usuarios**). Para obtener más información, vea [acerca de los roles de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

Para crear cuentas de administrador adicionales:

 1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administración</a> y, a continuación, elija usuarios **Users** \> **activos** de usuarios en el panel de navegación izquierdo.

    ![Elija usuarios y, a continuación, usuarios activos en el panel de navegación izquierdo](../media/Activeusers.png)

2. En la página **usuarios activos** , seleccione **Agregar un usuario** en la parte superior de la página y, en el panel **nuevo usuario** , escriba el nombre y otra información.
3. Expanda la sección **roles** y elija **administrador global** para conceder a este usuario acceso de administrador global. También puede elegir **Administrador personalizado** y elegir cualquiera de los roles que se muestran.

    Escriba un correo electrónico alternativo en el cuadro de texto **dirección de correo alternativa** . Puede usar esta dirección para recuperar la información de contraseña si se bloquea. Para los administradores globales, también se enviará una declaración de facturación a esta dirección.

    ![Elegir el rol de administrador](../media/adminroles.png)
    
4. En la sección **licencias de productos** , mueva el selector de **Microsoft 365 Business** a **desactivado** y la opción **crear usuario sin licencia de producto** en **activado**.

    ![Elegir la licencia del producto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Crear una cuenta de administrador de emergencia

También debe crear una cuenta de copia de seguridad que no esté configurada con multi-factor Authentication (MFA), de modo que no se bloquee por error (por ejemplo, si pierde el teléfono que está usando como segunda forma de verificación). Asegúrese de que la contraseña de esta cuenta es una frase o al menos 16 caracteres de longitud. Esto se conoce a menudo como una "cuenta de" Break-Glass ".

## <a name="create-a-user-account-for-yourself"></a>Crear una cuenta de usuario para usted

Use su cuenta de usuario para participar en la colaboración con su organización, incluida la comprobación del correo. Esto significa que las credenciales de administrador podrían ser similares a *Alice. Chavez <span></span> @Contoso. org* y la cuenta de usuario normal podría ser similar a *Alice <span></span> @Contoso. com*.

Para crear una nueva cuenta de usuario:
1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administración</a> y, a continuación, elija usuarios **Users** \> **activos** de usuarios en el panel de navegación izquierdo.
2. En la página **usuarios activos** , seleccione **Agregar un usuario** en la parte superior de la página y, en el panel **nuevo usuario** , escriba el nombre y otra información.
3. Expanda la sección **roles** y elija **usuario (sin acceso administrativo)**.
1. En la sección **licencias de producto** , mueva el selector de **Microsoft 365 empresa** a **activado**. 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registrar cada una de estas cuentas para la autenticación multifactor


## <a name="additional-recommendations"></a>Recomendaciones adicionales

- Asegúrese de que las cuentas de administrador también están configuradas para la autenticación multifactor. Le mostraremos cómo hacerlo en [configurar directivas de acceso condicional](m365-campaigns-conditional-access.md).
- Antes de usar cuentas de administrador, cierre todas las sesiones y aplicaciones del explorador no relacionadas, incluidas las cuentas de correo electrónico personales. También puede usar en las ventanas del explorador privado o incógnito.
- Después de completar las tareas de administración, asegúrese de cerrar la sesión del explorador.
