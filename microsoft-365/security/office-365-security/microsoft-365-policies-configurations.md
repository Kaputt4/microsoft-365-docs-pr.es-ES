---
title: 'Configuraciones de identidad y acceso a dispositivos: Microsoft 365 para empresas'
description: Describe las recomendaciones de Microsoft y los conceptos básicos para implementar configuraciones y directivas de correo electrónico seguro, documentos y aplicaciones.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-overview
ms.technology: mdo
ms.openlocfilehash: 948f4515b37f27695e1e66730134aa19114ca1cf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539004"
---
# <a name="identity-and-device-access-configurations"></a>Configuraciones de acceso a dispositivos e identidades

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)

El perímetro de seguridad moderno de la organización ahora se extiende más allá de la red para incluir usuarios que acceden a aplicaciones basadas en la nube desde cualquier ubicación con una variedad de dispositivos. La infraestructura de seguridad debe determinar si se debe conceder una solicitud de acceso determinada y en qué condiciones.

Esta determinación debe basarse en la cuenta de usuario del inicio de sesión, el dispositivo que se usa, la aplicación que el usuario está usando para obtener acceso, la ubicación desde la que se realiza la solicitud de acceso y una evaluación del riesgo de la solicitud. Esta funcionalidad le permite garantizar que solo los usuarios y dispositivos aprobados puedan acceder a los recursos críticos.

En esta serie de artículos se describe un conjunto de configuraciones de requisitos previos de acceso a dispositivos y identidades y un conjunto de directivas de acceso condicional de Azure Active Directory (Azure AD), Microsoft Intune y otras directivas para proteger el acceso a Microsoft 365 para servicios y aplicaciones en la nube empresariales, otros servicios SaaS y aplicaciones locales publicadas con proxy de aplicación de Azure AD.

La configuración y las directivas de acceso a identidades y dispositivos se recomiendan en tres niveles: protección de línea base, protección confidencial y protección para entornos con datos altamente regulados o clasificados. Estos niveles y sus configuraciones correspondientes proporcionan niveles de protección coherentes en los datos, las identidades y los dispositivos.

Estas funcionalidades y sus recomendaciones:

- Se admiten en Microsoft 365 E3 y Microsoft 365 E5.
- Se alinean con [la puntuación segura de Microsoft,](../defender/microsoft-secure-score.md) así como con la puntuación de identidad en [Azure AD,](/azure/active-directory/fundamentals/identity-secure-score)y aumentarán estas puntuaciones para su organización.
- Le ayudará a implementar estos [cinco pasos para proteger su infraestructura de identidad.](/azure/security/azure-ad-secure-steps)

Si su organización tiene requisitos de entorno únicos o complejidades, use estas recomendaciones como punto de partida. Sin embargo, la mayoría de las organizaciones pueden implementar estas recomendaciones según lo prescrito.

Vea este vídeo para obtener una introducción rápida a las configuraciones de acceso a dispositivos y identidades para Microsoft 365 empresa.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft también vende licencias Enterprise Mobility + Security (EMS) para Office 365 suscripciones. Las capacidades de EMS E3 y EMS E5 son equivalentes a las de Microsoft 365 E3 y Microsoft 365 E5. Para [obtener más información, vea Planes](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) ems.

## <a name="intended-audience"></a>Público objetivo

Estas recomendaciones están dirigidas a arquitectos empresariales y profesionales de TI familiarizados con los servicios de seguridad y productividad de la nube de Microsoft 365, que incluyen Azure AD (identidad), Microsoft Intune (administración de dispositivos) y Microsoft Information Protection (protección de datos).

### <a name="customer-environment"></a>Entorno del cliente

Las directivas recomendadas se aplican a las organizaciones empresariales que operan completamente en la nube de Microsoft y a los clientes con infraestructura de identidad híbrida, que es un bosque local de Servicios de dominio de Active Directory (AD DS) que se sincroniza con un inquilino de Azure AD.

Muchas de las recomendaciones proporcionadas dependen de los servicios disponibles solo con Microsoft 365 E5, Microsoft 365 E3 con el complemento de seguridad E5, EMS E5 o azure AD Premium licencias P2.

Para aquellas organizaciones que no tienen estas licencias, Microsoft recomienda implementar al menos los valores predeterminados de [seguridad,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)que se incluyen en todos los planes Microsoft 365 licencias.

### <a name="caveats"></a>Advertencias

Su organización puede estar sujeta a requisitos normativos u otros requisitos de cumplimiento, incluidas recomendaciones específicas que pueden requerir que aplique directivas que difieren de estas configuraciones recomendadas. Estas configuraciones recomiendan controles de uso que históricamente no han estado disponibles. Se recomiendan estos controles porque creemos que representan un equilibrio entre seguridad y productividad.

Hemos hecho todo lo posible para tener en cuenta una amplia variedad de requisitos de protección de la organización, pero no podemos tener en cuenta todos los requisitos posibles ni todos los aspectos únicos de su organización.

## <a name="three-tiers-of-protection"></a>Tres niveles de protección

La mayoría de las organizaciones tienen requisitos concretos relacionados con la seguridad y la protección de datos. Estos requisitos varían dentro de las organizaciones según el segmento sectorial y las funciones de trabajo. Por ejemplo, el departamento jurídico y los administradores pueden requerir controles adicionales de seguridad y protección de la información en torno a su correspondencia de correo electrónico que no son necesarios para otras unidades de negocio.

Cada sector además tiene su propio conjunto de normas especializadas. En lugar de proporcionar una lista de todas las opciones de seguridad posibles o una recomendación por segmento del sector o función de trabajo, se han proporcionado recomendaciones para tres niveles diferentes de seguridad y protección que se pueden aplicar en función de la granularidad de sus necesidades.

- **Protección de línea** base: se recomienda establecer un estándar mínimo para proteger los datos, así como las identidades y los dispositivos que tienen acceso a los datos. Puede seguir estas recomendaciones de línea base para proporcionar una protección predeterminada sólida que satisfaga las necesidades de muchas organizaciones.
- **Protección confidencial:** algunos clientes tienen un subconjunto de datos que deben protegerse en niveles superiores o pueden requerir que todos los datos estén protegidos en un nivel superior. Puede aplicar una mayor protección a todos o conjuntos de datos específicos en su Microsoft 365 de datos. Se recomienda proteger las identidades y los dispositivos que acceden a información confidencial con niveles de seguridad comparables.
- **Altamente regulado:** algunas organizaciones pueden tener una pequeña cantidad de datos altamente clasificados, constituyen secretos comerciales o son datos regulados. Microsoft proporciona capacidades para ayudar a las organizaciones a cumplir estos requisitos, incluida protección adicional para identidades y dispositivos.

![Cono de seguridad: todos los > algunos clientes > clientes específicos. Aplicación general a una aplicación específica](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

En esta guía se muestra cómo implementar la protección de identidades y dispositivos para cada uno de estos niveles de protección. Use esta guía como punto de partida para su organización y ajuste las directivas para satisfacer los requisitos específicos de su organización.

Es importante usar niveles coherentes de protección en los datos, identidades y dispositivos. Por ejemplo, si implementa esta guía, asegúrese de proteger los datos en niveles comparables.

El **modelo identity and device protection for Microsoft 365** architecture muestra qué capacidades son comparables.

[![Imagen digital de identidad y protección de dispositivos para Microsoft 365 póster](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [Ver como un PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Descargar como pdf](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Descargar como un Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Además, vea la solución Implementar protección de [información para normativas](../../solutions/information-protection-deploy.md) de privacidad de datos para proteger la información almacenada en Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Equilibrio entre seguridad y productividad

La implementación de cualquier estrategia de seguridad requiere equilibrios entre la seguridad y la productividad. Es útil evaluar cómo afecta cada decisión al equilibrio de seguridad, funcionalidad y facilidad de uso.

![Equilibrio de la tríada de seguridad, la funcionalidad y la facilidad de uso.](../../media/microsoft-365-policies-configurations/security-triad.png)

Las recomendaciones proporcionadas se basan en los siguientes principios:

- Conozca a los usuarios y sea flexible a sus requisitos de seguridad y funcionalidad.
- Aplique una directiva de seguridad justo a tiempo y asegúrese de que es significativa.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Servicios y conceptos para la protección de acceso a dispositivos y identidades

Microsoft 365 para empresas está diseñada para que las grandes organizaciones puedan habilitar a todos para que sean creativos y trabajen juntos de forma segura.

En esta sección se proporciona información general sobre Microsoft 365 servicios y funcionalidades que son importantes para el acceso a identidades y dispositivos.

### <a name="azure-ad"></a>Azure AD

Azure AD proporciona un conjunto completo de funcionalidades de administración de identidades. Se recomienda usar estas funcionalidades para proteger el acceso.

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|[Autenticación multifactor (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA requiere que los usuarios proporcionen dos formas de comprobación, como una contraseña de usuario más una notificación de la aplicación Microsoft Authenticator o una llamada de teléfono. MFA reduce en gran medida el riesgo de que las credenciales robadas se puedan usar para obtener acceso al entorno. Microsoft 365 el servicio de autenticación multifactor de Azure AD para los inicios de sesión basados en MFA.|Microsoft 365 E3 o E5|
|[Acceso condicional](/azure/active-directory/conditional-access/overview)|Azure AD evalúa las condiciones del inicio de sesión del usuario y usa directivas de acceso condicional para determinar el acceso permitido. Por ejemplo, en esta guía te mostramos cómo crear una directiva de acceso condicional para requerir el cumplimiento del dispositivo para obtener acceso a datos confidenciales. Esto reduce en gran medida el riesgo de que un hacker con su propio dispositivo y credenciales robadas pueda acceder a sus datos confidenciales. También protege los datos confidenciales de los dispositivos, ya que los dispositivos deben cumplir requisitos específicos de salud y seguridad.|Microsoft 365 E3 o E5|
|[Grupos de Azure AD](/azure/active-directory/fundamentals/active-directory-manage-groups)|Las directivas de acceso condicional, la administración de dispositivos con Intune e incluso los permisos para archivos y sitios de la organización dependen de la asignación a cuentas de usuario o grupos de Azure AD. Se recomienda crear grupos de Azure AD que correspondan a los niveles de protección que está implementando. Por ejemplo, es probable que el personal ejecutivo sea un destino de mayor valor para los hackers. Por lo tanto, tiene sentido agregar las cuentas de usuario de estos empleados a un grupo de Azure AD y asignar este grupo a directivas de acceso condicional y otras directivas que aplican un mayor nivel de protección para el acceso.|Microsoft 365 E3 o E5|
|[Inscripción de dispositivos](/azure/active-directory/devices/overview)|Inscribir un dispositivo en Azure AD para crear una identidad para el dispositivo. Esta identidad se usa para autenticar el dispositivo cuando un usuario inicia sesión y para aplicar directivas de acceso condicional que requieren equipos unidos al dominio o compatibles. Para esta guía, usamos la inscripción de dispositivos para inscribir automáticamente equipos unidos Windows dominio. La inscripción de dispositivos es un requisito previo para administrar dispositivos con Intune.|Microsoft 365 E3 o E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización y configurar la directiva de corrección automatizada en riesgo de inicio de sesión bajo, medio y alto y riesgo de usuario. Esta guía se basa en esta evaluación de riesgos para aplicar directivas de acceso condicional para la autenticación multifactor. Esta guía también incluye una directiva de acceso condicional que requiere que los usuarios cambien su contraseña si se detecta actividad de alto riesgo para su cuenta.|Microsoft 365 E5, Microsoft 365 E3 con el complemento de seguridad E5, EMS E5 o azure AD Premium licencias de P2|
|[Restablecimiento de contraseñas de autoservicio (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Permitir que los usuarios restablezcan sus contraseñas de forma segura y sin intervención del servicio de asistencia, proporcionando la comprobación de varios métodos de autenticación que el administrador puede controlar.|Microsoft 365 E3 o E5|
|[Protección con contraseña de Azure AD](/azure/active-directory/authentication/concept-password-ban-bad)|Detectar y bloquear contraseñas débiles conocidas y sus variantes y términos débiles adicionales que son específicos de su organización. Las listas de contraseñas desvetadas global predeterminada se aplican automáticamente a todos los usuarios de un inquilino de Azure AD. Se puede definir entradas adicionales en una lista personalizada de contraseñas prohibidas. Cuando los usuarios cambien o restablezcan sus contraseñas, estas listas de contraseñas prohibidas se comprueban para exigir el uso de contraseñas seguras.|Microsoft 365 E3 o E5|
|

Estos son los componentes del acceso a dispositivos y identidades, incluidos los objetos, la configuración y los subservicios de Intune y Azure AD.

![Componentes de identidad y acceso a dispositivos](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](/intune/introduction-intune) es el servicio de administración de dispositivos móviles basado en la nube de Microsoft. En esta guía se recomienda la administración de dispositivos Windows equipos con Intune y se recomiendan las configuraciones de directivas de cumplimiento de dispositivos. Intune determina si los dispositivos son compatibles y envía estos datos a Azure AD para usarlos al aplicar directivas de acceso condicional.

#### <a name="intune-app-protection"></a>Protección de aplicaciones de Intune

[Las directivas de protección de](/intune/app-protection-policy) aplicaciones de Intune se pueden usar para proteger los datos de la organización en aplicaciones móviles, con o sin inscribir dispositivos en la administración. Intune ayuda a proteger la información, garantizar que los empleados puedan seguir siendo productivos y evitar la pérdida de datos. Al implementar directivas de nivel de aplicación, puede restringir el acceso a los recursos de la empresa y mantener los datos bajo el control de su departamento de TI.

En esta guía se muestra cómo crear directivas recomendadas para aplicar el uso de aplicaciones aprobadas y determinar cómo se pueden usar estas aplicaciones con los datos empresariales.

### <a name="microsoft-365"></a>Microsoft 365

Esta guía muestra cómo implementar un conjunto de directivas para proteger el acceso a los servicios en la nube de Microsoft 365, incluidos Microsoft Teams, Exchange Online, SharePoint Online y OneDrive para la Empresa. Además de implementar estas directivas, te recomendamos que también eleves el nivel de protección para el espacio empresarial con estos recursos:

- [Configurar su espacio empresarial para aumentar la seguridad](tenant-wide-setup-for-increased-security.md)

  Recomendaciones que se aplican a la seguridad de línea base para el inquilino.

- [Hoja de ruta de seguridad: prioridades principales para los primeros 30 días, 90 días y más allá](security-roadmap.md)

  Recomendaciones que incluyen registro, gobierno de datos, acceso de administrador y protección contra amenazas.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas y Windows 10

Windows 10 con Aplicaciones Microsoft 365 para empresas es el entorno de cliente recomendado para equipos. Se recomienda Windows 10 porque Azure está diseñado para proporcionar la experiencia más fluida posible tanto para el entorno local como para Azure AD. Windows 10 también incluye funcionalidades de seguridad avanzadas que se pueden administrar a través de Intune. Aplicaciones Microsoft 365 para empresas incluye las últimas versiones de Office aplicaciones. Estos usan la autenticación moderna, que es más segura y un requisito para el acceso condicional. Estas aplicaciones también incluyen herramientas mejoradas de seguridad y cumplimiento.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Aplicar estas capacidades en los tres niveles de protección

En la tabla siguiente se resumen nuestras recomendaciones para usar estas funcionalidades en los tres niveles de protección.

|Mecanismo de protección|Línea base|Confidencial|Extremadamente regulado|
|---|---|---|---|
|**Exigir MFA**|En riesgo de inicio de sesión medio o superior|En riesgo de inicio de sesión bajo o superior|En todas las sesiones nuevas|
|**Exigir el cambio de contraseña**|Para usuarios de alto riesgo|Para usuarios de alto riesgo|Para usuarios de alto riesgo|
|**Aplicar protección de aplicaciones de Intune**|Sí|Sí|Sí|
|**Exigir la inscripción de Intune para dispositivos propiedad de la organización**|Requerir un equipo compatible o unido a un dominio, pero permitir teléfonos y tabletas bring-your-own devices (BYOD)|Requerir un dispositivo compatible o unido a un dominio|Requerir un dispositivo compatible o unido a un dominio|
|

## <a name="device-ownership"></a>Propiedad del dispositivo

La tabla anterior refleja la tendencia de muchas organizaciones a admitir una combinación de dispositivos propiedad de la organización, así como dispositivos personales o BYOD para permitir la productividad móvil en todo el personal. Las directivas de protección de aplicaciones de Intune garantizan que el correo electrónico no se exfiltre fuera de la aplicación móvil de Outlook y otras aplicaciones móviles de Office, tanto en dispositivos propiedad de la organización como en byods.

Se recomienda que Intune administre los dispositivos propiedad de la organización o que se unan a un dominio para aplicar protecciones y control adicionales. Según la confidencialidad de los datos, la organización puede optar por no permitir byods para determinadas poblaciones de usuarios o aplicaciones específicas.

## <a name="deployment-and-your-apps"></a>Implementación y aplicaciones

Antes de configurar e implementar la configuración de acceso a dispositivos y identidades para las aplicaciones integradas en Azure AD, debe:

- Decide qué aplicaciones se usan en la organización que quieres proteger.
- Analice esta lista de aplicaciones para determinar los conjuntos de directivas que proporcionan niveles de protección adecuados.

  No debes crear conjuntos de directivas independientes para cada aplicación, ya que la administración de ellas puede resultar engorrosa. Microsoft recomienda agrupar las aplicaciones que tienen los mismos requisitos de protección para los mismos usuarios.

  Por ejemplo, podría tener un conjunto de directivas que incluyan todas las aplicaciones de Microsoft 365 para todos los usuarios para la protección de línea base y un segundo conjunto de directivas para todas las aplicaciones confidenciales, como las que usan los departamentos de recursos humanos o finanzas, y aplicarlas a esos grupos.

Una vez que haya determinado el conjunto de directivas de las aplicaciones que desea proteger, revierte las directivas a los usuarios de forma incremental y a solucionar problemas en el camino.

Por ejemplo, configure las directivas que se usarán para todas las aplicaciones de Microsoft 365 solo Exchange Online con los cambios adicionales para Exchange. Roll these policies out to your users and work through any issues. A continuación, Teams con sus cambios adicionales y revierte esto a los usuarios. A continuación, agregue SharePoint con sus cambios adicionales. Continúa agregando el resto de tus aplicaciones hasta que puedas configurar con confianza estas directivas de línea base para incluir todas las Microsoft 365 aplicaciones.

Del mismo modo, para las aplicaciones confidenciales, crea el conjunto de directivas y agrega una aplicación a la vez y trabaja con cualquier problema hasta que se incluyan todas en el conjunto de directivas de aplicaciones confidenciales.

Microsoft recomienda no crear conjuntos de directivas que se apliquen a todas las aplicaciones porque puede dar lugar a algunas configuraciones no deseadas. Por ejemplo, las directivas que bloquean todas las aplicaciones podrían bloquear a los administradores fuera de Azure Portal y las exclusiones no se pueden configurar para puntos de conexión importantes como Microsoft Graph.

## <a name="steps-to-configure-identity-and-device-access"></a>Pasos para configurar la identidad y el acceso a dispositivos

![Pasos para configurar la identidad y el acceso a dispositivos.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Configure las características de identidad de requisitos previos y su configuración.
2. Configure las directivas comunes de acceso y identidad de acceso.
3. Configurar directivas de acceso condicional para usuarios invitados y externos.
4. Configure directivas de acceso condicional para Microsoft 365 aplicaciones en la nube, como Microsoft Teams, Exchange Online y SharePoint y Microsoft Cloud App Security directivas.

Después de configurar el acceso a identidades y dispositivos, consulta la guía de implementación de características de [Azure AD](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) para obtener una lista de comprobación por fases de características adicionales que debes tener en cuenta y Gobierno de identidad de [Azure AD](/azure/active-directory/governance/) para proteger, supervisar y auditar el acceso.

## <a name="next-step"></a>Paso siguiente

[Trabajo previo para implementar directivas de acceso a dispositivos y identidades](identity-access-prerequisites.md)