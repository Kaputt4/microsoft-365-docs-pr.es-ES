---
title: Agregar usuarios y asignar licencias
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Obtenga información sobre cómo agregar usuarios y asignar licencias a Microsoft 365 al mismo tiempo.
ms.date: 07/01/2020
ms.openlocfilehash: 6745285600b6c5a62b4327d7174b2c249ff5276c
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307378"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Agregar usuarios y asignar licencias al mismo tiempo

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Los usuarios de su equipo necesitan una cuenta de usuario para poder iniciar sesión y obtener acceso a [Microsoft 365 para la empresa](https://go.microsoft.com/fwlink/?LinkID=519395). La forma más sencilla de agregar cuentas de usuario es agregarlas de una en una a la vez en el centro de administración de 365 de Microsoft. Después de realizar este paso, los usuarios tienen licencias de 365 de Microsoft, credenciales de inicio de sesión y buzones de correo de 365 de Microsoft.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser un administrador global, una licencia o un administrador de usuarios para agregar usuarios y asignar licencias. Para obtener más información, vea [Asignar roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-admin-center"></a>Ver: agregar usuarios en el centro de administración

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Los pasos que se usan en el vídeo muestran un punto de partida diferente para agregar usuarios, pero los pasos restantes son los mismos que los del procedimiento siguiente.

## <a name="add-users-one-at-a-time"></a>Agregar usuarios de uno en uno

::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.
2. Vaya a **usuarios** > **activos**y seleccione **Agregar un usuario**.
3. En el panel **configurar los conceptos básicos** , rellene la información básica del usuario y, a continuación, seleccione **siguiente**.
    - **Nombre** de Rellene el nombre y el apellido, el nombre para mostrar y el nombre de usuario.
    - **Dominio** Elija el dominio para la cuenta de usuario. Por ejemplo, si el nombre de usuario del usuario es Jakob y el dominio es contoso.com, iniciará sesión con jakob@contoso.com.
    - **Configuración de contraseña** Elija usar la contraseña generada automáticamente o crear su propia contraseña segura para el usuario.
    - El usuario debe cambiar su contraseña después de 90 días. O bien, puede optar por **requerir que este usuario cambie su contraseña la primera vez que inicie sesión**.
    - Elija si desea enviar la contraseña por correo electrónico cuando se agregue el usuario.
4. En el panel **asignar licencias de producto** , seleccione la ubicación y la licencia correspondiente para el usuario. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales. Expande **aplicaciones** y selecciona o anula la selección de aplicaciones para limitar las aplicaciones para las que el usuario tiene una licencia. Seleccione **Siguiente**.
5. En el panel **configuración opcional** , expanda **roles** para que el usuario sea administrador. Expanda **información de perfil** para agregar información adicional acerca del usuario.
6. Seleccione **siguiente**, revise la configuración del nuevo usuario, realice los cambios que quiera y, después, haga clic en **Finalizar agregar**y luego en **cerrar**.

::: moniker-end

::: moniker range="o365-germany"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.
2. Vaya a **usuarios** > **activos**y seleccione **Agregar un usuario**.
3. En el panel **nuevo usuario** , rellene la siguiente información. Cuando haya terminado, seleccione **Agregar**.
    - **Nombre** Rellene el nombre, apellido, nombre para mostrar y nombre de usuario.
    - **Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y el dominio es contoso.com, se iniciará sesión en escribiendo jakob@contoso.com.
    - **Información de contacto** Expándala para rellenar el número de teléfono móvil, la dirección y demás datos similares.
    - **Contraseña** Use la contraseña generada automáticamente o expanda para especificar una contraseña segura para el usuario. Deben cambiar su contraseña después de 90 días. También puede elegir la opción **Solicitar a este usuario que cambie su contraseña la primera vez que inicie sesión**.
    - **Roles** Expándala si necesita hacer que este usuario sea administrador.
    - **Licencias de producto** Expanda esta sección y seleccione la licencia adecuada. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.
2. Vaya a **usuarios** > **activos**y seleccione **Agregar un usuario**.
3. En el panel **nuevo usuario** , rellene la siguiente información. Cuando haya terminado, seleccione **Agregar**.
    - **Nombre** Rellene el nombre, apellido, nombre para mostrar y nombre de usuario.
    - **Dominio** Por ejemplo, si el nombre de usuario del usuario es Jakob y el dominio es contoso.com, se iniciará sesión en escribiendo jakob@contoso.com.
    - **Información de contacto** Expándala para rellenar el número de teléfono móvil, la dirección y demás datos similares.
    - **Contraseña** Use la contraseña generada automáticamente o expanda para especificar una contraseña segura para el usuario. Deben cambiar su contraseña después de 90 días. También puede elegir la opción **Solicitar a este usuario que cambie su contraseña la primera vez que inicie sesión**.
    - **Roles** Expándala si necesita hacer que este usuario sea administrador.
    - **Licencias de producto** Expanda esta sección y seleccione la licencia adecuada. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales.

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>Agregar varios usuarios a la vez

Puede usar cualquiera de los métodos siguientes para agregar varios usuarios al mismo tiempo:
  
- **Use una hoja de cálculo para agregar usuarios en masa.** Consulte [agregar varios usuarios al mismo tiempo](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time).
- **Automatice la agregación de cuentas y la asignación de licencias.** Consulte [Create User accounts with Microsoft 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell). Seleccione este método si ya está familiarizado con el uso de cmdlets de Windows PowerShell.
- **¿Usa ActiveDirectory?** [Configurar la sincronización de directorios para Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization). Use la herramienta de Azure AD Connect para replicar cuentas de usuario de Active Directory (y otros objetos de Active Directory) en Microsoft 365. La sincronización solo agrega las cuentas de usuario. Debe asignar licencias a los usuarios sincronizados para poder usar el correo electrónico y otras aplicaciones de Office.
- **¿Va a migrar desde Exchange?** Consulte [formas de migrar varias cuentas de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration). Al migrar varios buzones a Microsoft 365 mediante transferencia, por fases o mediante un método híbrido de Exchange, los usuarios se agregan automáticamente como parte de la migración. La migración solo agrega las cuentas de usuario. Debe asignar licencias a los usuarios para que puedan usar el correo electrónico y otras aplicaciones de Office. Si no asigna una licencia a un usuario, su buzón se deshabilita tras un período de gracia de 30 días. Obtenga información sobre cómo [asignar licencias a usuarios](../manage/assign-licenses-to-users.md) en el centro de administración de Microsoft 365.

## <a name="next-steps"></a>Pasos siguientes

Una vez que haya agregado un usuario, recibirá una notificación por correo electrónico de Microsoft. El correo electrónico contiene el identificador de usuario y la contraseña de la persona para que puedan iniciar sesión en Microsoft 365. Use el proceso habitual para comunicar nuevas contraseñas. Comparta la [Guía de inicio rápido de empleado](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) con los nuevos usuarios para configurar elementos como, por ejemplo, cómo [Descargar e instalar aplicaciones de Office en un equipo PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) y cómo [configurar las aplicaciones de Office y el correo electrónico en un dispositivo móvil](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Contenido relacionado

[Agregar un nuevo empleado a Microsoft 365](add-new-employee.md) (artículo) \
[Agregar varios usuarios al mismo tiempo a Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (artículo) \
[Restaurar un usuario en Microsoft 365](restore-user.md) (artículo) \
[Asignar licencias a usuarios](../manage/assign-licenses-to-users.md) (artículo) \
[Eliminación de un usuario de la organización](delete-a-user.md) (artículo)