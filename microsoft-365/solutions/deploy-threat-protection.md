---
title: Implementar la protección contra amenazas de seguridad de red en Microsoft 365
description: Obtenga información sobre cómo implementar servicios de protección contra amenazas y capacidades de seguridad de red de IT en Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 79352aca2012e6615f41b19f4a77fc5cf125f4c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926755"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Implementar capacidades de protección contra amenazas en Microsoft 365

[El malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)y los ciberataques sofisticados, como las amenazas [sin](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)archivos, son una ocurrencia habitual. Las empresas deben protegerse a sí mismas y a sus clientes con capacidades de seguridad de red de IT eficaces. Estos ataques pueden causar problemas importantes para su organización, que van desde una pérdida de confianza hasta problemas financieros, tiempos de inactividad que causan problemas empresariales y mucho más. La protección contra las amenazas es importante, pero puede resultar difícil determinar dónde centrarse el tiempo, el esfuerzo y los recursos de su organización. 

Las soluciones de seguridad de Microsoft están integradas en nuestros productos y servicios. Las capacidades de automatización y aprendizaje automático reducen la carga en los equipos de seguridad para asegurarse de que se abordan los elementos adecuados. Y la solidez de las soluciones de seguridad de red de Microsoft se basa en trillones de señales que procesamos cada día en nuestro [Gráfico de seguridad inteligente.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Las soluciones de seguridad de [Microsoft 365 incluyen Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)una solución que reúne señales en su correo electrónico, datos, dispositivos e identidades para pintar una imagen de amenazas avanzadas contra su organización.


Vea este vídeo para obtener información general del proceso.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Use este artículo como guía para implementar la solución de protección contra amenazas.

## <a name="threat-protection-in-microsoft-365-e5"></a>Protección contra amenazas en Microsoft 365 E5

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) le permite proteger su organización con inteligencia integrada adaptable. Con las características de protección contra amenazas de Microsoft 365 E5, puede detectar e investigar amenazas avanzadas, identidades comprometidas y acciones malintencionadas en su entorno local y en la nube.

En Microsoft 365 E5, las capacidades de protección contra amenazas están integradas de forma predeterminada. Las señales de cada funcionalidad agregan fuerza a la capacidad general de detectar y responder a las amenazas. El conjunto combinado de funcionalidades ofrece la mejor protección para las organizaciones, especialmente las organizaciones nacionales, en comparación con la ejecución de productos que no son de Microsoft. En la imagen siguiente se muestran los servicios y capacidades de protección contra amenazas de Microsoft 365 E5 que se describen en este artículo.

![Información general sobre Microsoft 365 Defender](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

Tan pronto como implemente cualquiera de las funcionalidades de Defender para Office 365, puede activar Microsoft 365 Defender, que reúne las señales y los datos en un solo lugar. 

![Ilustración conceptual del panel de Microsoft 365 Defender](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

En la siguiente ilustración se muestra una ruta de acceso recomendada para implementar estas capacidades individuales. 

![Señales de protección contra amenazas M365](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Solución/funcionalidades  |Descripción  |
|---------|---------|
|Autenticación multifactor y acceso condicional     |Protegerse contra identidades y dispositivos en peligro. Comience con esta protección porque es fundamental. La configuración recomendada en esta guía incluye Azure AD Identity Protection como requisito previo.     |
|Microsoft Defender for Identity     |  Una solución de seguridad basada en la nube que aprovecha las señales locales de Active Directory para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización. Céntrate en Microsoft Defender para Identity a continuación porque protege tu infraestructura local y de nube, no tiene dependencias ni requisitos previos y puede proporcionar ventajas inmediatas.       | 
|Microsoft Defender para Office 365     | Protege su organización contra las amenazas malintencionadas que suponen los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración. Protecciones contra malware, phishing, suplantación de identidad y otros tipos de ataques. A continuación, se recomienda configurar Microsoft Defender para Office 365 porque el control de cambios, la migración de la configuración del sistema actual y otras consideraciones pueden tardar más en implementarse. <br><br>Nota: Asegúrese de configurar las capacidades de protección contra amenazas que se incluyen en todas las suscripciones de Office 365 (Exchange Online Protection).       |
|Microsoft Defender para punto de conexión    | Una plataforma de protección de puntos de conexión que ayuda a prevenir, detectar, investigar y responder a amenazas avanzadas.  Defender for Endpoint puede tardar algún tiempo en implementarse, pero la configuración puede realizarse en paralelo con otras funcionalidades.   |
|Microsoft Cloud App Security     |   Un agente de seguridad de acceso a la nube para la detección, investigación y gobierno. Puede habilitar Microsoft Cloud App Security pronto para empezar a recopilar datos y perspectivas. La implementación de información y otra protección dirigida en las aplicaciones SaaS implica la planeación y puede tardar más tiempo.       | 

> [!TIP]
> Las organizaciones con varios equipos de seguridad pueden implementar estas funcionalidades en paralelo.

## <a name="deploy-your-threat-protection-solution"></a>Implementar la solución de protección contra amenazas

Para asegurarse de que su organización tiene la mejor protección posible, configure e implemente la solución de seguridad para incluir los siguientes pasos:

1. [Configurar la autenticación multifactor y las directivas de acceso condicional](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Configurar Microsoft Defender para la identidad](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Activar Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Configurar Defender para Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Configurar Microsoft Defender para endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Configurar Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Supervisar el estado y realizar acciones](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Entrenar a los usuarios](deploy-threat-protection-configure.md#step-8-train-users)

Las características de protección contra amenazas se pueden configurar en paralelo, por lo que si tiene varios equipos de seguridad de red responsables de diferentes servicios, pueden configurar las características de protección de su organización al mismo tiempo. En el siguiente diagrama se muestra el proceso de alto nivel para implementar capacidades de protección contra amenazas. 

![Proceso para implementar funcionalidades de protección contra amenazas](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 
