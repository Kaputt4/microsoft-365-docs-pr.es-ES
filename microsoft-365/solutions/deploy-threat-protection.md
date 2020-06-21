---
title: Implementar capacidades de protección contra amenazas en Microsoft 365
description: Aprenda a implementar capacidades y servicios de protección contra amenazas en Microsoft 365 E5.
ms.author: bcarter
author: brendacarter
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: e39e69fa7c65d7846cc91b3603c5b6ef96f56752
ms.sourcegitcommit: 92f641cad63379bf16417854a43b16b48a71a30a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2020
ms.locfileid: "44724835"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Implementar capacidades de protección contra amenazas en Microsoft 365

El [malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)y los cyberattacks sofisticados, como las [amenazas no archivadas](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats), son un acontecimiento común. Las empresas necesitan protegerse a sí mismos y a sus clientes. Estos ataques pueden ocasionar problemas importantes para su organización, que van desde una pérdida de confianza a la woes financiera, tiempo de inactividad de la empresa amenazante y mucho más. La protección contra amenazas es importante, pero puede resultar difícil determinar dónde centrarse en el tiempo, el esfuerzo y los recursos de la organización. 

Las soluciones de seguridad de Microsoft están integradas en nuestros productos y servicios. Las funcionalidades de automatización y aprendizaje de máquinas reducen la carga de los equipos de seguridad para asegurarse de que se resuelven los elementos correctos. Y la solidez de las soluciones de seguridad de Microsoft se basa en billones de señales que procesamos todos los días en nuestro [gráfico de seguridad inteligente](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph). Las soluciones de seguridad de Microsoft 365 incluyen la [protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection), una solución que combina señales en el correo electrónico, los datos, los dispositivos y las identidades para pintar una imagen de amenazas avanzadas en su organización.

Vea este vídeo para obtener información general sobre el proceso de implementación.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Use este artículo como guía para implementar la solución de protección contra amenazas.

## <a name="threat-protection-in-microsoft-365-e5"></a>Protección contra amenazas en Microsoft 365 E5

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) le permite proteger a su organización con inteligencia adaptable e integrada. Con las características de protección contra amenazas de Microsoft 365 E5, puede detectar e investigar las amenazas avanzadas, las identidades en peligro y las acciones malintencionadas en los entornos locales y en la nube.

En Microsoft 365 E5, las capacidades de protección contra amenazas están integradas de forma predeterminada. Las señales de cada función agregan fuerza a la capacidad general de detectar y responder a las amenazas. El conjunto combinado de capacidades ofrece la mejor protección para las organizaciones, especialmente las organizaciones multinacionales, en comparación con la ejecución de productos que no son de Microsoft. En la siguiente imagen se muestran los servicios y las capacidades de protección contra amenazas en Microsoft 365 E5 que se describen en este artículo.

![Información general sobre la protección contra amenazas de Microsoft](../media/solutions-architecture-center/deploy-threat-protection-across-m365-overview.png)

En cuanto implemente cualquiera de las funciones de la protección contra amenazas avanzada, puede activar Microsoft Threat Protection, que une las señales y los datos en un solo punto. 

![Ilustración conceptual del panel de protección contra amenazas de Microsoft](../media/solutions-architecture-center/deploy-threat-protection-across-m365-mtp.png)

En la siguiente ilustración se muestra una ruta de acceso recomendada para implementar estas funciones individuales. 

![Señales de protección contra amenazas de M365](../media/solutions-architecture-center/deploy-threat-protection-across-m365.png)

|Solución/capacidades  |Descripción  |
|---------|---------|
|Autenticación multifactor y acceso condicional     |Protéjase contra las identidades y los dispositivos comprometidos. Comience con esta protección porque es fundamental. La configuración recomendada en esta guía incluye Azure AD Identity Protection como requisito previo.     |
|Azure Advanced Threat Protection     |  Una solución de seguridad basada en la nube que aprovecha las señales locales de Active Directory para identificar, detectar e investigar las amenazas avanzadas, las identidades en peligro y las acciones de Insider malintencionadas dirigidas a la organización. Céntrese en este siguiente porque protege su infraestructura local y de nube, no tiene dependencias o requisitos previos y puede proporcionar ventajas inmediatas.       | 
|Protección contra amenazas avanzada de Office 365     | Salvaguarda a su organización frente a amenazas malintencionadas que plantean mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración. Protecciones para malware, suplantación de identidad (phishing), suplantación de identidad y otros tipos de ataques. Esto es recomendable porque el control de cambios, la migración de la configuración del sistema no y otras consideraciones pueden tardar más en implementarse. <br><br>Nota: Asegúrese de configurar también las capacidades de protección contra amenazas incluidas en todas las suscripciones de Office 365 (Exchange Online Protection).       |
|Protección contra amenazas avanzada de Microsoft Defender    | Una plataforma de protección de extremos que ayuda a prevenir, detectar, investigar y responder a amenazas avanzadas. Esto tarda más en implementarse, pero puede realizarse en paralelo con las otras funciones si otros administradores son responsables.   |
|Microsoft Cloud App Security     |   Un agente de seguridad de acceso a la nube para descubrimiento, investigación y gobernanza. Puede habilitar esto anticipadamente para empezar a recopilar datos y obtener información. La implementación de información y otra protección dirigida en todas las aplicaciones SaaS implica la planeación y puede tardar más tiempo.       | 

> [!TIP]
> Las organizaciones con varios equipos de seguridad pueden implementar estas capacidades en paralelo.

## <a name="deploy-your-threat-protection-solution"></a>Implementación de la solución de protección contra amenazas

Para asegurarse de que su organización tiene la mejor protección posible, configure e implemente la solución de seguridad de manera que incluya los siguientes pasos:

1. [Configurar la autenticación multifactor y las directivas de acceso condicional](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Configurar la protección contra amenazas avanzada de Azure](deploy-threat-protection-configure.md#step-2-configure-azure-advanced-threat-protection)
3. [Habilitar la Protección contra amenazas de Microsoft](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-threat-protection)
4. [Configuración de la protección contra amenazas avanzada de Office 365](deploy-threat-protection-configure.md#step-4-configure-office-365-advanced-threat-protection)
5. [Configurar la protección contra amenazas avanzada de Microsoft defender](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-advanced-threat-protection)
6. [Configurar Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Supervisar el estado y realizar acciones](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Entrenar a los usuarios](deploy-threat-protection-configure.md#step-8-train-users)

Las características de protección contra amenazas se pueden configurar en paralelo, por lo que si tiene varios equipos de seguridad responsables de los distintos servicios, pueden configurar las características de protección de la organización al mismo tiempo. El siguiente diagrama ilustra el proceso de alto nivel para la implementación de capacidades de protección contra amenazas. 

![Proceso para implementar capacidades de protección contra amenazas](../media/solutions-architecture-center/deploy-threat-protection-across-m365-grid.png) 


