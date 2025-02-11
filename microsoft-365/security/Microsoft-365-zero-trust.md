---
title: Confianza cero plan de implementación con Microsoft 365
f1.keywords:
- deploy zero trust
- zero trust strategy
ms.author: bcarter
author: brendacarter
manager: dansimp
audience: Admin
description: Aprenda a aplicar Confianza cero principios de seguridad con Microsoft 365 para defenderse de amenazas y proteger la información confidencial.
ms.topic: tutorial
ms.service: microsoft-365-security
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- m365solution-zerotrust
- m365solution-overview
- m365-security
- zerotrust-solution
- highpri
- tier1
ms.openlocfilehash: de227a1f4524770709e1a25345cfbdb697076c8d
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68815603"
---
# <a name="zero-trust-deployment-plan-with-microsoft-365"></a>Confianza cero plan de implementación con Microsoft 365

En este artículo se proporciona un plan de implementación para crear **Confianza cero** seguridad con Microsoft 365. Confianza cero es un nuevo modelo de seguridad que supone una infracción y comprueba cada solicitud como si se originase en una red no controlada. Independientemente de dónde se origine la solicitud o del recurso al que acceda, el modelo de Confianza cero nos enseña a "no confiar nunca, comprobar siempre".

Use este artículo junto con este póster.

| Elemento | Descripción |
|:-----|:-----|
|[![Ilustración del plan de implementación de Microsoft 365 Confianza cero.](../media/solutions-architecture-center/m365-zero-trust-deployment-plan-thumb.png) ](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.pdf) <br/> [PDF](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.pdf) \| [Visio](https://download.microsoft.com/download/f/d/b/fdb6ab0c-34bb-4cb8-84e6-5de8f13298da/m365-zero-trust-deployment-plan.vsdx) <br/> Actualizado en marzo de 2022 | **Guías de soluciones relacionadas** <br/> <ul><li>[Implementación de la infraestructura de identidad para Microsoft 365](/microsoft-365/enterprise/deploy-identity-solution-overview)</li><li>[Configuraciones recomendadas de acceso a dispositivos e identidades](../security/office-365-security/microsoft-365-policies-configurations.md)</li><li>[Administrar dispositivos con Intune](../solutions/manage-devices-with-intune-overview.md)</li><li>[Evaluar Microsoft 365 Defender y realizar una prueba piloto](../security/defender/eval-overview.md)</li><li>[Implementación de una solución de protección de la información con Microsoft Purview](../compliance/information-protection-solution.md)</li><li>[Implementación de la protección de la información para las regulaciones de privacidad de datos con Microsoft 365](../solutions/information-protection-deploy.md)</li></ul>

## <a name="zero-trust-security-architecture"></a>arquitectura de seguridad de Confianza cero

Un enfoque de Confianza cero se extiende por todo el patrimonio digital y actúa como una filosofía de seguridad integrada y una estrategia integral.

En esta ilustración se proporciona una representación de los elementos principales que contribuyen a Confianza cero.

:::image type="content" source="../media/zero-trust/zero-trust-architecture.png" alt-text="La arquitectura de seguridad Confianza cero" lightbox="../media/zero-trust/zero-trust-architecture.png":::

En la ilustración:

- La aplicación de directivas de seguridad está en el centro de una arquitectura de Confianza cero. Esto incluye Multi Factor Authentication con acceso condicional que tiene en cuenta el riesgo de la cuenta de usuario, el estado del dispositivo y otros criterios y directivas que establezca.
- Las identidades, los dispositivos, los datos, las aplicaciones, la red y otros componentes de infraestructura están configurados con la seguridad adecuada. Las directivas que se configuran para cada uno de estos componentes se coordinan con la estrategia general de Confianza cero. Por ejemplo, las directivas de dispositivo determinan los criterios para los dispositivos en buen estado y las directivas de acceso condicional requieren dispositivos en buen estado para el acceso a aplicaciones y datos específicos.
- La protección contra amenazas y la inteligencia supervisan el entorno, exponen los riesgos actuales y toman medidas automatizadas para corregir los ataques.

Para obtener más información sobre Confianza cero, consulte [_**el Centro de orientación de Confianza cero**_](/security/zero-trust) de Microsoft.

<!---
For more information about this architecture, including deployment objectives for your entire digital estate, see [Zero Trust Rapid Modernization Plan (RaMP)](/security/zero-trust/zero-trust-ramp-overview).
-->

## <a name="deploying-zero-trust-for-microsoft-365"></a>Implementación de Confianza cero para Microsoft 365

Microsoft 365 se ha creado intencionadamente con muchas funcionalidades de seguridad y protección de la información para ayudarle a crear Confianza cero en su entorno. Muchas de las funcionalidades se pueden ampliar para proteger el acceso a otras aplicaciones SaaS que usa su organización y los datos de estas aplicaciones.

Esta ilustración representa el trabajo de implementación de funcionalidades de Confianza cero. Este trabajo se divide en unidades de trabajo que se pueden configurar juntas, empezando desde la parte inferior y trabajando hasta la parte superior para asegurarse de que el trabajo previo está completo.

:::image type="content" source="../media/zero-trust/m365-zero-trust-deployment-stack.png" alt-text="Pila de implementación de Microsoft 365 Confianza cero" lightbox="../media/zero-trust/m365-zero-trust-deployment-stack.png":::

En esta ilustración:

- Confianza cero comienza con una base de protección de dispositivos e identidades.
- Las funcionalidades de protección contra amenazas se basan en esta base para proporcionar supervisión y corrección en tiempo real de las amenazas de seguridad.
- La protección de la información y la gobernanza proporcionan controles sofisticados dirigidos a tipos específicos de datos para proteger su información más valiosa y ayudarle a cumplir con los estándares de cumplimiento, incluida la protección de la información personal.


En este artículo se supone que ya ha configurado la identidad en la nube. Si necesita instrucciones para este objetivo, consulte [**Implementación de la infraestructura de identidad para Microsoft 365**](/microsoft-365/enterprise/deploy-identity-solution-overview).

## <a name="step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies"></a>Paso 1. Configuración de la protección de acceso a dispositivos e identidades de Confianza cero: directivas de punto de partida

El primer paso consiste en crear la base de Confianza cero mediante la configuración de la protección de identidad y acceso a dispositivos.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-1b.png" alt-text="Proceso para configurar Confianza cero protección de acceso a dispositivos e identidades" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-1b.png":::

Vaya a [**_Confianza cero protección de acceso a dispositivos e identidades_**](office-365-security/microsoft-365-policies-configurations.md) para obtener instrucciones prescriptivas para ello. En esta serie de artículos se describe un conjunto de configuraciones de requisitos previos de acceso a dispositivos e identidades y un conjunto de acceso condicional de Azure Active Directory (Azure AD), Microsoft Intune y otras directivas para proteger el acceso a Microsoft 365 para aplicaciones y servicios en la nube empresariales, otros servicios SaaS y aplicaciones locales publicadas con Azure AD Application Proxy.

|Incluye|Requisitos previos|No incluye|
|---------|---------|---------|
|Directivas de acceso a dispositivos e identidades recomendadas para tres niveles de protección: <ul><li>Punto de inicio</li><li>Enterprise (recomendado)</li><li>Especializado</li></ul> <br> Recomendaciones adicionales para: <ul><li>Usuarios externos (invitados)</li><li>Microsoft Teams</li><li>SharePoint Online</li><li>Microsoft Defender for Cloud Apps</lu></ul>|Microsoft E3 o E5 <br><br> Azure Active Directory en cualquiera de estos modos: <ul><li>Solo de nube</li><li>Autenticación híbrida con sincronización de hash de contraseña (PHS)</li><li>Híbrido con autenticación de paso a través (PTA)</li><li>Federados</li></ul>|Inscripción de dispositivos para directivas que requieren dispositivos administrados. Consulte [el paso 2. Administración de puntos de conexión con Intune](#step-2-manage-endpoints-with-intune) para inscribir dispositivos|

Para empezar, implemente el nivel de punto inicial. Estas directivas no requieren la inscripción de dispositivos en la administración.

:::image type="content" source="../media/zero-trust/identity-access-starting-point-tier.png" alt-text="Las directivas de acceso a dispositivos e identidades de Confianza cero: nivel de punto inicial" lightbox="../media/zero-trust/identity-access-starting-point-tier.png":::

## <a name="step-2-manage-endpoints-with-intune"></a>Paso 2. Administración de puntos de conexión con Intune

A continuación, inscriba los dispositivos en la administración y comience a protegerlos con controles más sofisticados.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-step-2.png" alt-text="Elemento Administrar puntos de conexión con Intune" lightbox="../media/zero-trust/m365-zero-trust-architecture-step-2.png":::

Vaya a [**_Administración de dispositivos con Intune_**](../solutions/manage-devices-with-intune-overview.md) para obtener instrucciones prescriptivas para ello.

|Incluye|Requisitos previos|No incluye|
|---------|---------|---------|
|Inscribir dispositivos con Intune: <ul><li>Dispositivos de propiedad corporativa</li><li>Autopilot/automatizado</li><li>Inscripción</li></ul> <br> Configurar directivas: <ul><li>Directivas de App Protection</li><li>Directivas de cumplimiento</li><li>Directivas de perfil de dispositivo</li></ul>|Registro de puntos de conexión con Azure AD|Configuración de funcionalidades de protección de la información, entre las que se incluyen: <ul><li>Tipos de información confidencial</li><li>Etiquetas</li><li>Directivas DLP</li></ul> <br> Para obtener estas funcionalidades, consulte [el paso 5. Proteger y controlar la información confidencial](#step-5-protect-and-govern-sensitive-data) (más adelante en este artículo).|

## <a name="step-3-add-zero-trust-identity-and-device-access-protection--enterprise-policies"></a>Paso 3. Agregar Confianza cero protección de identidad y acceso a dispositivos: directivas empresariales

Con los dispositivos inscritos en la administración, ahora puede implementar el conjunto completo de directivas de acceso a dispositivos e identidades de Confianza cero recomendadas, que requieren dispositivos compatibles.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png" alt-text="Las directivas de identidad y acceso de Confianza cero con la administración de dispositivos" lightbox="../media/zero-trust/m365-zero-trust-architecture-enterprise-policies.png":::

Vuelva a [**_las directivas de acceso a dispositivos e identidades comunes_**](office-365-security/identity-access-policies.md) y agregue las directivas en el nivel Enterprise.

:::image type="content" source="../media/zero-trust/identity-access-enterprise-tier.png" alt-text="Las directivas de identidad y acceso de Confianza cero: nivel Enterprise (recomendado)" lightbox="../media/zero-trust/identity-access-enterprise-tier.png":::

## <a name="step-4-evaluate-pilot-and-deploy-microsoft-365-defender"></a>Paso 4. Evaluar, probar e implementar Microsoft 365 Defender

Microsoft 365 Defender es una solución de detección y respuesta extendida (XDR) que recopila, correlaciona y analiza automáticamente datos de señales, amenazas y alertas de todo el entorno de Microsoft 365, incluidos puntos de conexión, correo electrónico, aplicaciones e identidades.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-defender.png" alt-text="Proceso de adición de Microsoft 365 Defender a la arquitectura de Confianza cero" lightbox="../media/zero-trust/m365-zero-trust-architecture-defender.png":::

Vaya a [**_Evaluación y Microsoft 365 Defender piloto_**](defender/eval-overview.md) para obtener una guía metódica sobre cómo pilotar e implementar componentes de Microsoft 365 Defender.

|Incluye|Requisitos previos|No incluye|
|---------|---------|---------|
|Configure el entorno piloto y de evaluación para todos los componentes: <ul><li>Defender for Identity</li><li>Defender para Office 365</li><li>Defender para punto de conexión</li><li>Microsoft Defender for Cloud Apps</li></ul> <br> Protección contra amenazas <br><br> Investigar y responder a amenazas|Consulte las instrucciones para obtener información sobre los requisitos de arquitectura de cada componente de Microsoft 365 Defender.| Azure AD Identity Protection no se incluye en esta guía de solución. Se incluye en [el paso 1. Configure Confianza cero protección de identidad y acceso a dispositivos](#step-1-configure-zero-trust-identity-and-device-access-protection--starting-point-policies).|

## <a name="step-5-protect-and-govern-sensitive-data"></a>Paso 5. Protección y control de datos confidenciales

Implemente Microsoft Purview Information Protection para ayudarle a detectar, clasificar y proteger información confidencial dondequiera que viva o viaje.

Microsoft Purview Information Protection funcionalidades se incluyen con Microsoft Purview y le proporcionan las herramientas para conocer los datos, proteger los datos y evitar la pérdida de datos.

:::image type="content" source="../media/zero-trust/m365-zero-trust-architecture-info-protect.png" alt-text="Funcionalidades de protección de la información que protegen los datos mediante la aplicación de directivas" lightbox="../media/zero-trust/m365-zero-trust-architecture-info-protect.png":::

Aunque este trabajo se representa en la parte superior de la pila de implementación ilustrada anteriormente en este artículo, puede comenzar este trabajo en cualquier momento.

Microsoft Purview Information Protection proporciona un marco, un proceso y funcionalidades que puede usar para lograr sus objetivos empresariales específicos.

![Microsoft Purview Information Protection](../media/zero-trust/mip-solution-overview.png)

Para obtener más información sobre cómo planear e implementar la protección de la información, consulte [**_Implementación de una solución de Microsoft Purview Information Protection_**](../compliance/information-protection-solution.md). 

Si va a implementar la protección de la información para las regulaciones de privacidad de datos, esta guía de solución proporciona un marco recomendado para todo el proceso: [**_Implementar la protección de la información para las regulaciones de privacidad de datos con Microsoft 365_**](../solutions/information-protection-deploy.md).
