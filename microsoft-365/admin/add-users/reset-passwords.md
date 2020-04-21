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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: 'Obtenga información sobre cómo restablecer la contraseña de un usuario en la suscripción de Microsoft 365 para empresas. '
ms.openlocfilehash: 0d8a68edb0b85094b271712f018eea79ca9f0aee
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626951"
---
# <a name="reset-passwords"></a>Restablecer contraseñas

Vea un breve vídeo sobre el restablecimiento de contraseñas de usuario.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="let-users-reset-their-own-passwords"></a>Permitir que los usuarios puedan restablecer sus propias contraseñas

Le recomendamos encarecidamente que configure el autoservicio de restablecimiento de contraseña. Así, no tendrá que restablecer de forma manual las contraseñas de los usuarios. Para obtener información sobre cómo hacerlo, vea [Permitir que los usuarios puedan restablecer sus propias contraseñas en Office 365](let-users-reset-passwords.md).
  
## <a name="reset-a-business-password-for-someone-else"></a>Restablecer una contraseña de empresa para otra persona

Estos pasos son solo para los usuarios que usan un plan de 365 para empresas de Microsoft. Para hacerlo, debe iniciar sesión con su cuenta de administrador de 365 de Microsoft. [¿Qué es una cuenta de administrador?](../admin-overview/admin-overview.md)

 
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. En la página **usuarios activos** , seleccione el usuario y, a continuación, seleccione **Restablecer contraseña**.
    
3. Siga las instrucciones de la página **Restablecer contraseña** para generar automáticamente una nueva contraseña para el usuario o crear una para ellas y, a continuación, seleccione **restablecer**.  
    
4. Escriba una dirección de correo electrónico a la que el usuario pueda acceder para que reciba la nueva contraseña y realice un seguimiento con ella para asegurarse de que la obtuvo.
 
  
## <a name="reset-my-admin-password"></a>Restablecer mi contraseña de administrador

Siga estos pasos si ha olvidado la contraseña pero puede iniciar sesión en Microsoft 365 porque, por ejemplo, la contraseña se guarda en el explorador: 
    
1. En Microsoft 365, seleccione **configuración** \> **Office 365** \> **información personal**. 
          
2. Compruebe que la información de **contacto** y el **correo electrónico alternativo** sean correctos. Si no es así, cámbielas ahora. 
        
3. Cierre de sesión de Office 365: Seleccione su nombre en la esquina superior derecha (en la imagen anterior, mostrado como **Diane**) \> **Cerrar sesión**. 
        
4. Vuelva a iniciar sesión: escriba \> **su nombre de usuario a continuación** \> y seleccione **olvidé contraseña**. 
    
5. Siga los pasos del Asistente para restablecer la contraseña. Usa tu información de contacto alternativa para comprobar que eres la persona adecuada para restablecer la contraseña. 
    
Si ha olvidado la contraseña y no puede iniciar sesión: 
    
- Pida a otro administrador global de su empresa que restablezca su contraseña.
    
- O [llame al soporte técnico de Microsoft](https://support.office.com/article/contact-support-for-business-products-admin-help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?ui=en-US&amp;rs=en-US&amp;ad=US#ID0EAADAAA=Phone_support_). 
    
## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Restablecer todas las contraseñas de empresa para todos los usuarios de la organización al mismo tiempo
<a name="bkmk_forgot"> </a>

Estos pasos son aplicables a una empresa con decenas de usuarios. Si cuenta con cientos o miles de usuarios, consulte la siguiente sección sobre cómo restablecer las contraseñas de forma masiva.
  
1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
    
2. Seleccione la opción situada junto a **nombre para mostrar** para seleccionar todos los usuarios de la empresa. A continuación, desmarque su usuario. No puede restablecer su propia contraseña y las contraseñas de todas las personas de su organización al mismo tiempo.
    
3. Seleccione **Restablecer contraseña**. 

4. Siga las instrucciones de la página **Restablecer contraseña** y seleccione **restablecer**.  Si optó por generar automáticamente las contraseñas, se mostrarán las nuevas contraseñas temporales.   
    
5. Escriba una dirección de correo electrónico a la que pueda recibir las contraseñas temporales. Deberá notificar a los usuarios sus contraseñas temporales.
    

  
## <a name="reset-business-passwords-in-bulk"></a>Restablecer contraseñas de empresa en masa
<a name="bkmk_forgot"> </a>

Use PowerShell. Lea esta publicación de Eyal Doron: [Administrar contraseñas con PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
Artículo relacionado: [Establecer las contraseñas de varias cuentas de usuario](https://support.office.com/article/014fc912-bee1-461d-ad00-56b80428b907.aspx#bkmk_password).
  
Para obtener información general, consulte [PowerShell para administradores de Microsoft 365](https://support.office.com/article/40fdcbd4-c34f-42ab-8678-8b3751137ef1.aspx).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Forzar un cambio de contraseña para todos los usuarios de su empresa
<a name="bkmk_forgot"> </a>

Consulte esta excelente entrada de blog publicada por Vasil Michev, MVP de Microsoft: [Forzar el cambio de contraseña para todos los usuarios en Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="im-lost"></a>Sigo sin solucionar el problema
<a name="bkmk_forgot"> </a>

Lea el artículo [He olvidado el nombre de usuario o la contraseña de la cuenta que uso en Office.](https://support.office.com/article/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-articles"></a>Artículos relacionados
<a name="bkmk_forgot"> </a>
  
[Permitir que los usuarios restablezcan sus propias contraseñas](let-users-reset-passwords.md)

[Establecer la contraseña de un usuario individual que nunca caduque](set-password-to-never-expire.md)

[Cambiar la directiva de expiración de las contraseñas de la organización](../manage/set-password-expiration-policy.md)

[Restaurar un usuario](restore-user.md)

[Quitar un antiguo empleado](remove-former-employee.md)

[Vídeos de aprendizaje de Microsoft 365 para empresas](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)