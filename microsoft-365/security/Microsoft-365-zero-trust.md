---
title: Plan de implementación de Confianza cero de Microsoft 365
f1.keywords:
- deploy zero trust
- zero trust strategy
ms.author: bcarter
author: brendacarter
manager: dansimp
audience: Admin
description: Obtenga información sobre cómo implementar la Microsoft 365 de confianza cero en su entorno para defenderse de las amenazas y proteger los datos confidenciales.
ms.topic: tutorial
ms.prod: m365-security
ms.technology: m365d
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- m365solution-zerotrust
- m365solution-overview
- M365-security-compliance
ms.openlocfilehash: f8ffdcb817763589dfb43f7389bc44b7a28459f2
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473065"
---
# <a name="microsoft-365-zero-trust-deployment-plan"></a>Plan de implementación de Confianza cero de Microsoft 365

En este artículo se proporciona un plan de implementación para crear la seguridad **de** confianza cero con Microsoft 365. Confianza cero es un nuevo modelo de seguridad que supone una infracción y comprueba cada solicitud como si se originase desde una red sin control. Independientemente de dónde se origine la solicitud o a qué recurso tiene acceso, el modelo de confianza cero nos enseña a "nunca confiar, comprobar siempre".


## <a name="zero-trust-security-architecture"></a>Arquitectura de seguridad de confianza cero

Un enfoque de confianza cero se extiende por toda la propiedad digital y sirve como una filosofía de seguridad integrada y una estrategia integral. 

En esta ilustración se proporciona una representación de los elementos principales que contribuyen a la confianza cero.

:::image type="content" source="../media/zero-trust/zero-trust-architecture.png" alt-text="La arquitectura de seguridad de confianza cero" lightbox="../media/zero-trust/zero-trust-architecture.png":::

En la ilustración:
- La aplicación de directivas de seguridad está en el centro de una arquitectura de confianza cero. Esto incluye la autenticación multifactor con acceso condicional que tiene en cuenta el riesgo de la cuenta de usuario, el estado del dispositivo y otros criterios y directivas que establezcas.
- Las identidades, los dispositivos, los datos, las aplicaciones, la red y otros componentes de infraestructura están configurados con la seguridad adecuada. Las directivas configuradas para cada uno de estos componentes se coordinan con la estrategia de confianza cero general. Por ejemplo, las directivas de dispositivos determinan los criterios para dispositivos en buen estado y las directivas de acceso condicional requieren dispositivos en buen estado para tener acceso a datos y aplicaciones específicas.
- La protección contra amenazas y la inteligencia supervisan el entorno, detectan los riesgos actuales y realiza acciones automatizadas para corregir los ataques.

<!---
For more information about this architecture, including deployment objectives for your entire digital estate, see [Zero Trust Rapid Modernization Plan (RaMP)](https://review.docs.microsoft.com/security/zero-trust/zero-trust-ramp-overview?branch=zt-content-prototype). 
-->

Para obtener más información acerca de La confianza cero, consulte Centro de orientación [_**de confianza cero de**_](/security/zero-trust) Microsoft.

## <a name="deploying-zero-trust-for-microsoft-365"></a>Implementación de la confianza cero para Microsoft 365

Microsoft 365 se crea de forma intencionada con muchas capacidades de seguridad y protección de la información para ayudarle a crear confianza cero en su entorno. Muchas de las funcionalidades se pueden ampliar para proteger el acceso a otras aplicaciones SaaS que usa su organización y los datos de estas aplicaciones.

Esta ilustración representa el trabajo de implementación de capacidades de confianza cero. Este trabajo se divide en unidades de trabajo que se pueden configurar juntas, empezando desde la parte inferior y trabajando hasta la parte superior para garantizar que el trabajo previo se haya completado.


:::image type="content" source="../media/zero-trust/m365-zero-trust-deployment-stack.png" alt-text="La Microsoft 365 de implementación de confianza cero" lightbox="../media/zero-trust/m365-zero-trust-deployment-stack.png":::

En esta ilustración:
- La confianza cero comienza con una base de identidad y protección de dispositivos. 
- Las capacidades de protección contra amenazas se basan en esta base para proporcionar supervisión y corrección en tiempo real de las amenazas de seguridad. 
- La protección de la información y el gobierno proporcionan controles sofisticados dirigidos a tipos específicos de datos para proteger la información más valiosa y para ayudarle a cumplir con los estándares de cumplimiento, incluida la protección de la información personal.

## <a name="step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies"></a>Paso 1. Configurar la identidad de confianza cero y la protección de acceso a dispositivos: directivas de punto de inicio

El primer paso es crear la base de confianza cero mediante la configuración de la identidad y la protección de acceso a dispositivos. 


:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-1b.png" alt-text="El proceso para configurar la identidad de confianza cero y la protección de acceso a dispositivos" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-1b.png":::



Ve a [**_Identidad de confianza cero y protección de acceso a dispositivos_**](office-365-security/microsoft-365-policies-configurations.md) para obtener instrucciones prescriptivas para lograrlo. Esta serie de artículos describe un conjunto de configuraciones de requisitos previos de acceso a dispositivos y identidades y un conjunto de Azure Active Directory (Azure AD), acceso condicional, Microsoft Intune y otras directivas para proteger el acceso a Microsoft 365  para servicios y aplicaciones de nube empresariales, otros servicios SaaS y aplicaciones locales publicadas con Azure AD proxy de aplicación.



|Incluye  |Requisitos previos  |No incluye  |
|---------|---------|---------|
|Directivas de identidad y acceso a dispositivos recomendadas para tres niveles de protección:<br>- Punto de partida<br>- Enterprise (recomendado)<br>- Specialized<br><br>Recomendaciones adicionales para:<br>- Usuarios externos (invitados)<br>- Microsoft Teams<br>- SharePoint Online<br>- Microsoft Defender para aplicaciones en la nube| Microsoft E3 o E5<br><br>Azure Active Directory en cualquiera de estos modos:<br>- Solo nube<br>- Híbrido con autenticación de sincronización de hash de contraseña (PHS)<br>- Híbrido con autenticación de paso a través (PTA)<br>- Federado     |Inscripción de dispositivos para directivas que requieren dispositivos administrados. Consulta "Administrar puntos de conexión con Intune" para inscribir dispositivos |
| | | |

Comience implementando el nivel de punto inicial. Estas directivas no requieren la inscripción de dispositivos en la administración. 


:::image type="content" source="../media/zero-trust/identity-access-starting-point-tier.png" alt-text="Las directivas de identidad de confianza cero y acceso a dispositivos: nivel de punto inicial" lightbox="../media/zero-trust/identity-access-starting-point-tier.png":::


## <a name="step-2-manage-endpoints-with-intune"></a>Paso 2. Administrar puntos de conexión con Intune

A continuación, inscriba sus dispositivos en la administración y comience a protegerlos con controles más sofisticados. 

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-2.png" alt-text="El elemento Administrar puntos de conexión con Intune" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-2.png":::


Ve a [**_Administrar dispositivos con Intune_**](../solutions/manage-devices-with-intune-overview.md) para obtener instrucciones prescriptivas para lograrlo. 


|Incluye  |Requisitos previos  |No incluye  |
|---------|---------|---------|
|Inscribir dispositivos con Intune<br>- Dispositivos de propiedad corporativa<br>- Autopilot/automated<br>- inscripción<br><br>Configurar directivas<br>- Directivas de Protección de aplicaciones<br>- Directivas de cumplimiento<br>- Directivas de perfil de dispositivo | Registrar puntos de conexión con Azure AD     | Configuración de capacidades de protección de la información, como:<br>- Tipos de información confidencial<br>- Etiquetas<br>- Directivas DLP<br>Para obtener estas funcionalidades, consulte Step 5. Proteger y gobernar datos (más adelante en este artículo).       |
|    |         |         |

## <a name="step-3-add-zero-trust-identity-and-device-access-protection--enterprise-policies"></a>Paso 3. Agregar identidad de confianza cero y protección de acceso a dispositivos: Enterprise directivas

Con los dispositivos inscritos en la administración, ahora puedes implementar el conjunto completo de directivas recomendadas de identidad de confianza cero y acceso a dispositivos, que requieren dispositivos compatibles.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png" alt-text="Las directivas de identidad y acceso de confianza cero con la administración de dispositivos" lightbox="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png":::

Vuelva a [**_Identidad común y directivas de acceso a_**](office-365-security/identity-access-policies.md) dispositivos y agregue las directivas en el Enterprise dispositivo.  

:::image type="content" source="../media/zero-trust/identity-access-enterprise-tier.png" alt-text="Las directivas de acceso y identidad de confianza cero Enterprise nivel (recomendado)" lightbox="../media/zero-trust/identity-access-enterprise-tier.png":::

## <a name="step-4-evaluate-pilot-and-deploy-microsoft-365-defender"></a>Paso 4. Evaluar, piloto e implementar Microsoft 365 Defender

Microsoft 365 Defender es una solución de detección y respuesta extendida (XDR) que recopila, correlaciona y analiza automáticamente datos de señales, amenazas y alertas de todo el entorno de Microsoft 365, incluidos puntos de conexión, correo electrónico, aplicaciones e identidades.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-defender.png" alt-text="El proceso de agregar Microsoft 365 Defender a la arquitectura de confianza cero" lightbox="../media/zero-trust/m365-zero-trust-architecture-defender.png":::

Vaya a [**_Evaluar y prueba piloto Microsoft 365 Defender_**](defender/eval-overview.md) una guía metódico para pilotar e implementar Microsoft 365 Defender componentes. 

|Incluye  |Requisitos previos  |No incluye  |
|---------|---------|---------|
| Configurar el entorno piloto y de evaluación para todos los componentes:<br>- Defender for Identity<br>- Defender para Office 365<br>- Defender for Endpoint<br>- Microsoft Defender para aplicaciones en la nube<br><br>Protección contra amenazas<br><br> Investigar y responder a amenazas   | Vea las instrucciones para leer acerca de los requisitos de arquitectura para cada componente de Microsoft 365 Defender.        | Azure AD identity protection no se incluye en esta guía de soluciones. Se incluye en step 1: Configure Zero Trust identity and device access protection.        |
|    |         |         |

## <a name="step-5-protect-and-govern-sensitive-data"></a>Paso 5. Proteger y gobernar datos confidenciales

Implemente Microsoft Information Protection (MIP) para descubrir, clasificar y proteger la información confidencial donde esta resida o hacia donde se transfiera.

Las características de MIP se incluyen con el Centro de cumplimiento de Microsoft 365 y proporcionan las herramientas necesarias para conocer, proteger y evitar la pérdida de sus datos.


:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-info-protect.png" alt-text="Las capacidades de protección de la información que protegen los datos mediante la aplicación de directivas" lightbox="../media/zero-trust/m365-zero-trust-architecture-info-protect.png":::

Aunque este trabajo se representa en la parte superior de la pila de implementación ilustrada anteriormente en este artículo, puede comenzar este trabajo en cualquier momento. 

Microsoft Information Protection proporciona un marco, un proceso y capacidades que puede usar para lograr sus objetivos empresariales específicos.

:::image type="content" source="../media/zero-trust/mip-solution-overview.png" alt-text="Marco Microsoft Information Protection (MIP)" lightbox="../media/zero-trust/mip-solution-overview.png":::


Para obtener más información sobre cómo planear e implementar la protección de la información, vea [**_Deploy a Microsoft Information Protection solution_**](../compliance/information-protection-solution.md). 

Si va a implementar la protección de la información para las normativas de privacidad de datos, esta guía de soluciones proporciona un marco recomendado para todo el proceso: Implementar la protección de la información para las normativas de privacidad de [**_datos con Microsoft 365_**](../solutions/information-protection-deploy.md).