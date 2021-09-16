---
title: Pasos para configurar las capacidades de protección contra amenazas en Microsoft 365
description: Use este artículo como guía para implementar la solución de protección contra amenazas. Implemente funciones y servicios de protección contra amenazas en Microsoft 365 E5.
keywords: solución de seguridad, configuración, configuración, Microsoft 365 E5, protección contra amenazas avanzada, defender
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
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
ms.openlocfilehash: 32ee06e77b9c3f32e4bb9b07458925a254756d2d
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2021
ms.locfileid: "59401895"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Configurar las capacidades de protección contra amenazas en Microsoft 365

Siga estos pasos para configurar la protección contra amenazas en Microsoft 365.

## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Paso 1: Configurar la autenticación multifactor y las directivas de acceso condicional

[La autenticación multifactor](/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) requiere que los usuarios comprueben su identidad con una llamada telefónica o una aplicación de autenticación. [Las directivas de acceso](/azure/active-directory/conditional-access/overview) condicional definen ciertos requisitos que deben cumplirse para que los usuarios puedan acceder a aplicaciones y datos en Microsoft 365. Mfa y las directivas de acceso condicional funcionan conjuntamente para proteger su organización. Por ejemplo, si alguien intenta iniciar sesión desde un dispositivo móvil con una cuenta que no está habilitada para MFA y una directiva de acceso condicional requiere que MFA esté en vigor, ese usuario no podrá iniciar sesión.  

Microsoft ha probado y recomendado un conjunto específico de directivas relacionadas y de acceso condicional para proteger el acceso a todas las aplicaciones SaaS, especialmente Microsoft 365. Las directivas se recomiendan para la protección de línea base, confidencial y altamente regulada. Comience implementando las directivas para la protección de línea base.

[ ![ Directivas comunes para configurar la identidad y el acceso a dispositivos.](../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png) 
 [Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Para implementar la protección de línea base para Microsoft 365

![Proceso para implementar la protección de línea base.](../media/deploy-threat-protection/deploy-threat-protection-identity-access-steps.png) 

1. [Configure los requisitos previos, incluido Azure AD Identity Protection](../security/office-365-security/identity-access-prerequisites.md).
2. [Configure directivas comunes de acceso a dispositivos y identidades](../security/office-365-security/identity-access-policies.md) para la protección de línea base.
3. Configurar directivas para [usuarios invitados,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams](../security/office-365-security/teams-access-policies.md), [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)y SharePoint Online [y OneDrive](../security/office-365-security/sharepoint-file-access-policies.md).

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

![Proceso para implementar Microsoft Defender for Identity.](../media/deploy-threat-protection/deploy-azure-atp-steps.png) 

1. [Configure Microsoft Defender for Identity para](/azure-advanced-threat-protection/install-atp-step1) proteger los entornos principales.
2. Proteger todos los [controladores de dominio](/azure-advanced-threat-protection/atp-sensor-monitoring) y [bosques](/azure-advanced-threat-protection/atp-multi-forest).
3. Integre [alertas de Microsoft Defender para identidades](/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) en el flujo de trabajo de operaciones de seguridad (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Más información sobre Microsoft Defender for Identity

- [¿Qué es Microsoft Defender for Identity?](/azure-advanced-threat-protection/what-is-atp)
- [Vídeo: Introducción a Microsoft Defender for Identity](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Implementación de Microsoft Defender para identidades](/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Paso 3: Activar Microsoft 365 Defender

[Microsoft 365 Defender](../security/defender/microsoft-365-defender.md) combina las señales y las capacidades de orquesta en una única solución. Con la solución Microsoft 365 Defender integrada, los profesionales de seguridad pueden unir las señales de amenaza que cada uno de estos productos reciben y determinar el alcance completo y el impacto de la amenaza; cómo entró en el entorno, lo que está afectado y cómo está afectando actualmente a la organización. Microsoft 365 Defender realiza acciones automáticas para evitar o detener el ataque y auto-sanar los buzones, puntos de conexión e identidades de usuario afectados.

Microsoft 365 Defender unifica alertas, incidentes, investigación y respuesta automatizadas y búsqueda avanzada entre cargas de trabajo (Microsoft Defender para la identidad, Microsoft Defender para Office 365, Microsoft Defender para endpoint y Microsoft Cloud App Security) en un único panel de experiencia de cristal. Las nuevas características se agregan continuamente a Microsoft 365 Defender; considere la posibilidad de participar para recibir características de vista previa.

### <a name="to-set-up-microsoft-365-defender"></a>Para configurar Microsoft 365 Defender

![Proceso para implementar Microsoft 365 Defender.](../media/deploy-threat-protection/deploy-mtp-steps.png) 

1. [Revise los requisitos previos](../security/defender/prerequisites.md).
2. [Active la Microsoft 365 Defender](../security/defender/m365d-enable.md).
3. [Opt in for preview features](../security/defender/preview.md).

### <a name="more-information-about-microsoft-365-defender"></a>Más información sobre Microsoft 365 Defender

- [¿Qué es Microsoft 365 Defender?](../security/defender/microsoft-365-defender.md)
- [Novedades de Microsoft 365 Defender](../security/defender/whats-new.md)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Paso 4: Configurar Microsoft Defender para Office 365

[Microsoft Defender para Office 365](../security/office-365-security/defender-for-office-365.md) protege su organización contra amenazas malintencionadas en mensajes de correo electrónico (datos adjuntos y direcciones URL), documentos Office documentos y herramientas de colaboración. En la tabla siguiente se enumeran las Office 365 y las funcionalidades de Microsoft Defender que se incluyen en Microsoft 365 E5:

<br/><br/>

|Capacidades de configuración, protección y detección|Capacidades de automatización, investigación, corrección y educación|
|---|---|
|[Archivos adjuntos seguros](../security/office-365-security/safe-attachments.md) <p> [Vínculos seguros](../security/office-365-security/safe-links.md) <p> [Documentos seguros](../security/office-365-security/safe-docs.md) <p> [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md) <p> [Protección contra suplantación de identidad en Microsoft 365](../security/office-365-security/anti-phishing-protection.md)|[Rastreadores de amenazas](../security/office-365-security/threat-trackers.md) <p> [Explorador de amenazas](../security/office-365-security/threat-explorer.md) <p> [Investigación y respuesta automatizadas](../security/office-365-security/office-365-air.md) <p> [Aprendizaje de simulación de ataque](../security/office-365-security/attack-simulation-training.md)|

Con Microsoft Defender para Office 365, las personas de toda la organización pueden comunicarse y colaborar de forma más segura, con protección contra amenazas para su contenido de correo electrónico y Office documentos.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Para configurar Microsoft Defender para Office 365

![Proceso para implementar Microsoft Defender para Office 365.](../media/deploy-threat-protection/deploy-office365-atp-steps.png) 

1. [Configurar y configurar Microsoft Defender para Office 365 directivas](../security/office-365-security/protect-against-threats.md).
2. [Ver y usar Microsoft Defender para Office 365 informes](../security/office-365-security/view-reports-for-mdo.md).
3. [Usar capacidades de investigación y respuesta de amenazas](../security/office-365-security/office-365-ti.md).

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Más información sobre Microsoft Defender para Office 365

- [Introducción a Microsoft Defender para Office 365 web](../security/office-365-security/defender-for-office-365.md)
- [Novedades de Microsoft Defender para Office 365](../security/office-365-security/whats-new-in-defender-for-office-365.md)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Paso 5: Configurar Microsoft Defender para endpoint

[Microsoft Defender para endpoint](/windows/security/threat-protection) protege los dispositivos de la organización (también denominados puntos de conexión) de ciberamenazas, ataques avanzados e infracciones de datos. Los equipos de seguridad pueden ser más eficientes en la administración de la seguridad de sus puntos de conexión. Las herramientas sólidas ayudan a las organizaciones a mantenerse al día con los sistemas no apareados mediante la detección de vulnerabilidades con la administración de [amenazas y vulnerabilidades.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Las capacidades automatizadas de detección y corrección, como la [](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) reducción de superficie de [ataque,](/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)la protección de próxima generación, [](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) [detección y respuesta de puntos de conexión](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)y la investigación y corrección automatizadas ayudan a mantener los dispositivos a salvo de malware. Además de estas capacidades, los clientes pueden recibir notificaciones proactivas y consultar con Expertos en amenazas de Microsoft a petición, como parte del servicio de búsqueda administrada de participación.

### <a name="set-up-microsoft-defender-for-endpoint"></a>Configurar Microsoft Defender para punto de conexión

![Proceso para implementar Microsoft Defender para endpoint.](../media/deploy-threat-protection/deploy-mdatp-steps.png) 

1. [Prepare su entorno para Microsoft Defender para Endpoint](../security/defender-endpoint/deployment-phases.md).
2. [Implementar Microsoft Defender para endpoint](../security/defender-endpoint/production-deployment.md).
3. [Incorporación al servicio de Microsoft Defender para puntos de conexión](../security/defender-endpoint/onboarding.md).
4. [Complete las tareas administrativas de seguridad superior](../security/defender-endpoint/tvm-security-recommendation.md).

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Más información sobre Microsoft Defender para endpoint

- [Obtenga más información sobre Microsoft Defender para endpoint](../security/defender-endpoint/microsoft-defender-endpoint.md).
- [Pruebe el laboratorio de evaluación de Microsoft Defender para endpoints](../security/defender-endpoint/evaluation-lab.md).

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Paso 6: Configurar Microsoft Cloud App Security

[Microsoft Cloud App Security](/cloud-app-security) es un agente de seguridad de Cloud Access que admite la recopilación de registros, conectores de API y proxy inverso. Microsoft Cloud App Security una amplia visibilidad, control sobre los viajes de datos y análisis sofisticados para identificar y combatir las ciberamenazas en todos los servicios en la nube. Con Microsoft Cloud App Security, las operaciones de seguridad pueden proteger la información confidencial de la organización, protegerse contra ciberamenazas y anomalías, detectar y supervisar aplicaciones que tienen acceso a los datos de la organización y ayudar a garantizar que las aplicaciones en la nube de su organización cumplan los requisitos de cumplimiento.

### <a name="set-up-microsoft-cloud-app-security"></a>Configurar Microsoft Cloud App Security

![Proceso para implementar Microsoft Cloud App Security.](../media/deploy-threat-protection/deploy-mcas-steps.png) 

1. [Configurar el portal y otros requisitos básicos](/cloud-app-security/general-setup).
2. [Configurar la detección en la nube](/cloud-app-security/set-up-cloud-discovery) [y conectar aplicaciones](/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps).
3. [Implementar control de aplicaciones de acceso condicional para aplicaciones características.](/cloud-app-security/proxy-deployment-aad)
4. [Use las herramientas de investigación y los paneles](/cloud-app-security/investigate).

### <a name="more-information-about-microsoft-cloud-app-security"></a>Más información sobre Microsoft Cloud App Security

- [Revisar nuevas características y funcionalidades](/cloud-app-security/release-notes).
- [Obtenga más información sobre Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security).

## <a name="step-7-monitor-status-and-take-actions"></a>Paso 7: Supervisar el estado y realizar acciones

Después de configurar e implementar los servicios y capacidades de protección contra amenazas, el siguiente paso es supervisar las detecciones de amenazas y realizar las acciones adecuadas. El mejor punto de partida es el centro de seguridad de Microsoft 365 ( ), donde puede supervisar y administrar la seguridad en todas las identidades, datos, dispositivos, aplicaciones e infraestructura de [https://security.microsoft.com](https://security.microsoft.com) Microsoft.

![Microsoft 365 de seguridad.](../media/solutions-architecture-center/m365-security-center.png)

El Microsoft 365 de seguridad está pensado para los administradores de seguridad y los equipos de operaciones de seguridad. En el Microsoft 365 de seguridad, puede:

- Ver el estado de seguridad general de su organización con [Puntuación segura](/microsoft-365/security/defender/microsoft-secure-score).
- [Supervisar y ver informes sobre](../security/defender-endpoint/threat-protection-reports.md) el estado de las identidades, los datos, los dispositivos, las aplicaciones y la infraestructura.
- Conectar los puntos en las alertas a través [de incidentes](/microsoft-365/security/defender/incident-queue).
- Use [la investigación automatizada y la corrección para](../security/defender/m365d-autoir.md) solucionar las amenazas.
- [Busca de forma proactiva amenazas,](/microsoft-365/security/defender/advanced-hunting-overview)como intentos de intrusión o actividad de infracción que afecten al correo electrónico, los datos, los dispositivos y las identidades.
- [Comprenda las últimas campañas y](/microsoft-365/security/defender/latest-attack-campaigns) técnicas de ataque con análisis de amenazas.
- ... y mucho más.

### <a name="more-information-about-the-microsoft-365-security-center"></a>Más información sobre el centro Microsoft 365 seguridad

- [Introducción al centro de Microsoft 365 seguridad](../security/defender/overview-security-center.md).
- [Supervisar y ver informes](../security/defender/overview-security-center.md).
- [Vea los portales de seguridad en Microsoft 365](../security/defender/portals.md).

## <a name="step-8-train-users"></a>Paso 8: Entrenar usuarios

La formación de los usuarios puede ahorrar mucho tiempo y frustración a los usuarios y al equipo de operaciones de seguridad. Los usuarios expertos tienen menos probabilidades de abrir datos adjuntos o hacer clic en vínculos en mensajes de correo electrónico cuestionables, y es más probable que eviten sitios web sospechosos. 

El Manual [](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) de la campaña de ciberseguridad de la Escuela Kennedy de Harvard proporciona excelentes instrucciones para establecer una cultura sólida de concienciación de seguridad en su organización, incluida la formación de los usuarios para identificar los ataques de suplantación de identidad. 

Microsoft 365 proporciona los siguientes recursos para ayudar a informar a los usuarios de su organización:

<br/><br/>

|Concepto|Recursos|
|---|---|
|Microsoft 365|[Caminos de aprendizaje personalizables](/office365/customlearning/) <p> Estos recursos pueden ayudarle a crear formación para los usuarios finales de su organización|
|Centro de seguridad de Microsoft 365|[Learning: proteja su organización con seguridad inteligente integrada desde Microsoft 365](/learn/modules/security-with-microsoft-365) <p> Este módulo le permite describir cómo funcionan Microsoft 365 de seguridad conjuntas y para expresar las ventajas de estas características de seguridad.|
|Autenticación multifactor|[Comprobación en dos pasos: ¿Cuál es la página de verificación adicional?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p> Este artículo ayuda a los usuarios finales a comprender qué es la autenticación multifactor y por qué se usa en su organización.|

Además de esta guía, Microsoft recomienda que los usuarios tomen las acciones descritas en este artículo: Proteger su cuenta y dispositivos de [los piratas informáticos y malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Entre estas acciones se incluyen:

- Uso de contraseñas seguras
- Protección de dispositivos
- Habilitar características de seguridad en Windows 10 y equipos Mac (para dispositivos no administrados)

Microsoft también recomienda a los usuarios proteger sus cuentas de correo electrónico personales mediante las acciones recomendadas en los siguientes artículos:

- [Ayudar a proteger su cuenta de correo Outlook.com](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Proteger tu cuenta de Gmail con la comprobación de 2 pasos](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
