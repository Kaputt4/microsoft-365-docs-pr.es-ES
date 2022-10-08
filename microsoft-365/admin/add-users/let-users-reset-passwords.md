---
title: Permitir que los usuarios puedan restablecer sus propias contraseñas
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- adminvideo
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Obtenga información sobre cómo puede establecer una directiva en el Centro de administración de Microsoft 365 para permitir que los usuarios restablezcan sus propias contraseñas mediante la herramienta de autoservicio de restablecimiento de contraseña.
ms.openlocfilehash: d9c962b26343cf5e2ddd6c1f4b2c8126b2b157fa
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68195201"
---
# <a name="let-users-reset-their-own-passwords"></a>Permitir que los usuarios puedan restablecer sus propias contraseñas

Consulte [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

Como administrador de Microsoft 365, puede permitir que los usuarios usen la [herramienta de autoservicio de restablecimiento de contraseña](https://go.microsoft.com/fwlink/p/?LinkId=522677) para que no tenga que restablecer las contraseñas para ellas. Así no tendrá tanto trabajo.

> [!TIP]
> Si necesita ayuda con los pasos que se describen en este tema, considere la posibilidad de [trabajar con un especialista en pequeñas empresas de Microsoft](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.
 
## <a name="watch-let-users-reset-their-own-passwords"></a>Ver: Permitir que los usuarios restablezcan sus propias contraseñas

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198214).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

1. En el Centro de administración de Microsoft 365, en el panel de navegación izquierdo, seleccione **Configuración Configuración** > **Configuración de la organización** y, a continuación, <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**Seguridad & privacidad**</a>.
1. En **Autoservicio de restablecimiento de contraseña**, seleccione **Ir al Azure Portal para activar el autoservicio de restablecimiento de contraseña**.
1. En el panel de navegación izquierdo, seleccione **Usuarios** y, a continuación, en la página **Usuarios: todos los usuarios** , seleccione **Restablecimiento de contraseña**.
1. Seleccione **Todo** para habilitar el autoservicio de restablecimiento de contraseña y, a continuación, seleccione **Guardar**.
1. En el panel de navegación izquierdo, seleccione **Métodos de autenticación** , seleccione el **número de métodos necesarios para restablecer** y los **métodos deseados disponibles para los usuarios** y, a continuación, seleccione **Guardar**. 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).
 
## <a name="before-you-begin"></a>Antes de empezar
  
- Obtiene el autoservicio de restablecimiento de contraseña para los usuarios en la nube **gratis** con cualquier plan de pago para empresas, educación o organizaciones sin ánimo de lucro de Microsoft 365. No funciona con la versión de prueba de Microsoft 365.

- It uses Azure. You'll automatically get this feature in Azure for **free** when you do these steps. It won't cost you anything to turn on self-service password reset if you don't use other Azure features.

- **Si usa un Active Directory local**, no se aplican los dos puntos anteriores. En su lugar, puede **configurarlo, pero requiere una suscripción de pago a Azure AD Premium**.

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?] (Información general de la Centro de administración de Microsoft 365](.. /admin-overview/admin-center-overview.md)

Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para realizar estos pasos.

## <a name="steps-let-people-reset-their-own-passwords"></a>Pasos: Permitir que las personas restablezcan sus propias contraseñas

Siga estos pasos para activar el restablecimiento de contraseña de autoservicio para todos los usuarios de su empresa.

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a>, vaya a la página **Configuración** > **de la organización** .

2. En la parte superior de la página Configuración de la **organización** , seleccione la pestaña **Seguridad & privacidad** .
  
3. Seleccione **Autoservicio de restablecimiento de contraseña**.

4. En **Autoservicio de restablecimiento de contraseña**, seleccione **Ir al Azure Portal para activar el autoservicio de restablecimiento de contraseña**.

5. En la página **Propiedades** , seleccione **Todo** para habilitarlo para todos los usuarios de su empresa y, a continuación, seleccione **Guardar**.

6. En el panel de navegación izquierdo, seleccione **Métodos de autenticación** , seleccione el **número de métodos necesarios para restablecer** y los **métodos deseados disponibles para los usuarios** y, a continuación, seleccione **Guardar**. 
  
7. Cuando los usuarios inicien sesión, se les pedirá que escriban información de contacto adicional que les ayudará a restablecer su contraseña en el futuro.

## <a name="related-content"></a>Contenido relacionado

[Establecer la directiva de expiración de contraseñas para su organización](../manage/set-password-expiration-policy.md) (artículo)\
[Establecer la contraseña de un usuario individual para que nunca expire](set-password-to-never-expire.md) (artículo)\
[Vídeos de formación empresarial de Microsoft 365](../../business-video/index.yml) (página de vínculos)
