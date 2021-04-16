---
title: Agregar usuarios y asignar licencias
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.openlocfilehash: a7c5fcf1a129a1d434b6e641688ce4c5d234817d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760007"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Agregar usuarios y asignar licencias al mismo tiempo

Todos los usuarios de su equipo necesitan una cuenta de usuario para poder iniciar sesión y acceder a [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/business). La forma más sencilla de agregar cuentas de usuario es hacerlo de una en una en el Centro de administración de Microsoft 365. Después de realizar este paso, los usuarios tendrán licencias de Microsoft 365, credenciales de inicio de sesión y buzones de Microsoft 365.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser un administrador global, de licencia o de usuario para agregar usuarios y asignar licencias. Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-admin-center"></a>Vídeo: Agregar usuarios en el Centro de administración

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Los pasos usados en el vídeo muestran un punto de partida diferente para agregar usuarios, pero los pasos restantes son los mismos que en el procedimiento siguiente.

## <a name="add-users-one-at-a-time"></a>Agregar usuarios uno por uno

 ::: moniker range="o365-worldwide"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Vaya a **Usuarios**  >  **Usuarios activos** y seleccione **Agregar un usuario**.
3. En el **Configurar los conceptos básicos** panel, rellene la información básica del usuario y, a continuación, seleccione **Siguiente**.
    - **Nombre** Rellene el nombre y los apellidos, el nombre para mostrar y el nombre de usuario.
    - **Dominio** Elija el dominio para la cuenta del usuario. Por ejemplo, si el nombre de usuario es Jakob y el dominio es contoso.com, iniciarán sesión con jakob@contoso.com.
    - **Configuración de contraseñas** Elija si desea usar la contraseña autogenerada o crear su propia contraseña segura para el usuario.
    - El usuario debe cambiar su contraseña después de 90 días. También puede elegir la opción **Solicitar a este usuario que cambie su contraseña la primera vez que inicie sesión**.
    - Elija si desea enviar la contraseña por correo electrónico cuando se agrega el usuario.
4. En el panel **Asignar licencias de productos**, seleccione la ubicación y la licencia correspondiente para el usuario. Si no cuenta con ninguna licencia disponible, todavía puede agregar un usuario y comprar licencias adicionales. Expanda **Aplicaciones**, y active o desactive la selección de aplicaciones para limitar las aplicaciones para las que el usuario tiene licencia. Seleccione **Siguiente**.
5. En el panel **Configuración opcional**, expanda **Roles** para convertir a este usuario en administrador. Expanda **Información del perfil** agregar información adicional sobre el usuario.
6. Seleccione **Siguiente**, revise la configuración del nuevo usuario, realice los cambios que desee y a continuación seleccione **Terminar de agregar** y después **Cerrar**.

## <a name="add-multiple-users-at-the-same-time"></a>Agregar varios usuarios al mismo tiempo

Puede usar cualquiera de los siguientes métodos para agregar varios usuarios al mismo tiempo:

- **Use una hoja de cálculo para agregar usuarios en masa.** Consulte [Agregar varios usuarios al mismo tiempo](../../enterprise/add-several-users-at-the-same-time.md).
- **Automatice el agregar cuentas y la asignación de licencias.** Consulte [Crear cuentas de usuario con Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Elija este método si ya está familiarizado con el uso de cmdlets de Windows PowerShell.
- **¿Usa ActiveDirectory?** [Configuración de la sincronización del directorio para Microsoft 365](../../enterprise/set-up-directory-synchronization.md) Use la herramienta Azure AD Connect para replicar cuentas de usuario de Active Directory (y otros objetos de Active Directory) en Microsoft 365. La sincronización solo agrega las cuentas de usuario. Deberá asignar licencias a los usuarios sincronizados para que puedan usar el correo electrónico y otras aplicaciones de Office.
- **¿Está migrando desde Exchange?** Consulte [Formas de migrar varias cuentas de correo electrónico a Office 365](/Exchange/mailbox-migration/mailbox-migration) Al migrar varios buzones de correo a Microsoft 365 mediante traslado, por etapas o un método de Exchange híbrido, podrá agregar usuarios automáticamente como parte de la migración. La migración solo agrega las cuentas de usuario. Deberá asignar licencias a los usuarios para que puedan usar el correo electrónico y otras aplicaciones de Office. Si no asigna una licencia a un usuario, su buzón se deshabilitará después de un período de gracia de 30 días. Obtenga información sobre cómo [asignar licencias a usuarios](../manage/assign-licenses-to-users.md) en el Centro de administración de Microsoft 365.

## <a name="next-steps"></a>Siguientes pasos

Después de agregar un usuario, recibirá un correo electrónico de Microsoft. El correo electrónico contendrá el identificador y la contraseña del usuario para que puedan iniciar sesión en Microsoft 365. Use el proceso habitual para comunicar nuevas contraseñas. Comparta la [Guía de inicio rápido de los empleados](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) con los nuevos usuarios para configurar opciones como [cómo descargar e instalar aplicaciones de Office en un equipo PC o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) y cómo [configurar el correo electrónico y las aplicaciones de Office en un dispositivo móvil](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Contenido relacionado

[Agregar un nuevo empleado a Microsoft 365](add-new-employee.md) (artículo)\
[Agregar varios usuarios al mismo tiempo a Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (artículo)\
[Restaurar un usuario en Microsoft 365](restore-user.md) (artículo)\
[Asignar licencias a los usuarios](../manage/assign-licenses-to-users.md) (artículo)\
[Elimine un usuario de su organización](delete-a-user.md) (artículo)