---
title: 'Directivas de acceso a dispositivos y identidades para permitir el acceso B2B de usuarios invitados y externos: Microsoft 365 para empresas | Microsoft Docs'
description: Describe el acceso condicional recomendado y las directivas relacionadas para proteger el acceso de invitados y usuarios externos.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
audience: Admin
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
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 090f5a81c624b22298c257fae890691c8e5151ee
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2021
ms.locfileid: "61121192"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Directivas para permitir el acceso de invitado y el acceso de usuarios externos B2B

En este artículo se describe cómo ajustar las directivas recomendadas de acceso a dispositivos y identidad de confianza cero para permitir el acceso a invitados y usuarios externos que tienen una cuenta de Azure Active Directory (Azure AD) empresa a empresa (B2B). Esta guía se basa en las directivas [comunes de acceso a dispositivos y identidades.](identity-access-policies.md)

Estas recomendaciones están diseñadas para aplicarse al nivel **de punto inicial** de protección. Pero también puede ajustar las recomendaciones en  función de sus necesidades específicas de protección de seguridad especializada **y** empresarial.

Proporcionar una ruta de acceso para que las cuentas B2B se autentiquen con su Azure AD inquilino no proporciona a estas cuentas acceso a todo el entorno. Los usuarios B2B y sus cuentas tienen acceso a servicios y recursos, como archivos, compartidos con ellos mediante la directiva de acceso condicional.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Actualizar las directivas comunes para permitir y proteger el acceso de invitados y usuarios externos

En este diagrama se muestran las directivas que se agregarán o actualizarán entre las directivas comunes de acceso a dispositivos y identidades, para el acceso de invitado b2B y de usuario externo.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png" alt-text="Resumen de las actualizaciones de directivas para proteger el acceso de invitados." lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png":::

En la tabla siguiente se enumeran las directivas que debe crear y actualizar. Las directivas comunes se vinculan a las instrucciones de configuración asociadas en [el artículo Identidad común y directivas de acceso a dispositivos.](identity-access-policies.md)

|Nivel de protección|Directivas|Más información|
|---|---|---|
|**Punto de inicio**|[Requerir MFA siempre para invitados y usuarios externos](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Cree esta nueva directiva y configure: <ul><li>Para **Asignaciones > Usuarios** y grupos > Incluir , elija **Seleccionar** usuarios y grupos y, a continuación, seleccione Todos los usuarios **invitados y externos.**</li><li>Para **las asignaciones > condiciones > inicio** de sesión, deje todas las opciones desactivadas para aplicar siempre la autenticación multifactor (MFA).</li></ul>|
||[Requerir MFA cuando el riesgo de inicio de sesión *es medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modifique esta directiva para excluir invitados y usuarios externos.|

Para incluir o excluir **invitados** y usuarios externos en directivas de acceso condicional, para Asignaciones > Usuarios y grupos > Incluir o **Excluir**, compruebe Todos los usuarios invitados **y externos**.

![captura de pantalla de controles para excluir invitados y usuarios externos.](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Más información

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Invitados y acceso de usuario externo con Microsoft Teams

Microsoft Teams define los siguientes usuarios:

- **El acceso** de invitado usa Azure AD cuenta B2B que se puede agregar como miembro de un equipo y tener acceso a las comunicaciones y recursos del equipo.

- **El acceso** externo es para un usuario externo que no tiene una cuenta B2B. El acceso de usuarios externos incluye invitaciones, llamadas, chats y reuniones, pero no incluye la pertenencia al equipo ni el acceso a los recursos del equipo.

Para obtener más información, vea la [comparación entre invitados y el acceso de usuarios externos para teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Para obtener más información sobre cómo proteger las directivas de acceso a dispositivos y identidades para Teams, consulte [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).

### <a name="require-mfa-always-for-guest-and-external-users"></a>Requerir MFA siempre para usuarios invitados y externos

Esta directiva solicita a los invitados que se registren en MFA en el inquilino, independientemente de si están registrados para MFA en su inquilino principal. Al obtener acceso a recursos en el inquilino, los invitados y los usuarios externos deben usar MFA para cada solicitud.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Excluir invitados y usuarios externos de MFA basada en riesgos

Aunque las organizaciones pueden aplicar directivas basadas en riesgos para los usuarios de B2B mediante la protección de identidades de Azure AD, existen limitaciones en la implementación de la protección de identidades de Azure AD para los usuarios de colaboración B2B en un directorio de recursos debido a su identidad existente en su directorio principal. Debido a estas limitaciones, Microsoft recomienda excluir invitados de las directivas de MFA basadas en riesgos y requerir que estos usuarios usen siempre MFA.

Para obtener más información, vea [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).

### <a name="excluding-guests-and-external-users-from-device-management"></a>Excluir invitados y usuarios externos de la administración de dispositivos

Solo una organización puede administrar un dispositivo. Si no excluyes a los invitados ni a los usuarios externos de las directivas que requieren el cumplimiento de dispositivos, estas directivas bloquearán a estos usuarios.

## <a name="next-step"></a>Paso siguiente

![Paso 4: Directivas para Microsoft 365 aplicaciones en la nube y Microsoft Defender para aplicaciones en la nube.](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurar directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
- [Microsoft Defender for Cloud Apps](mcas-saas-access-policies.md)
 
