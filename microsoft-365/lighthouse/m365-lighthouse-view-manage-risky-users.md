---
title: Ver y administrar usuarios riesgosos
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo ver y administrar usuarios arriesgados.
ms.openlocfilehash: 708fc0576c85d9b8511ac6b31ed0398fae1b20d3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331236"
---
# <a name="view-and-manage-risky-users"></a>Ver y administrar usuarios riesgosos

Microsoft recopila y analiza trillones de señales de inicio de sesión de usuario cada día. Estas señales se usan para ayudar a crear buenos patrones de comportamiento de inicio de sesión del usuario e identificar posibles intentos de inicio de sesión de riesgo. Azure Active Directory (Azure AD) Identity Protection usa estas señales para revisar los intentos de inicio de sesión del usuario y tomar medidas si hay actividad sospechosa.

Microsoft 365 Lighthouse ayuda a administrar los riesgos detectados por Azure AD Identity Protection proporcionando una única vista de los usuarios de riesgo en todos los inquilinos administrados. Puedes proteger rápidamente a los usuarios arriesgados restablecimiento de su contraseña o bloqueándolos para que no inicien sesión en su Microsoft 365 usuario. También puede ver información para comprender mejor el riesgo de un usuario y determinar los pasos siguientes.

Azure AD identity protection identifica los riesgos de muchos tipos, incluidos:

- Credenciales filtradas
- Uso de IP anónima
- Viajes atípicos
- Iniciar sesión desde dispositivos infectados
- Iniciar sesión desde direcciones IP con actividad sospechosa
- Iniciar sesión desde ubicaciones desconocidas

## <a name="before-you-begin"></a>Antes de empezar

Se deben cumplir las siguientes condiciones antes de que los usuarios puedan aparecer en la lista de usuarios de riesgo:

- El inquilino del cliente debe tener una Azure AD Premium licencia para cada usuario. Para obtener más información sobre las licencias que admiten Azure AD identidad, vea [¿Qué es la protección de identidades?](/azure/active-directory/identity-protection/overview-identity-protection)

- El inquilino del cliente debe estar activo en Microsoft 365 Lighthouse. Para determinar si un espacio empresarial está activo, consulte [Microsoft 365 Lighthouse de la página Inquilinos](m365-lighthouse-tenant-list-overview.md).

## <a name="review-detected-risks-and-take-action"></a>Revisar los riesgos detectados y tomar medidas

En Azure AD identity protection, las detecciones de riesgos incluyen cualquier acción sospechosa identificada relacionada con cuentas de usuario en Azure AD.

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Usuarios**.

2. Seleccione la **pestaña Usuarios arriesgados** .

3. Revise los usuarios de la lista con un estado de riesgo en **Riesgo**.

4. Seleccione **Ver detecciones de riesgos** para obtener información detallada sobre los riesgos detectados para cada usuario. Para obtener más información acerca de los tipos de riesgo y la detección, vea [¿Qué es el riesgo?](/azure/active-directory/identity-protection/concept-identity-protection-risks).

5. Para cada usuario, evalúe las detecciones de riesgos y seleccione una de las siguientes acciones, según corresponda:

    - Restablecer contraseña: cambie o restablezca la contraseña del usuario.

    - Bloquear el inicio de sesión: impedir que alguien inicie sesión como este usuario.

    - Confirmar que el usuario está en peligro: establezca el estado de riesgo en confirmado en peligro.

    - Descartar riesgo de usuario: establezca el estado de riesgo en descartado.

## <a name="take-action-on-multiple-user-accounts-at-once"></a>Realizar acciones en varias cuentas de usuario a la vez

Para tomar medidas en varios usuarios afectados a la vez:

1. En la **pestaña Usuarios arriesgados** , seleccione el conjunto de usuarios en los que desea realizar acciones.

2. Elija una de las siguientes acciones para realizar:

    - Restablecer contraseña

    - Bloquear inicio de sesión

    - Confirmar que el usuario está en peligro

    - Descartar riesgo de usuario

> [!NOTE]
> Si la organización que está administrando tiene una licencia Azure AD Premium P2, se recomienda habilitar las directivas de acceso condicional basadas en riesgos del usuario. Para obtener más información, [vea Conditional Access: User risk-based Conditional Access](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk-user).

## <a name="related-content"></a>Contenido relacionado
[Tutorial: Usar detecciones de riesgos para inicios](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) de sesión de usuario para desencadenar Azure AD autenticación multifactor o cambios de contraseña (artículo)\
[¿Cuál es el riesgo?](/azure/active-directory/identity-protection/concept-identity-protection-risks) (artículo) \
[Corregir riesgos y desbloquear usuarios](/azure/active-directory/identity-protection/howto-identity-protection-remediate-unblock) (artículo)
