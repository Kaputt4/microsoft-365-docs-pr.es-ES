---
title: Implementar capacidades de protección contra amenazas en Microsoft 365
description: Obtenga información general sobre los servicios de protección contra amenazas y las capacidades de seguridad en Microsoft 365 E5. Proteja sus cuentas de usuario, dispositivos, contenido de correo electrónico y más con Microsoft 365 E5.
keywords: protección contra amenazas de microsoft, defender, configuración, protección contra amenazas avanzada, seguridad, microsoft 365 E5, proteger dispositivos
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: ITPro
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 4008f4e0198058e2b13de62c34697e3034d499b2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583225"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Implementar capacidades de protección contra amenazas en Microsoft 365 E5

Esta solución describe las potentes capacidades de protección contra amenazas Microsoft 365 E5 y por qué la protección contra amenazas es importante. Obtenga información general sobre la protección contra amenazas en Microsoft 365 E5 y vea cómo abordar la configuración y la configuración de su organización.

## <a name="why-threat-protection-is-important"></a>Por qué la protección contra amenazas es importante 

[El malware](/windows/security/threat-protection/intelligence/understanding-malware)y los ciberataques sofisticados, como las [amenazas sin](/windows/security/threat-protection/intelligence/fileless-threats)archivos, son una ocurrencia común. Las empresas deben protegerse a sí mismas y a sus clientes con capacidades de seguridad de IT eficaces. Los ciberataques pueden causar problemas importantes para su organización, que van desde una pérdida de confianza hasta problemas financieros, tiempos de inactividad que amenazan la empresa y mucho más. La protección contra amenazas es importante, pero puede resultar difícil determinar dónde enfocar el tiempo, el esfuerzo y los recursos de la organización. Microsoft 365 E5 puede ayudarle. 

## <a name="threat-protection-in-microsoft-365-e5"></a>Protección contra amenazas en Microsoft 365 E5

Las soluciones de seguridad de Microsoft están integradas en nuestros productos y servicios. Las capacidades de automatización y aprendizaje automático reducen la carga en los equipos de seguridad para asegurarse de que se abordan los elementos correctos. La solidez de las soluciones de seguridad de Microsoft se basa en trillones de señales que procesamos todos los días en nuestro servicio de seguridad [inteligente Graph](/graph/security-concept-overview). Microsoft 365 de seguridad incluyen [Microsoft 365 Defender,](../security/defender/microsoft-365-defender.md)una solución que reúne señales en el correo electrónico, los datos, los dispositivos y las identidades para pintar una imagen de amenazas avanzadas contra su organización.

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) le permite proteger su organización con inteligencia integrada adaptable. Con las capacidades de seguridad de Microsoft 365 E5, puede detectar e investigar amenazas avanzadas, identidades comprometidas y acciones malintencionadas en todo el entorno (local y en la nube).

## <a name="better-protection-with-integration"></a>Mejor protección con integración

En Microsoft 365 E5, las capacidades de protección contra amenazas están integradas de forma predeterminada. Las señales de cada funcionalidad agregan fuerza a la capacidad general de detectar y responder a las amenazas. El conjunto combinado de capacidades ofrece la mejor protección para las organizaciones, especialmente las organizaciones nacionales, en comparación con la ejecución de productos que no son de Microsoft. En la siguiente imagen se muestran los servicios y las capacidades de protección contra amenazas que se describen en este artículo.

![Información general sobre Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defender reúne las señales y los datos en un centro de [Microsoft 365 de seguridad unificada.](/microsoft-365/security/defender/overview-security-center) 

> [!div class="mx-imgBorder"]
> ![Ilustración conceptual del panel Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

## <a name="deployment-overview"></a>Información general sobre la implementación

En la siguiente ilustración se muestra una ruta de acceso recomendada para implementar estas capacidades individuales. 

> [!div class="mx-imgBorder"]
> ![Señales de protección contra amenazas M365](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

Vea este vídeo para obtener información general del proceso de implementación.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

En la tabla siguiente se describen las distintas soluciones/capacidades que se deben configurar y lo que hacen.

|Paso |Solución/funcionalidades  |Descripción  |
|--|---------|---------|
| 1 |[Autenticación multifactor y acceso condicional](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)     |Proteger contra identidades y dispositivos en peligro. Comience con esta protección porque es fundamental. La configuración recomendada en esta guía incluye Azure AD Identity Protection como requisito previo. Para obtener más información, vea [Azure AD Identity Protection](/azure/security/fundamentals/threat-detection#azure-active-directory-identity-protection).     |
| 2 |[Microsoft Defender for Identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)     |  Una solución de seguridad basada en la nube que usa las señales locales de Servicios de dominio de Active Directory (AD DS) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización. Céntrate en Microsoft Defender para Identity a continuación porque protege la infraestructura local y en la nube, no tiene dependencias ni requisitos previos y puede proporcionar ventajas de seguridad inmediatas. Para obtener más información, vea [What is Identity Protection?](/azure/active-directory/identity-protection/overview-identity-protection). | 
| 3 |[Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender) |Combina las señales y orquesta las capacidades en una única solución. Permite a los profesionales de seguridad unir señales de amenaza y determinar el alcance completo y el impacto de una amenaza. Microsoft 365 Defender realiza acciones automáticas para evitar o detener el ataque y auto sanar los buzones, puntos de conexión e identidades de usuario afectados. Para obtener más información, [vea Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). |
| 4  |[Microsoft Defender para Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)     | Protege su organización contra las amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración. Protege contra malware, phishing, suplantación de identidad y otros tipos de ataques. Se recomienda configurar Microsoft Defender para Office 365 porque el control de cambios, la migración de la configuración desde el sistema actual y otras consideraciones pueden tardar más tiempo en implementarse. Para obtener más información, vea [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365).       |
| 5  |[Microsoft Defender para punto de conexión](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)    | Ayuda a prevenir, detectar, investigar y responder a amenazas avanzadas en todos los dispositivos (también denominados puntos de conexión). Defender for Endpoint es una sólida oferta de protección contra amenazas. Para obtener más información, vea [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).  |
| 6  |[Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)     | Un agente de seguridad de acceso a la nube para la detección, investigación y gobierno. Puede habilitar la Microsoft Cloud App Security para empezar a recopilar datos e información. Implementar información y otra protección dirigida en las aplicaciones SaaS implica planear y puede tardar más tiempo. Para obtener más información, vea [What is Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)      | 

> [!TIP]
> Las organizaciones que tienen varios equipos de seguridad pueden implementar funcionalidades en paralelo. Por ejemplo, un equipo puede configurar Defender para Office 365 mientras que otro equipo configura Defender para endpoint. La configuración no tiene que seguir nuestro orden sugerido exactamente. 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>Planear la implementación de la solución de protección contra amenazas

En el siguiente diagrama se muestra el proceso de alto nivel para implementar funcionalidades de protección contra amenazas. 

![Proceso para implementar funcionalidades de protección contra amenazas](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Para asegurarse de que su organización tiene la mejor protección posible, [configure](deploy-threat-protection-configure.md) e implemente la solución de seguridad con un proceso que incluya los siguientes pasos:

1. [Configurar la autenticación multifactor y las directivas de acceso condicional.](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Configurar Microsoft Defender para identity](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity).
3. [Active Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender).
4. [Configurar Defender para Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365).
5. [Configurar Microsoft Defender para endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint).
6. [Configurar Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security).
7. [Supervisar el estado y realizar acciones](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions).
8. [Entrenar usuarios](deploy-threat-protection-configure.md#step-8-train-users).

Las características de protección contra amenazas se pueden configurar en paralelo, por lo que si tiene varios equipos de seguridad de red responsables de diferentes servicios, pueden configurar las características de protección de la organización al mismo tiempo.

## <a name="next-step"></a>Paso siguiente

Continúe con [Configurar las capacidades de protección contra amenazas en Microsoft 365](deploy-threat-protection-configure.md).


