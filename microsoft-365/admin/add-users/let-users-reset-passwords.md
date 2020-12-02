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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Obtenga información sobre cómo restablecer las contraseñas con la herramienta de restablecimiento de contraseña de autoservicio.
ms.openlocfilehash: bbde517858186d844412aca21f231620ed76496a
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551925"
---
# <a name="let-users-reset-their-own-passwords"></a>Permitir que los usuarios puedan restablecer sus propias contraseñas

Como administrador de Microsoft 365, puede permitir que los usuarios usen la [herramienta de restablecimiento de contraseñas de autoservicio](https://go.microsoft.com/fwlink/p/?LinkId=522677) para no tener que restablecer sus contraseñas. Así no tendrá tanto trabajo.
  
## <a name="before-you-begin"></a>Antes de empezar
  
- Obtiene el restablecimiento de contraseñas de autoservicio para los usuarios en la nube de forma gratuita con cualquier plan pagado de Microsoft 365 Business, Education o **sin** ánimo de lucro. No funciona con la versión de prueba de Microsoft 365.

- Usa Azure. Recibirá esta característica automáticamente en Azure **gratis** cuando realice estos pasos. No le costará nada activar el autoservicio de restablecimiento de contraseñas si no usa otras características de Azure.

- **Si está usando un Active Directory local**, no se aplican los dos puntos anteriores. En su lugar, puede configurar esto pero **requiere una suscripción de pago a Azure ad Premium**.

Este artículo está dirigido a personas que establecen una política de caducidad de contraseñas para una empresa, una escuela o una organización sin fines de lucro. Para completar estos pasos, debe iniciar sesión con su cuenta de administrador de Microsoft 365. [¿Qué es una cuenta de administrador?](../admin-overview/admin-overview.md)

Debe ser [administrador global o administrador de contraseñas](about-admin-roles.md) para poder realizar estos pasos.

## <a name="watch-let-users-reset-their-own-passwords"></a>Inspección: permitir a los usuarios restablecer sus propias contraseñas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="steps-let-people-reset-their-own-passwords"></a>Pasos: permitir que los usuarios restablezcan sus propias contraseñas

Siga estos pasos para activar el restablecimiento de contraseña de autoservicio para todos los usuarios de su empresa.
  
::: moniker range="o365-worldwide"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administración</a>, vaya a la página **configuración** de la > **organización** .

::: moniker-end

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **configuración** de \> **&amp; privacidad de seguridad** .

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página configuración **de configuración de** \> **Settings** \> **&amp; privacidad de seguridad** .

::: moniker-end

2. En la parte superior de la página Configuración de la **organización** , seleccione la pestaña **seguridad & privacidad** .
  
3. Seleccione **restablecimiento de contraseña de autoservicio**.

4. En **autoservicio de restablecimiento de contraseñas**, seleccione **ir a Azure portal para activar el restablecimiento de contraseña de autoservicio**.

5. En el panel de navegación izquierdo, seleccione **usuarios** y, a continuación, en la sección **usuarios | Página todos los usuarios** , seleccione **restablecimiento de contraseña**.
  
6. En la página de **propiedades** , seleccione **todos** para habilitarlo para todos los usuarios de su empresa y, a continuación, seleccione **Guardar**.
  
7. Cuando los usuarios inicien sesión, se les pedirá que escriban información de contacto adicional que les ayude a restablecer la contraseña en el futuro.

## <a name="related-content"></a>Contenido relacionado

[Cambiar la directiva de expiración de las contraseñas de la organización](../manage/set-password-expiration-policy.md)

[Establecer la contraseña de un usuario individual que nunca caduque](set-password-to-never-expire.md)

[Vídeos de aprendizaje de Microsoft 365 Empresa](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
