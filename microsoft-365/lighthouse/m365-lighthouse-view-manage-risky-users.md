---
title: Visualización y administración de usuarios de riesgo en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo ver y administrar usuarios de riesgo.
ms.openlocfilehash: 45c91ec0871393f69e7a166cc8582f149479ad1b
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66011846"
---
# <a name="view-and-manage-risky-users-in-microsoft-365-lighthouse"></a>Visualización y administración de usuarios de riesgo en Microsoft 365 Lighthouse

Microsoft recopila y analiza billones de señales de inicio de sesión de usuario cada día. Estas señales se usan para ayudar a crear buenos patrones de comportamiento de inicio de sesión de usuario e identificar posibles intentos de inicio de sesión de riesgo. Azure Active Directory (Azure AD) Identity Protection usa estas señales para revisar los intentos de inicio de sesión de los usuarios y tomar medidas si hay actividad sospechosa.

Microsoft 365 Lighthouse ayuda a administrar los riesgos detectados por Azure AD Identity Protection proporcionando una vista única de los usuarios de riesgo en todos los inquilinos administrados. Para proteger rápidamente a los usuarios de riesgo, restablezca su contraseña o bloquee el inicio de sesión en su cuenta de Microsoft 365. También puede ver información para comprender mejor el riesgo de un usuario y determinar los pasos siguientes.

Azure AD Identity Protection identifica los riesgos de muchos tipos, entre los que se incluyen:

- Credenciales filtradas
- Uso de IP anónima
- Viaje atípico
- Inicio de sesión desde dispositivos infectados
- Inicio de sesión desde direcciones IP con actividad sospechosa
- Inicio de sesión desde ubicaciones desconocidas

## <a name="before-you-begin"></a>Antes de empezar

Se deben cumplir las condiciones siguientes para que los usuarios puedan aparecer en la lista de usuarios de riesgo:

- El inquilino del cliente debe tener una licencia de Azure AD Premium para cada usuario. Para obtener más información sobre qué licencias admiten Azure AD Identity Protection, consulte [¿Qué es Identity Protection?](/azure/active-directory/identity-protection/overview-identity-protection)

- El inquilino del cliente debe estar activo dentro de Microsoft 365 Lighthouse. Para determinar si un inquilino está activo, consulte [Información general de la página Windows 365 (PC en la nube) en Microsoft 365 Lighthouse](m365-lighthouse-tenant-list-overview.md).

## <a name="review-detected-risks-and-take-action"></a>Revisar los riesgos detectados y tomar medidas

En Azure AD Identity Protection, las detecciones de riesgos incluyen las acciones sospechosas identificadas relacionadas con las cuentas de usuario de Azure AD.

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Usuarios**.

2. Seleccione la pestaña **Usuarios de riesgo** .

3. Revise los usuarios de la lista con un estado de riesgo de **En riesgo**.

4. Seleccione **Ver detecciones de riesgos** para obtener información detallada sobre los riesgos detectados para cada usuario. Para obtener más información sobre los tipos de riesgo y la detección, consulte [¿Qué es el riesgo?](/azure/active-directory/identity-protection/concept-identity-protection-risks).

5. Para cada usuario, evalúe las detecciones de riesgo y seleccione una de las siguientes acciones, según corresponda:

    - Restablecer contraseña: cambie o restablezca la contraseña de usuario.

    - Bloquear inicio de sesión: impedir que nadie inicie sesión como este usuario.

    - Confirmar que el usuario está en peligro: establezca el estado de riesgo en confirmado en peligro.

    - Descartar el riesgo de usuario: establezca el estado de riesgo en descartado.

## <a name="take-action-on-multiple-user-accounts-at-once"></a>Realizar acciones en varias cuentas de usuario a la vez

Para realizar acciones en varios usuarios afectados a la vez:

1. En la pestaña **Usuarios de riesgo** , seleccione el conjunto de usuarios en los que desea realizar acciones.

2. Elija una de las siguientes acciones para realizar:

    - Restablecer contraseña

    - Bloquear inicio de sesión

    - Confirmar que el usuario está en peligro

    - Descartar el riesgo del usuario

> [!NOTE]
> Si la organización que administra tiene una licencia de Azure AD Premium P2, se recomienda habilitar directivas de acceso condicional basadas en riesgos de usuario. Para obtener más información, vea [Acceso condicional: Acceso condicional basado en riesgos del usuario](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk-user).

## <a name="related-content"></a>Contenido relacionado
[Tutorial: Uso de detecciones de riesgo para inicios de sesión de usuario para desencadenar cambios de contraseña o multifactor de Azure AD](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) (artículo)\
[¿Qué es el riesgo?](/azure/active-directory/identity-protection/concept-identity-protection-risks) (artículo) \
[Corrección de riesgos y desbloqueo de usuarios](/azure/active-directory/identity-protection/howto-identity-protection-remediate-unblock) (artículo)
