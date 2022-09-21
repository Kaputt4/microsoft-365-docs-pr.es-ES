---
title: 'Confianza cero configuraciones de acceso a dispositivos e identidades: Microsoft 365 para empresas'
description: Describe las recomendaciones de Microsoft y los conceptos básicos para implementar directivas y configuraciones de aplicaciones, documentos y correo electrónico seguros para Confianza cero.
ms.author: dansimp
author: dansimp
manager: dansimp
ms.service: microsoft-365-security
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
- m365solution-zero-trust
- zerotrust-solution
- highpri
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 811938ba4c4b4e174e594bd3855112524771ec5e
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851686"
---
# <a name="zero-trust-identity-and-device-access-configurations"></a>Configuraciones de identidad y acceso a dispositivos de Confianza cero

Las arquitecturas de seguridad que se basan en firewalls de red y redes privadas virtuales (VPN) para aislar y restringir el acceso a los recursos y servicios tecnológicos de una organización ya no son suficientes para un personal que requiere regularmente acceso a aplicaciones y recursos que existen más allá de los límites de red corporativos tradicionales.

Para abordar este nuevo mundo de la informática, Microsoft recomienda encarecidamente el modelo de seguridad Confianza cero, que se basa en estos principios rectores:

- Comprobar de forma explícita.

  Autentíquese y autorice siempre en función de todos los puntos de datos disponibles. Aquí es donde Confianza cero directivas de acceso a dispositivos e identidades son fundamentales para el inicio de sesión y la validación en curso.

- Utilizar el acceso con menos privilegios

  Limite el acceso de usuario con Just-In-Time y Just-Enough-Access (JIT/JEA), directivas adaptables basadas en riesgos y protección de datos.

- Asumir la vulneración.

  Minimice el radio de explosión y el acceso a segmentos. Compruebe el cifrado de un extremo a otro y use análisis para obtener visibilidad, impulsar la detección de amenazas y mejorar las defensas.

Esta es la arquitectura general de Confianza cero.

:::image type="content" source="../../media/microsoft-365-policies-configurations/zero-trust-architecture.png" alt-text="Arquitectura de Microsoft Confianza cero" lightbox="../../media/microsoft-365-policies-configurations/zero-trust-architecture.png":::

Confianza cero directivas de acceso a dispositivos e identidades abordan el principio de guía **Comprobar explícitamente** para:

- Identidades

  Cuando una identidad intenta acceder a un recurso, compruebe esa identidad con autenticación segura y asegúrese de que el acceso solicitado es compatible y típico.

- Dispositivos (también denominados puntos de conexión)

  Supervise y aplique los requisitos de cumplimiento y estado del dispositivo para un acceso seguro.

- Aplicaciones

  Aplique controles y tecnologías para detectar shadow IT, garantizar los permisos adecuados desde la aplicación, garantizar el acceso de puerta en función del análisis en tiempo real, supervisar el comportamiento anómalo, controlar las acciones del usuario y validar opciones de configuración seguras.

En esta serie de artículos se describe un conjunto de configuraciones de requisitos previos de acceso a dispositivos e identidades y un conjunto de acceso condicional de Azure Active Directory (Azure AD), Microsoft Intune y otras directivas para Confianza cero acceso a Microsoft 365 para aplicaciones y servicios en la nube empresariales, otros servicios SaaS y aplicaciones locales publicadas con Azure AD Application Proxy.

Confianza cero configuración y directivas de acceso a dispositivos e identidades se recomiendan en tres niveles: punto de partida, empresa y seguridad especializada para entornos con datos altamente regulados o clasificados. Estos niveles y sus configuraciones correspondientes proporcionan niveles coherentes de protección de Confianza cero en los datos, identidades y dispositivos.

Estas funcionalidades y sus recomendaciones:

- Se admiten en Microsoft 365 E3 y Microsoft 365 E5.
- Se alinean con [la puntuación segura de Microsoft](../defender/microsoft-secure-score.md) , así como con la [puntuación de identidad en Azure AD](/azure/active-directory/fundamentals/identity-secure-score), y aumentarán estas puntuaciones para su organización.
- Le ayudará a implementar estos [cinco pasos para proteger la infraestructura de identidad](/azure/security/azure-ad-secure-steps).

Si su organización tiene requisitos o complejidades de entorno únicos, use estas recomendaciones como punto de partida. Sin embargo, la mayoría de las organizaciones pueden implementar estas recomendaciones según lo prescrito.

Vea este vídeo para obtener información general rápida sobre las configuraciones de acceso a dispositivos y identidades para Microsoft 365 para empresas.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft también vende licencias de Enterprise Mobility + Security (EMS) para suscripciones Office 365. Las capacidades EMS E3 y EMS E5 son equivalentes a las de Microsoft 365 E3 y Microsoft 365 E5. Consulte [los planes de EMS](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) para obtener los detalles.

## <a name="intended-audience"></a>Público objetivo

Estas recomendaciones están pensadas para arquitectos empresariales y profesionales de TI que están familiarizados con los servicios de productividad y seguridad en la nube de Microsoft 365, que incluyen Azure AD (identidad), Microsoft Intune (administración de dispositivos) y Microsoft Purview Information Protection (protección de datos).

### <a name="customer-environment"></a>Entorno del cliente

Las directivas recomendadas se aplican a las organizaciones empresariales que operan por completo en la nube de Microsoft y a los clientes con infraestructura de identidad híbrida, que es un bosque Active Directory local Domain Services (AD DS) que se sincroniza con un inquilino de Azure AD.

Muchas de las recomendaciones proporcionadas se basan en servicios disponibles solo con Microsoft 365 E5, Microsoft 365 E3 con el complemento de seguridad E5, EMS E5 o licencias de Azure AD Premium P2.

Para aquellas organizaciones que no tienen estas licencias, Microsoft recomienda implementar al menos [los valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), que se incluyen con todos los planes de Microsoft 365.

### <a name="caveats"></a>Advertencias

Su organización puede estar sujeta a requisitos normativos u otros requisitos de cumplimiento, incluidas recomendaciones específicas que pueden requerir que aplique directivas que divergen de estas configuraciones recomendadas. Estas configuraciones recomiendan controles de uso que históricamente no han estado disponibles. Recomendamos estos controles porque creemos que representan un equilibrio entre seguridad y productividad.

Hemos hecho todo lo posible para tener en cuenta una amplia variedad de requisitos de protección de la organización, pero no podemos tener en cuenta todos los requisitos posibles ni todos los aspectos únicos de su organización.

## <a name="three-tiers-of-protection"></a>Tres niveles de protección

La mayoría de las organizaciones tienen requisitos concretos relacionados con la seguridad y la protección de datos. Estos requisitos varían dentro de las organizaciones según el segmento sectorial y las funciones de trabajo. Por ejemplo, el departamento legal y los administradores pueden requerir controles adicionales de seguridad y protección de la información en torno a su correspondencia de correo electrónico que no son necesarias para otras unidades de negocio.

Cada sector además tiene su propio conjunto de normas especializadas. En lugar de proporcionar una lista de todas las opciones de seguridad posibles o una recomendación por segmento del sector o función de trabajo, se han proporcionado recomendaciones para tres niveles diferentes de seguridad y protección que se pueden aplicar en función de la granularidad de sus necesidades.

- **Punto de partida**: se recomienda que todos los clientes establezcan y usen un estándar mínimo para proteger los datos, así como las identidades y los dispositivos que acceden a los datos. Puede seguir estas recomendaciones para proporcionar una protección predeterminada segura como punto de partida para todas las organizaciones.
- **Empresa**: algunos clientes tienen un subconjunto de datos que deben protegerse en niveles superiores, o bien pueden requerir que todos los datos estén protegidos en un nivel superior. Puede aplicar una mayor protección a todos o conjuntos de datos específicos en el entorno de Microsoft 365. Se recomienda proteger las identidades y los dispositivos que acceden a información confidencial con niveles de seguridad comparables.
- **Seguridad especializada**: según sea necesario, algunos clientes tienen una pequeña cantidad de datos altamente clasificados, constituyen secretos comerciales o están regulados. Microsoft proporciona funcionalidades para ayudar a estos clientes a cumplir estos requisitos, incluida la protección adicional para identidades y dispositivos.

:::image type="content" source="../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png" alt-text="El cono de seguridad" lightbox="../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png":::

En esta guía se muestra cómo implementar Confianza cero protección para identidades y dispositivos para cada uno de estos niveles de protección. Use esta guía como mínimo para su organización y ajuste las directivas para satisfacer los requisitos específicos de su organización.

Es importante usar niveles coherentes de protección en las identidades, dispositivos y datos. Por ejemplo, la protección de los usuarios con cuentas&mdash;prioritarias, como ejecutivos, líderes, administradores y otros&mdash;, debe incluir el mismo nivel de protección para sus identidades, sus dispositivos y los datos a los que acceden. 
<!--

The **Zero Trust identity and device protection for Microsoft 365** architecture model shows you which capabilities are comparable.

[![Thumb image for Zero Trust Identity and device protection for Microsoft 365 poster.](../../media/microsoft-365-policies-configurations/zero-trust-id-device-protection-model-thumbnail.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [View as a PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Download as a PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf)  \| [Download as a Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)

--> 

Además, consulte la solución [Implementar la protección de la información para las regulaciones de privacidad de datos](../../solutions/information-protection-deploy.md) para proteger la información almacenada en Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Equilibrio entre seguridad y productividad

La implementación de cualquier estrategia de seguridad requiere compensaciones entre la seguridad y la productividad. Resulta útil evaluar cómo afecta cada decisión al equilibrio de seguridad, funcionalidad y facilidad de uso.

:::image type="content" source="../../media/microsoft-365-policies-configurations/security-triad.png" alt-text="La seguridad, la funcionalidad y la facilidad de uso del equilibrio de la tríada de seguridad" lightbox="../../media/microsoft-365-policies-configurations/security-triad.png":::

Las recomendaciones proporcionadas se basan en los siguientes principios:

- Conozca a los usuarios y sea flexible con sus requisitos funcionales y de seguridad.
- Aplique una directiva de seguridad justo a tiempo y asegúrese de que es significativa.

## <a name="services-and-concepts-for-zero-trust-identity-and-device-access-protection"></a>Servicios y conceptos para Confianza cero protección de identidad y acceso a dispositivos

Microsoft 365 para empresas está diseñado para que las grandes organizaciones puedan capacitar a todos para que sean creativos y trabajen juntos de forma segura.

En esta sección se proporciona información general sobre los servicios y funcionalidades de Microsoft 365 que son importantes para Confianza cero identidad y acceso al dispositivo.

### <a name="azure-ad"></a>Azure AD

Azure AD proporciona un conjunto completo de funcionalidades de administración de identidades. Se recomienda usar estas funcionalidades para proteger el acceso.

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|[Autenticación multifactor (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA requiere que los usuarios proporcionen dos formas de verificación, como una contraseña de usuario y una notificación de la aplicación Microsoft Authenticator o una llamada telefónica. MFA reduce en gran medida el riesgo de que se puedan usar credenciales robadas para acceder a su entorno. Microsoft 365 usa el servicio Multi-Factor Authentication de Azure AD para inicios de sesión basados en MFA.|Microsoft 365 E3 o E5|
|[Acceso condicional](/azure/active-directory/conditional-access/overview)|Azure AD evalúa las condiciones del inicio de sesión del usuario y usa directivas de acceso condicional para determinar el acceso permitido. Por ejemplo, en esta guía se muestra cómo crear una directiva de acceso condicional para requerir el cumplimiento de dispositivos para el acceso a datos confidenciales. Esto reduce en gran medida el riesgo de que un hacker con su propio dispositivo y credenciales robadas pueda acceder a sus datos confidenciales. También protege la información confidencial en los dispositivos, ya que los dispositivos deben cumplir requisitos específicos para el estado y la seguridad.|Microsoft 365 E3 o E5|
|[Grupos de Azure AD](/azure/active-directory/fundamentals/active-directory-manage-groups)|Las directivas de acceso condicional, la administración de dispositivos con Intune e incluso los permisos para archivos y sitios de su organización dependen de la asignación a cuentas de usuario o grupos de Azure AD. Se recomienda crear grupos de Azure AD que se correspondan con los niveles de protección que está implementando. Por ejemplo, es probable que el personal ejecutivo tenga objetivos de mayor valor para los hackers. Por lo tanto, tiene sentido agregar las cuentas de usuario de estos empleados a un grupo de Azure AD y asignar este grupo a directivas de acceso condicional y otras directivas que exijan un mayor nivel de protección para el acceso.|Microsoft 365 E3 o E5|
|[Inscripción de dispositivos](/azure/active-directory/devices/overview)|Inscribe un dispositivo en Azure AD para crear una identidad para el dispositivo. Esta identidad se usa para autenticar el dispositivo cuando un usuario inicia sesión y para aplicar directivas de acceso condicional que requieren equipos unidos a un dominio o compatibles. Para esta guía, usamos la inscripción de dispositivos para inscribir automáticamente equipos Windows unidos a un dominio. La inscripción de dispositivos es un requisito previo para administrar dispositivos con Intune.|Microsoft 365 E3 o E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Permite detectar posibles vulnerabilidades que afectan a las identidades de su organización y configurar la directiva de corrección automatizada en riesgo de inicio de sesión bajo, medio y alto y riesgo de usuario. Esta guía se basa en esta evaluación de riesgos para aplicar directivas de acceso condicional para la autenticación multifactor. Esta guía también incluye una directiva de acceso condicional que requiere que los usuarios cambien su contraseña si se detecta actividad de alto riesgo para su cuenta.|Microsoft 365 E5, Microsoft 365 E3 con el complemento de seguridad E5, EMS E5 o licencias de Azure AD Premium P2|
|[Autoservicio de restablecimiento de contraseña (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Permitir que los usuarios restablezcan sus contraseñas de forma segura y sin intervención del departamento de soporte técnico, proporcionando la comprobación de varios métodos de autenticación que el administrador puede controlar.|Microsoft 365 E3 o E5|
|[Protección con contraseña de Azure AD](/azure/active-directory/authentication/concept-password-ban-bad)|Detecte y bloquee contraseñas débiles conocidas y sus variantes y términos débiles adicionales específicos de su organización. Las listas de contraseñas desvetadas global predeterminada se aplican automáticamente a todos los usuarios de un inquilino de Azure AD. Se puede definir entradas adicionales en una lista personalizada de contraseñas prohibidas. Cuando los usuarios cambien o restablezcan sus contraseñas, estas listas de contraseñas prohibidas se comprueban para exigir el uso de contraseñas seguras.|Microsoft 365 E3 o E5|

Estos son los componentes de Confianza cero identidad y acceso al dispositivo, incluidos los objetos, la configuración y los subservicios Intune y Azure AD.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-components.png" alt-text="Componentes de Confianza cero identidad y acceso al dispositivo" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-components.png":::

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](/intune/introduction-intune) es el servicio de administración de dispositivos móviles basado en la nube de Microsoft. En esta guía se recomienda la administración de dispositivos de equipos Windows con Intune y se recomiendan las configuraciones de directivas de cumplimiento de dispositivos. Intune determina si los dispositivos son compatibles y envía estos datos a Azure AD para usarlos al aplicar directivas de acceso condicional.

#### <a name="intune-app-protection"></a>Intune protección de aplicaciones

[Intune directivas de protección](/intune/app-protection-policy) de aplicaciones se pueden usar para proteger los datos de su organización en aplicaciones móviles, con o sin inscribir dispositivos en la administración. Intune ayuda a proteger la información, a asegurarse de que los empleados pueden seguir siendo productivos y a evitar la pérdida de datos. Al implementar directivas de nivel de aplicación, puede restringir el acceso a los recursos de la empresa y mantener los datos bajo el control del departamento de TI.

En esta guía se muestra cómo crear directivas recomendadas para aplicar el uso de aplicaciones aprobadas y determinar cómo se pueden usar estas aplicaciones con los datos empresariales.

### <a name="microsoft-365"></a>Microsoft 365

En esta guía se muestra cómo implementar un conjunto de directivas para proteger el acceso a los servicios en la nube de Microsoft 365, incluidos Microsoft Teams, Exchange, SharePoint y OneDrive. Además de implementar estas directivas, se recomienda aumentar también el nivel de protección para el inquilino mediante estos recursos:

- [Configurar su espacio empresarial para aumentar la seguridad](tenant-wide-setup-for-increased-security.md)

### <a name="windows-11-or-windows-10-with-microsoft-365-apps-for-enterprise"></a>Windows 11 o Windows 10 con Aplicaciones Microsoft 365 para empresas

Windows 11 o Windows 10 con Aplicaciones Microsoft 365 para empresas es el entorno de cliente recomendado para equipos. Se recomienda Windows 11 o Windows 10 porque Azure está diseñado para proporcionar la experiencia más fluida posible tanto en el entorno local como en Azure AD. Windows 11 o Windows 10 también incluye funcionalidades de seguridad avanzadas que se pueden administrar a través de Intune. Aplicaciones Microsoft 365 para empresas incluye las versiones más recientes de las aplicaciones de Office. Estos usan la autenticación moderna, que es más segura y un requisito para el acceso condicional. Estas aplicaciones también incluyen herramientas de cumplimiento y seguridad mejoradas.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Aplicación de estas funcionalidades en los tres niveles de protección

En la tabla siguiente se resumen nuestras recomendaciones para usar estas funcionalidades en los tres niveles de protección.

|Mecanismo de protección|Punto de inicio|Enterprise|Seguridad especializada|
|---|---|---|---|
|**Exigir MFA**|En riesgo de inicio de sesión medio o superior|En riesgo de inicio de sesión bajo o superior|En todas las sesiones nuevas|
|**Aplicar el cambio de contraseña**|Para usuarios de alto riesgo|Para usuarios de alto riesgo|Para usuarios de alto riesgo|
|**Aplicación de Intune protección de aplicaciones**|Sí|Sí|Sí|
|**Exigir la inscripción de Intune para el dispositivo propiedad de la organización**|Requerir un equipo compatible o unido a un dominio, pero permitir teléfonos y tabletas bring-your-own devices (BYOD)|Requerir un dispositivo compatible o unido a un dominio|Requerir un dispositivo compatible o unido a un dominio|

## <a name="device-ownership"></a>Propiedad del dispositivo

En la tabla anterior se refleja la tendencia de muchas organizaciones a admitir una combinación de dispositivos propiedad de la organización, así como personal o BYOD para permitir la productividad móvil en todo el personal. Intune directivas de protección de aplicaciones garantizan que el correo electrónico esté protegido frente a la filtración fuera de la aplicación móvil de Outlook y otras aplicaciones móviles de Office, tanto en dispositivos propiedad de la organización como en BYOD.

Se recomienda administrar los dispositivos propiedad de la organización mediante Intune o unidos a un dominio para aplicar protecciones y controles adicionales. En función de la confidencialidad de los datos, su organización puede optar por no permitir BYOD para poblaciones de usuarios específicas o aplicaciones específicas.

## <a name="deployment-and-your-apps"></a>Implementación y aplicaciones

Antes de configurar e implementar Confianza cero configuración de acceso a dispositivos e identidades para las aplicaciones integradas en Azure AD, debe:

- Decida qué aplicaciones se usan en su organización que desea proteger.
- Analice esta lista de aplicaciones para determinar los conjuntos de directivas que proporcionan los niveles adecuados de protección.

  No debe crear conjuntos de directivas independientes para cada aplicación porque la administración de ellas puede resultar complicada. Microsoft recomienda agrupar las aplicaciones que tengan los mismos requisitos de protección para los mismos usuarios.

  Por ejemplo, podría tener un conjunto de directivas que incluyan todas las aplicaciones de Microsoft 365 para todos los usuarios para la protección de punto de partida y un segundo conjunto de directivas para todas las aplicaciones confidenciales, como las que usan los recursos humanos o los departamentos financieros, y aplicarlas a esos grupos.

Una vez que haya determinado el conjunto de directivas para las aplicaciones que desea proteger, implemente las directivas para los usuarios de forma incremental y solucione los problemas a lo largo del proceso.

Por ejemplo, configure las directivas que se usarán para todas las aplicaciones de Microsoft 365 solo para Exchange con los cambios adicionales para Exchange. Implemente estas directivas para los usuarios y trabaje con cualquier problema. A continuación, agregue Teams con sus cambios adicionales y implemente esto a los usuarios. A continuación, agregue SharePoint con sus cambios adicionales. Continúe agregando el resto de las aplicaciones hasta que pueda configurar con confianza estas directivas de punto de partida para incluir todas las aplicaciones de Microsoft 365.

Del mismo modo, en el caso de las aplicaciones confidenciales, cree el conjunto de directivas y agregue una aplicación a la vez y trabaje con cualquier problema hasta que se incluyan en el conjunto de directivas de aplicaciones confidenciales.

Microsoft recomienda no crear conjuntos de directivas que se apliquen a todas las aplicaciones porque puede dar lugar a algunas configuraciones no intencionadas. Por ejemplo, las directivas que bloquean todas las aplicaciones podrían bloquear a los administradores fuera de la Azure Portal y las exclusiones no se pueden configurar para puntos de conexión importantes como Microsoft Graph.

## <a name="steps-to-configure-zero-trust-identity-and-device-access"></a>Pasos para configurar Confianza cero identidad y acceso al dispositivo

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-steps.png" alt-text="Los pasos para configurar Confianza cero identidad y acceso al dispositivo" lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-steps.png":::

1. Configure las características de identidad de requisitos previos y sus opciones.
2. Configure las directivas comunes de acceso condicional de identidad y acceso.
3. Configure directivas de acceso condicional para usuarios invitados y externos.
4. Configure directivas de acceso condicional para aplicaciones&mdash;en la nube de Microsoft 365 como Microsoft Teams, Exchange y SharePoint&mdash;y directivas de Microsoft Defender for Cloud Apps.

Después de configurar Confianza cero acceso a identidades y dispositivos, consulte la guía de [implementación de características de Azure AD](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) para obtener una lista de comprobación por fases de características adicionales que se deben tener en cuenta y [Gobernanza de identidades de Azure AD](/azure/active-directory/governance/) para proteger, supervisar y auditar el acceso.

## <a name="next-step"></a>Paso siguiente

[Trabajo de requisitos previos para implementar directivas de acceso a dispositivos e identidades de Confianza cero](identity-access-prerequisites.md)
