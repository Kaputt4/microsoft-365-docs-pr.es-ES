---
title: Implementar la protección contra ransomware para el inquilino de Microsoft 365
author: dansimp
f1.keywords:
- NOCSH
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- ransomware
- m365solution-ransomware
- m365solution-overview
ms.custom: seo-marvel-jun2020
keywords: ransomware, ransomware operado por humanos, HumOR, ataque de extorsión, ataque de ransomware, cifrado, criptovirología, confianza cero
description: Paso a paso para proteger los recursos de Microsoft 365 frente a ataques de ransomware.
ms.openlocfilehash: 6196feca7236fa98513e0d735d91cfbd2a6bd2ea
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986012"
---
# <a name="deploy-ransomware-protection-for-your-microsoft-365-tenant"></a>Implementar la protección contra ransomware para el inquilino de Microsoft 365

El ransomware es un tipo de ataque de extorsión que destruye o cifra archivos y carpetas, lo que impide el acceso a datos críticos. Por lo general, el ransomware estándar se propaga como un virus que infecta los dispositivos y solo requiere una corrección de malware. El ransomware operado por personas es el resultado de un ataque activo por parte de ciberdelincuentes que se infiltran en la infraestructura de TI local o en la nube de una organización, elevan sus privilegios e implementan ransomware en datos críticos.

Una vez completado el ataque, un atacante exige dinero a las víctimas a cambio de los archivos eliminados, las claves de descifrado de los archivos cifrados o una promesa de no liberar datos confidenciales en la web oscura o en la red pública de Internet. El ransomware operado por personas también se puede usar para apagar máquinas o procesos críticos, como los necesarios para la producción industrial, lo que detiene las operaciones comerciales normales hasta que se paga el rescate y se corrigen los daños, o bien la organización corrige los daños por su cuenta.

Un ataque de ransomware operado por personas puede ser catastrófico para empresas de todos los tamaños y es difícil de limpiar, puesto que requiere una expulsión total del adversario para protegerse frente a futuros ataques. A diferencia del ransomware estándar, el ransomware operado por personas puede seguir amenazando las operaciones de las empresas después de la solicitud inicial de rescate.

>[!Note]
>Un ataque de ransomware en un inquilino de Microsoft 365 supone que el atacante tiene credenciales de cuenta de usuario válidas para un inquilino y tiene acceso a todos los archivos y recursos que se le permiten a la cuenta de usuario. Un atacante sin credenciales de cuenta de usuario válidas tendría que descifrar los datos en reposo que Microsoft 365 haya cifrado con el uso del cifrado predeterminado y mejorado. Para obtener más información, consulte [Información general sobre el cifrado y la administración de claves](/compliance/assurance/assurance-encryption). 
>

Para obtener más información sobre la protección contra ransomware en todos los productos de Microsoft, consulte estos [recursos adicionales de ransomware](#additional-ransomware-resources).

## <a name="security-in-the-cloud-is-a-partnership"></a>La seguridad en la nube representa una asociación

La seguridad de los servicios en la nube de Microsoft es una asociación entre usted y Microsoft:

- Los servicios en la nube de Microsoft se basan en unos cimientos de confianza y seguridad. Microsoft le proporciona controles de seguridad y capacidades que le ayudarán a proteger sus datos y aplicaciones.
- Usted es propietario de sus datos e identidades, así como es usted mismo el encargado de protegerlos, tal y como debe hacer con sus recursos locales y con la seguridad de los componentes en la nube que controle.

Al combinar estas capacidades y responsabilidades, podemos proporcionarle la mejor protección contra un ataque de ransomware.

## <a name="ransomware-mitigation-and-recovery-capabilities-provided-with-microsoft-365"></a>Capacidades de mitigación y recuperación de ransomware proporcionadas con Microsoft 365

Un atacante de ransomware que se haya infiltrado en un inquilino de Microsoft 365 puede retener a su organización para su rescate mediante:

- Eliminación de archivos o correo electrónico
- Cifrado de archivos locales
- Copia de archivos fuera del inquilino (filtración de datos)

Sin embargo, los servicios en línea de Microsoft 365 tienen muchas capacidades y controles integrados para proteger los datos del cliente de ataques de ransomware. En las secciones siguientes, se proporciona un resumen de estos. Para obtener más información sobre cómo Microsoft protege los datos de los clientes, consulte [Protección contra ransomware y software en Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection).

>[!Note]
>Un ataque de ransomware en un inquilino de Microsoft 365 supone que el atacante tiene credenciales de cuenta de usuario válidas para un inquilino y tiene acceso a todos los archivos y recursos que se le permiten a la cuenta de usuario. Un atacante sin credenciales de cuenta de usuario válidas tendría que descifrar los datos en reposo que Microsoft 365 haya cifrado con el uso del cifrado predeterminado y mejorado. Para obtener más información, consulte [Información general sobre el cifrado y la administración de claves](/compliance/assurance/assurance-encryption). 
>

### <a name="deleting-files-or-email"></a>Eliminación de archivos o correo electrónico

Los archivos de SharePoint y OneDrive para la Empresa están protegidos por:

- Control de versiones 

   Microsoft 365 conserva, como mínimo, 500 versiones de un archivo de forma predeterminada, y es posible que se configure para que pueda conservar más. 

   Para minimizar la carga del personal de seguridad y soporte técnico, entrene a los usuarios con información sobre cómo [restaurar versiones anteriores de archivos](https://support.microsoft.com/office/restore-a-previous-version-of-an-item-or-file-in-sharepoint-f66dbda0-81f4-4d1e-b08c-793265c58934).

- Papelera de reciclaje

   Si el ransomware crea una nueva copia cifrada del archivo y elimina el archivo antiguo, los clientes tienen 93 días para restaurarlo desde la papelera de reciclaje. Después de 93 días, hay una ventana de 14 días en la que Microsoft todavía puede recuperar los datos. 
  
   Para minimizar la carga del personal de seguridad y soporte técnico, entrene a los usuarios con información sobre cómo [restaurar archivos de la papelera de reciclaje](https://support.microsoft.com/office/restore-deleted-items-from-the-site-collection-recycle-bin-5fa924ee-16d7-487b-9a0a-021b9062d14b).

- [Restauración de archivos](https://support.microsoft.com/office/restore-your-onedrive-fa231298-759d-41cf-bcd0-25ac53eb8a15)

   Una solución completa de autoservicio de recuperación para SharePoint y OneDrive que permite a los administradores y usuarios finales restaurar archivos a partir de cualquier fecha durante los últimos 30 días.

   Para minimizar la carga del personal del departamento de soporte técnico de TI y seguridad, entrene a los usuarios sobre la [Restauración de archivos](https://support.microsoft.com/office/restore-your-onedrive-fa231298-759d-41cf-bcd0-25ac53eb8a15).


En el caso de los archivos de OneDrive y SharePoint, Microsoft puede revertir su espacio a un momento dado anterior de hasta 14 días, si se produce un ataque masivo.

El correo electrónico está protegido por las funcionalidades:

- [Recuperación de elementos individuales](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery) y retención de buzones, con las que puede recuperar los elementos de un buzón tras una eliminación prematura involuntaria o malintencionada. De manera predeterminada, puede revertir el estado de los mensajes de correo eliminados en un plazo de 14 días desde su eliminación. Es posible configurar este plazo para expandirlo hasta 30 días.

- Las [directivas de retención](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies) le permiten conservar copias inmutables del correo electrónico durante el período de retención configurado.

### <a name="encrypting-files-in-place"></a>Cifrado de archivos locales

Como se ha descrito anteriormente, los archivos de SharePoint y OneDrive para la Empresa están protegidos contra el cifrado malintencionado con:

- Control de versiones
- Papelera de reciclaje
- Biblioteca de suspensión para conservación

Para obtener más información, consulte [Ocuparse de los datos dañados en Microsoft 365](/compliance/assurance/assurance-dealing-with-data-corruption).

### <a name="copying-files-outside-your-tenant"></a>Copiar archivos fuera de su inquilino 

Puede evitar que un atacante de ransomware copie archivos fuera de su inquilino con:

- Directivas de [prevención de pérdida de datos (DLP) de Microsoft Purview](/microsoft-365/compliance/dlp-learn-about-dlp)

    Detecte, avise y bloquee el uso compartido peligroso, involuntario o inadecuado de los datos que contengan:

    - Información personal, como información de identificación personal (DCP) para el cumplimiento de las normativas de privacidad regionales.

    - Información confidencial de la organización basada en etiquetas de confidencialidad.

- [Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)

    Bloquee descargas de información confidencial, como archivos. 

    También se puede usar directivas de sesión para el [Control de aplicaciones de acceso condicional de Defender for Cloud](/cloud-app-security/tutorial-dlp#how-to-discover-and-protect-sensitive-information-in-your-organization) y, así, supervisar el flujo de información entre un usuario y una aplicación en tiempo real.

## <a name="whats-in-this-solution"></a>Acerca de esta solución

Esta solución le guiará a través de la implementación de características de protección y mitigación de Microsoft 365, configuraciones y operaciones continuas para minimizar la capacidad de un atacante de ransomware de usar los datos críticos del espacio empresarial de Microsoft 365 para intentar pedir rescate.

![Pasos para protegerse contra ransomware con Microsoft 365](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step-grid.png)

Los pasos de esta solución son:

1. [Configurar las líneas base de seguridad](ransomware-protection-microsoft-365-security-baselines.md)
2. [Implementar la detección y respuesta ante ataques](ransomware-protection-microsoft-365-attack-detection-response.md)
3. [Proteger identidades](ransomware-protection-microsoft-365-identities.md)
4. [Proteger dispositivos](ransomware-protection-microsoft-365-devices.md)
5. [Proteger la información](ransomware-protection-microsoft-365-information.md)

Estos son los cinco pasos de la solución implementada para el inquilino de Microsoft 365.

![Protección contra ransomware para un inquilino de Microsoft 365](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-architecture.png)

Esta solución usa los principios de [Confianza cero](/security/zero-trust/): 

- **Comprobar de forma explícita:** autentique y autorice siempre en función de todos los puntos de datos disponibles.
- **Usar acceso con privilegios mínimos:** limite el acceso del usuario con acceso suficiente y justo a tiempo (JIT/JEA), directivas adaptables basadas en los riesgos y protección de datos.
- **Asumir la vulneración:** minimice el radio de explosión y el acceso a los segmentos. Compruebe el cifrado de un extremo a otro y use análisis para obtener visibilidad, impulsar la detección de amenazas y mejorar las defensas.

Unlike conventional intranet access, which trusts everything behind an organization's firewall, Zero Trust treats each sign-in and access as though it originated from an uncontrolled network, whether it's behind the organization firewall or on the Internet. Zero Trust requires protection for the network, infrastructure, identities, endpoints, apps, and data.

## <a name="microsoft-365-capabilities-and-features"></a>Funcionalidades y características de Microsoft 365

Para proteger a su inquilino de Microsoft 365 de un ataque de ransomware, use estas características y funcionalidades de Microsoft 365 para estos pasos de la solución.

### <a name="1-security-baseline"></a>1. Línea base de seguridad

| Funcionalidad o característica | Description | Ayuda... | Licencias |
|:-------|:-----|:-------|:-------|
| Puntuación de seguridad de Microsoft |  Mide la posición de seguridad de un espacio empresarial de Microsoft 365. | Evalúe la configuración de seguridad y sugiera mejoras. | Microsoft 365 E3 o Microsoft 365 E5 |
| Reglas de reducción de la superficie expuesta a ataques | Reduce la vulnerabilidad de la organización a los ciberataques mediante una variedad de opciones de configuración. | Bloquea la actividad sospechosa y el contenido vulnerable. | Microsoft 365 E3 o Microsoft 365 E5 |
| Configuración de correo electrónico de Exchange |  Habilita los servicios que reducen la vulnerabilidad de la organización a un ataque basado en el correo electrónico. | Evite el acceso inicial a su inquilino a través de suplantación de identidad (phishing) y otros ataques basados en correo electrónico.  | Microsoft 365 E3 o Microsoft 365 E5 |
| Configuración de Microsoft Windows, Microsoft Edge y aplicaciones de Microsoft 365 para empresas | Proporciona configuraciones de seguridad estándar del sector que son ampliamente conocidas y están probadas. | Evite ataques a través de Windows, Edge y aplicaciones de Microsoft 365 para empresas. | Microsoft 365 E3 o Microsoft 365 E5 |
|

### <a name="2-detection-and-response"></a>2. Detección y respuesta

| Funcionalidad o característica | Description | Ayuda a detectar y responder a... | Licencias |
|:-------|:-----|:-------|:-------|
| Microsoft 365 Defender | Combina señales y dispone las funcionalidades en una única solución. <br><br> Permite a los profesionales de la seguridad reunir las señales de amenazas y determinar el ámbito y el impacto completos de una amenaza. <br><br> Automatiza las acciones para evitar o detener el ataque y reparar de manera automática los buzones afectados, los puntos de conexión y las identidades de usuario. | Incidentes, que son las alertas combinadas y los datos que componen un ataque. | Microsoft 365 E5 o Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5 |
| Microsoft Defender for Identity |  Identifica, detecta e investiga amenazas avanzadas, identidades en peligro y acciones internas malintencionadas dirigidas a la organización a través de una interfaz de seguridad basada en la nube que usa las señales de Active Directory Domain Services (AD DS) local. | Credenciales en peligro para cuentas de AD DS. | Microsoft 365 E5 o Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5 |
| Microsoft Defender para Office 365 | Protege a la organización frente a las amenazas dañinas que se presentan en mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración. <br><br> Protege contra software malintencionado, phishing, suplantación de identidad y otro tipo de ataques. | Ataques de suplantación de identidad (phishing). | Microsoft 365 E5 o Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5 |
| Microsoft Defender para punto de conexión | Habilita la detección y respuesta a amenazas avanzadas en los distintos puntos de conexión (dispositivos). | La instalación de malware y el dispositivo están en peligro. | Microsoft 365 E5 o Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5 |
| Azure Active Directory (Azure AD) Identity Protection | Automatiza la detección y corrección de riesgos basados en identidades y la investigación de dichos riesgos. | Vulneración de credenciales en cuentas de Azure AD y elevación de privilegios. | Microsoft 365 E5 o Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5 |
| Defender for Cloud Apps | Agente de seguridad de acceso a la nube para la detección, investigación y gobernanza en todos los servicios en la nube de Microsoft y de terceros | Movimiento lateral y filtración de datos. | Microsoft 365 E5 o Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5 |
|

### <a name="3-identities"></a>3. Identidades

| Funcionalidad o característica | Description | Ayuda a evitar... | Licencias |
|:-------|:-----|:-------|:-------|
|Protección de contraseñas de Azure AD | Bloquear contraseñas de una lista común y entradas personalizadas. | Determinación de la contraseña de la cuenta de usuario local o en la nube. |Microsoft 365 E3 o Microsoft 365 E5|
|Autenticación multifactor aplicada con acceso condicional | Requerir la autenticación multifactor según las propiedades del inicio de sesión con directivas de acceso condicional. | Acceso y vulneración de credenciales. | Microsoft 365 E3 o Microsoft 365 E5|
|Autenticación multifactor aplicada con acceso condicional basado en riesgos | Requerir la autenticación multifactor según el riesgo de los inicios de sesión de usuario con Azure AD Identity Protection. |Acceso y vulneración de credenciales. | Microsoft 365 E5 o Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5|
|

### <a name="4-devices"></a>4. Dispositivos

Para administración de dispositivos y aplicaciones:

| Funcionalidad o característica | Description | Ayuda a evitar... | Licencias |
|:-------|:-----|:-------|:-------|
| Microsoft Intune | Administrar dispositivos y las aplicaciones que se ejecutan en ellos.  | Dispositivo o aplicación en peligro y acceso. | Microsoft 365 E3 o E5 |
|  |  |  |  |

Para dispositivos Windows 11 o 10:

| Funcionalidad o característica | Description | Ayuda... | Licencias |
|:-------|:-----|:-------|:-------|
| Firewall de Microsoft Defender | Proporciona un firewall basado en host.  | Evite ataques de tráfico de red entrante no solicitado. | Microsoft 365 E3 o Microsoft 365 E5 |
| Antivirus de Microsoft Defender | Proporciona protección antimalware de dispositivos (puntos de conexión) mediante aprendizaje automático, análisis de macrodatos, investigación en profundidad de resistencia a amenazas, y la infraestructura en la nube de Microsoft. | Impedir la instalación y ejecución de malware. | Microsoft 365 E3 o Microsoft 365 E5 |
| SmartScreen de Microsoft Defender | Protege contra sitios web y aplicaciones de suplantación de identidad (phishing) o malware, así como contra la descarga de archivos potencialmente malintencionados. | Bloquear o advertir al comprobar sitios, descargas, aplicaciones y archivos. | Microsoft 365 E3 o Microsoft 365 E5 |
| Microsoft Defender para punto de conexión | Ayuda a evitar, detectar, investigar y responder a amenazas avanzadas en todos los dispositivos (puntos de conexión). | Protegerse contra la alteración de la red. | Microsoft 365 E5 o Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5 |
|  |  |  |  |

### <a name="5-information"></a>5. Información

| Funcionalidad o característica | Description | Ayuda... | Licencias |
|:-------|:-----|:-------|:-------|
| Acceso controlado a carpetas | Protege los datos al comprobar las aplicaciones con una lista de aplicaciones conocidas y de confianza. | Impedir que los archivos se modifiquen o se cifren mediante ransomware. | Microsoft 365 E3 o Microsoft 365 E5 |
| Microsoft Purview Information Protection | Permite que las etiquetas de confidencialidad se apliquen a la información que es rescatable. | Impedir el uso de información filtrada. | Microsoft 365 E3 o Microsoft 365 E5 |
| Prevención de pérdida de datos (DLP) | Protege los datos confidenciales y reduce el riesgo al impedir que los usuarios los compartan de forma inapropiada. | Evitar la filtración de datos. | Microsoft 365 E3 o Microsoft 365 E5 |
| Defender for Cloud Apps | Un agente de seguridad de acceso a la nube para detección, investigación y gobernanza. | Detecte el movimiento lateral y evite la filtración de datos. | Microsoft 365 E5 o Microsoft 365 E3 con el complemento Seguridad de Microsoft 365 E5 |
|

## <a name="impact-on-users-and-change-management"></a>Impacto en los usuarios y administración de cambios

La implementación de características de seguridad adicionales y la implementación de requisitos y directivas de seguridad para el inquilino de Microsoft 365 puede afectar a los usuarios. 

Por ejemplo, puede imponer una nueva directiva de seguridad que requiera que los usuarios creen nuevos equipos para usos específicos con una lista de cuentas de usuario como miembros; o, en su lugar, de manera más sencilla, crear un equipo para todos los usuarios de la organización. Esto puede ayudar a evitar que un atacante de ransomware explore equipos que no están disponibles para la cuenta de usuario en peligro del atacante y que se dirijan a los recursos de ese equipo en el ataque posterior.

Esta solución básica identificará cuándo las nuevas configuraciones o las directivas de seguridad recomendadas pueden afectar a los usuarios para que pueda realizar la administración de cambios necesaria.

## <a name="next-steps"></a>Próximos pasos

Siga estos pasos para implementar una protección completa para su inquilino de Microsoft 365:

1. [Configurar las líneas base de seguridad](ransomware-protection-microsoft-365-security-baselines.md)
2. [Implementar la detección y respuesta ante ataques](ransomware-protection-microsoft-365-attack-detection-response.md)
3. [Proteger identidades](ransomware-protection-microsoft-365-identities.md)
4. [Proteger dispositivos](ransomware-protection-microsoft-365-devices.md)
5. [Proteger la información](ransomware-protection-microsoft-365-information.md)

[![Paso 1 para la protección contra ransomware con Microsoft 365](../media/ransomware-protection-microsoft-365/ransomware-protection-microsoft-365-step1.png)](ransomware-protection-microsoft-365-security-baselines.md)

## <a name="additional-ransomware-resources"></a>Recursos adicionales de ransomware

Información clave de Microsoft:

- [La creciente amenaza de ransomware](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/), entrada de blog de Microsoft On the Issues del 20 de julio de 2021
- [Ransomware operado por humanos](/security/compass/human-operated-ransomware)
- [Protéjase contra ransomware y extorsión de manera rápida](/security/compass/protect-against-ransomware)
- [Informe de Microsoft Digital Defense 2021](https://www.microsoft.com/security/business/microsoft-digital-defense-report) (vea las páginas 10-19)
- [Ransomware: informe de análisis de amenazas generalizado y continuo](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview) en el portal de Microsoft 365 Defender
- [Enfoque y procedimientos recomendados](/security/compass/incident-response-playbook-dart-ransomware-approach) de ransomware del equipo de detección y respuesta de Microsoft (DART) y [caso práctico](/security/compass/dart-ransomware-case-study)

Microsoft 365:

- [Maximizar la resistencia de ransomware con Azure y Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Recuperarse de un ataque de ransomware](/microsoft-365/security/office-365-security/recover-from-ransomware)
- [Protección de malware y ransomware](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [Proteger su equipo con Windows 10 de los ataques de ransomware](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [Control de ransomware en SharePoint Online](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- [Informes de análisis de amenazas para ransomware](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag) en el portal de Microsoft 365 Defender

Microsoft 365 Defender:

- [Buscar ransomware con la búsqueda avanzada de amenazas](/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Azure:

- [Defensas de Azure para los ataques de ransomware](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Maximizar la resistencia de ransomware con Azure y Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Plan de restauración y copia de seguridad para la protección contra ransomware](/security/compass/backup-plan-to-protect-against-ransomware)
- [Ayuda para la protección contra ransomware con Microsoft Azure Backup](https://www.youtube.com/watch?v=VhLOr2_1MCg) (vídeo de 26 minutos)
- [Recuperación de una identidad en peligro](/azure/security/fundamentals/recover-from-identity-compromise)
- [Detección avanzada de ataques de varias fases en Microsoft Sentinel](/azure/sentinel/fusion#ransomware)
- [Detección de difusión para ransomware en Microsoft Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Defender for Cloud Apps:

-  [Crear directivas de detección de anomalías en Defender para aplicaciones en la nube](/cloud-app-security/anomaly-detection-policy)

Entradas de blog del equipo de Seguridad de Microsoft:

- [3 pasos para evitar y recuperarse del ransomware (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [Una guía para combatir el ransomware operado por personas: Parte 1 (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/)

  Pasos clave sobre cómo el equipo de detección y respuesta de Microsoft (DART) lleva a cabo investigaciones de incidentes de ransomware.

- [Una guía para combatir el ransomware operado por personas: Parte 2 (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/)

  Recomendaciones y procedimientos recomendados.

- [Camino a la resistencia al comprender los riesgos de ciberseguridad: Parte 4 — Navegación por las amenazas actuales (mayo de 2021)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  Consulte la sección **Ransomware**.

- [Ataques de ransomware operados por humanos: Un desastre evitable (marzo de 2020)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  Incluye análisis de cadenas de ataques, de ataques reales.

- [Respuesta frente a ransomware: ¿pagar o no pagar? (diciembre de 2019)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro responde ante ataques de ransomware con transparencia (diciembre de 2019)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
