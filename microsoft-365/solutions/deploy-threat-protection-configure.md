---
title: Pasos para configurar las capacidades de protección contra amenazas en Microsoft 365
description: Use este artículo como guía para implementar la solución de protección contra amenazas. Implemente funciones y servicios de protección contra amenazas en Microsoft 365 E5.
keywords: seguridad, configuración, configuración, Microsoft 365 E5, protección contra amenazas avanzada
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 847dd2d090fb26c5558d4a3496a79cf4829881fb
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604398"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Configurar las capacidades de protección contra amenazas en Microsoft 365

Siga estos pasos para configurar la protección contra amenazas en Microsoft 365.

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Paso 1: Configurar la autenticación multifactor y las directivas de acceso condicional

[La autenticación multifactor](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) requiere que los usuarios comprueben su identidad con una llamada telefónica o una aplicación de autenticación. [Las directivas de acceso](/azure/active-directory/conditional-access/overview) condicional definen ciertos requisitos que deben cumplirse para que los usuarios puedan acceder a aplicaciones y datos en Microsoft 365. Mfa y las directivas de acceso condicional funcionan conjuntamente para proteger su organización. Por ejemplo, si alguien intenta iniciar sesión desde un dispositivo móvil con una cuenta que no está habilitada para MFA y una directiva de acceso condicional requiere que MFA esté en vigor, ese usuario no podrá iniciar sesión.  

Microsoft ha probado y recomienda un conjunto específico de directivas relacionadas y acceso condicional para proteger el acceso a todas las aplicaciones SaaS, especialmente Microsoft 365. Las directivas se recomiendan para la protección de línea base, confidencial y altamente regulada. Comience implementando las directivas para la protección de línea base. 


[ ![ Directivas comunes para configurar la identidad y el acceso](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [a dispositivos Vea una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Para implementar la protección de línea base para Microsoft 365

![Proceso para implementar la protección de línea base](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [Configure los requisitos previos, incluido Azure AD Identity Protection](../security/office-365-security/identity-access-prerequisites.md).
2. [Configure directivas comunes de acceso a dispositivos y identidades](../security/office-365-security/identity-access-policies.md) para la protección de línea base.
3. Configurar directivas para [usuarios invitados,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)y [SharePoint Online y OneDrive](../security/office-365-security/sharepoint-file-access-policies.md).

### <a name="more-information-about-protecting-identities"></a>Más información sobre la protección de identidades

- [Configuraciones de acceso a dispositivos e identidades](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Instrucciones de seguridad para Azure MFA](/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Paso 2: Configurar Microsoft Defender para identidad

[Microsoft Defender for Identity](/defender-for-identity/what-is) es una solución de seguridad basada en la nube que funciona con las señales locales de Servicios de dominio de Active Directory (AD DS) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización.

Microsoft Defender for Identity permite a los analistas y profesionales de seguridad de operaciones de seguridad (SecOps) que tienen dificultades para detectar ataques avanzados en entornos híbridos para:
- Supervisar usuarios, comportamiento de entidad y actividades con análisis basados en aprendizaje.
- Proteger las identidades de usuario y las credenciales almacenadas en Active Directory.
- Identificar e investigar actividades de usuarios sospechosas y ataques avanzados en la cadena de eliminación.
- Proporcionar información clara sobre el incidente en una escala de tiempo simple para una evaluación rápida.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Para configurar Microsoft Defender for Identity

![Proceso para implementar Microsoft Defender for Identity](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. [Configure Microsoft Defender for Identity para](/azure-advanced-threat-protection/install-atp-step1) proteger los entornos principales.
2. Proteger todos los [controladores de dominio](/azure-advanced-threat-protection/atp-sensor-monitoring) y [bosques](/azure-advanced-threat-protection/atp-multi-forest).
3. Integre [alertas de Microsoft Defender para identidades](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) en el flujo de trabajo de operaciones de seguridad (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Más información sobre Microsoft Defender for Identity

- [¿Qué es Microsoft Defender for Identity?](/azure-advanced-threat-protection/what-is-atp)
- [Vídeo: Introducción a Microsoft Defender for Identity](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Implementación de Microsoft Defender para identidades](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Paso 3: Activar Microsoft 365 Defender

[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md) combina las señales y orquesta las capacidades en una única solución. Con la solución integrada de Microsoft 365 Defender, los profesionales de seguridad pueden unir las señales de amenaza que cada uno de estos productos recibe y determinar el alcance completo y el impacto de la amenaza; cómo entró en el entorno, lo que está afectado y cómo está afectando actualmente a la organización. Microsoft 365 Defender realiza acciones automáticas para evitar o detener el ataque y auto-sanar los buzones, puntos de conexión e identidades de usuario afectados.

Microsoft 365 Defender unifica alertas, incidentes, investigación y respuesta automatizadas y búsqueda avanzada entre cargas de trabajo (Microsoft Defender para la identidad, Microsoft Defender para Office 365, Microsoft Defender para endpoint y Microsoft Cloud App Security) en un único panel de experiencia de cristal. Las nuevas características se agregan continuamente a Microsoft 365 Defender; considere la posibilidad de participar para recibir características de vista previa.

### <a name="to-set-up-microsoft-365-defender"></a>Para configurar Microsoft 365 Defender

![Proceso para implementar Microsoft 365 Defender](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [Revise los requisitos previos](../security/defender/prerequisites.md).
2. [Active Microsoft 365 Defender](../security/defender/m365d-enable.md).
3. [Opt in for preview features](../security/defender/preview.md).

### <a name="more-information-about-microsoft-365-defender"></a>Más información sobre Microsoft 365 Defender

- [¿Qué es Microsoft 365 Defender?](../security/defender/microsoft-365-defender.md)
- [Novedades de Microsoft 365 Defender](../security/defender/whats-new.md)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Paso 4: Configurar Microsoft Defender para Office 365

[Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md) protege su organización contra amenazas malintencionadas en mensajes de correo electrónico (datos adjuntos y direcciones URL), documentos de Office y herramientas de colaboración. En la tabla siguiente se enumeran las características y capacidades de Microsoft Defender para Office 365 que se incluyen en Microsoft 365 E5:

|Capacidades de configuración, protección y detección|Capacidades de automatización, investigación, corrección y educación|
|:---|:---|
|[Archivos adjuntos seguros](../security/office-365-security/safe-attachments.md)<br/>[Vínculos seguros](../security/office-365-security/safe-links.md)<br/>[Documentos seguros](../security/office-365-security/safe-docs.md)<br/>[ATP para SharePoint, OneDrive y Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md)<br/> [Protección contra suplantación de identidad (phishing) en Microsoft 365](../security/office-365-security/anti-phishing-protection.md)|[Rastreadores de amenazas](../security/office-365-security/threat-trackers.md)<br/>[Explorador de amenazas](../security/office-365-security/threat-explorer.md)<br/>[Investigación y respuesta automatizadas](../security/office-365-security/office-365-air.md)<br/>[Simulador de ataque](../security/office-365-security/attack-simulator.md)|
|

Con Microsoft Defender para Office 365, los usuarios de toda la organización pueden comunicarse y colaborar de forma más segura, con protección contra amenazas para su contenido de correo electrónico y documentos de Office.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Para configurar Microsoft Defender para Office 365

![Proceso para implementar Microsoft Defender para Office 365](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. Configurar y configurar las directivas de [Microsoft Defender para Office 365](../security/office-365-security/protect-against-threats.md).
2. [Ver y usar los informes de Microsoft Defender para Office 365](../security/office-365-security/view-reports-for-mdo.md).
3. [Usar capacidades de investigación y respuesta de amenazas](../security/office-365-security/office-365-ti.md).

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Más información sobre Microsoft Defender para Office 365

- [Introducción a Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md)
- [Novedades de Microsoft Defender para Office 365](../security/office-365-security/whats-new-in-defender-for-office-365.md)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Paso 5: Configurar Microsoft Defender para endpoint

[Microsoft Defender para endpoint](/windows/security/threat-protection) protege los dispositivos de la organización (también denominados puntos de conexión) de ciberamenazas, ataques avanzados e infracciones de datos. Los equipos de seguridad pueden ser más eficientes en la administración de la seguridad de sus puntos de conexión. Las herramientas sólidas ayudan a las organizaciones a mantenerse al día con los sistemas no apareados mediante la detección de vulnerabilidades con la administración de [amenazas y vulnerabilidades.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Las capacidades automatizadas de detección y corrección, [](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)como la reducción de superficie de [ataque,](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)la protección de última generación, [](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)la detección y respuesta de puntos de conexión y la investigación y corrección automatizadas ayudan a mantener los dispositivos a salvo de malware. [](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) Además de estas capacidades, los clientes pueden recibir notificaciones proactivas y consultar con expertos en amenazas de Microsoft a petición, como parte del servicio de búsqueda administrada de participación. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Configurar Microsoft Defender para endpoint

![Proceso para implementar Microsoft Defender para endpoint](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. [Prepare su entorno para Microsoft Defender para Endpoint](../security/defender-endpoint/deployment-phases.md).

2. [Implementar Microsoft Defender para endpoint](../security/defender-endpoint/production-deployment.md).

3. [Incorporación al servicio de Microsoft Defender para puntos de conexión](../security/defender-endpoint/onboarding.md).

4. [Complete las tareas administrativas de seguridad superior](../security/defender-endpoint/tvm-security-recommendation.md).

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Más información sobre Microsoft Defender para endpoint

- [Obtenga más información sobre Microsoft Defender para endpoint](../security/defender-endpoint/microsoft-defender-endpoint.md).
- [Pruebe el laboratorio de evaluación de Microsoft Defender para endpoints](../security/defender-endpoint/evaluation-lab.md).

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Paso 6: Configurar Microsoft Cloud App Security

[Microsoft Cloud App Security es](/cloud-app-security) un agente de seguridad de Cloud Access que admite la recopilación de registros, conectores de API y proxy inverso. Microsoft Cloud App Security proporciona una amplia visibilidad, control sobre los viajes de datos y análisis sofisticados para identificar y combatir las ciberamenazas en todos los servicios en la nube. Con Microsoft Cloud App Security, las operaciones de seguridad pueden proteger la información confidencial de la organización, protegerse contra ciberamenazas y anomalías, detectar y supervisar aplicaciones que tienen acceso a los datos de la organización y ayudar a garantizar que las aplicaciones en la nube de la organización cumplan los requisitos de cumplimiento.

### <a name="set-up-microsoft-cloud-app-security"></a>Configurar Microsoft Cloud App Security

![Proceso para implementar Microsoft Cloud App Security](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [Configurar el portal y otros requisitos básicos](/cloud-app-security/general-setup).

2. [Configurar la detección en la nube](/cloud-app-security/set-up-cloud-discovery) [y conectar aplicaciones](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).

3. [Implementar control de aplicaciones de acceso condicional para aplicaciones características.](/cloud-app-security/proxy-deployment-aad)

4. [Use las herramientas de investigación y los paneles](/cloud-app-security/investigate).

### <a name="more-information-about-microsoft-cloud-app-security"></a>Más información sobre Microsoft Cloud App Security

- [Revisar nuevas características y funcionalidades](/cloud-app-security/release-notes).
- [Obtenga más información sobre Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Paso 7: Supervisar el estado y realizar acciones

Después de configurar e implementar los servicios y capacidades de protección contra amenazas, el siguiente paso es supervisar las detecciones de amenazas y realizar las acciones adecuadas. El mejor punto de partida es el Centro de seguridad de Microsoft 365 ( ), donde puede supervisar y administrar la seguridad en todas las identidades, datos, dispositivos, aplicaciones e infraestructura de [https://security.microsoft.com](https://security.microsoft.com) Microsoft. 

![Centro de seguridad de Microsoft 365](../media/solutions-architecture-center/m365-security-center.png)

El Centro de seguridad de Microsoft 365 está pensado para administradores de seguridad y equipos de operaciones de seguridad. En el Centro de seguridad de Microsoft 365, puede:
- Ver el estado de seguridad general de su organización con [Puntuación segura](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-secure-score).
- [Supervisar y ver informes sobre](../security/defender-endpoint/threat-protection-reports.md) el estado de las identidades, los datos, los dispositivos, las aplicaciones y la infraestructura.
- Conectar los puntos en alertas a través [de incidentes](https://docs.microsoft.com/microsoft-365/security/defender/incident-queue).
- Use [la investigación automatizada y la corrección para](../security/defender/m365d-autoir.md) solucionar las amenazas.
- [Busca de forma proactiva amenazas,](https://docs.microsoft.com/microsoft-365/security/defender/advanced-hunting-overview)como intentos de intrusión o actividad de infracción que afecten al correo electrónico, los datos, los dispositivos y las identidades.
- [Comprenda las últimas campañas y](https://docs.microsoft.com/microsoft-365/security/defender/latest-attack-campaigns) técnicas de ataque con análisis de amenazas.
- ... y mucho más.

### <a name="more-information-about-the-microsoft-365-security-center"></a>Más información sobre el Centro de seguridad de Microsoft 365

- [Introducción al Centro de seguridad de Microsoft 365](../security/defender/overview-security-center.md).
- [Supervisar y ver informes](../security/defender/overview-security-center.md).
- [Vea los portales de seguridad en Microsoft 365](../security/defender/portals.md).

## <a name="step-8-train-users"></a>Paso 8: Entrenar usuarios

La formación de los usuarios puede ahorrar mucho tiempo y frustración a los usuarios y al equipo de operaciones de seguridad. Los usuarios expertos tienen menos probabilidades de abrir datos adjuntos o hacer clic en vínculos en mensajes de correo electrónico cuestionables, y es más probable que eviten sitios web sospechosos. 

El Manual [](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) de la campaña de ciberseguridad de la Escuela Kennedy de Harvard proporciona excelentes instrucciones para establecer una cultura sólida de concienciación de seguridad en su organización, incluida la formación de los usuarios para identificar los ataques de suplantación de identidad. 

Microsoft 365 proporciona los siguientes recursos para ayudar a informar a los usuarios de su organización:

|Concepto  |Recursos  |
|---------|---------|
|Microsoft 365     |[Caminos de aprendizaje personalizables](/office365/customlearning/) <p>Estos recursos pueden ayudarle a crear formación para los usuarios finales de su organización        |
|Centro de seguridad de Microsoft 365 |[Módulo de aprendizaje: proteger la organización con seguridad inteligente integrada de Microsoft 365](/learn/modules/security-with-microsoft-365) <p>Este módulo le permite describir cómo funcionan conjuntamente las características de seguridad de Microsoft 365 y para expresar las ventajas de estas características de seguridad. |
|Autenticación multifactor     | [Comprobación en dos pasos: ¿Cuál es la página de verificación adicional?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Este artículo ayuda a los usuarios finales a comprender qué es la autenticación multifactor y por qué se usa en su organización.    |

Además de esta guía, Microsoft recomienda que los usuarios tomen las acciones descritas en este artículo: Proteger su cuenta y dispositivos de [los piratas informáticos y malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Entre estas acciones se incluyen:
- Uso de contraseñas seguras
- Protección de dispositivos 
- Habilitar características de seguridad en equipos Windows 10 y Mac (para dispositivos no administrados)
    
Microsoft también recomienda a los usuarios proteger sus cuentas de correo electrónico personales mediante las acciones recomendadas en los siguientes artículos:
- [Ayudar a proteger su Outlook.com de correo electrónico](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Proteger tu cuenta de Gmail con la comprobación de 2 pasos](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
