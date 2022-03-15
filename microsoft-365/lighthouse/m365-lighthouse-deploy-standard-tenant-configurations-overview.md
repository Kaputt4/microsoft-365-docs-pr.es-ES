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
ms.openlocfilehash: 643bb962277d30caf8ea067b9276a5986af8914f
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504513"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>Introducción al uso de líneas base para implementar configuraciones de inquilino estándar 

Microsoft 365 Lighthouse línea base proporcionan una forma repetible y escalable de administrar la configuración de seguridad Microsoft 365 en varios inquilinos de clientes. Las líneas base proporcionan configuraciones de inquilino estándar que implementan directivas de seguridad principales y estándares de cumplimiento que mantienen seguros a los usuarios, dispositivos y datos de los inquilinos.

Puede ver la línea base predeterminada y sus pasos de implementación desde Lighthouse. Para aplicar una línea base a un inquilino, seleccione **Inquilinos** en el panel de navegación izquierdo y, a continuación, seleccione un espacio empresarial. A continuación, vaya a la **pestaña Planes de** implementación para iniciar la implementación.

## <a name="lighthouse-baseline"></a>Línea base de Faro

Las configuraciones de línea base de Faro están diseñadas para asegurarse de que todos los inquilinos administrados son seguros y compatibles. Seleccione **Líneas base en** el panel de navegación izquierdo para ver la línea base predeterminada que se aplica a todos los inquilinos.  Para ver los pasos de implementación incluidos en la línea base predeterminada, seleccione **Ver línea base** para abrir la página de línea base predeterminada. Seleccione cualquiera de los pasos de implementación para ver los detalles de implementación y el impacto del usuario.

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Captura de pantalla de la página de línea base predeterminada.":::

### <a name="default-lighthouse-configurations"></a>Configuraciones predeterminadas de Faro

| Configuración de línea base | Descripción |
|--|--|
| Requerir MFA para administradores | Una directiva de acceso condicional que requiere autenticación multifactor para todos los administradores. Es necesario para todas las aplicaciones en la nube. Para obtener más información acerca de esta línea base, vea [Acceso condicional: requerir MFA para todos los administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa).|
| Requerir MFA para usuarios finales | Una directiva de acceso condicional que requiere autenticación multifactor para todos los usuarios.  Es necesario para todas las aplicaciones en la nube. Para obtener más información acerca de esta línea base, vea [Acceso condicional: requerir MFA para todos los usuarios](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa). |
| Bloquear la autenticación heredada | Una directiva de acceso condicional para bloquear la autenticación de cliente heredada. Para obtener más información acerca de esta línea base, vea [Bloquear la autenticación heredada Azure AD acceso condicional](/azure/active-directory/conditional-access/block-legacy-authentication).|
| Configurar la inscripción de dispositivos | Inscripción de dispositivos para permitir que los dispositivos de inquilino se inscriban en Microsoft Endpoint Manager. Para ello, configura la inscripción automática entre Azure Active Directory y Microsoft Endpoint Manager. Para obtener más información acerca de esta línea base, consulta [Configurar la inscripción para Windows dispositivos.](/mem/intune/enrollment/windows-enroll) |
| Configurar Antivirus de Microsoft Defender para Windows 10 y versiones posteriores | Un perfil de configuración de dispositivo para Windows dispositivos con opciones de configuración Antivirus de Microsoft Defender configuradas previamente. Para obtener más información acerca de esta línea base, consulte [Configure Microsoft Defender for Endpoint in Intune](/mem/intune/protect/advanced-threat-protection-configure).|
| Configurar firewall de Microsoft Defender para Windows 10 y versiones posteriores | Una directiva de firewall para ayudar a proteger los dispositivos evitando el tráfico de red no deseado y no autorizado. Para obtener más información acerca de esta línea base, consulte [Procedimientos recomendados para configurar el firewall Windows Defender cliente](/windows/security/threat-protection/windows-firewall/best-practices-configuring).  |
| Configurar una directiva de cumplimiento de dispositivos para Windows 10 y versiones posteriores | Una Windows de dispositivos con configuraciones preconfiguradas para cumplir los requisitos básicos de cumplimiento. Para obtener más información acerca de esta línea base, consulta [Acceso condicional: Requerir dispositivos Azure AD compatibles o híbridos](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device). |

## <a name="deployment-plans"></a>Planes de implementación

Cada inquilino activo tiene un plan de implementación que incluye los pasos de implementación de la línea Microsoft 365 Lighthouse línea base. Para obtener acceso al plan de implementación de un inquilino, seleccione un inquilino activo en la lista de la página **Inquilinos** y, a continuación, seleccione la **pestaña Plan de** implementación.

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/deployment-plan-tab.png" alt-text="Captura de pantalla de la pestaña Plan de implementación.":::

La pestaña Plan de implementación incluye la siguiente información:


|Columna  |Descripción  |
|---------|---------|
|Paso de implementación     |  Descripción del paso de implementación.       |
|Estado     |El estado del paso de implementación.         |
|Línea base     |Línea base desde la que se deriva el paso de implementación.         |
|Categoría     | Si el paso de implementación está asociado con la administración de dispositivos, identidad o datos.        |
|Actualizado por última vez    | La fecha en la que se actualizó por última vez el paso de implementación.        |


La pestaña Plan de implementación también incluye las siguientes opciones:

- **Exportar:** Seleccione esta opción para exportar los datos del paso de implementación Excel un archivo de valores separados por comas (.csv).
- **Actualizar:** Seleccione esta opción para recuperar los datos del paso de implementación más actuales.
- **Buscar:** Escriba palabras clave para localizar rápidamente un paso de implementación específico en la lista.

## <a name="deployment-steps-and-processes"></a>Pasos y procesos de implementación

El plan de implementación de cada inquilino incluye los pasos de implementación de la línea Microsoft 365 Lighthouse línea base. Cada paso de implementación se compone de uno o varios procesos que deben completarse para cumplir los requisitos del paso de implementación. Cuando un nuevo inquilino se activa, debe completar las actividades de implementación asociadas con los pasos y procesos de implementación.

Para cada paso de implementación, puede realizar las siguientes acciones:

|Acción  |Descripción  |
|---------|---------|
| Compartir    |  Permite que el contenido del paso de implementación se comparta a través de un vínculo o por correo electrónico.    |
| Revisar e implementar    |  Permite al usuario: <ul><li>Cuando se admite, compare las opciones de configuración del paso de implementación con las de las directivas existentes sin implementar la configuración en el espacio empresarial.<br>Los siguientes pasos de implementación admiten la comparación:</br><ul><li>Configurar una directiva de cumplimiento de dispositivos para Windows 10 y versiones posteriores</li><li>Requerir MFA para usuarios finales</li><li>Requerir MFA para administradores</li><li>Bloquear la autenticación heredada</li></ul></li> <li>Implemente las opciones de configuración en el espacio empresarial.</li></ul>**Nota:** Los pasos que no admiten la capacidad de comparar sin implementar la configuración en el espacio empresarial le permitirán revisar las opciones de configuración e implementarlas.|
| Actualizar el estado del plan de acción    |  Permite al usuario notificar el estado de su plan de acción para el paso de implementación.      |

## <a name="related-content"></a>Contenido relacionado

[Implementar Microsoft 365 Lighthouse líneas base](m365-lighthouse-deploy-baselines.md) (artículo)\
[Directivas comunes de acceso condicional](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
