---
title: Pasos para configurar las capacidades de protección contra amenazas en Microsoft 365
description: Obtenga información sobre cómo implementar servicios y capacidades de protección contra amenazas en Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-threatprotection
- m365solution-scenario
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 492db78c9aea881ae05dbc66f5e84ad98629b923
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931991"
---
# <a name="configure-threat-protection-capabilities-across-microsoft-365"></a>Configurar las capacidades de protección contra amenazas en Microsoft 365

Siga estos pasos para configurar la protección contra amenazas en Microsoft 365.


## <a name="step-1-set-up-multi-factor-authentication-and-conditional-access-policies"></a>Paso 1: Configurar la autenticación multifactor y las directivas de acceso condicional

[La autenticación multifactor](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) (MFA) requiere que los usuarios comprueben su identidad con una llamada telefónica o una aplicación autenticador. [Las directivas de acceso](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) condicional definen ciertos requisitos que deben cumplirse para que los usuarios puedan acceder a aplicaciones y datos en Microsoft 365. Mfa y las directivas de acceso condicional funcionan conjuntamente para proteger su organización. Por ejemplo, si alguien intenta iniciar sesión desde un dispositivo móvil con una cuenta que no está habilitada para MFA y una directiva de acceso condicional requiere que MFA esté en vigor, se impedirá que el usuario inicie sesión.  

Microsoft ha probado y recomendado un conjunto específico de acceso condicional y directivas relacionadas para proteger el acceso a todas las aplicaciones SaaS, especialmente Microsoft 365. Las directivas se recomiendan para la protección de línea base, confidencial y altamente regulada. Comience por implementar las directivas para la protección de línea base. 


[ ![ Directivas comunes para configurar el acceso a dispositivos e](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [identidades. Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

### <a name="to-implement-baseline-protection-for-microsoft-365"></a>Para implementar la protección de línea base para Microsoft 365

![Proceso para implementar la protección de línea base](../media/solutions-architecture-center/deploy-threat-protection-identity-access-steps.png) 

1. [Configure los requisitos previos, incluido Azure Identity Protection.](../security/office-365-security/identity-access-prerequisites.md)
2. [Configurar directivas comunes de acceso a dispositivos e identidades](../security/office-365-security/identity-access-policies.md) para la protección de línea base.
3. Configure directivas para [usuarios invitados,](../security/office-365-security/identity-access-policies-guest-access.md) [Microsoft Teams,](../security/office-365-security/teams-access-policies.md) [Exchange Online](../security/office-365-security/secure-email-recommended-policies.md)y [SharePoint Online y OneDrive.](../security/office-365-security/sharepoint-file-access-policies.md)

### <a name="more-information-about-protecting-identities"></a>Más información sobre la protección de identidades

- [Configuraciones de acceso a dispositivos e identidades](../security/office-365-security/microsoft-365-policies-configurations.md)
- [Instrucciones de seguridad para Azure MFA](https://docs.microsoft.com/azure/active-directory/authentication/multi-factor-authentication-security-best-practices)

## <a name="step-2-configure-microsoft-defender-for-identity"></a>Paso 2: Configurar Microsoft Defender para la identidad

[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) es una solución de seguridad basada en la nube que funciona con las señales locales de [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) para identificar, detectar e investigar amenazas avanzadas, identidades comprometidas y acciones internas malintencionadas dirigidas a su organización.

Microsoft Defender for Identity permite a los analistas y profesionales de seguridad de operaciones de seguridad (SecOps) detectar ataques avanzados en entornos híbridos para:
- Supervise los usuarios, el comportamiento de la entidad y las actividades con análisis basados en aprendizaje.
- Proteger las identidades de usuario y las credenciales almacenadas en Active Directory.
- Identificar e investigar actividades de usuarios sospechosas y ataques avanzados en la cadena de eliminación.
- Proporcionar información clara sobre el incidente en una escala de tiempo simple para una evaluación rápida.

### <a name="to-set-up-microsoft-defender-for-identity"></a>Para configurar Microsoft Defender para identity

![Proceso para implementar Microsoft Defender for Identity](../media/solutions-architecture-center/deploy-azure-atp-steps.png) 

1. [Configure Microsoft Defender for Identity para](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) proteger los entornos principales.
2. Proteja todos los controladores [de dominio y](https://docs.microsoft.com/azure-advanced-threat-protection/atp-sensor-monitoring) [bosques.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-multi-forest)
3. Integre [alertas de Microsoft Defender para Identidad](https://docs.microsoft.com/azure-advanced-threat-protection/suspicious-activity-guide?tabs=external) en el flujo de trabajo de operaciones de seguridad (SecOps).

### <a name="more-information-about-microsoft-defender-for-identity"></a>Más información sobre Microsoft Defender para Identidad

- [¿Qué es Microsoft Defender for Identity?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Vídeo: Introducción a Microsoft Defender para la identidad](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- [Implementación de Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="step-3-turn-on-microsoft-365-defender"></a>Paso 3: Activar Microsoft 365 Defender

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) combina señales y orquesta funcionalidades en una única solución. Con la solución integrada de Microsoft 365 Defender, los profesionales de seguridad pueden unir las señales de amenaza que cada uno de estos productos recibe y determinar el alcance completo y el impacto de la amenaza; cómo se introdujo en el entorno, qué se ve afectado y cómo afecta actualmente a la organización. Microsoft 365 Defender toma medidas automáticas para evitar o detener el ataque y sanar automáticamente los buzones de correo, los puntos de conexión y las identidades de usuario afectados.

Microsoft 365 Defender unifica alertas, incidentes, investigación y respuesta automatizadas y búsqueda avanzada en cargas de trabajo (Microsoft Defender para Identidad, Microsoft Defender para Office 365, Microsoft Defender para Endpoint y Microsoft Cloud App Security) en un único panel de experiencia. Después de configurar uno o varios de los servicios de Defender para Office 365, active Microsoft 365 Defender. Las nuevas características se agregan continuamente a Microsoft 365 Defender; considere la posibilidad de participar para recibir características de vista previa.

### <a name="to-set-up-microsoft-365-defender"></a>Para configurar Microsoft 365 Defender

![Proceso para implementar Microsoft 365 Defender](../media/solutions-architecture-center/deploy-mtp-steps.png) 

1. [Revise los requisitos previos.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)
2. [Active Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)
3. [Opte por las características de vista previa.](https://docs.microsoft.com/microsoft-365/security/mtp/preview)

### <a name="more-information-about-microsoft-365-defender"></a>Más información sobre Microsoft 365 Defender

- [¿Qué es Microsoft 365 Defender?](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
- [Novedades de Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)

## <a name="step-4-configure-microsoft-defender-for-office-365"></a>Paso 4: Configurar Microsoft Defender para Office 365

[Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) protege su organización contra amenazas malintencionadas en mensajes de correo electrónico (datos adjuntos y DIRECCIONES URL), documentos de Office y herramientas de colaboración. En la siguiente tabla se enumeran las características y capacidades de Microsoft Defender para Office 365 que se incluyen en Microsoft 365 E5:

|Capacidades de configuración, protección y detección|Capacidades de automatización, investigación, corrección y educación|
|---|---|
|[Archivos adjuntos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br/>[Vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)<br/>[Documentos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)<br/>[ATP para SharePoint, OneDrive y Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)<br/>[Protección antiphishing en Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies#exclusive-settings-in-atp-anti-phishing-policies)|[Rastreadores de amenazas](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-trackers)<br/>[Explorador de amenazas](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer)<br/>[Investigación y respuesta automatizadas](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)<br/>[Simulador de ataque](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulator)|
|

Con Microsoft Defender para Office 365, las personas de su organización pueden comunicarse y colaborar de forma más segura, con protección contra amenazas para su contenido de correo electrónico y documentos de Office.

### <a name="to-set-up-microsoft-defender-for-office-365"></a>Para configurar Microsoft Defender para Office 365

![Proceso para implementar Microsoft Defender para Office 365](../media/solutions-architecture-center/deploy-office365-atp-steps.png) 

1. [Configure y configure las directivas de Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)
2. [Ver y usar los informes de Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)
3. [Usar capacidades de investigación y respuesta de amenazas.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)

### <a name="more-information-about-microsoft-defender-for-office-365"></a>Más información sobre Microsoft Defender para Office 365

- [Introducción a Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Novedades de Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp)

## <a name="step-5-configure-microsoft-defender-for-endpoint"></a>Paso 5: Configurar Microsoft Defender para endpoint

[Microsoft Defender para puntos](https://docs.microsoft.com/windows/security/threat-protection) de conexión protege los dispositivos de la organización (también denominados puntos de conexión) de ciberamenazas, ataques avanzados e infracciones de datos. Los equipos de seguridad pueden ser más eficientes en la administración de la seguridad de sus puntos de conexión. Las herramientas sólidas ayudan a las organizaciones a mantenerse al día con los sistemas sin corregir mediante la detección de vulnerabilidades con la administración de [amenazas y vulnerabilidades.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Las capacidades automatizadas de detección y corrección, [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)como reducción [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) de superficie de [ataque,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-attack-surface-reduction)protección de última generación, [](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)detección y respuesta de puntos de conexión e investigación y corrección automatizadas ayudan a mantener los dispositivos a salvo de malware. Además de estas capacidades, los clientes pueden recibir notificaciones proactivas y consultar a los expertos en amenazas de Microsoft a petición, como parte del servicio de búsqueda administrada de participación. 


### <a name="set-up-microsoft-defender-for-endpoint"></a>Configurar Microsoft Defender para endpoint

![Proceso para implementar Microsoft Defender para puntos de conexión](../media/solutions-architecture-center/deploy-mdatp-steps.png) 

1. [Preparar Microsoft Defender para la implementación de puntos de conexión.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases)
2. [Configurar la implementación de Microsoft Defender para puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/micros.oft-defender-atp/production-deployment)
3. [Incorporarse al servicio Microsoft Defender para puntos de conexión.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboarding)
4. [Complete las tareas administrativas de seguridad superior.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation)

### <a name="more-information-about-microsoft-defender-for-endpoint"></a>Más información sobre Microsoft Defender para puntos de conexión

- [Obtenga más información sobre Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/security/threat-protection)
- [Pruebe el laboratorio de evaluación de Microsoft Defender para endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluation-lab)

## <a name="step-6-configure-microsoft-cloud-app-security"></a>Paso 6: Configurar Microsoft Cloud App Security

[Microsoft Cloud App Security es](https://docs.microsoft.com/cloud-app-security) un agente de seguridad de Acceso a la nube que admite la recopilación de registros, conectores de API y proxy inverso. Microsoft Cloud App Security proporciona una visibilidad enriqueciendo, control sobre los viajes de datos y análisis sofisticados para identificar y combatir ciberamenazas en todos los servicios en la nube. Con Microsoft Cloud App Security, las operaciones de seguridad pueden proteger la información confidencial de su organización, protegerse contra ciberamenazas y anomalías, detectar y supervisar aplicaciones que tienen acceso a los datos de su organización y ayudar a garantizar que las aplicaciones en la nube de su organización cumplan los requisitos de cumplimiento.

### <a name="set-up-microsoft-cloud-app-security"></a>Configurar Microsoft Cloud App Security

![Proceso para implementar Microsoft Cloud App Security](../media/solutions-architecture-center/deploy-mcas-steps.png) 

1. [Configure el portal y otros requisitos básicos.](https://docs.microsoft.com/cloud-app-security/general-setup)
2. [Configurar la detección en la nube](https://docs.microsoft.com/cloud-app-security/set-up-cloud-discovery) y [conectar aplicaciones.](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)
3. [Implementar el control de aplicaciones de acceso condicional para aplicaciones destacados.](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)
4. [Use las herramientas y paneles de investigación.](https://docs.microsoft.com/cloud-app-security/investigate)

### <a name="more-information-about-microsoft-cloud-app-security"></a>Más información sobre Microsoft Cloud App Security

- [Revise las nuevas características y capacidades.](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Obtenga más información sobre Microsoft Cloud App Security.](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

## <a name="step-7-monitor-status-and-take-actions"></a>Paso 7: Supervisar el estado y realizar acciones

Después de configurar e implementar los servicios y capacidades de protección contra amenazas, el siguiente paso es supervisar las detecciones de amenazas y realizar las acciones adecuadas. El mejor punto de partida es el Centro de seguridad de Microsoft 365 ( ), donde puede supervisar y administrar la seguridad en sus identidades, datos, dispositivos, aplicaciones e infraestructura de [https://security.microsoft.com](https://security.microsoft.com) Microsoft. 

![Centro de seguridad de Microsoft 365](../media/solutions-architecture-center/m365-security-center.png)

El Centro de seguridad de Microsoft 365 está diseñado específicamente para administradores de seguridad y equipos de operaciones de seguridad. En el Centro de seguridad de Microsoft 365, puede:
- Vea el estado de seguridad general de su organización con [puntuación de seguridad.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)
- [Supervise y vea informes](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting) sobre el estado de las identidades, los datos, los dispositivos, las aplicaciones y la infraestructura.
- Conecte los puntos en alertas a través [de incidentes.](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- Use [la investigación automatizada y la corrección para](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir) abordar las amenazas.
- [Búsqueda proactiva de amenazas,](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview)como intentos de intrusiones o actividad de infracción que afecten al correo electrónico, los datos, los dispositivos y las identidades.
- [Comprenda las últimas campañas y técnicas](https://docs.microsoft.com/microsoft-365/security/mtp/latest-attack-campaigns) de ataque con análisis de amenazas.
- ... y mucho más.

### <a name="more-information-about-the-microsoft-365-security-center"></a>Más información sobre el Centro de seguridad de Microsoft 365

- [Introducción al Centro de seguridad de Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center)
- [Supervisar y ver informes.](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting)
- [Vea los portales de seguridad de Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="step-8-train-users"></a>Paso 8: Formar a los usuarios

La formación de los usuarios puede ahorrarle a los usuarios y al equipo de operaciones de seguridad mucho tiempo y frustración. Los usuarios expertos tienen menos probabilidades de abrir datos adjuntos o hacer clic en vínculos en mensajes de correo electrónico cuestionables, y es más probable que eviten sitios web sospechosos. 

El Manual [](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) de campañas de ciberseguridad de la escuela Desaceditiva de Phish proporciona instrucciones excelentes para establecer una cultura sólida de reconocimiento de la seguridad dentro de su organización, incluida la formación a los usuarios para identificar ataques de suplantación de identidad. 

Microsoft 365 proporciona los siguientes recursos para ayudar a informar a los usuarios de su organización:

|Concepto  |Recursos  |
|---------|---------|
|Microsoft 365     |[Caminos de aprendizaje personalizables](https://docs.microsoft.com/office365/customlearning/) <p>Estos recursos pueden ayudarle a reunir formación para los usuarios finales de su organización        |
|Seguridad de Microsoft 365 |[Módulo de aprendizaje: proteger su organización con seguridad inteligente integrada de Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Este módulo le permite describir cómo funcionan conjuntamente las características de seguridad de Microsoft 365 y para articular las ventajas de estas características de seguridad. |
|Autenticación multifactor     | [Comprobación en dos pasos: ¿Cuál es la página de verificación adicional?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Este artículo ayuda a los usuarios finales a comprender qué es la autenticación multifactor y por qué se usa en su organización.    |

Además de esta guía, Microsoft recomienda que los usuarios tomen las acciones descritas en este artículo: Proteger su cuenta y dispositivos de [hackers y malware.](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx) Entre estas acciones se incluyen:
- Uso de contraseñas seguras
- Protección de dispositivos 
- Habilitación de características de seguridad en equipos Windows 10 y Mac (para dispositivos no administrados)
    
Microsoft también recomienda que los usuarios protejan sus cuentas de correo electrónico personales mediante las acciones recomendadas en los artículos siguientes:
- [Ayudar a proteger su Outlook.com de correo electrónico](https://support.microsoft.com/office/help-protect-your-outlook-com-email-account-a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)
- [Proteger su cuenta de Gmail con verificación en dos pasos](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)
