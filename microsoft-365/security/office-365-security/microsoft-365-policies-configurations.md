---
title: 'Configuración de acceso a dispositivos y identidad de confianza cero: Microsoft 365 para empresas'
description: Describe las recomendaciones de Microsoft y los conceptos básicos para implementar directivas y configuraciones seguras de correo electrónico, documentos y aplicaciones para La confianza cero.
ms.author: dansimp
author: dansimp
manager: dansimp
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
- m365solution-zero-trust
ms.technology: mdo
ms.openlocfilehash: abfd2603d4b374899ba3ff17d1be977043c5d5ab
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313039"
---
# <a name="zero-trust-identity-and-device-access-configurations"></a>Configuraciones de identidad y acceso a dispositivos de Confianza cero

Las arquitecturas de seguridad que dependen de firewalls de red y redes privadas virtuales (VPN) para aislar y restringir el acceso a los recursos y servicios tecnológicos de una organización ya no son suficientes para un personal que requiere regularmente acceso a aplicaciones y recursos que existen más allá de los límites tradicionales de la red corporativa.

Para abordar este nuevo mundo de la informática, Microsoft recomienda encarecidamente el modelo de seguridad De confianza cero, que se basa en estos principios guía:

- Comprobar explícitamente

  Autentique y autorice siempre en función de todos los puntos de datos disponibles. Aquí es donde las directivas de identidad de confianza cero y de acceso a dispositivos son cruciales para iniciar sesión y la validación continua.

- Usar acceso con privilegios mínimos

  Limite el acceso de los usuarios con Just-In-Time y Just-Enough-Access (JIT/JEA), directivas adaptables basadas en riesgos y protección de datos.  

- Asumir infracción

  Minimizar el radio de explosión y el acceso de segmentos. Compruebe el cifrado de un extremo a otro y use análisis para obtener visibilidad, impulsar la detección de amenazas y mejorar las defensas.

Esta es la arquitectura general de La confianza cero.

:::image type="content" source="../../media/microsoft-365-policies-configurations/zero-trust-architecture.png" alt-text="La arquitectura de confianza cero de Microsoft" lightbox="../../media/microsoft-365-policies-configurations/zero-trust-architecture.png":::

Las directivas de identidad de confianza cero y acceso a dispositivos abordan **el** principio de guía Comprobar explícitamente para:

- Identidades

  Cuando una identidad intenta obtener acceso a un recurso, compruebe esa identidad con autenticación segura y asegúrese de que el acceso solicitado es compatible y típico.

- Dispositivos (también denominados puntos de conexión)

  Supervisar y aplicar los requisitos de cumplimiento y estado del dispositivo para el acceso seguro.

- Aplicaciones

  Aplicar controles y tecnologías para detectar ti de instantánea, garantizar los permisos adecuados desde la aplicación, el acceso de puerta basado en análisis en tiempo real, supervisar comportamientos anormales, controlar las acciones del usuario y validar opciones de configuración seguras.

En esta serie de artículos se describe un conjunto de configuraciones de requisitos previos de acceso a dispositivos y identidades y un conjunto de directivas de acceso condicional de Azure Active Directory (Azure AD), Microsoft Intune y otras directivas para el acceso de confianza cero a Microsoft 365  para servicios y aplicaciones de nube empresariales, otros servicios SaaS y aplicaciones locales publicadas con Azure AD proxy de aplicación.

La configuración y las directivas de acceso a dispositivos y identidad de confianza cero se recomiendan en tres niveles: punto de partida, seguridad empresarial y especializada para entornos con datos altamente regulados o clasificados. Estos niveles y sus configuraciones correspondientes proporcionan niveles coherentes de protección de confianza cero en todos los datos, identidades y dispositivos.

Estas funcionalidades y sus recomendaciones:

- Se admiten en Microsoft 365 E3 y Microsoft 365 E5.
- Se alinean con [la puntuación segura de Microsoft](../defender/microsoft-secure-score.md), así como con la puntuación de [identidad en Azure AD](/azure/active-directory/fundamentals/identity-secure-score) y aumentarán estas puntuaciones para su organización.
- Le ayudará a implementar estos [cinco pasos para proteger su infraestructura de identidad](/azure/security/azure-ad-secure-steps).

Si su organización tiene requisitos de entorno únicos o complejidades, use estas recomendaciones como punto de partida. Sin embargo, la mayoría de las organizaciones pueden implementar estas recomendaciones según lo prescrito.

Vea este vídeo para obtener una introducción rápida a las configuraciones de acceso a dispositivos y identidades Microsoft 365 para empresas.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxEDQ]

> [!NOTE]
> Microsoft también vende licencias Enterprise Mobility + Security (EMS) para Office 365 suscripciones. Las capacidades de EMS E3 y EMS E5 son equivalentes a las de Microsoft 365 E3 y Microsoft 365 E5. Para [obtener más información, vea Planes](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/compare-plans-and-pricing) ems.

## <a name="intended-audience"></a>Público objetivo

Estas recomendaciones están dirigidas a arquitectos empresariales y profesionales de TI familiarizados con los servicios de seguridad y productividad de la nube de Microsoft 365, que incluyen Azure AD (identidad), Microsoft Intune (administración de dispositivos) y Microsoft Information Protection ( protección de datos).

### <a name="customer-environment"></a>Entorno del cliente

Las directivas recomendadas se aplican a las organizaciones empresariales que operan completamente en la nube de Microsoft y a los clientes con infraestructura de identidad híbrida, que es un bosque local de Servicios de dominio de Active Directory (AD DS) que se sincroniza con un inquilino de Azure AD.

Muchas de las recomendaciones proporcionadas dependen de los servicios disponibles solo con Microsoft 365 E5, Microsoft 365 E3 con el complemento de seguridad E5, EMS E5 o Azure AD Premium P2 licencias.

Para aquellas organizaciones que no tienen estas licencias, Microsoft recomienda implementar al menos los valores predeterminados de [seguridad, que](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se incluyen en todos los planes Microsoft 365 licencias.

### <a name="caveats"></a>Advertencias

Su organización puede estar sujeta a requisitos normativos u otros requisitos de cumplimiento, incluidas recomendaciones específicas que pueden requerir que aplique directivas que difieren de estas configuraciones recomendadas. Estas configuraciones recomiendan controles de uso que históricamente no han estado disponibles. Se recomiendan estos controles porque creemos que representan un equilibrio entre seguridad y productividad.

Hemos hecho todo lo posible para tener en cuenta una amplia variedad de requisitos de protección de la organización, pero no podemos tener en cuenta todos los requisitos posibles ni todos los aspectos únicos de su organización.

## <a name="three-tiers-of-protection"></a>Tres niveles de protección

La mayoría de las organizaciones tienen requisitos concretos relacionados con la seguridad y la protección de datos. Estos requisitos varían dentro de las organizaciones según el segmento sectorial y las funciones de trabajo. Por ejemplo, el departamento jurídico y los administradores pueden requerir controles adicionales de seguridad y protección de la información en torno a su correspondencia de correo electrónico que no son necesarios para otras unidades de negocio.

Cada sector además tiene su propio conjunto de normas especializadas. En lugar de proporcionar una lista de todas las opciones de seguridad posibles o una recomendación por segmento del sector o función de trabajo, se han proporcionado recomendaciones para tres niveles diferentes de seguridad y protección que se pueden aplicar en función de la granularidad de sus necesidades.

- **Punto de** partida: se recomienda que todos los clientes establezcan y usen un estándar mínimo para proteger los datos, así como las identidades y los dispositivos que tienen acceso a los datos. Puede seguir estas recomendaciones para proporcionar una protección predeterminada sólida como punto de partida para todas las organizaciones.
- **Enterprise**: algunos clientes tienen un subconjunto de datos que deben protegerse en niveles superiores o pueden requerir que todos los datos estén protegidos en un nivel superior. Puede aplicar una mayor protección a todos o conjuntos de datos específicos de su Microsoft 365 entorno. Se recomienda proteger las identidades y los dispositivos que acceden a información confidencial con niveles de seguridad comparables.
- **Seguridad especializada**: según sea necesario, algunos clientes tienen una pequeña cantidad de datos altamente clasificados, constituyen secretos comerciales o están regulados. Microsoft proporciona funcionalidades para ayudar a estos clientes a cumplir estos requisitos, incluida la protección adicional para identidades y dispositivos.

![Cono de seguridad: todos los > algunos clientes > Algunos clientes](../../media/microsoft-365-policies-configurations/M365-idquality-threetiers.png)

En esta guía se muestra cómo implementar la protección de confianza cero para identidades y dispositivos para cada uno de estos niveles de protección. Use esta guía como mínimo para su organización y ajuste las directivas para satisfacer los requisitos específicos de su organización.

Es importante usar niveles coherentes de protección en todas las identidades, dispositivos y datos. Por ejemplo,&mdash; la protección para usuarios con cuentas de prioridad como ejecutivos, líderes,&mdash; administradores y otros debería incluir el mismo nivel de protección para sus identidades, sus dispositivos y los datos a los que tienen acceso. 
<!--

The **Zero Trust identity and device protection for Microsoft 365** architecture model shows you which capabilities are comparable.

[![Thumb image for Zero Trust Identity and device protection for Microsoft 365 poster.](../../media/microsoft-365-policies-configurations/zero-trust-id-device-protection-model-thumbnail.png)](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) <br> [View as a PDF](../../downloads/MSFT_cloud_architecture_identity&device_protection.pdf) \| [Download as a PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.pdf)  \| [Download as a Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT_cloud_architecture_identity&device_protection.vsdx)

--> 

Además, vea la solución [Deploy information protection for data privacy regulations](../../solutions/information-protection-deploy.md) para proteger la información almacenada en Microsoft 365.

## <a name="security-and-productivity-trade-offs"></a>Equilibrio entre seguridad y productividad

La implementación de cualquier estrategia de seguridad requiere equilibrios entre la seguridad y la productividad. Es útil evaluar cómo afecta cada decisión al equilibrio de seguridad, funcionalidad y facilidad de uso.

![Equilibrio de la tríada de seguridad, la funcionalidad y la facilidad de uso.](../../media/microsoft-365-policies-configurations/security-triad.png)

Las recomendaciones proporcionadas se basan en los siguientes principios:

- Conozca a los usuarios y sea flexible a sus requisitos de seguridad y funcionalidad.
- Aplique una directiva de seguridad justo a tiempo y asegúrese de que es significativa.

## <a name="services-and-concepts-for-zero-trust-identity-and-device-access-protection"></a>Servicios y conceptos para la identidad de confianza cero y la protección de acceso a dispositivos

Microsoft 365 para empresas está diseñado para que las grandes organizaciones puedan habilitar a todos para que sean creativos y trabajen juntos de forma segura.

En esta sección se proporciona información general sobre Microsoft 365 servicios y funcionalidades que son importantes para el acceso a dispositivos y identidades de confianza cero.

### <a name="azure-ad"></a>Azure AD

Azure AD proporciona un conjunto completo de funcionalidades de administración de identidades. Se recomienda usar estas funcionalidades para proteger el acceso.

|Funcionalidad o característica|Description|Licencias|
|---|---|---|
|[Autenticación multifactor (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks)|MFA requiere que los usuarios proporcionen dos formas de comprobación, como una contraseña de usuario más una notificación de la aplicación Microsoft Authenticator o una llamada de teléfono. MFA reduce en gran medida el riesgo de que las credenciales robadas se puedan usar para obtener acceso al entorno. Microsoft 365 el servicio Azure AD multifactor authentication para inicios de sesión basados en MFA.|Microsoft 365 E3 o E5|
|[Acceso condicional](/azure/active-directory/conditional-access/overview)|Azure AD evalúa las condiciones del inicio de sesión del usuario y usa directivas de acceso condicional para determinar el acceso permitido. Por ejemplo, en esta guía te mostramos cómo crear una directiva de acceso condicional para requerir el cumplimiento del dispositivo para obtener acceso a datos confidenciales. Esto reduce en gran medida el riesgo de que un hacker con su propio dispositivo y credenciales robadas pueda acceder a sus datos confidenciales. También protege los datos confidenciales de los dispositivos, ya que los dispositivos deben cumplir requisitos específicos de salud y seguridad.|Microsoft 365 E3 o E5|
|[Azure AD grupos](/azure/active-directory/fundamentals/active-directory-manage-groups)|Las directivas de acceso condicional, la administración de dispositivos con Intune e incluso los permisos para archivos y sitios de la organización dependen de la asignación a cuentas de usuario o grupos Azure AD usuario. Se recomienda crear grupos Azure AD que correspondan a los niveles de protección que está implementando. Por ejemplo, es probable que el personal ejecutivo sea un destino de mayor valor para los hackers. Por lo tanto, tiene sentido agregar las cuentas de usuario de estos empleados a un grupo de Azure AD y asignar este grupo a directivas de acceso condicional y otras directivas que exijan un mayor nivel de protección para el acceso.|Microsoft 365 E3 o E5|
|[Inscripción de dispositivos](/azure/active-directory/devices/overview)|Inscribir un dispositivo en Azure AD para crear una identidad para el dispositivo. Esta identidad se usa para autenticar el dispositivo cuando un usuario inicia sesión y para aplicar directivas de acceso condicional que requieren equipos unidos al dominio o compatibles. Para esta guía, usamos la inscripción de dispositivos para inscribir automáticamente equipos unidos Windows dominio. La inscripción de dispositivos es un requisito previo para administrar dispositivos con Intune.|Microsoft 365 E3 o E5|
|[Azure AD Identity Protection](/azure/active-directory/identity-protection/overview)|Le permite detectar posibles vulnerabilidades que afectan a las identidades de su organización y configurar la directiva de corrección automatizada en riesgo de inicio de sesión bajo, medio y alto y riesgo de usuario. Esta guía se basa en esta evaluación de riesgos para aplicar directivas de acceso condicional para la autenticación multifactor. Esta guía también incluye una directiva de acceso condicional que requiere que los usuarios cambien su contraseña si se detecta actividad de alto riesgo para su cuenta.|Microsoft 365 E5, Microsoft 365 E3 con el complemento de seguridad E5, EMS E5 o Azure AD Premium P2 licencias|
|[Restablecimiento de contraseñas de autoservicio (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks)|Permitir que los usuarios restablezcan sus contraseñas de forma segura y sin intervención del servicio de asistencia, proporcionando la comprobación de varios métodos de autenticación que el administrador puede controlar.|Microsoft 365 E3 o E5|
|[Azure AD de contraseña](/azure/active-directory/authentication/concept-password-ban-bad)|Detectar y bloquear contraseñas débiles conocidas y sus variantes y términos débiles adicionales que son específicos de su organización. Las listas de contraseñas desvetadas global predeterminada se aplican automáticamente a todos los usuarios de un inquilino de Azure AD. Se puede definir entradas adicionales en una lista personalizada de contraseñas prohibidas. Cuando los usuarios cambien o restablezcan sus contraseñas, estas listas de contraseñas prohibidas se comprueban para exigir el uso de contraseñas seguras.|Microsoft 365 E3 o E5|
|

Estos son los componentes de la identidad de confianza cero y el acceso a dispositivos, incluidos intune y Azure AD objetos, configuración y subservicios.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-components.png" alt-text="Componentes de identidad de confianza cero y acceso a dispositivos." lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-components.png":::

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](/intune/introduction-intune) es el servicio de administración de dispositivos móviles basado en la nube de Microsoft. En esta guía se recomienda la administración de dispositivos Windows equipos con Intune y se recomiendan las configuraciones de directivas de cumplimiento de dispositivos. Intune determina si los dispositivos son compatibles y envía estos datos a Azure AD usar al aplicar directivas de acceso condicional.

#### <a name="intune-app-protection"></a>Protección de aplicaciones de Intune

[Las directivas de protección de](/intune/app-protection-policy) aplicaciones de Intune se pueden usar para proteger los datos de la organización en aplicaciones móviles, con o sin inscribir dispositivos en la administración. Intune ayuda a proteger la información, garantizar que los empleados puedan seguir siendo productivos y evitar la pérdida de datos. Al implementar directivas de nivel de aplicación, puede restringir el acceso a los recursos de la empresa y mantener los datos bajo el control de su departamento de TI.

En esta guía se muestra cómo crear directivas recomendadas para aplicar el uso de aplicaciones aprobadas y determinar cómo se pueden usar estas aplicaciones con los datos empresariales.

### <a name="microsoft-365"></a>Microsoft 365

Esta guía muestra cómo implementar un conjunto de directivas para proteger el acceso a los servicios en la nube de Microsoft 365, incluidos Microsoft Teams, Exchange, SharePoint y OneDrive. Además de implementar estas directivas, te recomendamos que también eleves el nivel de protección para el espacio empresarial con estos recursos:

- [Configurar su espacio empresarial para aumentar la seguridad](tenant-wide-setup-for-increased-security.md)

  Recomendaciones que se aplican a la seguridad de punto de inicio para el inquilino.

- [Hoja de ruta de seguridad: prioridades principales para los primeros 30 días, 90 días y más allá](security-roadmap.md)

  Recomendaciones que incluyen el registro, el gobierno de datos, el acceso a los administradores y la protección contra amenazas.

### <a name="windows-11-or-windows-10-with-microsoft-365-apps-for-enterprise"></a>Windows 11 o Windows 10 con Aplicaciones Microsoft 365 para empresas

Windows 11 o Windows 10 con Aplicaciones Microsoft 365 para empresas es el entorno de cliente recomendado para equipos. Se recomienda Windows 11 o Windows 10 porque Azure está diseñado para proporcionar la experiencia más fluida posible tanto en el entorno local como en Azure AD. Windows 11 o Windows 10 también incluye funciones de seguridad avanzadas que se pueden administrar a través de Intune. Aplicaciones Microsoft 365 para empresas incluye las últimas versiones de Office aplicaciones. Estos usan la autenticación moderna, que es más segura y un requisito para el acceso condicional. Estas aplicaciones también incluyen herramientas mejoradas de seguridad y cumplimiento.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>Aplicar estas capacidades en los tres niveles de protección

En la tabla siguiente se resumen nuestras recomendaciones para usar estas funcionalidades en los tres niveles de protección.

|Mecanismo de protección|Punto de inicio|Empresa|Seguridad especializada|
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

Antes de configurar e implementar la configuración de acceso a dispositivos y identidad de confianza cero para las Azure AD integradas, debes:

- Decide qué aplicaciones se usan en la organización que quieres proteger.
- Analice esta lista de aplicaciones para determinar los conjuntos de directivas que proporcionan niveles de protección adecuados.

  No debes crear conjuntos de directivas independientes para cada aplicación, ya que la administración de ellas puede resultar engorrosa. Microsoft recomienda agrupar las aplicaciones que tienen los mismos requisitos de protección para los mismos usuarios.

  Por ejemplo, podría tener un conjunto de directivas que incluyan todas las aplicaciones de Microsoft 365 para todos los usuarios para la protección de punto inicial y un segundo conjunto de directivas para todas las aplicaciones confidenciales, como las que usan los departamentos de recursos humanos o finanzas, y aplicarlas a esos grupos.

Una vez que haya determinado el conjunto de directivas de las aplicaciones que desea proteger, revierte las directivas a los usuarios de forma incremental y a solucionar problemas en el camino.

Por ejemplo, configure las directivas que se usarán para todas las aplicaciones de Microsoft 365 solo para Exchange con los cambios adicionales para Exchange. Roll these policies out to your users and work through any issues. A continuación, Teams con sus cambios adicionales y revierte esto a los usuarios. A continuación, SharePoint con sus cambios adicionales. Continúa agregando el resto de tus aplicaciones hasta que puedas configurar con confianza estas directivas de punto de inicio para incluir todas las Microsoft 365 aplicaciones.

Del mismo modo, para las aplicaciones confidenciales, crea el conjunto de directivas y agrega una aplicación a la vez y trabaja con cualquier problema hasta que se incluyan todas en el conjunto de directivas de aplicaciones confidenciales.

Microsoft recomienda no crear conjuntos de directivas que se apliquen a todas las aplicaciones porque puede dar lugar a algunas configuraciones no deseadas. Por ejemplo, las directivas que bloquean todas las aplicaciones podrían bloquear a los administradores fuera de Azure Portal y las exclusiones no se pueden configurar para puntos de conexión importantes como Microsoft Graph.

## <a name="steps-to-configure-zero-trust-identity-and-device-access"></a>Pasos para configurar la identidad de confianza cero y el acceso a dispositivos

![Pasos para configurar la identidad de confianza cero y el acceso a dispositivos.](../../media/microsoft-365-policies-configurations/identity-device-access-steps.png)

1. Configure las características de identidad de requisitos previos y su configuración.
2. Configure las directivas comunes de acceso y identidad de acceso.
3. Configurar directivas de acceso condicional para usuarios invitados y externos.
4. Configurar directivas de acceso condicional para Microsoft 365&mdash; aplicaciones en la nube como Microsoft Teams, Exchange y SharePoint&mdash; y directivas de Microsoft Defender para aplicaciones en la nube.

Después de configurar la identidad de confianza cero y el acceso a dispositivos, consulta la guía de implementación de características de [Azure AD](/azure/active-directory/fundamentals/active-directory-deployment-checklist-p2) para obtener una lista de comprobación por fases de características adicionales para considerar y Azure AD [Identity Governance](/azure/active-directory/governance/) para proteger, supervisar y auditar el acceso.

## <a name="next-step"></a>Paso siguiente

[Trabajo previo para implementar directivas de identidad de confianza cero y acceso a dispositivos](identity-access-prerequisites.md)
