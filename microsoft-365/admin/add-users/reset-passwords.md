---
title: Restablecer contraseñas
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: Obtenga información sobre cómo restablecer la contraseña de un usuario en Microsoft 365 suscripción para empresas.
ms.openlocfilehash: 8720942d60b5ce4efaca8885bd5209cb3e7e7ef8
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291000"
---
# <a name="reset-passwords"></a>Restablecer contraseñas

En este artículo se explica cómo restablecer las contraseñas para usted y para los usuarios cuando tiene una suscripción Microsoft 365 para empresas.

## <a name="before-you-begin"></a>Antes de empezar

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).

Debe ser administrador global o administrador [de contraseñas](about-admin-roles.md) para realizar estos pasos.

## <a name="watch-reset-a-business-password-for-a-user"></a>Watch: Reset a business password for a user

Vea un breve vídeo sobre el restablecimiento de contraseñas de usuario.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP]

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).
  
## <a name="steps-reset-a-business-password-for-a-user"></a>Pasos: Restablecer una contraseña de empresa para un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la **página Usuarios activos,** seleccione el usuario y, a continuación, **seleccione Restablecer contraseña.**

3. Siga las instrucciones de la **página Restablecer contraseña** para generar automáticamente una nueva contraseña para el usuario o crear una para ellos y, a continuación, seleccione **Restablecer**.  

4. Escriba una dirección de correo electrónico a la que pueda llegar el usuario para que reciba la nueva contraseña y realice un seguimiento con ellos para asegurarse de que la obtuvo.

## <a name="let-users-reset-their-own-passwords"></a>Permitir que los usuarios puedan restablecer sus propias contraseñas

Le recomendamos encarecidamente que configure el autoservicio de restablecimiento de contraseña. Así, no tendrá que restablecer de forma manual las contraseñas de los usuarios. Para obtener información sobre cómo hacerlo, vea [Permitir que los usuarios puedan restablecer sus propias contraseñas en Office 365](let-users-reset-passwords.md).

## <a name="reset-my-admin-password"></a>Restablecer mi contraseña de administrador

Siga estos pasos si ha olvidado la contraseña, pero puede iniciar sesión en Microsoft 365 porque, por ejemplo, la contraseña se guarda en el explorador:

1. Seleccione su nombre (icono) en la esquina superior derecha > Información personal **de Mi**  >  **cuenta**.

2. En **Detalles de contacto,** compruebe que **el** correo electrónico alternativo es preciso y que ha proporcionado un número de teléfono móvil. Si no es así, cámbienlos ahora.

3. Cerrar sesión: seleccione su nombre en la esquina superior derecha \> **Cerrar sesión.**

4. Ahora vuelva a iniciar sesión: escriba el nombre de usuario Siguiente y, a \>  \> continuación, seleccione **Contraseña olvidada.**

5. Siga los pasos del asistente para restablecer la contraseña. Usa la información de contacto alternativa para comprobar que eres la persona adecuada para restablecer la contraseña.

Si ha olvidado la contraseña y no puede iniciar sesión:

- Pida a otro administrador global de su empresa que restablezca su contraseña.

- Asegúrese de que ha proporcionado información de contacto alternativa, incluido un número de teléfono móvil.

- O bien, [llama al soporte técnico de Microsoft](../../business-video/get-help-support.md).

## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Restablecer todas las contraseñas empresariales para todos los usuarios de la organización al mismo tiempo
<a name="bkmk_forgot"> </a>

Estos pasos son aplicables a una empresa con decenas de usuarios. Si tiene cientos o miles de usuarios, consulte la siguiente sección sobre el restablecimiento masivo de contraseñas (máximo 40 usuarios a la vez).
  
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione la opción situada junto a **Nombre para mostrar** para seleccionar todos los usuarios de su empresa. A continuación, desmarque su usuario. No puede restablecer su propia contraseña y las contraseñas de todas las personas de su organización al mismo tiempo.

3. Seleccione **Restablecer contraseña**. 

4. Siga las instrucciones de la **página Restablecer contraseña** y seleccione **Restablecer**.  Si optó por generar automáticamente las contraseñas, se mostrarán las nuevas contraseñas temporales.

5. Escriba una dirección de correo electrónico donde pueda recibir las contraseñas temporales. Deberá notificar a los usuarios cuáles son sus contraseñas temporales.
  
## <a name="reset-business-passwords-in-bulk"></a>Restablecer contraseñas empresariales en masa
<a name="bkmk_forgot"> </a>

Use PowerShell. Lea esta publicación de Eyal Doron: [Administrar contraseñas con PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
<!-- Here's a related article: [Set the passwords for multiple user accounts](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). -->
  
Para obtener información general, [vea Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Forzar un cambio de contraseña para todos los usuarios de su empresa

Consulte esta excelente entrada de blog publicada por Vasil Michev, MVP de Microsoft: [Forzar el cambio de contraseña para todos los usuarios en Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="i-dont-have-a-microsoft-365-for-business-subscription"></a>No tengo una suscripción de Microsoft 365 para empresas

Lea el artículo [He olvidado el nombre de usuario o la contraseña de la cuenta que uso en Office.](https://support.microsoft.com/office/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-content"></a>Contenido relacionado
  
[Permitir que los usuarios puedan restablecer sus propias contraseñas](../add-users/let-users-reset-passwords.md)

[Restablecer contraseñas](../add-users/reset-passwords.md)

[Establecer la contraseña de un usuario individual que nunca caduque](set-password-to-never-expire.md)

[Cambiar la directiva de expiración de las contraseñas de la organización](../manage/set-password-expiration-policy.md)

[Restaurar un usuario](restore-user.md)

[Quitar un antiguo empleado](remove-former-employee.md)

[Vídeos de aprendizaje de Microsoft 365 para empresas](../../business-video/index.yml)