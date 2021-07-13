---
title: Cambiar un nombre de usuario y una dirección de correo electrónico
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: 'Obtenga información acerca de cómo un administrador global de Microsoft 365 puede cambiar la dirección de correo electrónico y el nombre para mostrar cuando cambie su nombre. '
ms.openlocfilehash: 29e2e57327550de13359106e7ba820204598f691
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394368"
---
# <a name="change-a-user-name-and-email-address"></a>Cambiar un nombre de usuario y una dirección de correo electrónico

Es posible que deba cambiar la dirección de correo electrónico y el nombre para mostrar de un usuario si, por ejemplo, este decide cambiarse los apellidos.

## <a name="watch-change-a-users-name-or-email-address"></a>Ver: Cambiar el nombre o la dirección de correo electrónico de un usuario

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc]

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

Debe ser [administrador global](about-admin-roles.md) para completar estos pasos.

## <a name="change-a-users-email-address"></a>Cambiar la dirección de correo electrónico de un usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

1. Seleccione el nombre de usuario y después, en la pestaña **Cuenta** seleccione **Administrar nombre de usuario**.

1. En el primer cuadro, escriba la primera parte de la nueva dirección de correo electrónico. Si ha agregado su propio dominio a Microsoft 365, puede elegir el dominio para el nuevo alias de correo electrónico a través de la lista desplegable. [Obtenga información sobre cómo agregar un dominio](../setup/add-domain.md).

1. Seleccione **Guardar cambios**.

> [!IMPORTANT]
> Si recibe un mensaje de error, consulte [Resolver mensajes de error](#resolve-error-messages).

## <a name="set-the-primary-email-address"></a>Establezca la dirección de correo electrónico principal.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione el nombre de usuario y después, en la pestaña **Cuenta**, seleccione **Administrar alias del correo electrónico**.

3. Seleccione **Establecer como principal** para la dirección de correo electrónico que desea establecer como la dirección de correo electrónico principal de esa persona.

   > [!IMPORTANT]
   > No verá la opción "Establecer como principal" si adquirió Microsoft 365 a través del servicio GoDaddy u otro partner que proporcione una consola de administración. En su lugar, inicie sesión en la consola de administración de GoDaddy o del partner para establecer el alias principal.
   >
   > Además, solo verá esta opción si es un administrador global. Si no ve la opción, no tiene permisos para cambiar el nombre ni la dirección de correo electrónico principal del usuario.

4. Verá una gran advertencia amarilla que le dice que va a cambiar la información de inicio de sesión del usuario. Seleccione **Guardar** y, a continuación, **Cerrar**.

5. Comunique a la persona la siguiente información:

   - Este cambio puede tardar un tiempo.

   - Su nombre de usuario nuevo. Será necesario que inicie sesión en Microsoft 365.

   - Si usan Skype Empresarial Online, deben programar otra vez cualquier reunión de Skype Empresarial Online que hayan organizado y comunicar a sus contactos externos que actualicen la información de contacto anterior.

   - Si usan OneDrive, la URL para esta ubicación ha cambiado. Si tienen los cuadernos de notas de OneNote en sus OneDrive, puede que necesiten cerrarlos y reabrirlos en OneNote. Si tienen archivos compartidos desde sus OneDrive, entonces puede que no funcionen los vínculos a los archivos y el usuario puede volver a compartir.

   - Si también se cambió su contraseña, infórmeles de que se les solicitará que escriban la nueva en su dispositivo móvil o, de lo contrario, no se realizará la sincronización.

## <a name="change-a-users-display-name"></a>Cambiar el nombre para mostrar de un usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>. 

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione el nombre de usuario y después, en la pestaña **Cuenta** seleccione **Administrar información de contacto**.

3. En el cuadro **Nombre para mostrar**, escriba un nombre nuevo de la persona y después, seleccione **Guardar**.

   Si recibió el mensaje de error **No se pudo modificar el usuario. Revise la información de usuario y vuelva a intentarlo**, consulte [Resolver mensajes de error](#resolve-error-messages). 

Este cambio puede tardar hasta 24 horas en surtir efecto en todos los servicios. Una vez que se aplique, la persona tendrá que iniciar sesión en Outlook, Skype Empresarial y SharePoint con su nombre de usuario actualizado.

## <a name="resolve-error-messages"></a>Resolver mensajes de error

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"No se encuentra ningún parámetro que coincida con el nombre de parámetro `EmailAddresses´"

Si recibe el mensaje de error "**No se encuentra ningún parámetro que coincida con el nombre de parámetro ‘EmailAddresses’"**, significa que la configuración de su espacio empresarial o de su dominio personalizado, si ha agregado alguno recientemente, está tardando un poco más de lo normal. El proceso de configuración puede tardar hasta 4 horas en completarse. Espere un poco para que el proceso de configuración tenga el tiempo suficiente para finalizarse y, a continuación, inténtelo de nuevo. Si el problema continúa, llame al [soporte técnico](../../business-video/get-help-support.md) y pídales que hagan una sincronización completa.

### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>"Lo sentimos, no se pudo modificar el usuario. Revise la información de usuario y vuelva a intentarlo"

Si recibió el mensaje de error "**No se pudo modificar el usuario. Revise la información de usuario y vuelva a intentarlo**". significa que no es un administrador global y no tiene permisos para cambiar el nombre del usuario. Busque el administrador global de su empresa y pídale que realice el cambio.

## <a name="what-to-do-with-old-email-addresses"></a>Qué hacer con las direcciones de correo electrónico antiguas

La dirección de correo electrónico principal anterior de la persona se conservará como dirección de correo electrónico adicional. **Recomendamos encarecidamente no quitar la dirección de correo electrónico antigua**.

Es probable que algunos usuarios continúen enviando correos electrónicos a la antigua dirección, por lo que eliminarla puede provocar errores NDR. Microsoft lo redirigirá automáticamente a la nueva dirección. Además, tampoco debe volver a usar direcciones de correo electrónico SMTP ni aplicarlas a nuevas cuentas. Esto también puede provocar errores NDR o que se realicen entregas en buzones no deseados.

## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>¿Qué sucede si la libreta de direcciones sin conexión de la persona no se sincroniza con la lista global de direcciones?

Si el usuario está usando Exchange Online o si su cuenta está vinculada al entorno de Exchange local de su organización, es posible que vea este error al intentar cambiar un nombre de usuario y una dirección de correo electrónico: "Este usuario se sincroniza con su Active Directory local. Algunos detalles se pueden modificar solo a través de su Active Directory local".

Esto es debido a la dirección de enrutamiento de correo electrónico de Microsoft Online (MOERA). La dirección MOERA se crea a partir del atributo  _userPrincipalName_ de la persona en Active Directory y se asigna automáticamente a la cuenta de la nube durante la sincronización inicial. Una vez que se ha creado, no puede modificarse ni quitarse en Microsoft 365. Posteriormente, podrá cambiar el nombre de usuario en Active Directory, pero esto no cambiará la dirección MOERA. Además, es posible que se produzcan problemas al mostrar el nombre recién cambiado en la lista global de direcciones.

Para corregir este error, inicie sesión en el [Módulo Microsoft Azure Active Directory para PowerShell](https://go.microsoft.com/fwlink/?LinkId=823193) con sus credenciales de administrador de Microsoft 365. Use la sintaxis que se muestra a continuación:

```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> Esto cambia el atributo **userPrincipalName** de la persona y no influirá en su dirección de correo electrónico Microsoft Online Email Routing Address (MOERA). Sin embargo, es recomendable, que el inicio de sesión del usuario UPN coincida con su dirección SMTP principal.

Para obtener información sobre cómo cambiar el nombre de usuario de una persona en Active Directory, en Windows Server 2003 y en las versiones anteriores, vea [Cambiar el nombre de una cuenta de usuario](/previous-versions/windows/it-pro/windows-server-2003/cc772952(v=ws.10)).

## <a name="related-content"></a>Contenido relacionado

[Agregar un dominio](../setup/add-domain.md)
[Administradores: restablecer una contraseña para uno o varios usuarios](reset-passwords.md)
[Agregar otra dirección de correo electrónico a un usuario](../email/add-another-email-alias-for-a-user.md)
[Crear un buzón compartido](../email/create-a-shared-mailbox.md)
