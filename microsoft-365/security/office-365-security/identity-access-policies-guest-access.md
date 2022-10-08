---
title: 'Directivas de acceso a dispositivos e identidades para permitir el acceso B2B de usuario invitado y externo: Microsoft 365 para empresas | Microsoft Docs'
description: Describe el acceso condicional recomendado y las directivas relacionadas para proteger el acceso de invitados y usuarios externos.
ms.service: microsoft-365-security
ms.topic: article
ms.author: dansimp
author: dansimp
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
- m365-security
- m365solution-identitydevice
- m365solution-scenario
- zerotrust-solution
- highpri
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 0d7a51a8afb51265a63954749370f4939557a11b
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68088671"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Directivas para permitir el acceso de invitado y el acceso de usuarios externos B2B

En este artículo se describe cómo ajustar las directivas recomendadas de acceso a dispositivos e identidades Confianza cero para permitir el acceso de invitados y usuarios externos que tienen una cuenta de Negocio a Negocio (B2B) de Azure Active Directory (Azure AD). Esta guía se basa en las [directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md).

Estas recomendaciones están diseñadas para aplicarse al **nivel de punto inicial** de protección. Pero también puede ajustar las recomendaciones en función de sus necesidades específicas para la protección de **seguridad** **empresarial** y especializada.

Proporcionar una ruta de acceso para que las cuentas B2B se autentiquen con el inquilino de Azure AD no proporciona a estas cuentas acceso a todo el entorno. Los usuarios B2B y sus cuentas tienen acceso a servicios y recursos, como archivos, compartidos con ellos mediante la directiva de acceso condicional.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Actualización de las directivas comunes para permitir y proteger el acceso de invitados y usuarios externos

En este diagrama se muestran las directivas que se van a agregar o actualizar entre las directivas comunes de acceso a dispositivos e identidades, para el acceso de usuario externo e invitado B2B.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png" alt-text="Resumen de las actualizaciones de directivas para proteger el acceso de invitado" lightbox="../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png":::

En la tabla siguiente se enumeran las directivas que debe crear y actualizar. Las directivas comunes se vinculan a las instrucciones de configuración asociadas en el artículo [Common identity and device access policies (Directivas comunes de acceso a dispositivos e identidades](identity-access-policies.md) ).

|Nivel de protección|Directivas|Más información|
|---|---|---|
|**Punto de inicio**|[Requerir MFA siempre para invitados y usuarios externos](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Cree esta nueva directiva y configure: <ul><li>En **Asignaciones > Usuarios y grupos > Incluir**, elija **Seleccionar usuarios y grupos** y, a continuación, seleccione **Todos los usuarios invitados y externos**.</li><li>En **Asignaciones > Condiciones > inicio de sesión**, deje todas las opciones desactivadas para aplicar siempre la autenticación multifactor (MFA).</li></ul>|
||[Requerir MFA cuando el riesgo de inicio de sesión es *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Modifique esta directiva para excluir invitados y usuarios externos.|

Para incluir o excluir invitados y usuarios externos en las directivas de acceso condicional, en **Asignaciones > Usuarios y grupos > Incluir** o **Excluir**, compruebe **Todos los usuarios invitados y externos**.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png" alt-text="Controles para excluir invitados y usuarios externos" lightbox="../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png":::

## <a name="more-information"></a>Más información

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Acceso de invitados y usuarios externos con Microsoft Teams

Microsoft Teams define los siguientes usuarios:

- **El acceso de invitado** usa una cuenta B2B de Azure AD que se puede agregar como miembro de un equipo y tener acceso a las comunicaciones y los recursos del equipo.

- **El acceso externo** es para un usuario externo que no tiene una cuenta B2B. El acceso de usuarios externos incluye invitaciones, llamadas, chats y reuniones, pero no incluye la pertenencia al equipo ni el acceso a los recursos del equipo.

Para obtener más información, consulte la [comparación entre invitados y el acceso de usuarios externos para los equipos](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Para obtener más información sobre cómo proteger las directivas de acceso a dispositivos e identidades para Teams, consulte [Recomendaciones de directivas para proteger chats, grupos y archivos de Teams](teams-access-policies.md).

### <a name="require-mfa-always-for-guest-and-external-users"></a>Requerir MFA siempre para usuarios invitados y externos

Esta directiva solicita a los invitados que se registren para MFA en el inquilino, independientemente de si están registrados para MFA en su inquilino principal. Al acceder a los recursos del inquilino, los invitados y los usuarios externos deben usar MFA para cada solicitud.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Exclusión de invitados y usuarios externos de MFA basada en riesgos

Aunque las organizaciones pueden aplicar directivas basadas en riesgos para usuarios B2B mediante Azure AD Identity Protection, hay limitaciones en la implementación de Azure AD Identity Protection para usuarios de colaboración B2B en un directorio de recursos debido a su identidad existente en su directorio principal. Debido a estas limitaciones, Microsoft recomienda excluir a los invitados de las directivas de MFA basadas en riesgos y requerir que estos usuarios usen siempre MFA.

Para obtener más información, consulte [Limitaciones de Identity Protection para usuarios de colaboración B2B](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).

### <a name="excluding-guests-and-external-users-from-device-management"></a>Exclusión de invitados y usuarios externos de la administración de dispositivos

Solo una organización puede administrar un dispositivo. Si no excluye a los invitados y usuarios externos de las directivas que requieren el cumplimiento del dispositivo, estas directivas bloquearán a estos usuarios.

## <a name="next-step"></a>Paso siguiente

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png" alt-text="Directivas para aplicaciones en la nube de Microsoft 365 y Microsoft Defender for Cloud Apps" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png":::

Configurar directivas de acceso condicional para:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
- [Microsoft Defender for Cloud Apps](mcas-saas-access-policies.md)
 
