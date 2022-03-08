---
title: Introducción al uso de líneas base para implementar configuraciones de inquilino estándar
f1.keywords: CSH
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo usar líneas base para implementar configuraciones de inquilino estándar.
ms.openlocfilehash: f59ca686892e0b20ce5e9ffb6d62859ce8079896
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323155"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>Introducción al uso de líneas base para implementar configuraciones de inquilino estándar 

Microsoft 365 Lighthouse línea base proporcionan una forma repetible y escalable de administrar la configuración de seguridad Microsoft 365 en varios inquilinos de clientes. Las líneas base también ayudan a supervisar las directivas de seguridad principales y los estándares de cumplimiento de inquilinos con configuraciones que protegen usuarios, dispositivos y datos.

Diseñado para ayudar a los proveedores de servicios administrados (MSP) a permitir la adopción de seguridad por parte de los clientes, Lighthouse proporciona un conjunto estándar de parámetros de línea base y configuraciones predefinidas para Microsoft 365 servicios. Estas configuraciones de seguridad ayudan a medir el progreso Microsoft 365 seguridad y cumplimiento de los inquilinos.

Puede ver la línea base predeterminada y sus pasos de implementación desde Lighthouse. Para aplicar una línea base a un inquilino, seleccione **Inquilinos** en el panel de navegación izquierdo y, a continuación, seleccione un espacio empresarial. A continuación, vaya a la **pestaña Planes de** implementación e implemente la línea base.

## <a name="default-baseline-security-templates"></a>Plantillas de seguridad de línea base predeterminadas

Las configuraciones de línea base predeterminadas de Faro para cargas de trabajo de seguridad están diseñadas para asegurarse de que todos los inquilinos administrados son seguros y compatibles.

Las configuraciones de línea base de la tabla siguiente vienen estándar con la línea base predeterminada de Lighthouse.<br><br>

| Configuración de línea base | Descripción |
|--|--|
| Requerir MFA para administradores | Una directiva de acceso condicional que requiere autenticación multifactor para todos los administradores. Es necesario para todas las aplicaciones en la nube. Para obtener más información acerca de esta línea base, vea [Acceso condicional: requerir MFA para todos los administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa).|
| Requerir MFA para usuarios finales | Una directiva de acceso condicional que requiere autenticación multifactor para todos los usuarios.  Es necesario para todas las aplicaciones en la nube. Para obtener más información acerca de esta línea base, vea [Acceso condicional: requerir MFA para todos los usuarios](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa). |
| Bloquear la autenticación heredada | Una directiva de acceso condicional para bloquear la autenticación de cliente heredada. Para obtener más información acerca de esta línea base, vea [Bloquear la autenticación heredada Azure AD acceso condicional](/azure/active-directory/conditional-access/block-legacy-authentication).|
| Configurar la inscripción de dispositivos | Inscripción de dispositivos para permitir que los dispositivos de inquilino se inscriban en Microsoft Endpoint Manager. Para ello, configura la inscripción automática entre Azure Active Directory y Microsoft Endpoint Manager. Para obtener más información acerca de esta línea base, consulta [Configurar la inscripción para Windows dispositivos.](/mem/intune/enrollment/windows-enroll) |
| Configurar Antivirus de Microsoft Defender para Windows 10 y versiones posteriores | Un perfil de configuración de dispositivo para Windows dispositivos con opciones de configuración Antivirus de Microsoft Defender configuradas previamente. Para obtener más información acerca de esta línea base, consulte [Configure Microsoft Defender for Endpoint in Intune](/mem/intune/protect/advanced-threat-protection-configure).|
| Configurar firewall de Microsoft Defender para Windows 10 y versiones posteriores | Una directiva de firewall para ayudar a proteger los dispositivos evitando el tráfico de red no deseado y no autorizado. Para obtener más información acerca de esta línea base, consulte [Procedimientos recomendados para configurar el firewall Windows Defender cliente](/windows/security/threat-protection/windows-firewall/best-practices-configuring).  |
| Configurar una directiva de cumplimiento de dispositivos para Windows 10 y versiones posteriores | Una Windows de dispositivos con configuraciones preconfiguradas para cumplir los requisitos básicos de cumplimiento. Para obtener más información acerca de esta línea base, consulta [Acceso condicional: Requerir dispositivos Azure AD compatibles o híbridos](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device). |


## <a name="related-content"></a>Contenido relacionado

[Implementar Microsoft 365 Lighthouse líneas base](m365-lighthouse-deploy-baselines.md) (artículo)\
[Directivas comunes de acceso condicional](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
