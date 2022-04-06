---
title: Revisar los requisitos de arquitectura y la estructura de Microsoft Defender para aplicaciones en la nube
description: Los diagramas técnicos de Microsoft Defender para Aplicaciones en la nube explican la arquitectura de Microsoft 365 Defender, lo que le ayudará a crear un entorno piloto.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6547c1b269ede9385b384ca18fe6f2ca34d35109
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500329"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-cloud-apps"></a>Revisar los requisitos de arquitectura y los conceptos clave para Microsoft Defender para aplicaciones en la nube


**Se aplica a:**

- Microsoft 365 Defender

Este artículo es [el paso 1 de 3](eval-defender-mcas-overview.md) en el proceso de configuración del entorno de evaluación de Microsoft Defender para aplicaciones en la nube junto con Microsoft 365 Defender. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-identity-overview.md).

Antes de habilitar Microsoft Defender para aplicaciones en la nube, asegúrese de comprender la arquitectura y de cumplir los requisitos. 

## <a name="understand-the-architecture"></a>Información sobre la arquitectura

Microsoft Defender para Aplicaciones en la nube es un agente de seguridad de acceso a la nube (CASB). Las CASB actúan como un guardián para el acceso de agente en tiempo real entre los usuarios de la empresa y los recursos en la nube que usan, independientemente del dispositivo que estén usando. Microsoft Defender para Aplicaciones en la nube se integra de forma nativa con las capacidades de seguridad de Microsoft, incluidas Microsoft 365 Defender.

Sin Defender para aplicaciones en la nube, las aplicaciones en la nube que usa la organización no están administradas y no están protegidas, como se muestra.

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-a.png" alt-text="La arquitectura de Microsoft Defender para aplicaciones en la nube" lightbox="../../media/defender/m365-defender-mcas-architecture-a.png":::

En la ilustración:
- El uso de aplicaciones en la nube por parte de una organización no se supervisa y no está protegido. 
- Este uso está fuera de las protecciones logradas dentro de una organización administrada. 

#### <a name="discovering-cloud-apps"></a>Descubriendo aplicaciones en la nube

El primer paso para administrar el uso de aplicaciones en la nube es descubrir qué aplicaciones en la nube usan su organización. En este diagrama siguiente se muestra cómo funciona la detección en la nube con Defender para aplicaciones en la nube.

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-b.png" alt-text="La arquitectura de Microsoft Defender para aplicaciones en la nube en la detección en la nube" lightbox="../../media/defender/m365-defender-mcas-architecture-b.png":::


En esta ilustración, hay dos métodos que se pueden usar para supervisar el tráfico de red y detectar las aplicaciones en la nube que está utilizando la organización.
- A. Cloud App Discovery se integra con Microsoft Defender para Endpoint de forma nativa. Defender for Endpoint informa de los servicios y aplicaciones en la nube a los que se accede desde dispositivos administrados por TI Windows 10 y Windows 11 dispositivos. 
- B. Para la cobertura en todos los dispositivos conectados a una red, el recopilador de registros defender para aplicaciones en la nube se instala en firewalls y otros servidores proxy para recopilar datos de puntos de conexión. Estos datos se envían a Defender for Cloud Apps para su análisis.

#### <a name="managing-cloud-apps"></a>Administración de aplicaciones en la nube

Después de descubrir aplicaciones en la nube y analizar cómo la organización usa estas aplicaciones, puedes empezar a administrar las aplicaciones en la nube que elijas. 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-c.png" alt-text="La arquitectura de Microsoft Defender para aplicaciones en la nube mientras se administran las aplicaciones en la nube" lightbox="../../media/defender/m365-defender-mcas-architecture-c.png":::

En esta ilustración:
- Algunas aplicaciones se sancionan por su uso. Esta sanción es una forma sencilla de empezar a administrar aplicaciones.
- Puedes habilitar una mayor visibilidad y control conectando aplicaciones con conectores de aplicaciones. Los conectores de aplicaciones usan las API de los proveedores de aplicaciones.


#### <a name="applying-session-controls-to-cloud-apps"></a>Aplicación de controles de sesión a aplicaciones en la nube

Microsoft Defender para aplicaciones en la nube sirve como proxy inverso, lo que proporciona acceso de proxy a aplicaciones en la nube sancionadas. Esta disposición permite a Defender for Cloud Apps aplicar controles de sesión que configures. 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-d.png" alt-text="La arquitectura de Microsoft Defender para aplicaciones en la nube: control de sesión de acceso de proxy" lightbox="../../media/defender/m365-defender-mcas-architecture-d.png":::

En esta ilustración:
- El acceso a las aplicaciones en la nube sancionadas de los usuarios y dispositivos de su organización se enruta a través de Defender para aplicaciones en la nube.
- Este acceso proxy permite aplicar controles de sesión.
- Las aplicaciones en la nube que no has sancionado o no autorizado explícitamente no se ven afectadas.

Los controles de sesión te permiten aplicar parámetros a la forma en que tu organización usa las aplicaciones en la nube. Por ejemplo, si su organización usa Salesforce, puede configurar una directiva de sesión que solo permita que los dispositivos administrados obtengan acceso a los datos de su organización en Salesforce. Un ejemplo más sencillo podría ser configurar una directiva para supervisar el tráfico desde dispositivos no administrados para que pueda analizar el riesgo de este tráfico antes de aplicar directivas más estrictas.

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a>Integración con Azure AD con control de aplicaciones de acceso condicional

Es posible que ya tenga aplicaciones SaaS agregadas a su inquilino de Azure AD para aplicar la autenticación multifactor y otras directivas de acceso condicional. Microsoft Defender para Aplicaciones en la nube se integra de forma nativa con Azure AD. Todo lo que tienes que hacer es configurar una directiva en Azure AD usar el control de aplicaciones de acceso condicional en Defender para aplicaciones en la nube. Esto enruta el tráfico de red de estas aplicaciones SaaS administradas a través de Defender para aplicaciones en la nube como proxy, lo que permite a Defender para Aplicaciones en la nube supervisar este tráfico y aplicar controles de sesión. 

:::image type="content" source="../../media/defender/m365-defender-mcas-architecture-e.png" alt-text="La arquitectura de Microsoft Defender para aplicaciones en la nube: aplicaciones SaaS" lightbox="../../media/defender/m365-defender-mcas-architecture-e.png":::

En esta ilustración:
- Las aplicaciones SaaS se integran con Azure AD inquilino. Esta integración permite Azure AD directivas de acceso condicional, incluida la autenticación multifactor.
- Se agrega una directiva a Azure Active Directory para dirigir el tráfico de aplicaciones SaaS a Defender para aplicaciones en la nube. La directiva especifica a qué aplicaciones SaaS aplicar esta directiva. Por lo tanto, Azure AD aplica cualquier directiva de acceso condicional que se aplique a estas aplicaciones SaaS, Azure AD dirigirá (servidores proxy) el tráfico de sesión a través de Defender para Aplicaciones en la nube.
- Defender para aplicaciones en la nube supervisa este tráfico y aplica las directivas de control de sesión configuradas por los administradores. 

Es posible que haya detectado y sancionado aplicaciones en la nube con Defender para aplicaciones en la nube que no se hayan agregado a Azure AD. Puedes aprovechar el control de aplicaciones de acceso condicional agregando estas aplicaciones en la nube a tu Azure AD inquilino y el ámbito de las reglas de acceso condicional.

#### <a name="protecting-your-organization-from-hackers"></a>Proteger su organización de los hackers

Defender para aplicaciones en la nube proporciona una protección eficaz por sí solo. Sin embargo, cuando se combina con las otras funcionalidades de Microsoft 365 Defender, Defender para Aplicaciones en la nube proporciona datos en las señales compartidas que (juntas) ayudan a detener los ataques.

Vale la pena repetir esta ilustración de la introducción a esta Microsoft 365 Defender evaluación y guía piloto. 

:::image type="content" source="../../media/defender/m365-defender-eval-threat-chain.png" alt-text="Cómo Microsoft 365 Defender una cadena de amenazas" lightbox="../../media/defender/m365-defender-eval-threat-chain.png":::

Centrándose en el lado derecho de esta ilustración, Microsoft Defender para Aplicaciones en la nube observa comportamientos anómalos como viajes imposibles, acceso a credenciales y una descarga inusual, recurso compartido de archivos o actividad de reenvío de correo e informa de estos comportamientos al equipo de seguridad. Por lo tanto, Defender para aplicaciones en la nube ayuda a evitar el movimiento lateral de los hackers y la filtración de datos confidenciales. Microsoft 356 Defender para la nube correlaciona las señales de todos los componentes para proporcionar la historia de ataque completa.

## <a name="understand-key-concepts"></a>Comprender conceptos clave

En la siguiente tabla se identificaron conceptos clave que son importantes para comprender al evaluar, configurar e implementar Microsoft Defender para aplicaciones en la nube.


|Concepto  |Descripción |Más información  |
|---------|---------|---------|
| Panel de defender para aplicaciones en la nube | Presenta una introducción a la información más importante sobre su organización y proporciona vínculos a una investigación más profunda.        | [Trabajar con el panel ](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| Control de aplicaciones de acceso condicional    | Arquitectura de proxy inverso que se integra con el proveedor de identidades (IdP) para proporcionar Azure AD de acceso condicional y aplicar controles de sesión de forma selectiva.        |  [Proteger aplicaciones con El control de aplicaciones de acceso condicional de Microsoft Defender para aplicaciones en la nube](/cloud-app-security/proxy-intro-aad)       |
|  Catálogo de aplicaciones en la nube   | El Catálogo de aplicaciones en la nube te ofrece una imagen completa del catálogo de Microsoft de más de 16 000 aplicaciones en la nube clasificadas y puntuadas en función de más de 80 factores de riesgo.    |  [Trabajar con puntuaciones de riesgo de la aplicación](/cloud-app-security/risk-score)       |
| Panel de detección de nube    | Cloud Discovery analiza los registros de tráfico y está diseñado para ofrecer más información sobre cómo se usan las aplicaciones en la nube en su organización, así como para proporcionar alertas y niveles de riesgo.     |  [Trabajar con aplicaciones detectadas   ](/cloud-app-security/discovered-apps)    |
|Aplicaciones conectadas |Defender para aplicaciones en la nube proporciona protección de extremo a extremo para las aplicaciones conectadas que usan integración de nube a nube, conectores de API y controles de acceso y sesión en tiempo real mediante nuestros controles de acceso a aplicaciones condicionales. |[Protección de aplicaciones conectadas](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a>Revisión de los requisitos de arquitectura

### <a name="discovering-cloud-apps"></a>Descubriendo aplicaciones en la nube

Para detectar las aplicaciones en la nube que se usan en el entorno, puedes implementar uno o ambos de los siguientes métodos:

- Para empezar a trabajar rápidamente con Cloud Discovery, integre con Microsoft Defender para Endpoint. Esta integración nativa le permite empezar inmediatamente a recopilar datos sobre el tráfico en la nube en Windows 11 y Windows 10 dispositivos, tanto en la red como fuera de la red.
- Para descubrir todas las aplicaciones en la nube a las que acceden todos los dispositivos conectados a la red, implemente el recopilador de registros defender para aplicaciones en la nube en los firewalls y otros servidores proxy. Esta implementación ayuda a recopilar datos de los puntos de conexión y los envía a Defender for Cloud Apps para su análisis. Defender for Cloud Apps se integra de forma nativa con algunos servidores proxy de terceros para obtener aún más funcionalidades.

Estas opciones se incluyen en [el paso 2. Habilitar el entorno de evaluación](eval-defender-mcas-enable-eval.md). 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a>Aplicación de Azure AD de acceso condicional a aplicaciones en la nube

El control de aplicaciones de acceso condicional (la capacidad de aplicar directivas de acceso condicional a aplicaciones en la nube) requiere la integración con Azure AD. Esta integración no es un requisito para empezar a trabajar con Defender para aplicaciones en la nube. Es un paso que le animamos a probar durante la fase piloto: [paso 3. Piloto de Microsoft Defender para aplicaciones en la nube](eval-defender-mcas-pilot.md).

## <a name="siem-integration"></a>Integración de SIEM

Puedes integrar Microsoft Defender para aplicaciones en la nube con el servidor SIEM genérico o con Microsoft Sentinel para habilitar la supervisión centralizada de alertas y actividades de aplicaciones conectadas. 

Además, Microsoft Sentinel incluye un conector de Microsoft Defender para aplicaciones en la nube para proporcionar una integración más profunda con Microsoft Sentinel. Esta disposición le permite no solo obtener visibilidad de las aplicaciones en la nube, sino también obtener análisis sofisticados para identificar y combatir las ciberamenazas y controlar cómo viajan los datos.

- [Integración de SIEM genérica](/cloud-app-security/siem)
- [Transmitir alertas y registros de detección en la nube desde Defender para aplicaciones en la nube en Microsoft Sentinel](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a>Pasos siguientes

Paso 2 de 3: [Habilitar el entorno de evaluación para Microsoft Defender para aplicaciones en la nube](eval-defender-mcas-enable-eval.md)

Vuelva a la introducción a [Evaluar Microsoft Defender para aplicaciones en la nube](eval-defender-mcas-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)
