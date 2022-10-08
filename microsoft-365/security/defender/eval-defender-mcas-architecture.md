---
title: Revise los requisitos de arquitectura y la estructura de Microsoft Defender for Cloud Apps
description: Microsoft Defender for Cloud Apps diagramas técnicos explican la arquitectura en Microsoft 365 Defender, lo que le ayudará a crear un entorno piloto.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: 30e7d46cfc07035b073b39f878a6dc8c11040817
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68048954"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-cloud-apps"></a>Revise los requisitos de arquitectura y los conceptos clave para Microsoft Defender for Cloud Apps


**Se aplica a:**

- Microsoft 365 Defender

Este artículo es el [paso 1 del 3](eval-defender-mcas-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Cloud Apps junto con Microsoft 365 Defender. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-identity-overview.md).

Antes de habilitar Microsoft Defender for Cloud Apps, asegúrese de comprender la arquitectura y de que puede cumplir los requisitos. 

## <a name="understand-the-architecture"></a>Información sobre la arquitectura

Microsoft Defender for Cloud Apps es un agente de seguridad de acceso a la nube (CASB). Los CASB actúan como un portero para brokerar el acceso en tiempo real entre los usuarios empresariales y los recursos en la nube que usan, dondequiera que se encuentren los usuarios e independientemente del dispositivo que usen. Microsoft Defender for Cloud Apps se integra de forma nativa con las funcionalidades de seguridad de Microsoft, incluidos los Microsoft 365 Defender.

Sin Defender for Cloud Apps, las aplicaciones en la nube que usa su organización no se administran y no están protegidas, como se muestra en este artículo.

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-a.png" alt-text="Arquitectura de Microsoft Defender for Cloud Apps" lightbox="../../media/defender/m365-defender-mcas-architecture-a.png":::

En la ilustración:
- El uso de aplicaciones en la nube por parte de una organización no está supervisado y no protegido. 
- Este uso queda fuera de las protecciones logradas dentro de una organización administrada. 

#### <a name="discovering-cloud-apps"></a>Detección de aplicaciones en la nube

El primer paso para administrar el uso de aplicaciones en la nube es detectar qué aplicaciones en la nube usa la organización. En este diagrama siguiente se muestra cómo funciona la detección de nube con Defender for Cloud Apps.

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-b.png" alt-text="Arquitectura de Microsoft Defender for Cloud Apps en Cloud Discovery" lightbox="../../media/defender/m365-defender-mcas-architecture-b.png":::


En esta ilustración, hay dos métodos que se pueden usar para supervisar el tráfico de red y detectar aplicaciones en la nube que usa la organización.
- A. Cloud App Discovery se integra con Microsoft Defender para punto de conexión de forma nativa. Defender for Endpoint informa de que se accede a las aplicaciones y servicios en la nube desde dispositivos de Windows 10 y Windows 11 administrados por TI. 
- B. Para la cobertura en todos los dispositivos conectados a una red, el recopilador de registros de Defender for Cloud Apps se instala en firewalls y otros servidores proxy para recopilar datos de puntos de conexión. Estos datos se envían a Defender for Cloud Apps para su análisis.

#### <a name="managing-cloud-apps"></a>Administración de aplicaciones en la nube

Después de detectar aplicaciones en la nube y analizar cómo la organización usa estas aplicaciones, puede empezar a administrar las aplicaciones en la nube que elija. 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-c.png" alt-text="La arquitectura de Microsoft Defender for Cloud Apps mientras se administran las aplicaciones en la nube" lightbox="../../media/defender/m365-defender-mcas-architecture-c.png":::

En esta ilustración:
- Algunas aplicaciones están autorizadas para su uso. Esta sanción es una forma sencilla de empezar a administrar aplicaciones.
- Puede habilitar una mayor visibilidad y control mediante la conexión de aplicaciones con conectores de aplicaciones. Los conectores de aplicaciones usan las API de los proveedores de aplicaciones.


#### <a name="applying-session-controls-to-cloud-apps"></a>Aplicación de controles de sesión a aplicaciones en la nube

Microsoft Defender for Cloud Apps actúa como proxy inverso, lo que proporciona acceso proxy a las aplicaciones en la nube autorizadas. Esta aprovisionamiento permite que Defender for Cloud Apps aplique los controles de sesión que configure. 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-d.png" alt-text="Arquitectura de Microsoft Defender for Cloud Apps: control de sesión de acceso de proxy" lightbox="../../media/defender/m365-defender-mcas-architecture-d.png":::

En esta ilustración:
- El acceso a las aplicaciones en la nube autorizadas desde usuarios y dispositivos de su organización se enruta a través de Defender for Cloud Apps.
- Este acceso de proxy permite aplicar controles de sesión.
- Las aplicaciones en la nube que no haya autorizado o no autorizado explícitamente no se verán afectadas.

Los controles de sesión le permiten aplicar parámetros a la forma en que su organización usa las aplicaciones en la nube. Por ejemplo, si su organización usa Salesforce, puede configurar una directiva de sesión que permita que solo los dispositivos administrados accedan a los datos de su organización en Salesforce. Un ejemplo más sencillo podría ser configurar una directiva para supervisar el tráfico desde dispositivos no administrados, de modo que pueda analizar el riesgo de este tráfico antes de aplicar directivas más estrictas.

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a>Integración con Azure AD con el control de aplicaciones de acceso condicional

Es posible que ya haya agregado aplicaciones SaaS al inquilino de Azure AD para aplicar la autenticación multifactor y otras directivas de acceso condicional. Microsoft Defender for Cloud Apps se integra de forma nativa con Azure AD. Todo lo que tiene que hacer es configurar una directiva en Azure AD para usar el control de aplicaciones de acceso condicional en Defender for Cloud Apps. Esto enruta el tráfico de red de estas aplicaciones SaaS administradas a través de Defender for Cloud Apps como proxy, lo que permite a Defender for Cloud Apps supervisar este tráfico y aplicar controles de sesión. 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-e.png" alt-text="Arquitectura de la Microsoft Defender for Cloud Apps: aplicaciones SaaS" lightbox="../../media/defender/m365-defender-mcas-architecture-e.png":::

En esta ilustración:
- Las aplicaciones SaaS se integran con el inquilino de Azure AD. Esta integración permite a Azure AD aplicar directivas de acceso condicional, incluida la autenticación multifactor.
- Se agrega una directiva a Azure Active Directory para dirigir el tráfico de las aplicaciones SaaS a Defender for Cloud Apps. La directiva especifica a qué aplicaciones SaaS aplicar esta directiva. Por lo tanto, después de que Azure AD aplique las directivas de acceso condicional que se aplican a estas aplicaciones SaaS, Azure AD dirige (proxies) el tráfico de sesión a través de Defender for Cloud Apps.
- Defender for Cloud Apps supervisa este tráfico y aplica las directivas de control de sesión configuradas por los administradores. 

Es posible que haya detectado y autorizado aplicaciones en la nube mediante Defender for Cloud Apps que no se han agregado a Azure AD. Puede aprovechar el control de aplicaciones de acceso condicional agregando estas aplicaciones en la nube al inquilino de Azure AD y el ámbito de las reglas de acceso condicional.

#### <a name="protecting-your-organization-from-hackers"></a>Protección de la organización frente a hackers

Defender for Cloud Apps proporciona una protección eficaz por sí sola. Sin embargo, cuando se combina con otras funcionalidades de Microsoft 365 Defender, Defender for Cloud Apps proporciona datos en las señales compartidas que (juntos) ayudan a detener los ataques.

Merece la pena repetir esta ilustración de la introducción a esta Microsoft 365 Defender guía piloto y evaluación. 

:::image type="content" source="../../media/defender/m365-defender-eval-threat-chain.png" alt-text="Cómo Microsoft 365 Defender detiene una cadena de amenazas" lightbox="../../media/defender/m365-defender-eval-threat-chain.png":::

Centrándose en el lado derecho de esta ilustración, Microsoft Defender for Cloud Apps observa un comportamiento anómalo, como el viaje imposible, el acceso a credenciales y la descarga inusual, el recurso compartido de archivos o la actividad de reenvío de correo, y notifica estos comportamientos al equipo de seguridad. Por lo tanto, Defender for Cloud Apps ayuda a evitar el movimiento lateral de los hackers y la filtración de datos confidenciales. Microsoft 356 Defender for Cloud correlaciona las señales de todos los componentes para proporcionar la historia completa de ataques.

## <a name="understand-key-concepts"></a>Descripción de los conceptos clave

En la tabla siguiente se identificaron conceptos clave que son importantes comprender al evaluar, configurar e implementar Microsoft Defender for Cloud Apps.


|Concepto  |Descripción |Más información  |
|---------|---------|---------|
| Panel de Defender for Cloud Apps | Presenta una introducción a la información más importante sobre su organización y proporciona vínculos a una investigación más profunda.        | [Trabajar con el panel ](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| Control de aplicaciones de acceso condicional    | Arquitectura de proxy inverso que se integra con el proveedor de identidades (IdP) para proporcionar directivas de acceso condicional de Azure AD y aplicar controles de sesión de forma selectiva.        |  [Protección de aplicaciones con Microsoft Defender for Cloud Apps control de aplicaciones de acceso condicional](/cloud-app-security/proxy-intro-aad)       |
|  Catálogo de aplicaciones en la nube   | El Catálogo de aplicaciones en la nube le ofrece una imagen completa en el catálogo de Microsoft de más de 16 000 aplicaciones en la nube que se clasifican y puntúan en función de más de 80 factores de riesgo.    |  [Trabajar con puntuaciones de riesgo de aplicaciones](/cloud-app-security/risk-score)       |
| Panel de Cloud Discovery    | Cloud Discovery analiza los registros de tráfico y está diseñado para proporcionar más información sobre cómo se usan las aplicaciones en la nube en su organización, así como para proporcionar alertas y niveles de riesgo.     |  [Trabajar con aplicaciones detectadas   ](/cloud-app-security/discovered-apps)    |
|Aplicaciones conectadas |Defender for Cloud Apps proporciona protección de un extremo a otro para las aplicaciones conectadas mediante la integración de nube a nube, conectores de API y controles de acceso y sesión en tiempo real mediante nuestros controles de acceso condicional a aplicaciones. |[Protección de aplicaciones conectadas](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a>Revisión de los requisitos de arquitectura

### <a name="discovering-cloud-apps"></a>Detección de aplicaciones en la nube

Para detectar las aplicaciones en la nube que se usan en su entorno, puede implementar uno o ambos de los métodos siguientes:

- Empiece a trabajar rápidamente con Cloud Discovery mediante la integración con Microsoft Defender para punto de conexión. Esta integración nativa le permite empezar inmediatamente a recopilar datos sobre el tráfico en la nube en los dispositivos Windows 11 y Windows 10, dentro y fuera de la red.
- Para detectar todas las aplicaciones en la nube a las que acceden todos los dispositivos conectados a la red, implemente el recopilador de registros de Defender for Cloud Apps en los firewalls y otros servidores proxy. Esta implementación ayuda a recopilar datos de los puntos de conexión y los envía a Defender for Cloud Apps para su análisis. Defender for Cloud Apps se integra de forma nativa con algunos servidores proxy de terceros para obtener aún más funcionalidades.

Estas opciones se incluyen en [el paso 2. Habilite el entorno de evaluación](eval-defender-mcas-enable-eval.md). 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a>Aplicación de directivas de acceso condicional de Azure AD a aplicaciones en la nube

El control de aplicaciones de acceso condicional (la capacidad de aplicar directivas de acceso condicional a aplicaciones en la nube) requiere la integración con Azure AD. Esta integración no es un requisito para empezar a trabajar con Defender for Cloud Apps. Es un paso que le animamos a probar durante la fase piloto: [paso 3. Microsoft Defender for Cloud Apps piloto](eval-defender-mcas-pilot.md).

## <a name="siem-integration"></a>Integración de SIEM

Puede integrar Microsoft Defender for Cloud Apps con el servidor SIEM genérico o con Microsoft Sentinel para habilitar la supervisión centralizada de alertas y actividades desde aplicaciones conectadas. 

Además, Microsoft Sentinel incluye un conector de Microsoft Defender for Cloud Apps para proporcionar una integración más profunda con Microsoft Sentinel. Esta disposición le permite no solo obtener visibilidad sobre las aplicaciones en la nube, sino también obtener análisis sofisticados para identificar y combatir las ciberamenazas y controlar cómo viajan los datos.

- [Integración de SIEM genérica](/cloud-app-security/siem)
- [Transmisión de alertas y registros de Cloud Discovery desde Defender for Cloud Apps a Microsoft Sentinel](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a>Pasos siguientes

Paso 2 de 3: [Habilitar el entorno de evaluación para Microsoft Defender for Cloud Apps](eval-defender-mcas-enable-eval.md)

Vuelva a la introducción para [Evaluar Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
