---
title: Proteger las cuentas de administrador en Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
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
description: Obtenga información sobre cómo configurar y proteger las cuentas de administrador en Microsoft 365 Empresa Premium.
ms.openlocfilehash: b054267264b8440929559ad1a2e335449f3c0309
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091531"
---
# <a name="protect-your-administrator-accounts-in-microsoft-365-business-premium"></a>Proteger las cuentas de administrador en Microsoft 365 Empresa Premium

Dado que las cuentas de administrador incluyen privilegios elevados, son un objetivo de valor para hackers y ciberdelincuentes. Este artículo describe:

- Cómo configurar otra cuenta Administrador para emergencias.
- Cómo proteger estas cuentas.

Cuando se registra en Microsoft 365 e introduce su información, se convierte automáticamente en Administrador global (también conocido como Administrador de empresa). Un administrador global tiene el control final de las cuentas de usuario y de todas las demás configuraciones en el Centro de administración de Microsoft ([https://admin.microsoft.com](https://admin.microsoft.com)). Sin embargo, existen varios tipos de cuentas de administrador con distintos niveles de acceso. Consulte [acerca de los roles de administrador](/office365/admin/add-users/about-admin-roles) para obtener información sobre los distintos niveles de acceso para cada tipo de rol de administrador.

## <a name="create-additional-admin-accounts"></a>Crear cuentas de administrador adicionales

Use cuentas de administrador solo para la administración. Los administradores deben tener una cuenta de usuario independiente para usar las aplicaciones de Office de forma habitual y solo usar la cuenta administrativa cuando sea necesario para gestionar cuentas y dispositivos y mientras trabajan en otras funciones de administrador. Además, es una buena idea quitar la licencia de Microsoft 365 de las cuentas de administrador para que no tenga que pagar por ellas.

Querrá configurar al menos una cuenta de administrador global extra para dar acceso de administrador a otro empleado de confianza. También puede crear cuentas de administrador independientes para la administración de usuarios (este rol se denomina **Administrador de control de usuarios**). Para más información, consulte [Sobre los roles de administrador](/office365/admin/add-users/about-admin-roles).

Para crear cuentas de administrador adicionales:

 1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Centro de administración de Microsoft 365</a> y elija **Usuarios** \> **Usuarios activos** en el panel de navegación izquierdo.

    ![Elija Usuarios y, a continuación, Usuarios activos en el panel de navegación izquierdo.](../media/Activeusers.png)

 2. En la página **Usuarios activos**, seleccione **Agregar un usuario** en la parte superior de la página y, en el panel **Nuevo usuario**, escriba el nombre y cualquier otra información.

 3. Expanda la sección **Roles** y elija **Administrador global** para conceder a este usuario acceso de administrador global. También puede elegir **Administrador personalizado** y elegir cualquiera de los roles que se muestran.

    Escriba un correo electrónico alternativo en el cuadro de texto **Dirección de correo electrónico alternativa**. Podrá usar esta dirección para recuperar la información de contraseña si no puede acceder. En el caso de los administradores globales, también se enviará un extracto de facturación a esta dirección.

    ![Elija el rol de administrador.](../media/adminroles.png)

 4. En la sección **Licencias de producto**, mueva el selector de **Microsoft 365 Empresa** a **Desactivado** y **Crear usuario sin licencia de producto** a **Activado**.

    ![Elija la licencia del producto.](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Crear una cuenta de administrador de emergencia

También debería crear una cuenta como copia de seguridad que no esté configurada con autenticación multifactor (MFA) para que no se bloquee accidentalmente (por ejemplo, si pierde el teléfono que usa como otra forma de comprobación). Asegúrese de que la contraseña de esta cuenta tenga una frase o al menos 16 caracteres. Esto se conoce a menudo como una "cuenta de emergencia".

## <a name="create-a-user-account-for-yourself"></a>Crear una cuenta de usuario propia

Use su cuenta de usuario para colaborar con su organización, incluido comprobar el correo electrónico. Lo que significa que las credenciales de administrador pueden ser similares a  *Alice.Chavez <span></span>@Contoso.org* y la cuenta de usuario habitual podría asemejarse a *Alice <span></span>@Contoso.com*.

Para crear una nueva cuenta de usuario:

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Centro de administración de Microsoft 365</a> y elija **Usuarios** \> **Usuarios activos** en el panel de navegación izquierdo.

2. En la página **Usuarios activos**, seleccione **Agregar un usuario** en la parte superior de la página y, en el panel **Nuevo usuario**, escriba el nombre y cualquier otra información.

3. Expanda la sección **Roles** y elija **Usuario (sin acceso administrativo)**.

4. En la sección **Licencias de producto**, mueva el selector de **Microsoft 365 Empresa** a **Activado**.

## <a name="additional-recommendations"></a>Recomendaciones adicionales

- Antes de usar cuentas de administrador, cierre todas las aplicaciones y sesiones de explorador no relacionadas, incluidas las cuentas de correo electrónico personales. También podrá usar ventanas de explorador privadas o de incógnito.

- Después de completar las tareas de administrador, asegúrese de cerrar la sesión del explorador.

## <a name="next-objective"></a>Siguiente objetivo

Realice los pasos necesarios para [activar los valores predeterminados de seguridad](m365bp-conditional-access.md).

