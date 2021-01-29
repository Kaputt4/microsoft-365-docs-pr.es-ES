---
title: Configurar directivas de acceso condicional
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo requerir MFA y configurar directivas de acceso condicional para Microsoft 365 para empresas.
ms.openlocfilehash: b13ba9f8c948d9a1209655c44871ca62cb5354dd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044505"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Requerir la autenticación multifactor y configurar directivas de acceso condicional

El acceso a los datos se protege con la autenticación multifactor y las directivas de acceso condicional. Esto agrega una seguridad adicional considerable. Microsoft proporciona un conjunto de directivas de acceso condicional de línea base que se recomiendan para todos los clientes. Las directivas de línea base son un conjunto de directivas predefinidas que ayudan a proteger a las organizaciones contra muchos ataques comunes. Estos ataques comunes pueden incluir la protección contra contraseñas, la reproducción y la suplantación de identidad.

Estas directivas requieren que los administradores y los usuarios escriban una segunda forma de autenticación (denominada autenticación multifactor o MFA) en determinadas condiciones. Por ejemplo, si un usuario de su organización intenta iniciar sesión en Microsoft 365 desde un país diferente o desde un dispositivo desconocido, el inicio de sesión puede considerarse arriesgado. El usuario debe proporcionar una forma adicional de autenticación (como una huella digital o un código) para demostrar su identidad.

Actualmente, las directivas de línea base incluyen las siguientes directivas:

- Configurar en el Centro de administración de Microsoft 365:
  - **Requerir MFA para administradores:** requiere autenticación multifactor para los roles de administrador con más privilegios, incluido el administrador global.
  - **Protección del usuario final:** requiere autenticación multifactor para los usuarios solo cuando un inicio de sesión es arriesgado. 
- Configurar en el portal de Azure Active Directory:
  - **Bloquear la autenticación heredada:** las aplicaciones cliente más antiguas y algunas aplicaciones nuevas no usan protocolos de autenticación más recientes y seguros. Estas aplicaciones anteriores pueden omitir las directivas de acceso condicional y obtener acceso no autorizado a su entorno. Esta directiva bloquea el acceso de clientes que no admiten el acceso condicional. 
  - **Requerir MFA para la administración de** servicios: requiere autenticación multifactor para obtener acceso a las herramientas de administración, incluido Azure Portal (donde se configuran las directivas de línea base).

Se recomienda habilitar todas estas directivas de línea base. Una vez habilitadas estas directivas, se pedirá a los administradores y usuarios que se registren para la autenticación multifactor de Azure AD.

Para obtener más información acerca de estas directivas, vea [¿Qué son las directivas de línea base?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)

## <a name="require-mfa"></a>Requerimiento de la MFA

Para requerir que todos los usuarios inicien sesión con una segunda forma de identificador:

1. Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> y elija **Configurar.**

2. En la página de instalación, elija **Ver** en la tarjeta de inicio de **sesión más** segura.

    ![Haga que el inicio de sesión sea más seguro.](../media/setupmfa.png)
3. On the Make sign-in more secure page, choose **Get started**.

4. En el panel Reforzar la seguridad de inicio de sesión, active las **casillas situadas** junto a Requerir autenticación multifactor para los administradores y Requerir que los usuarios se registren para la autenticación multifactor y bloquee el acceso si se detecta un **riesgo.**
    Asegúrese de excluir la cuenta de [administrador](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) de emergencia o "break-glass" del requisito de MFA en **el** cuadro Buscar usuarios.

    ![Reforzar la página de seguridad de inicio de sesión.](../media/requiremfa.png)

5. Elija **Crear directiva** en la parte inferior de la página.

## <a name="set-up-baseline-policies"></a>Configurar directivas de línea base

1. Vaya a [Azure Portal y](https://portal.azure.com)vaya a Acceso condicional de Azure Active **Directory** para crear una \>  nueva **directiva.**

Vea las siguientes instrucciones específicas para cada directiva: <br>
    - [Requerir MFA para administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [Requerir MFA para los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Bloquear la autenticación heredada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [Requerir MFA para la administración de servicios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> Las directivas de vista previa ya no existen y los usuarios tendrán que crear sus propias directivas.

Puedes configurar directivas adicionales, como requerir aplicaciones cliente aprobadas. Para obtener más información, consulte la [documentación de acceso condicional.](https://docs.microsoft.com/azure/active-directory/conditional-access/)
