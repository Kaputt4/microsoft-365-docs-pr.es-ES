---
title: Permitir que los usuarios puedan restablecer sus propias contraseñas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Obtenga información sobre cómo restablecer las contraseñas con la herramienta de restablecimiento de contraseña de autoservicio.
ms.openlocfilehash: beffbcac997806f0c13347dfba42a1ab0ec65c1d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617151"
---
# <a name="let-users-reset-their-own-passwords"></a>Permitir que los usuarios puedan restablecer sus propias contraseñas

¿No cesan de pedirle que restablezca contraseñas? Como administrador de Microsoft 365, puede permitir que los usuarios usen la [herramienta de restablecimiento de contraseñas de autoservicio](https://go.microsoft.com/fwlink/p/?LinkId=522677) para no tener que restablecer sus contraseñas. Así no tendrá tanto trabajo. 
  
Algunas cuestiones que debería conocer:
  
- Obtiene el restablecimiento de contraseñas de autoservicio para los usuarios en la nube de forma gratuita con cualquier plan pagado de Microsoft 365 Business, Education o **sin** ánimo de lucro. No funciona con la versión de prueba de Microsoft 365. 
    
- Usa Azure. Recibirá esta característica automáticamente en Azure **gratis** cuando realice estos pasos. No le costará nada activar el autoservicio de restablecimiento de contraseñas si no usa otras características de Azure. 
    
- **Si está usando un Active Directory local**, no se aplican los dos puntos anteriores. En su lugar, puede configurar esto pero **requiere una suscripción de pago a Azure ad Premium**. 

Vea un breve vídeo sobre cómo permitir que los usuarios restablezcan sus propias contraseñas. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="let-people-reset-their-own-passwords"></a>Permitir que los usuarios restablezcan sus propias contraseñas 

Siga estos pasos para activar el restablecimiento de contraseña de autoservicio para todos los usuarios de su empresa.
  
::: moniker range="o365-worldwide"
1.  En el centro de administración, vaya a la página **configuración** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">seguridad & privacidad</a> .

::: moniker-end

::: moniker range="o365-germany"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administración</a>, vaya a la página **configuración** \> de **privacidad de seguridad &amp; ** .

::: moniker-end

::: moniker range="o365-21vianet"

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administración</a>, vaya a la página **configuración** \> de **privacidad de seguridad &amp; ** .

::: moniker-end

   
2. En **permitir que su personal restablezca sus propias contraseñas**, seleccione el vínculo del **centro de administración de Azure ad**. Recibirá Azure de forma gratuita.
  
3. Seleccione **usuarios** en el panel de navegación izquierdo y, a continuación, seleccione **restablecimiento de contraseña**.
  
4. En la página de propiedades, seleccione **todos** para habilitarlo para todos los usuarios de su empresa y, a continuación, seleccione **Guardar**.
  
5. Cuando los usuarios inicien sesión en Office 365, se les pedirá que escriban información de contacto adicional para poder restablecer su contraseña en el futuro.

## <a name="related-articles"></a>Artículos relacionados

[Cambiar la directiva de expiración de las contraseñas de la organización](../manage/set-password-expiration-policy.md)
  
[Establecer la contraseña de un usuario individual que nunca caduque](set-password-to-never-expire.md)

[Vídeos de aprendizaje de Microsoft 365 Empresa](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)