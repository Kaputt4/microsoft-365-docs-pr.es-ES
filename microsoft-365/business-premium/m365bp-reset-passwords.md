---
title: Restablecer contraseñas
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
ms.localizationpriority: medium
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
description: Restablezca las contraseñas de los usuarios de Microsoft 365 Empresa Premium.
ms.openlocfilehash: 1d38b19222280d14ce953fb793c4be903f0a8793
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67739948"
---
# <a name="reset-passwords-in-microsoft-365-business-premium"></a>Restablecer contraseñas en Microsoft 365 Empresa Premium

Obtenga información sobre cómo restablecer las contraseñas para usted y los usuarios cuando sea necesario. Como administrador, puede restablecer la contraseña de un usuario si la olvida.

## <a name="user-initiated-password-reset"></a>Restablecimiento de contraseña iniciado por el usuario

Cuando un usuario solicita una nueva contraseña, se envía una solicitud de restablecimiento de contraseña por correo electrónico.

1. Para restablecer la contraseña, abra el iniciador de aplicaciones y seleccione **Administración** e inicie sesión con sus credenciales.

2. En el Centro de administración de Microsoft 365, seleccione **Usuarios**, <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Usuarios activos**</a> y, a continuación, seleccione el icono de clave junto al usuario que solicitó el restablecimiento.

3. Seleccione **Generar contraseña automáticamente** para que se cree automáticamente una contraseña aleatoria.

4. Seleccione **Restablecer**. 

## <a name="admin-initiated-password-reset"></a>Restablecimiento de contraseña iniciado por Administración

Hay ocasiones en las que un administrador puede querer forzar el restablecimiento de contraseña en las cuentas.

1. En el centro de Administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">usuarios activos</a>.

2. En la página **Usuarios activos** , seleccione el usuario específico que se va a restablecer y, a continuación, seleccione **Restablecer contraseña**.

3. Siga las instrucciones de la página **Restablecer contraseña** para generar automáticamente una nueva contraseña para el usuario o crear una para ellos y, a continuación, seleccione **Restablecer**.  

4. Escriba una dirección de correo electrónico a la que el usuario pueda acceder para que reciba la nueva contraseña y realice un seguimiento con ella para asegurarse de que la obtuvo.

## <a name="let-users-reset-their-own-passwords"></a>Permitir que los usuarios puedan restablecer sus propias contraseñas

Se recomienda encarecidamente configurar el autoservicio de restablecimiento de contraseña. Así, no tendrá que restablecer de forma manual las contraseñas de los usuarios. Para obtener información sobre cómo hacerlo, vea [Permitir que los usuarios puedan restablecer sus propias contraseñas en Office 365](/admin/add-users/let-users-reset-passwords.md).

## <a name="reset-my-admin-password"></a>Restablecimiento de la contraseña de administrador

Siga estos pasos si olvidó la contraseña, pero puede iniciar sesión en Microsoft 365 porque, por ejemplo, la contraseña se guarda en el explorador:

1. Seleccione su nombre (icono) en la esquina superior derecha > Información **personal** **de mi cuenta** > .

2. En **Detalles de contacto**, compruebe que el **correo electrónico alternativo** es preciso y que ha proporcionado un número de teléfono móvil. Si no es así, cámbielos ahora.

3. Cerrar sesión: seleccione su nombre en la esquina \> superior derecha **Cerrar sesión**.

4. Vuelva a iniciar sesión: escriba el nombre \> de usuario **Siguiente** \> y, a continuación, seleccione **Olvidó la contraseña**.

5. Siga los pasos del asistente para restablecer la contraseña. Usa la información de contacto alternativa para comprobar que eres la persona adecuada para restablecer la contraseña.

Si olvidó la contraseña y no puede iniciar sesión:

- Pida a otro administrador global de su empresa que restablezca su contraseña.

- Asegúrese de que ha proporcionado información de contacto alternativa, incluido un número de teléfono móvil.

## <a name="reset-all-business-passwords-for-everyone-at-the-same-time"></a>Restablecer todas las contraseñas empresariales para todos al mismo tiempo

<a name="bkmk_forgot"> </a>

Estos pasos son aplicables a una empresa con decenas de usuarios. Si tiene cientos o miles de usuarios, consulte la siguiente sección sobre el restablecimiento masivo de contraseñas (un máximo de 40 usuarios a la vez).
  
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione la opción situada junto a **Nombre para mostrar** para seleccionar todos los usuarios de su empresa. A continuación, anule la selección. No puede restablecer su propia contraseña y las contraseñas de todas las personas de su organización al mismo tiempo.

3. Seleccione **Restablecer contraseña**.

4. Siga las instrucciones de la página **Restablecer contraseña** y seleccione **Restablecer**.  Si ha optado por generar automáticamente las contraseñas, se mostrarán las nuevas contraseñas temporales.

5. Escriba una dirección de correo electrónico donde pueda recibir las contraseñas temporales. Tendrá que notificar a los usuarios cuáles son sus contraseñas temporales.
  
## <a name="reset-business-passwords-in-bulk"></a>Restablecimiento masivo de contraseñas empresariales

<a name="bkmk_forgot"> </a>

Para restablecer las contraseñas de varias cuentas, use PowerShell. Lea esta publicación de Eyal Doron: [Administrar contraseñas con PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).

Para obtener información general, consulte [Administración de Microsoft 365 con PowerShell](../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).
  
## <a name="related-content"></a>Contenido relacionado
  
[Permitir que los usuarios restablezcan sus propias contraseñas](../admin/add-users/let-users-reset-passwords.md)
 [Restablecimiento de contraseñas en Microsoft 365 para empresas](../admin/add-users/reset-passwords.md)
 [Establecer la contraseña de un usuario individual para que nunca expire](../admin/add-users/set-password-to-never-expire.md) 
 [Establecimiento de la directiva de expiración de contraseñas para la organización](../admin/manage/set-password-expiration-policy.md)