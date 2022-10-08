---
title: Proteger las cuentas de administrador en Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.collection:
- M365-Campaigns
- m365solution-smb
- highpri
- tier1
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: Obtenga información sobre cómo configurar y proteger las cuentas de administrador en Microsoft 365 Empresa Premium.
ms.openlocfilehash: c1d7358fd0c117b20b35870b2a04cfd03885bf7a
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097059"
---
# <a name="protect-your-administrator-accounts-in-microsoft-365-business-premium"></a>Proteger las cuentas de administrador en Microsoft 365 Empresa Premium

Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals. This article describes:

- [ Cómo configurar otra cuenta de administrador para emergencias](#create-other-admin-accounts).
- [Crear una cuenta de administrador de emergencia](#create-an-emergency-admin-account).
- [Cómo crear una cuenta de usuario para usted](#create-a-user-account-for-yourself).
- [Cómo proteger las cuentas de administrador](#protect-admin-accounts)
- [Recomendaciones adicionales](#additional-recommendations) y su [próximo objetivo](#next-objective).

Cuando se registra en Microsoft 365 e introduce su información, se convierte automáticamente en Administrador global (también conocido como Administrador de empresa). Un administrador global tiene el control final de las cuentas de usuario y de todas las demás configuraciones en el Centro de administración de Microsoft ([https://admin.microsoft.com](https://admin.microsoft.com)). Sin embargo, existen varios tipos de cuentas de administrador con distintos niveles de acceso. Consulte [acerca de los roles de administrador](/office365/admin/add-users/about-admin-roles) para obtener información sobre los distintos niveles de acceso para cada tipo de rol de administrador.

## <a name="create-other-admin-accounts"></a>Crear otras cuentas de administrador

Use cuentas de administrador solo para la administración de Microsoft 365. Los administradores deben tener una cuenta de usuario independiente para su uso habitual de las aplicaciones de Office y solo usar su cuenta administrativa cuando sea necesario para administrar cuentas y dispositivos, y mientras trabajan en otras funciones de administración. También es una buena idea quitar la licencia de Microsoft 365 de sus cuentas de administrador para que no tenga que pagar por licencias adicionales.

Querrá configurar al menos otra cuenta de administrador global para dar acceso de administrador a otro empleado de confianza. También puede crear cuentas de administrador independientes para la administración de usuarios (este rol se denomina **Administrador de control de usuarios**). Para más información, consulte [Sobre los roles de administrador](/office365/admin/add-users/about-admin-roles).

> [!IMPORTANT]
> Aunque recomendamos configurar un conjunto de cuentas de administrador, querrá limitar el número de administradores globales de su organización. Además, recomendamos adherirse al concepto de acceso con privilegios mínimos, lo que significa que solo otorga acceso a los datos y operaciones necesarios para realizar sus trabajos. [Más información sobre el principio de privilegios mínimos](/azure/active-directory/develop/secure-least-privileged-access). 

Para crear más cuentas de administrador:

 1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Centro de administración de Microsoft 365</a> y elija **Usuarios** \> **Usuarios activos** en el panel de navegación izquierdo.

    ![Elija Usuarios y, a continuación, Usuarios activos en el panel de navegación izquierdo.](../media/Activeusers.png)

 2. En la página **Usuarios activos**, seleccione **Agregar un usuario** en la parte superior de la página. 

 3. En el panel **Agregar un usuario**, escriba información básica, como la información de nombre y nombre de usuario.

 4. Escriba y configure la información de **Licencias de productos**.

 5. En **Configuración opcional**, defina el rol del usuario, incluida la adición del acceso al centro de administración si procede.

    :::image type="content" source="media/m365bp-global-admin.png" alt-text="Definir nuevos roles de usuario.":::

 6. Finalice y revise la configuración y seleccione **Finalizar la adición** para confirmar los detalles.

## <a name="create-an-emergency-admin-account"></a>Crear una cuenta de administrador de emergencia

También debe crear una cuenta de respaldo que no esté configurada con autenticación multifactor (MFA) para no bloquearse accidentalmente (por ejemplo, si pierde el teléfono que está utilizando como segunda forma de verificación). Asegúrese de que la contraseña de esta cuenta tenga una frase o al menos 16 caracteres. Esta cuenta de administrador de emergencia se suele denominar "cuenta de ruptura".

## <a name="create-a-user-account-for-yourself"></a>Crear una cuenta de usuario propia

Si es administrador, necesitará una cuenta de usuario para las tareas de trabajo habituales, como comprobar el correo. Asigne un nombre a sus cuentas para saber cuál es cuál. Por ejemplo, sus credenciales de administrador pueden ser similares a  *Alice.Chavez <span></span>@Contoso.org* y su cuenta de usuario normal puede ser similar a *Alice <span></span>@Contoso.com*.

Para crear una nueva cuenta de usuario:

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Centro de administración de Microsoft 365</a> y elija **Usuarios** \> **Usuarios activos** en el panel de navegación izquierdo.

2. En la página **Usuarios activos**, seleccione **Agregar un usuario** en la parte superior de la página y, en el panel **Agregar un usuario**, escriba el nombre y cualquier otra información.

3. En la sección **Licencias de productos**, seleccione la casilla de **Microsoft 365 Empresa Premium (sin acceso administrativo)**.

4. En la sección **Configuración opcional**, deje seleccionado el botón de radio predeterminado para **Usuario (sin acceso al centro de administración)**.

5. Finalice y revise la configuración y seleccione **Finalizar la adición** para confirmar los detalles.

## <a name="protect-admin-accounts"></a>Proteger cuentas de administrador

Para proteger todas sus cuentas de administrador, asegúrese de seguir estas recomendaciones:

- Solicitar que todas las cuentas de administrador usen la autenticación sin contraseña (como Windows Hello o una aplicación de autenticación) o MFA. Para obtener más información sobre por qué es importante la autenticación sin contraseña, consulte [el documento del producto de seguridad de Microsoft: Protección sin contraseña](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE2KEup).

- Evite usar permisos personalizados para los administradores. En lugar de conceder permisos a usuarios específicos, asigne permisos a través de roles en Azure Active Directory (Azure AD). Además, otorgue acceso solo a los datos y las operaciones necesarias para realizar la tarea en cuestión. [ Obtenga información sobre los roles con privilegios mínimos en Azure AD](/azure/active-directory/roles/delegate-by-task).

- Utilice roles integrados para asignar permisos siempre que sea posible. El control de acceso basado en roles (RBAC) de Azure tiene varios roles integrados que puede usar. [ Obtenga más información sobre los roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference).

## <a name="additional-recommendations"></a>Recomendaciones adicionales

- Antes de usar cuentas de administrador, cierre todas las aplicaciones y sesiones de explorador no relacionadas, incluidas las cuentas de correo electrónico personales. También podrá usar ventanas de explorador privadas o de incógnito.

- Después de completar las tareas de administrador, asegúrese de cerrar la sesión del explorador.

## <a name="next-objective"></a>Siguiente objetivo

[Aumento de la protección contra amenazas para Microsoft 365 Empresa Premium](m365bp-increase-protection.md)
