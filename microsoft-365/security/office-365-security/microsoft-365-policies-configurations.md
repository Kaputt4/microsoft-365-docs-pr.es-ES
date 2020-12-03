---
title: 'Configuraciones de acceso a dispositivos e identidades: Microsoft 365 para Enterprise'
description: Describe las recomendaciones de Microsoft y los conceptos básicos para implementar directivas y configuraciones de correo electrónico seguro, documentos y aplicaciones.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/29/2020
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
ms.openlocfilehash: 0144e9478e74e252e0c4ccc0c902df376129c388
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558291"
---
# <a name="identity-and-device-access-configurations"></a>Configuraciones de acceso a dispositivos e identidades

El perímetro de seguridad moderno de su organización ahora se extiende más allá de la red para incluir a los usuarios que acceden a las aplicaciones basadas en la nube desde cualquier ubicación con una variedad de dispositivos. La infraestructura de seguridad debe determinar si se debe conceder una solicitud de acceso determinada y en qué condiciones.

Esta determinación debe basarse en la cuenta de usuario del inicio de sesión, el dispositivo que se usa, la aplicación que el usuario está usando para el acceso, la ubicación desde la que se realiza la solicitud de acceso y una evaluación del riesgo de la solicitud. Esta funcionalidad le permite garantizar que solo los usuarios y dispositivos aprobados puedan acceder a los recursos críticos.

En esta serie de artículos se describe un conjunto de configuraciones de requisitos previos de acceso a dispositivos e identidades y un conjunto de acceso condicional de Azure Active Directory (Azure AD), Microsoft Intune y otras directivas para proteger el acceso a Microsoft 365 para aplicaciones y servicios en la nube de empresa, otros servicios SaaS y aplicaciones locales publicadas con el proxy de aplicación de Azure AD.

Se recomienda la configuración y las directivas de acceso a los dispositivos y la identidad en tres niveles: protección de línea base, protección confidencial y protección para entornos con datos altamente regulados o clasificados. Estos niveles y sus configuraciones correspondientes proporcionan niveles de protección coherentes en los datos, las identidades y los dispositivos.

Estas capacidades y sus recomendaciones:

- Son compatibles con Microsoft 365 E3 y Microsoft 365 E5.
- Se alinean con la [puntuación segura de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) , así como con la [puntuación de identidad en Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score), y aumentan estos resultados para la organización.
- Le ayudarán a implementar estos [cinco pasos para proteger su infraestructura de identidades](https://docs.microsoft.com/azure/security/azure-ad-secure-steps).

Si su organización tiene requisitos de entorno únicos o complejidades, use estas recomendaciones como punto de partida. Sin embargo, la mayoría de las organizaciones pueden implementar estas recomendaciones como se recomiendan.

>[!Note]
>Microsoft también vende licencias de Enterprise Mobility + Security (EMS) para las suscripciones de Office 365. Las capacidades de EMS E3 y EMS E5 son equivalentes a las de Microsoft 365 E3 y Microsoft 365 E5. Consulte [planes de EMS](https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) para obtener información detallada.
>

## <a name="intended-audience"></a>Público objetivo

Estas recomendaciones están destinadas a arquitectos empresariales y profesionales de ti que están familiarizados con los servicios de seguridad y productividad en la nube de Microsoft 365, que incluyen Azure AD (identidad), Microsoft Intune (administración de dispositivos) y Azure Information Protection (protección de datos).

### <a name="customer-environment"></a>Entorno del cliente

Las directivas recomendadas se aplican a las organizaciones empresariales que operan completamente en la nube de Microsoft y a los clientes con una infraestructura de identidades híbrida, que es un bosque local de servicios de dominio de Active Directory (AD DS) que se sincroniza con un inquilino de Azure AD.

Muchas de las recomendaciones proporcionadas dependen de los servicios disponibles solo con Microsoft 365 E5, Microsoft 365 E3 con las licencias Identity & Threat Protection Add-on, EMS E5 o Azure Premium P2.

Para las organizaciones que no tienen estas licencias, Microsoft le recomienda al menos implementar los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), que se incluye con todos los planes de Microsoft 365.

### <a name="caveats"></a>ADVERTENCIAS

Es posible que su organización esté sujeta a requisitos normativos o de cumplimiento normativo, incluidas recomendaciones específicas que puedan requerir la aplicación de directivas que difieran de estas configuraciones recomendadas. Estas configuraciones recomiendan controles de uso que históricamente no han estado disponibles. Le recomendamos estos controles porque creemos que representan un equilibrio entre la seguridad y la productividad.

Hemos hecho lo mejor para explicar una amplia variedad de requisitos de protección organizacional, pero no podemos tener en cuenta todos los requisitos posibles o todos los aspectos exclusivos de su organización.

## <a name="three-tiers-of-protection"></a>Tres niveles de protección

La mayoría de las organizaciones tienen requisitos concretos relacionados con la seguridad y la protección de datos. Estos requisitos varían dentro de las organizaciones según el segmento sectorial y las funciones de trabajo. Por ejemplo, el departamento legal y los administradores pueden requerir controles adicionales de protección de la información y seguridad en torno a su correspondencia de correo electrónico que no son necesarios para otras unidades de negocio.

Cada sector además tiene su propio conjunto de normas especializadas. En lugar de proporcionar una lista de todas las opciones de seguridad posibles o una recomendación por segmento de la industria o función de trabajo, se han proporcionado recomendaciones para tres niveles distintos de seguridad y protección que se pueden aplicar en función de la granularidad de sus necesidades.

- **Protección de línea base**: le recomendamos que establezca un estándar mínimo para la protección de datos, así como las identidades y los dispositivos que tienen acceso a sus datos. Puede seguir estas recomendaciones de línea base para proporcionar una protección segura predeterminada que satisfaga las necesidades de muchas organizaciones.
- **Protección confidencial**: algunos clientes tienen un subconjunto de datos que deben protegerse en niveles superiores o pueden requerir que todos los datos estén protegidos en un nivel superior. Puede aplicar una mayor protección a todos o conjuntos de datos específicos en su entorno de Microsoft 365. Se recomienda proteger las identidades y los dispositivos que acceden a información confidencial con niveles de seguridad comparables.
- **Altamente regulado**: algunas organizaciones pueden tener una pequeña cantidad de datos clasificados en gran medida, que constituyen secretos comerciales o que son datos regulados. Microsoft proporciona capacidades para ayudar a las organizaciones a cumplir estos requisitos, incluida protección adicional para identidades y dispositivos.

![Cono de seguridad: todos los clientes > algunos clientes > clientes específicos. Amplia aplicación a aplicación específica](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

En esta guía se muestra cómo implementar la protección de las identidades y los dispositivos de cada uno de estos niveles de protección. Use esta guía como punto de partida para su organización y ajuste las directivas para cumplir los requisitos específicos de su organización.

Es importante usar niveles de protección coherentes en los datos, las identidades y los dispositivos. Por ejemplo, si implementa esta guía, asegúrese de proteger los datos en niveles comparables.

El modelo **de arquitectura de identidad y de protección de dispositivos para Microsoft 365** muestra qué capacidades son comparables.

[![Imagen en miniatura para la protección de identidades y dispositivos para el póster 365 de Microsoft](../../media/microsoft-365-policies-configurations/O365_Identity_device_protection_thumb.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br/>  [Ver como PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Descargar como PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Descargar como Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)  

Además, consulte la solución [de implementación de protección de información para las regulaciones de privacidad de datos](../../solutions/information-protection-deploy.md) para proteger la información almacenada en Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Equilibrio entre seguridad y productividad

La implementación de cualquier estrategia de seguridad requiere equilibrio entre la seguridad y la productividad. Es útil evaluar cómo afecta cada decisión al equilibrio de seguridad, funcionalidad y facilidad de uso.

![Seguridad tríada equilibrar la seguridad, la funcionalidad y la facilidad de uso.](../../media/microsoft-365-policies-configurations/security-triad.png)

Las recomendaciones proporcionadas se basan en los siguientes principios:

- Conozca a sus usuarios y sea flexible con respecto a sus requisitos de seguridad y funcionamiento.
- Aplique una directiva de seguridad justo a tiempo y asegúrese de que es significativa.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Servicios y conceptos de protección de acceso a dispositivos e identidades

Microsoft 365 para empresas está diseñado para organizaciones de gran tamaño para que todo el mundo pueda ser creativo y trabajar juntos de manera segura.

En esta sección se proporciona información general sobre los servicios y capacidades de Microsoft 365 que son importantes para el acceso a los dispositivos e identidades.

### <a name="azure-ad"></a>Azure AD

Azure AD ofrece un conjunto completo de capacidades de administración de identidades. Se recomienda usar estas funciones para proteger el acceso.

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|[Autenticación multifactor (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|La MFA requiere que los usuarios proporcionen dos formas de comprobación, como una contraseña de usuario y una notificación de la aplicación Microsoft Authenticator o una llamada telefónica. La MFA reduce en gran medida el riesgo de que se puedan usar credenciales robadas para obtener acceso al entorno. Microsoft 365 usa el servicio de autenticación multifactor de Azure AD para inicios de sesión basados en MFA.|Microsoft 365 E3 o E5|
|[Acceso condicional](/azure/active-directory/conditional-access/overview)|Azure AD evalúa las condiciones del inicio de sesión de los usuarios y usa directivas de acceso condicional para determinar el acceso permitido. Por ejemplo, en esta guía le mostramos cómo crear una directiva de acceso condicional para exigir el cumplimiento de dispositivos para el acceso a datos confidenciales. Esto reduce en gran medida el riesgo de que un pirata informático con su propio dispositivo y las credenciales robadas puedan tener acceso a sus datos confidenciales. También protege los datos confidenciales de los dispositivos, ya que los dispositivos deben cumplir requisitos específicos para la seguridad y la salud.|Microsoft 365 E3 o E5|
|[Grupos de Azure AD](/azure/active-directory/fundamentals/active-directory-manage-groups)|Las directivas de acceso condicional, administración de dispositivos con Intune e, incluso, los permisos para archivos y sitios de la organización dependen de la asignación a las cuentas de usuario o grupos de Azure AD. Le recomendamos que cree grupos de Azure AD que se correspondan con los niveles de protección que está implementando. Por ejemplo, el personal ejecutivo probablemente es un objetivo de mayor valor para los hackers. Por lo tanto, tiene sentido agregar las cuentas de usuario de estos empleados a un grupo de Azure AD y asignar este grupo a las directivas de acceso condicional y otras directivas que imponen un mayor nivel de protección para el acceso.|Microsoft 365 E3 o E5|
|[Inscripción de dispositivos](/azure/active-directory/devices/overview)|Inscriba un dispositivo en Azure AD para crear una identidad para el dispositivo. Esta identidad se usa para autenticar el dispositivo cuando un usuario inicia sesión y aplica directivas de acceso condicional que requieren equipos compatibles o Unidos a un dominio. Para esta guía, usamos la inscripción de dispositivos para inscribir automáticamente equipos con Windows Unidos a un dominio. La inscripción de dispositivos es un requisito previo para administrar dispositivos con Intune.|Microsoft 365 E3 o E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Permite detectar posibles vulnerabilidades que afectan a las identidades de su organización y configurar la Directiva de corrección automatizada para el riesgo de inicio de sesión de usuario, los riesgos y el riesgo de inicio de sesión bajo, medio y alto. Esta guía se basa en esta evaluación de riesgos para aplicar directivas de acceso condicional para la autenticación multifactor. Esta guía también incluye una directiva de acceso condicional que requiere que los usuarios cambien su contraseña si se detecta una actividad de alto riesgo para su cuenta.|Microsoft 365 E5, Microsoft 365 E3 con las licencias Identity & Threat Protection Add-on, EMS E5 o Azure Premium P2|
|[Restablecimiento de contraseña de autoservicio (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Permitir a los usuarios restablecer sus contraseñas de forma segura y sin intervención del servicio de asistencia técnica, mediante la comprobación de varios métodos de autenticación que el administrador puede controlar.|Microsoft 365 E3 o E5|
|[Protección con contraseña de Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)|Detectar y bloquear contraseñas débiles conocidas y sus variantes y términos débiles adicionales específicos de la organización. Las listas de contraseñas desvetadas global predeterminada se aplican automáticamente a todos los usuarios de un inquilino de Azure AD. Se puede definir entradas adicionales en una lista personalizada de contraseñas prohibidas. Cuando los usuarios cambien o restablezcan sus contraseñas, estas listas de contraseñas prohibidas se comprueban para exigir el uso de contraseñas seguras.|Microsoft 365 E3 o E5|
|

Estos son los componentes de acceso a los dispositivos e identidades, incluidos Intune y los objetos, la configuración y los subservicios de Azure AD.

![Componentes de acceso de identidad y de dispositivo](../../media/microsoft-365-policies-configurations/identity-device-access-components.png)

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) es el servicio de administración de dispositivos móviles basado en la nube de Microsoft. Esta guía recomienda la administración de dispositivos de Windows con Intune y recomienda la configuración de directivas de cumplimiento de dispositivos. Intune determina si los dispositivos son compatibles y envía los datos a Azure AD para usarlos cuando se aplican directivas de acceso condicional.

#### <a name="intune-app-protection"></a>Protección de aplicaciones de Intune

Las directivas de [protección de aplicaciones de Intune](https://docs.microsoft.com/intune/app-protection-policy) se pueden usar para proteger los datos de su organización en aplicaciones móviles, con o sin inscribir los dispositivos en la administración. Intune ayuda a proteger la información, asegurándose de que sus empleados todavía puedan ser productivos y evitando la pérdida de datos. Mediante la implementación de directivas de nivel de aplicación, puede restringir el acceso a los recursos de la empresa y mantener los datos dentro del control del Departamento de ti.

En esta guía se muestra cómo crear directivas recomendadas para exigir el uso de aplicaciones aprobadas y determinar cómo se pueden usar estas aplicaciones con los datos profesionales.

### <a name="microsoft-365"></a>Microsoft 365

Esta guía le muestra cómo implementar un conjunto de directivas para proteger el acceso a los servicios en la nube de Microsoft 365, incluidos Microsoft Teams, Exchange Online, SharePoint Online y OneDrive para la empresa. Además de implementar estas directivas, se recomienda aumentar también el nivel de protección del espacio empresarial con estos recursos:

- [Configurar su espacio empresarial para aumentar la seguridad](tenant-wide-setup-for-increased-security.md)

  Recomendaciones relativas a la seguridad de línea base de su espacio empresarial.

- [Plan de seguridad: principales prioridades de los primeros 30 días, 90 días y más allá](security-roadmap.md)

  Recomendaciones que incluyen el registro, el gobierno de datos, el acceso de administrador y la protección contra amenazas.

### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas y Windows 10

Windows 10 con Microsoft 365 apps for Enterprise es el entorno de cliente recomendado para equipos PC. Recomendamos Windows 10 porque Azure está diseñado para proporcionar la experiencia más fluida posible tanto en local como en Azure AD. Windows 10 también incluye funciones de seguridad avanzada que se pueden administrar a través de Intune. Microsoft 365 apps for Enterprise incluye las versiones más recientes de las aplicaciones de Office. Estos usan la autenticación moderna, que es más segura y un requisito de acceso condicional. Estas aplicaciones también incluyen herramientas de seguridad y cumplimiento mejoradas.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Aplicación de estas funcionalidades en los tres niveles de protección

La siguiente tabla resume nuestras recomendaciones para usar estas capacidades en los tres niveles de protección.

|Mecanismo de protección|Línea base|Confidencial|Extremadamente regulado|
|---|---|---|---|
|**Exigir MFA**|En riesgo de inicio de sesión medio o superior|En riesgo de inicio de sesión bajo o superior|En todas las sesiones nuevas|
|**Exigir cambio de contraseña**|Para usuarios de alto riesgo|Para usuarios de alto riesgo|Para usuarios de alto riesgo|
|**Exigir la protección de Intune Application**|Sí|Sí|Sí|
|**Exigir la inscripción de Intune para el dispositivo de propiedad de la organización**|Requerir un equipo compatible o unido a un dominio, pero permite que los teléfonos y las tabletas de los dispositivos (BYOD)|Requerir un dispositivo compatible o unido a un dominio|Requerir un dispositivo compatible o unido a un dominio|
|

## <a name="device-ownership"></a>Propiedad del dispositivo

La tabla anterior refleja la tendencia de muchas organizaciones para admitir una combinación de dispositivos propiedad de la organización, así como personal o BYODs para habilitar la productividad móvil en todo el personal. Las directivas de protección de aplicaciones de Intune garantizan que el correo electrónico esté protegido de la exfiltrating de la aplicación móvil de Outlook y otras aplicaciones móviles de Office, tanto en los dispositivos que pertenecen a la organización como en BYODs.

Se recomienda que los dispositivos de propiedad de la organización se administren con Intune o con un dominio Unido para aplicar protecciones y control adicionales. En función de la sensibilidad de los datos, su organización puede optar por no permitir BYODs para determinados grupos de usuarios o aplicaciones específicas.

## <a name="deployment-and-your-apps"></a>Implementación y sus aplicaciones

Antes de configurar e implementar la configuración de identidades y acceso a dispositivos para las aplicaciones integradas de Azure AD, debe:

- Decida qué aplicaciones se usan en la organización que desea proteger.
- Analice esta lista de aplicaciones para determinar los conjuntos de directivas que proporcionan los niveles adecuados de protección.

  No debe crear conjuntos de directivas independientes para cada aplicación, ya que la administración de ellas puede resultar engorroso. Microsoft recomienda que agrupe las aplicaciones que tengan los mismos requisitos de protección para los mismos usuarios.

  Por ejemplo, puede tener un conjunto de directivas que incluyan todas las aplicaciones de Microsoft 365 para todos los usuarios para la protección de línea de base y un segundo conjunto de directivas para todas las aplicaciones confidenciales, como las que usan los recursos humanos o los departamentos financieros, y aplicarlos a dichos grupos.

Una vez que haya determinado el conjunto de directivas para las aplicaciones que desea proteger, revierta las directivas a sus usuarios de manera incremental y resuelva los problemas a lo largo del proceso.

Por ejemplo, configure las directivas que se usarán para todas las aplicaciones de Microsoft 365 para solo Exchange Online con los cambios adicionales de Exchange. Desplace estas directivas a sus usuarios y trabaje con cualquier problema. A continuación, agregue Microsoft Teams con sus cambios adicionales y revierta esto en sus usuarios. A continuación, agregue SharePoint con sus cambios adicionales. Continúe agregando el resto de las aplicaciones hasta que pueda configurar con certeza estas directivas de línea de base para incluir todas las aplicaciones de Microsoft 365.

De forma similar, para las aplicaciones confidenciales, cree el conjunto de directivas y agregue una aplicación cada vez y trabaje con cualquier problema hasta que todos estén incluidos en el conjunto de directivas de aplicación confidencial.

Microsoft recomienda que no cree conjuntos de directivas que se apliquen a todas las aplicaciones, ya que esto puede dar como resultado configuraciones no deseadas. Por ejemplo, las directivas que bloquean todas las aplicaciones podrían bloquear a los administradores fuera del portal de Azure y las exclusiones no se pueden configurar para puntos de conexión importantes, como Microsoft Graph.

## <a name="steps-in-the-process-of-configuring-identity-and-device-access"></a>Pasos del proceso de configuración de la identidad y el acceso a dispositivos

![Pasos para configurar la identidad y el acceso al dispositivo.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Configure las características de identidad de requisitos previos y su configuración.
2. Configure las directivas de acceso condicional de acceso y de identidad comunes.
3. Configurar directivas de acceso condicional para usuarios externos y invitados.
4. Configure las directivas de acceso condicional para las aplicaciones en la nube de Microsoft 365, como Microsoft Teams, Exchange Online y SharePoint.

Una vez que haya configurado el acceso a los dispositivos e identidades, vea la [Guía de implementación de características de Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) para obtener una lista de comprobación escalonada de características adicionales que debe tener en cuenta y el [control de identidad de Azure ad](https://docs.microsoft.com/azure/active-directory/governance/) para proteger, supervisar y auditar el acceso.

## <a name="next-step"></a>Paso siguiente

[Trabajo de requisitos previos para implementar directivas de acceso a dispositivos e identidades](identity-access-prerequisites.md)
