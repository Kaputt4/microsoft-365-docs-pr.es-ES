---
title: Microsoft 365 Security for Business Decision Makers (BDM)
description: Los escenarios de amenazas y ataques más comunes a los que se enfrentan actualmente las organizaciones para sus entornos de Microsoft 365 y las acciones recomendadas para mitigar estos riesgos.
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.prod: m365-security
ms.technology: m365d
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.openlocfilehash: 6a961e3d2740809eb4f3c0741277ef267db1b9ee
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64935333"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security for Business Decision Makers (BDM)

En este artículo se describen algunos de los escenarios de amenazas y ataques más comunes a los que se enfrentan actualmente las organizaciones para sus entornos de Microsoft 365 y las acciones recomendadas para mitigar estos riesgos. Aunque Microsoft 365 incluye una amplia gama de características de seguridad preconfiguradas, también requiere que usted, como cliente, asuma la responsabilidad de proteger sus propias identidades, datos y dispositivos que se usan para acceder a los servicios en la nube. Esta guía fue desarrollada por Kozeta Beam (arquitecto de seguridad en la nube de Microsoft) y Thiagaraj Sundararajan (consultor sénior de Microsoft).

Este artículo se organiza por prioridad de trabajo, empezando por la protección de las cuentas que se usan para administrar los servicios y recursos más críticos, como el inquilino, el correo electrónico y SharePoint. Proporciona una manera metódica de abordar la seguridad y funciona junto con la siguiente hoja de cálculo para que pueda realizar un seguimiento de su progreso con las partes interesadas y los equipos de toda la organización: [Microsoft 365 la seguridad de la hoja de cálculo de BDM](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx).

:::image type="content" source="../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png" alt-text="Un ejemplo del spreadhsheet de recomendación de seguridad de BDM de Microsoft 365" lightbox="../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png":::

Microsoft le proporciona la herramienta Puntuación segura dentro de su inquilino para analizar automáticamente la posición de seguridad en función de sus actividades normales, asignar una puntuación y proporcionar recomendaciones de mejora de seguridad. Antes de realizar las acciones recomendadas en este artículo, tome nota de la puntuación y las recomendaciones actuales. Las acciones recomendadas en este artículo aumentarán la puntuación. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades de proteger el entorno de forma que no afecte negativamente a la productividad de los usuarios. Consulte [Puntuación de seguridad de Microsoft](defender/microsoft-secure-score.md).

:::image type="content" source="../media/security/security-for-bdms-overview.png" alt-text="Los pasos para mitigar los riesgos para su empresa" lightbox="../media/security/security-for-bdms-overview.png":::

Una cosa más antes de empezar . . . asegúrese de [activar el registro de auditoría](../compliance/search-the-audit-log-in-security-and-compliance.md). Necesitará estos datos más adelante, en caso de que necesite investigar un incidente o una infracción.

## <a name="protect-privileged-accounts"></a>Protección de cuentas con privilegios

Como primer paso, se recomienda garantizar que las cuentas críticas del entorno tengan una capa adicional de protección, ya que estas cuentas tienen acceso y permisos para administrar y modificar los servicios y recursos críticos, lo que puede afectar negativamente a toda la organización, si se pone en peligro. La protección de cuentas con privilegios es una de las formas más eficaces de proteger contra un atacante que busca elevar los permisos de una cuenta en peligro a una administrativa.

|Recomendación  |E3 |E5  |
|---------|---------|---------|
|Aplique la autenticación multifactor (MFA) para todas las cuentas administrativas.|![marca de verificación verde.](../media/green-check-mark.png)|![marca de verificación verde.](../media/green-check-mark.png)|
|Implemente Azure Active Directory (Azure AD) Privileged Identity Management (PIM) para aplicar el acceso con privilegios Just-In-Time a Azure AD y recursos de Azure. También puede descubrir quién tiene acceso y revisar el acceso con privilegios.|         | ![marca de verificación verde.](../media/green-check-mark.png)|
|Implemente la administración de acceso con privilegios para administrar el control de acceso pormenorizado sobre las tareas de administración con privilegios en Office 365. |         | ![marca de verificación verde.](../media/green-check-mark.png)|
|Configure y use estaciones de trabajo de acceso con privilegios (PAW) para administrar servicios. No use las mismas estaciones de trabajo para navegar por Internet y comprobar el correo electrónico no relacionado con su cuenta administrativa.|  !![marca de verificación verde.](../media/green-check-mark.png)|![marca de verificación verde.](../media/green-check-mark.png)::: |

En el diagrama siguiente se muestran estas funcionalidades.
:::image type="content" source="../media/m365-security-bdm-illustrations-privileged-accounts.png" alt-text="Funcionalidades recomendadas para proteger cuentas con privilegios" lightbox="../media/m365-security-bdm-illustrations-privileged-accounts.png":::

Recomendaciones adicionales:

- Asegúrese de que las cuentas que se sincronizan desde el entorno local no tienen asignados roles de administrador para los servicios en la nube. Esto ayuda a evitar que un atacante aplique cuentas locales para obtener acceso administrativo a los servicios en la nube.
- Asegúrese de que las cuentas de servicio no tienen asignados roles de administrador. Estas cuentas a menudo no se supervisan y se establecen con contraseñas que no expiran. Para empezar, asegúrese de que las cuentas de servicios de AADConnect y ADFS no son administradores globales de forma predeterminada.
- Quite las licencias de las cuentas de administrador. A menos que haya un caso de uso específico para asignar licencias a cuentas de administrador específicas, quite las licencias de estas cuentas.

## <a name="reduce-the-surface-of-attack"></a>Reducir la superficie de ataque

El siguiente área de enfoque es reducir la superficie de ataque. Esto se puede lograr con un esfuerzo mínimo e impacto para los usuarios y servicios. Al reducir el área expuesta de ataque, los atacantes tienen menos formas de iniciar un ataque contra su organización.

Estos son algunos ejemplos:

- Deshabilite los protocolos POP3, IMAP y SMTP. La mayoría de las organizaciones modernas ya no usan estos protocolos anteriores. Puede deshabilitarlas de forma segura y permitir excepciones solo según sea necesario.
- Reduzca y mantenga el número de administradores globales en el inquilino al mínimo necesario. Esto reduce directamente el área expuesta de ataque para todas las aplicaciones en la nube.
- Retire los servidores y las aplicaciones que ya no se usan en su entorno.
- Implemente un proceso para deshabilitar y eliminar cuentas que ya no se usan.

## <a name="protect-against-known-threats"></a>Protección contra amenazas conocidas

Entre las amenazas conocidas se incluyen malware, cuentas en peligro y suplantación de identidad (phishing). Algunas protecciones contra estas amenazas se pueden implementar rápidamente sin ningún impacto directo para los usuarios, mientras que otras requieren más planeamiento y aprendizaje de usuarios.

|Recomendación  |E3  |E5  |
|---------|---------|---------|
|**Configure la autenticación multifactor y use las directivas de acceso condicional recomendadas, incluidas las directivas de riesgo de inicio de sesión**. Microsoft recomienda y ha probado un conjunto de directivas que funcionan conjuntamente para proteger todas las aplicaciones en la nube, incluidos los servicios de Office 365 y Microsoft 365. Consulte [Configuraciones de acceso a dispositivos y identidades](./office-365-security/microsoft-365-policies-configurations.md). | |![marca de verificación verde.](../media/green-check-mark.png)|
|**Requerir la autenticación multifactor para todos los usuarios**. Si no tiene las licencias necesarias para implementar las directivas de acceso condicional recomendadas, como mínimo, necesita la autenticación multifactor para todos los usuarios.|![marca de verificación verde.](../media/green-check-mark.png)|![marca de verificación verde.](../media/green-check-mark.png)|
|**Aumentar el nivel de protección contra malware en el correo**. El entorno de Office 365 o Microsoft 365 incluye protección contra malware, pero puede aumentar esta protección bloqueando los datos adjuntos con los tipos de archivo que se usan normalmente para el malware.|![marca de verificación verde.](../media/green-check-mark.png)|![marca de verificación verde.](../media/green-check-mark.png)|
|**Proteja su correo electrónico frente a ataques de suplantación de identidad (phishing) dirigidos**. Si ha configurado uno o varios dominios personalizados para el entorno de Office 365 o Microsoft 365, puede configurar la protección contra phishing dirigida. La protección contra suplantación de identidad (phishing), que forma parte de Defender para Office 365, puede ayudar a proteger su organización frente a ataques de suplantación de identidad malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario hacerlo.| |![marca de verificación verde.](../media/green-check-mark.png)|
|**Proteger contra ataques de ransomware en el correo electrónico**. Ransomware quita el acceso a sus datos mediante el cifrado de archivos o el bloqueo de pantallas del equipo. A continuación, intenta extorsionar dinero de las víctimas pidiendo "rescate", normalmente en forma de criptomonedas como Bitcoin, a cambio de devolver el acceso a sus datos. Puede ayudar a defenderse contra ransomware creando una o más reglas de flujo de correo para bloquear las extensiones de archivo que se usan habitualmente para ransomware, o para advertir a los usuarios que reciben estos datos adjuntos en el correo electrónico.|![marca de verificación verde.](../media/green-check-mark.png)|![marca de verificación verde.](../media/green-check-mark.png)|
|**Bloquee las conexiones de países con los que no hace negocios**. Cree una directiva de acceso condicional de Azure AD para bloquear las conexiones procedentes de estos países, creando de forma eficaz un firewall geográfico alrededor del inquilino.| |![marca de verificación verde.](../media/green-check-mark.png)|

En el diagrama siguiente se muestran estas funcionalidades.
:::image type="content" source="../media/m365-security-bdm-illustrations-known-threats.png" alt-text="Las funcionalidades recomendadas para protegerse frente a amenazas conocidas" lightbox="../media/m365-security-bdm-illustrations-known-threats.png":::


## <a name="protect-against-unknown-threats"></a>Protección contra amenazas desconocidas

Después de agregar protecciones adicionales a las cuentas con privilegios y protegerse contra ataques conocidos, desplace su atención a la protección contra amenazas desconocidas. Los adversarios más determinados y avanzados usan métodos innovadores y nuevos y desconocidos para atacar a las organizaciones. Con la gran telemetría de datos de Microsoft recopilada en miles de millones de dispositivos, aplicaciones y servicios, podemos realizar Defender para Office 365 en Windows, Office 365 y Azure para evitar ataques Zero-Day, usar entornos de sand box y comprobar la validez antes de permitir el acceso al contenido.

|Recomendación  |E3  |E5  |
|---------|---------|---------|
|**Configurar Microsoft Defender para Office 365**:<br>*vínculos Caja fuerte adjuntos<br>* Caja fuerte    <br>*Microsoft Defender para punto de conexión para SharePoint, OneDrive y Microsoft Teams<br>* Anti-phishing en Defender para Office 365 protection|         |![marca de verificación verde.](../media/green-check-mark.png) |
|**Configuración de las funcionalidades de Microsoft Defender para punto de conexión**:<br>*<br>protección contra vulnerabilidades de seguridad de Antivirus de Windows Defender* <br> *Reducción de la superficie expuesta a ataques <br>*    Aislamiento basado en hardware <br>* Acceso controlado a carpetas     |         |![marca de verificación verde.](../media/green-check-mark.png) |
|**Use Microsoft Defender for Cloud Apps** para detectar aplicaciones SaaS y empezar a usar análisis de comportamiento y detección de anomalías. |         |![marca de verificación verde.](../media/green-check-mark.png) |

En el diagrama siguiente se muestran estas funcionalidades.
:::image type="content" source="../media/m365-security-bdm-illustrations-unknown-threats.png" alt-text="Un ejemplo de las funcionalidades que ofrecen las herramientas para protegerse frente a amenazas desconocidas" lightbox="../media/m365-security-bdm-illustrations-unknown-threats.png":::


Recomendaciones adicionales:

- Proteja las comunicaciones del canal de asociado, como correos electrónicos mediante TLS.
- Abra Teams Federación solo a los asociados con los que se comunica.
- No agregue dominios de remitente, remitentes individuales ni direcciones IP de origen a la lista de permitidos, ya que esto permite omitir las comprobaciones de spam y malware. Una práctica común con los clientes es agregar sus propios dominios aceptados o muchos otros dominios en los que se hayan notificado problemas de flujo de correo electrónico a la lista de permitidos. No agregue dominios en la lista spam y filtrado de conexiones, ya que esto podría omitir todas las comprobaciones de correo no deseado.
- Habilitar las notificaciones de correo no deseado saliente: habilite las notificaciones de correo no deseado salientes en una lista de distribución internamente al departamento de soporte técnico o al equipo de administración de TI para informar si alguno de los usuarios internos envía correos electrónicos no deseados externamente. Esto podría ser un indicador de que la cuenta se ha puesto en peligro.
- Deshabilitar PowerShell remoto para todos los usuarios: los administradores usan PowerShell remoto principalmente para acceder a los servicios con fines administrativos o el acceso a la API mediante programación. Se recomienda deshabilitar esta opción para que los usuarios que no sean administradores eviten el reconocimiento a menos que tengan un requisito empresarial para acceder a ella.
- Bloquee el acceso al portal de administración de Microsoft Azure a todos los usuarios que no sean administradores. Para ello, cree una regla de acceso condicional para bloquear a todos los usuarios, excepto a los administradores.

## <a name="assume-breach"></a>Asumir una infracción

Aunque Microsoft toma todas las medidas posibles para evitar amenazas y ataques, se recomienda trabajar siempre con la mentalidad "Asumir vulneración". Incluso si un atacante ha logrado entrar en el entorno, debemos asegurarnos de que no pueden filtrar datos o información de identidad del entorno. Por este motivo, se recomienda habilitar la protección contra pérdidas de datos confidenciales, como números del Seguro Social, números de tarjetas de crédito, otra información personal y otra información confidencial de nivel organizativo.


|Recomendación |E3|E5 |
|---------|---------|---------|
|**Revise y optimice el acceso condicional y las directivas relacionadas para alinearse con los objetivos de una red de confianza cero**. La protección contra amenazas conocidas incluye la implementación de un conjunto de [directivas recomendadas](./office-365-security/microsoft-365-policies-configurations.md). Revise la implementación de estas directivas para asegurarse de que protege sus aplicaciones y datos frente a los hackers que han obtenido acceso a la red. La directiva de protección de aplicaciones de Intune recomendada para Windows 10 habilita Windows Information Protection (WIP). WIP protege contra fugas accidentales de datos de la organización a través de aplicaciones y servicios, como el correo electrónico, las redes sociales y la nube pública. |         |![marca de verificación verde.](../media/green-check-mark.png)|
|**Deshabilite el reenvío de correo electrónico externo**. Los hackers que obtienen acceso al buzón de correo de un usuario pueden robar su correo estableciendo el buzón para reenviar automáticamente el correo electrónico. Esto puede ocurrir incluso sin el reconocimiento del usuario. Puede evitar que esto suceda configurando una regla de flujo de correo.|![marca de verificación verde.](../media/green-check-mark.png) |![marca de verificación verde.](../media/green-check-mark.png)|
|**Deshabilite el uso compartido de calendarios externos anónimos**. De forma predeterminada, se permite el uso compartido de calendario anónimo externo. [Deshabilite el uso compartido de calendarios](/exchange/sharing/sharing-policies/modify-a-sharing-policy) para reducir posibles pérdidas de información confidencial.|![marca de verificación verde.](../media/green-check-mark.png) |![marca de verificación verde.](../media/green-check-mark.png)|
|**Configurar directivas de prevención de pérdida de datos para datos confidenciales**. Cree una directiva de prevención de pérdida de datos de Microsoft Purview en el Centro de cumplimiento de seguridad &amp; para detectar y proteger datos confidenciales, como números de tarjeta de crédito, números de seguro social y números de cuenta bancaria. Microsoft 365 incluye muchos tipos de información confidencial predefinidos que puede usar en las directivas de prevención de pérdida de datos. También puede crear sus propios tipos de información confidencial para datos confidenciales personalizados para su entorno. |![marca de verificación verde.](../media/green-check-mark.png)|![marca de verificación verde.](../media/green-check-mark.png)|
|**Implementar directivas de clasificación de datos y protección de la información**. Implemente etiquetas de confidencialidad y úslas para clasificar y aplicar la protección a datos confidenciales. También puede usar estas etiquetas en las directivas de prevención de pérdida de datos. Si usa etiquetas de Azure Information Protection, se recomienda evitar la creación de etiquetas nuevas en otros centros de administración.|         |![marca de verificación verde.](../media/green-check-mark.png)|
|**Proteja los datos en aplicaciones y servicios de terceros mediante aplicaciones de Defender for Cloud**. Configure directivas de Defender for Cloud Apps para proteger la información confidencial en aplicaciones en la nube de terceros, como Salesforce, Box o Dropbox. Puede usar tipos de información confidencial y las etiquetas de confidencialidad que creó en las directivas de Defender for Cloud Apps y aplicarlas en las aplicaciones SaaS. <br><br>Microsoft Defender for Cloud Apps permite aplicar una amplia gama de procesos automatizados. Las directivas se pueden establecer para proporcionar exámenes de cumplimiento continuos, tareas de exhibición de documentos electrónicos legales, DLP para contenido confidencial compartido públicamente, etc. Defender for Cloud Apps puede supervisar cualquier tipo de archivo en función de más de 20 filtros de metadatos (por ejemplo, nivel de acceso, tipo de archivo). |         |![marca de verificación verde.](../media/green-check-mark.png)|
|**Use [Microsoft Defender para punto de conexión para](/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) identificar si los usuarios almacenan información confidencial en sus dispositivos Windows**. |         |![marca de verificación verde.](../media/green-check-mark.png)|
|**Use [AIP Scanner](/azure/information-protection/deploy-aip-scanner) para identificar y clasificar información entre servidores y recursos compartidos de archivos**. Use la herramienta de informes de AIP para ver los resultados y realizar las acciones adecuadas.|         |![marca de verificación verde.](../media/green-check-mark.png)|

En el diagrama siguiente se muestran estas funcionalidades.
:::image type="content" source="../media/m365-security-bdm-illustrations-assume-breach.png" alt-text="Las funcionalidades recomendadas para protegerse frente a amenazas desconocidas" lightbox="../media/m365-security-bdm-illustrations-assume-breach.png":::


## <a name="continuous-monitoring-and-auditing"></a>Supervisión y auditoría continuas

Por último, pero no menos importante, la supervisión y auditoría continuas del entorno de Microsoft 365 junto con los Windows y dispositivos es fundamental para asegurarse de que puede detectar y corregir rápidamente las intrusiones. Herramientas como La puntuación segura, el portal de Microsoft 365 Defender y el análisis avanzado de Microsoft Intelligent Graph proporcionan información valiosa en el inquilino y vinculan grandes cantidades de datos de seguridad e inteligencia sobre amenazas para proporcionar protección y detección de amenazas sin precedentes.

|Recomendación |E3 |E5 |
|---------|---------|---------|
|Asegúrese de que el **registro de auditoría** está activado.|![marca de verificación verde.](../media/green-check-mark.png)|![marca de verificación verde.](../media/green-check-mark.png)|
|**Revisar puntuación segura semanalmente** : la puntuación de seguridad es una ubicación central para acceder al estado de seguridad de su empresa y realizar acciones basadas en recomendaciones de puntuación segura. Se recomienda realizar esta comprobación semanalmente.|![marca de verificación verde.](../media/green-check-mark.png)|![marca de verificación verde.](../media/green-check-mark.png)|
|Use **las herramientas de Microsoft Defender para Office 365**:<br>*Capacidades<br> de investigación y respuesta de amenazas*    Investigación y respuesta automatizadas |         |![marca de verificación verde.](../media/green-check-mark.png)|
|Uso **de Microsoft Defender para punto de conexión**:<br> *[Detección y respuesta de puntos de conexión](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br>*    Investigación y corrección automatizadas Puntuación segura <br>*    [Búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![marca de verificación verde.](../media/green-check-mark.png)|
|Use **Microsoft Defender for Cloud Apps** para detectar un comportamiento inusual en las aplicaciones en la nube para identificar ransomware, usuarios en peligro o aplicaciones no autorizadas, analizar el uso de alto riesgo y corregir automáticamente para limitar el riesgo a su organización.|         |:::image type="content" source="../media/green-check-mark.png" alt-text="Ejemplo de marca de verificación de color verde" lightbox="../media/green-check-mark.png":::|
|Use **Microsoft Sentinel** o la herramienta SIEM actual para supervisar las amenazas en todo el entorno. |         |![marca de verificación verde.](../media/green-check-mark.png)|
|**Implemente [Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)** para supervisar y proteger frente a amenazas dirigidas a su entorno de Active Directory local.   |         |![marca de verificación verde.](../media/green-check-mark.png) |
|Use **Microsoft Defender for Cloud** para supervisar las amenazas en cargas de trabajo híbridas y en la nube. Microsoft Defender for Cloud incluye un nivel gratuito de funcionalidades y un nivel estándar de funcionalidades que se pagan en función de las horas de recursos o las transacciones.|         |         |

En el diagrama siguiente se muestran estas funcionalidades.

:::image type="content" source="../media/m365-security-bdm-illustrations-monitoring-auditing.png" alt-text="Las funcionalidades recomendadas para la supervisión y auditoría continuas" lightbox="../media/m365-security-bdm-illustrations-monitoring-auditing.png":::


Principales acciones de supervisión recomendadas:

- **Revisión semanal de puntuación segura de Microsoft** : la puntuación de seguridad es una ubicación central para acceder al estado de seguridad del inquilino y realizar acciones basadas en las recomendaciones principales. Se recomienda realizar esta comprobación semanalmente. Puntuación segura incluye recomendaciones de Azure AD, Intune, aplicaciones Defender for Cloud y Microsoft Defender para punto de conexión, así como Office 365.
- **Revisar los inicios de sesión de riesgo semanalmente**: use el centro de administración de Azure AD para revisar los inicios de sesión de riesgo semanalmente. El conjunto de reglas de acceso a dispositivos e identidad recomendado incluye una directiva para aplicar el cambio de contraseña en los inicios de sesión de riesgo.  
- **Revisar los principales usuarios de malware y phished semanalmente** : use Microsoft Defender para Office 365 Explorador de amenazas para revisar los principales usuarios dirigidos a malware y fish y para averiguar la causa principal de por qué estos usuarios se ven afectados.
