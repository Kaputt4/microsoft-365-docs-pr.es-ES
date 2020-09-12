---
title: 'Directivas de acceso a dispositivos e identidades para permitir el acceso de B2B a invitado y externo: Microsoft 365 para Enterprise | Microsoft docs'
description: Describe el acceso condicional recomendado y las directivas relacionadas para proteger el acceso de invitados y usuarios externos.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: a88fc5f46a6dafda72a24ba5e80587b24a216955
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546491"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Directivas para permitir el acceso de B2B y de invitado externo

En este artículo se describe cómo ajustar las directivas de identidad y acceso a dispositivos comunes recomendadas para permitir el acceso a la cuenta de empresa a empresa (B2B) (usuarios invitados y externos). Esta guía se basa en las [directivas comunes de identidad y acceso a dispositivos](identity-access-policies.md).

Estas recomendaciones están diseñadas para aplicarse al nivel de **línea base** de protección. Sin embargo, también puede ajustar las recomendaciones en función de la granularidad de sus necesidades de protección **sensible** y **altamente regulada** . 

Proporcionar una ruta de acceso para que los usuarios B2B se autentiquen con el inquilino de Azure Active Directory (Azure AD) no concede a estos usuarios acceso a todo su entorno. Los usuarios B2B solo tienen acceso a los recursos compartidos con ellos (por ejemplo, archivos) dentro de los servicios concedidos en las directivas de acceso condicional.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Actualización de las directivas comunes para permitir y proteger el acceso de invitados y externos 

Para proteger el acceso de clientes y externos, en el siguiente diagrama se ilustran las directivas que se deben agregar o actualizar desde las directivas comunes de identidad y acceso a dispositivos. 

[![Resumen de las actualizaciones de directivas para proteger el acceso de invitado](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

En la siguiente tabla se enumeran las directivas que debe actualizar o crear nuevas. Las directivas comunes vinculan a las instrucciones de configuración asociadas en el artículo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Nivel de protección|Directivas|Más información|
|:---------------|:-------|:----------------|
|**Baseline**|[Requerir MFA siempre para los usuarios externos y invitados](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Crear esta nueva Directiva y aplicarla solo a los invitados y a los usuarios externos. En **riesgo de inicio de sesión**, deje todas las opciones desactivadas para exigir siempre la autenticación multifactor (MFA).|
|        |[Requerir MFA cuando el riesgo de inicio de sesión sea *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modifique esta directiva para excluir usuarios externos y invitados.|
|        |[Exigir equipos PC compatibles](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Modifique esta directiva para excluir usuarios externos y invitados.|

Para incluir o excluir invitados y usuarios externos en las directivas de acceso condicional, haga clic en la ficha **incluir** o **excluir** y compruebe **todos los invitados y usuarios externos**.

![captura de pantalla de controles para excluir invitados](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Más información

### <a name="guests-vs-external-users"></a>Invitados frente a usuarios externos
En Azure AD, los usuarios externos y invitados son los mismos. El tipo de usuario para ambos es invitado. Los usuarios invitados son usuarios B2B.

Microsoft Teams diferencia entre los usuarios invitados y los usuarios externos dentro de la aplicación, pero ambos son usuarios B2B cuando se autentican. Para obtener más información acerca de los usuarios externos y invitados de Teams, consulte [Enabling Guest and external Access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).

### <a name="require-mfa-always-for-guest-and-external-users"></a>Requerir MFA siempre para los usuarios externos y invitados
Esta directiva solicita a los invitados que se registren en MFA en su espacio empresarial, independientemente de si están registrados para MFA en su inquilino de inicio. Al obtener acceso a los recursos de su espacio empresarial, los invitados y los usuarios externos deben usar MFA para cada solicitud. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Exclusión de invitados y usuarios externos de la MFA basada en riesgos
Si bien las organizaciones pueden aplicar directivas basadas en riesgos para los usuarios de B2B mediante Azure AD Identity Protection, hay limitaciones en la implementación de la protección de identidad de Azure AD para los usuarios de colaboración B2B en un directorio de recursos debido a la identidad existente en su directorio principal. Debido a estas limitaciones, Microsoft recomienda excluir a los usuarios invitados de las directivas de MFA basadas en riesgos y requerir que estos usuarios usen siempre la MFA. 

Para obtener más información, vea [limitaciones de la protección de identidad para usuarios de colaboración B2B](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users). 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Excluir usuarios externos y invitados de la administración de dispositivos 
Solo una organización puede administrar un dispositivo. Si no excluye a los usuarios externos y invitados de las directivas que requieran el cumplimiento de dispositivos, estas directivas bloquearán a estos usuarios. 

## <a name="next-step"></a>Paso siguiente

![Paso 4: directivas para las aplicaciones en la nube de Microsoft 365](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configure las directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

