---
title: Permitir que los usuarios puedan restablecer sus propias contraseñas
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
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Obtén información sobre cómo puedes restablecer las contraseñas con la herramienta de restablecimiento de contraseñas de autoservicio.
ms.openlocfilehash: 0842430eda8c96647dd12d0da6d0c9e0481346dc
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023766"
---
# <a name="let-users-reset-their-own-passwords"></a>Permitir que los usuarios puedan restablecer sus propias contraseñas

Como administrador de Microsoft 365, puede [](https://go.microsoft.com/fwlink/p/?LinkId=522677) permitir que los usuarios usen la herramienta de restablecimiento de contraseñas sin servicio para que no tenga que restablecer contraseñas para ellas. Así no tendrá tanto trabajo.
  
## <a name="before-you-begin"></a>Antes de empezar
  
- El restablecimiento de contraseñas  sin ánimo de lucro para los usuarios de la nube es gratuito con cualquier plan de pago para empresas, educación o ong de Microsoft 365. No funciona con la versión de prueba de Microsoft 365.

- Usa Azure. Recibirá esta característica automáticamente en Azure **gratis** cuando realice estos pasos. No le costará nada activar el autoservicio de restablecimiento de contraseñas si no usa otras características de Azure.

- **Si usa un Active Directory local,** no se aplican los dos puntos anteriores. En su lugar, puede configurar esto, pero requiere una suscripción **de pago a Azure AD Premium**.

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

Debe ser administrador global o administrador [de contraseñas](about-admin-roles.md) para realizar estos pasos.

## <a name="watch-let-users-reset-their-own-passwords"></a>Ver: permitir que los usuarios restablezcan sus propias contraseñas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Si este vídeo le ha sido de ayuda, vea la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

## <a name="steps-let-people-reset-their-own-passwords"></a>Pasos: permitir que los usuarios restablezcan sus propias contraseñas

Siga estos pasos para activar el restablecimiento de contraseña de autoservicio para todos los usuarios de su empresa.
  
::: moniker range="o365-worldwide"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración,</a>vaya a la **página Configuración** de > **la organización.**

::: moniker-end

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Centro de administración,</a>vaya a la **página Configuración** Seguridad de \> **&amp; privacidad.**

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Centro de administración,</a>vaya a la página **Configuración** \>  \> **seguridad &amp; privacidad.**

::: moniker-end

2. En la parte superior de la **página Configuración de la** organización, seleccione la pestaña Seguridad & **Privacidad.**
  
3. Seleccione **Autoservicio Restablecimiento de contraseña**.

4. En **Autoservicio de restablecimiento de contraseña,** seleccione Ir a Azure Portal para activar el restablecimiento **de contraseñas sin servicio.**

5. En el panel de navegación izquierdo, seleccione **Usuarios** y, a continuación, en el **panel Usuarios | Todos los usuarios** página, seleccione **Restablecimiento de contraseña**.
  
6. En la **página Propiedades,** seleccione **Todo** para habilitarlo para todos los usuarios de su empresa y, a continuación, **seleccione Guardar**.
  
7. Cuando los usuarios inicien sesión, se les pedirá que escriban información de contacto adicional que les ayudará a restablecer su contraseña en el futuro.

## <a name="related-content"></a>Contenido relacionado

[Cambiar la directiva de expiración de las contraseñas de la organización](../manage/set-password-expiration-policy.md)

[Establecer la contraseña de un usuario individual que nunca caduque](set-password-to-never-expire.md)

[Vídeos de aprendizaje de Microsoft 365 Empresa](../../business-video/index.yml)
