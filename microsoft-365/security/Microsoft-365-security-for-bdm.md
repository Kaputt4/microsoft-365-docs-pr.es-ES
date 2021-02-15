---
title: Seguridad de Microsoft 365 para responsables de decisiones empresariales (BDMs)
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: los escenarios de amenazas y ataques más comunes a los que se enfrentan actualmente las organizaciones para sus entornos de Microsoft 365 y las acciones recomendadas para mitigar estos riesgos.
ms.openlocfilehash: 64f4491db3dc4ef18411b166fb23c4388383dae2
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944309"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Seguridad de Microsoft 365 para responsables de decisiones empresariales (BDMs)

En este artículo se analizan algunos de los escenarios de amenazas y ataques más comunes a los que se enfrentan actualmente las organizaciones para sus entornos de Microsoft 365, así como las acciones recomendadas para mitigar estos riesgos. Aunque Microsoft 365 incluye una amplia variedad de características de seguridad preconfiguradas, también requiere que usted como cliente aseste la responsabilidad de proteger sus propias identidades, datos y dispositivos usados para acceder a los servicios en la nube. Esta guía fue desarrollada porDjeta Beam (arquitecto de seguridad en la nube de Microsoft) y Thiagandar Sundararajan (consultor sénior de Microsoft).

Este artículo se organiza por prioridad de trabajo, empezando por la protección de las cuentas usadas para administrar los servicios y activos más críticos, como el espacio empresarial, el correo electrónico y SharePoint. Proporciona un método para abordar la seguridad y funciona junto con la hoja de cálculo siguiente para que pueda realizar un seguimiento de su progreso con las partes interesadas y los equipos de toda la organización: seguridad de [Microsoft 365](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)para hojas de cálculo de BDMs. 

[![Hoja de cálculo de recomendaciones de seguridad BDM de Microsoft 365 para imágenes en miniatura](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft le proporciona la herramienta Puntuación segura dentro de su espacio empresarial para analizar automáticamente su posición de seguridad en función de sus actividades habituales, asignar una puntuación y proporcionar recomendaciones para mejorar la seguridad. Antes de tomar las acciones recomendadas en este artículo, tome nota de su puntuación y recomendaciones actuales. Las acciones recomendadas en este artículo aumentarán la puntuación. El objetivo no es lograr la puntuación máxima, sino tener en cuenta las oportunidades para proteger su entorno de forma que no afecte negativamente a la productividad de los usuarios. Vea [Puntuación de seguridad de Microsoft.](mtp/microsoft-secure-score.md)

![Siga estos pasos para mitigar los riesgos para su empresa.](../media/security/security-for-bdms-overview.png)

Una cosa más antes de empezar. . . asegúrese de activar [el registro de auditoría.](../compliance/search-the-audit-log-in-security-and-compliance.md) Necesitarás estos datos más adelante, en caso de que necesites investigar un incidente o una infracción. 

## <a name="protect-privileged-accounts"></a>Proteger cuentas con privilegios

Como primer paso, se recomienda garantizar que las cuentas críticas del entorno tengan un nivel adicional de protección, ya que estas cuentas tienen acceso y permisos para administrar y modificar los servicios y recursos críticos que pueden afectar negativamente a toda la organización, si se encuentran en peligro. Proteger las cuentas con privilegios es una de las formas más eficaces de protegerse contra un atacante que intenta elevar los permisos de una cuenta comprometida a una administrativa. 

|Recomendación  |E3 |E5  |
|---------|---------|---------|
|Aplicar la autenticación multifactor (MFA) para todas las cuentas administrativas.|![marca de verificación verde](../media/green-check-mark.png)|![marca de verificación verde](../media/green-check-mark.png)| 
|Implemente Azure Active Directory (Azure AD) Privileged Identity Management (PIM) para aplicar el acceso con privilegios just-in-time a los recursos de Azure AD y Azure. También puede descubrir quién tiene acceso y revisar el acceso con privilegios.|         | ![marca de verificación verde](../media/green-check-mark.png)|
|Implementar la administración de acceso con privilegios para administrar el control de acceso granular sobre las tareas de administración con privilegios en Office 365. |         | ![marca de verificación verde](../media/green-check-mark.png)|
|Configurar y usar estaciones de trabajo de acceso con privilegios (PAW) para administrar servicios. No use las mismas estaciones de trabajo para explorar Internet y comprobar el correo electrónico que no está relacionado con su cuenta administrativa.|  ![marca de verificación verde](../media/green-check-mark.png)|![marca de verificación verde](../media/green-check-mark.png) | 

En el siguiente diagrama se ilustran estas capacidades.
![Funcionalidades recomendadas para proteger cuentas con privilegios](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Recomendaciones adicionales:
- Asegúrese de que las cuentas sincronizadas desde el entorno local no tienen asignados roles de administrador para los servicios en la nube. Esto ayuda a evitar que un atacante aproveche las cuentas locales para obtener acceso administrativo a los servicios en la nube. 
- Asegúrese de que las cuentas de servicio no tienen roles de administrador asignados. A menudo, estas cuentas no se supervisan y se establecen con contraseñas que no expiran. Empiece por asegurarse de que las cuentas de servicios de AADConnect y ADFS no sean administradores globales de forma predeterminada.
- Quitar licencias de cuentas de administrador. A menos que haya un caso de uso específico para asignar licencias a cuentas de administrador específicas, quite las licencias de estas cuentas. 

## <a name="reduce-the-surface-of-attack"></a>Reducir la superficie de ataque

El siguiente área de enfoque es reducir la superficie de ataque. Esto se puede lograr con el mínimo esfuerzo e impacto en los usuarios y servicios. Al reducir el área de superficie de ataque, los atacantes tienen menos formas de iniciar un ataque contra la organización.

Aquí le mostramos otros ejemplos:
- Deshabilite los protocolos POP3, IMAP y SMTP. La mayoría de las organizaciones modernas ya no usan estos protocolos más antiguos. Puede deshabilitarlas de forma segura y permitir excepciones solo según sea necesario. 
- Reduzca y mantenga el número de administradores globales en el espacio empresarial al mínimo absoluto necesario. Esto reduce directamente el área de ataque de todas las aplicaciones en la nube. 
- Retire los servidores y las aplicaciones que ya no se usan en su entorno. 
- Implementar un proceso para deshabilitar y eliminar cuentas que ya no se usan. 

## <a name="protect-against-known-threats"></a>Proteger contra amenazas conocidas

Las amenazas conocidas incluyen malware, cuentas comprometidas y suplantación de identidad. Algunas protecciones contra estas amenazas se pueden implementar rápidamente sin ningún impacto directo en los usuarios, mientras que otras requieren más planeación y formación de los usuarios. 

|Recomendación  |E3  |E5  |
|---------|---------|---------|
|**Configure la autenticación multifactor y use las directivas de acceso condicional recomendadas, incluidas** las directivas de riesgo de inicio de sesión. Microsoft recomienda y ha probado un conjunto de directivas que funcionan conjuntamente para proteger todas las aplicaciones en la nube, incluidos los servicios de Office 365 y Microsoft 365. Consulta [Configuraciones de acceso a dispositivos e identidades.](./office-365-security/microsoft-365-policies-configurations.md) | |![marca de verificación verde](../media/green-check-mark.png)|
|**Requerir autenticación multifactor para todos los usuarios.** Si no dispone de la licencia necesaria para implementar las directivas de acceso condicional recomendadas, como mínimo, requiera autenticación multifactor para todos los usuarios.|![marca de verificación verde](../media/green-check-mark.png)|![marca de verificación verde](../media/green-check-mark.png)|
|**Aumentar el nivel de protección contra malware en el correo.** Su entorno de Office 365 o Microsoft 365 incluye protección contra malware, pero puede aumentar esta protección bloqueando los datos adjuntos con tipos de archivo que se usan habitualmente para malware.|![marca de verificación verde](../media/green-check-mark.png)|![marca de verificación verde](../media/green-check-mark.png)|
|**Proteja su correo electrónico de ataques de suplantación de identidad dirigidos.** Si ha configurado uno o más dominios personalizados para su entorno de Office 365 o Microsoft 365, puede configurar la protección contra suplantación de identidad dirigida. La protección contra la suplantación de identidad(phishing), que forma parte de Defender para Office 365, puede ayudar a proteger su organización contra ataques de suplantación de identidad malintencionados y otros ataques de suplantación de identidad. Si no ha configurado un dominio personalizado, no es necesario hacerlo.| |![marca de verificación verde](../media/green-check-mark.png)|
|**Protegerse contra ataques de ransomware en el correo electrónico.** Ransomware quita el acceso a los datos mediante el cifrado de archivos o el bloqueo de pantallas del equipo. A continuación, intenta extorsionar dinero a las víctimas solicitando "rescate", normalmente en forma de criptodivisas, como Crypto, a cambio de devolver el acceso a los datos. Puede ayudar a defenderse contra ransomware creando una o más reglas de flujo de correo para bloquear las extensiones de archivo que se usan habitualmente para ransomware, o para advertir a los usuarios que reciben estos datos adjuntos por correo electrónico.|![marca de verificación verde](../media/green-check-mark.png)|![marca de verificación verde](../media/green-check-mark.png)|
|**Bloquear conexiones de países con los que no se hace negocio.** Cree una directiva de acceso condicional de Azure AD para bloquear las conexiones procedentes de estos países, creando de forma eficaz un firewall geográfico alrededor de su espacio empresarial.| |![marca de verificación verde](../media/green-check-mark.png)|

En el siguiente diagrama se ilustran estas capacidades.
![Funcionalidades recomendadas para proteger contra amenazas conocidas](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Proteger contra amenazas desconocidas

Después de agregar protecciones adicionales a las cuentas con privilegios y protegerse contra ataques conocidos, desconsódale la protección contra amenazas desconocidas. Los adversarios más decididos y avanzados usan métodos nuevos y desconocidos para atacar a las organizaciones. Con la gran telemetría de datos de Microsoft recopilada en miles de millones de dispositivos, aplicaciones y servicios, podemos realizar Defender para Office 365 en Windows, Office 365 y Azure para evitar ataques de día cero, usar entornos de arena y comprobar la validez antes de permitir el acceso a su contenido. 


|Recomendación  |E3  |E5  |
|---------|---------|---------|
|**Configurar Microsoft Defender para Office 365:**<br>* Datos adjuntos seguros<br>* Vínculos seguros<br>* ATP para SharePoint, OneDrive y Microsoft Teams<br>* Anti-phishing in Defender for Office 365 protection|         |![marca de verificación verde](../media/green-check-mark.png) |
|**Configurar Microsoft Defender para las funcionalidades de puntos de conexión:**<br>* Windows Defender Antivirus <br>* Protección contra vulnerabilidades <br> * Reducción de superficie de ataque <br> * Aislamiento basado en hardware <br>* Acceso controlado a carpetas     |         |![marca de verificación verde](../media/green-check-mark.png) |
|**Use Microsoft Cloud App Security para** detectar aplicaciones SaaS y empezar a usar análisis de comportamiento y detección de anomalías. |         |![marca de verificación verde](../media/green-check-mark.png) |

En el siguiente diagrama se ilustran estas capacidades.
![Funcionalidades recomendadas para proteger contra amenazas desconocidas](../media/m365-security-bdm-illustrations-unknown-threats.png)

Recomendaciones adicionales:
- Proteger las comunicaciones del canal de asociados, como correos electrónicos con TLS.
- Abra la federación de Teams solo para los partners con los que se comunique.
- No agregue dominios de remitente, remitentes individuales ni direcciones IP de origen a la lista de permitidos, ya que esto permite omitir las comprobaciones de correo no deseado y malware: una práctica común con los clientes es agregar sus propios dominios aceptados o varios otros dominios en los que se hayan notificado problemas de flujo de correo electrónico a la lista de permitidos. No agregue dominios a la lista de filtrado de correo no deseado y de conexión, ya que esto podría omitir todas las comprobaciones de correo no deseado. 
- Habilitar las notificaciones de correo no deseado saliente: habilite las notificaciones de correo no deseado saliente a una lista de distribución internamente al departamento de soporte técnico o al equipo de administración de TI para informar si alguno de los usuarios internos envía correos electrónicos de correo no deseado externamente. Esto podría ser un indicador de que la cuenta se ha visto comprometida.
- Deshabilitar PowerShell remoto para todos los usuarios: PowerShell remoto lo usan principalmente los administradores para obtener acceso a los servicios con fines administrativos o mediante programación de acceso a la API. Recomendamos deshabilitar esta opción para que los usuarios que no sean administradores eviten el reconocimiento a menos que tengan un requisito empresarial para acceder a ella. 
- Bloquear el acceso al portal de administración de Microsoft Azure para todos los usuarios que no son administradores. Puede hacerlo creando una regla de acceso condicional para bloquear todos los usuarios, excepto los administradores. 


## <a name="assume-breach"></a>Asumir una infracción

Aunque Microsoft toma todas las medidas posibles para evitar amenazas y ataques, le recomendamos que siempre trabaje con la idea de "Asumir vulneración". Incluso si un atacante ha logrado entrar en el entorno, debemos asegurarnos de que no puedan filtrar datos o información de identidad del entorno. Por este motivo, se recomienda habilitar la protección contra pérdidas de datos confidenciales, como números de la Seguridad Social, números de tarjetas de crédito, información personal adicional y otra información confidencial de nivel organizativo. 

La idea "Asumir vulneración" requiere implementar una estrategia de red de confianza cero, lo que significa que los usuarios no son de plena confianza solo porque son internos en la red. En su lugar, como parte de la autorización de lo que pueden hacer los usuarios, se especifican conjuntos de condiciones y, cuando se cumplen dichas condiciones, se aplican ciertos controles. Las condiciones pueden incluir el estado del dispositivo, el acceso a la aplicación, las operaciones realizadas y el riesgo del usuario. Por ejemplo, una acción de inscripción de dispositivos siempre debe desencadenar la autenticación MFA para asegurarse de que no se agregan dispositivos móviles al entorno. 

Una estrategia de red de confianza cero también requiere que sepa dónde se almacena la información y aplique los controles adecuados para la clasificación, protección y retención. Para proteger eficazmente los activos más críticos y confidenciales, primero debe identificar dónde se encuentran y realizar un inventario, lo que puede resultar complicado. A continuación, trabaje con su organización para definir una estrategia de gobierno. La definición de un esquema de clasificación para una organización y la configuración de directivas, etiquetas y condiciones requiere una planeación y preparación cuidadosas. Es importante tener en cuenta que no se trata de un proceso controlado por EL. Asegúrese de trabajar con su equipo legal y de cumplimiento para desarrollar un esquema de clasificación y etiquetado adecuado para los datos de su organización.

Las capacidades de protección de la información de Microsoft 365 pueden ayudarle a descubrir qué información tiene, dónde se almacena y qué información requiere protección adicional. La protección de la información es un proceso continuo y las funcionalidades de Microsoft 365 proporcionan visibilidad sobre cómo los usuarios usan y distribuyen información confidencial, dónde se almacena actualmente la información y dónde fluye. También puede ver cómo los usuarios manejan la información regulada para asegurarse de que se aplican las etiquetas y protecciones adecuadas.


|Recomendación |E3|E5 |
|---------|---------|---------|
|**Revise y optimice el acceso condicional y las directivas** relacionadas para que se alineen con los objetivos de una red de confianza cero. La protección contra amenazas conocidas incluye la implementación de un conjunto de [directivas recomendadas.](./office-365-security/microsoft-365-policies-configurations.md) Revisa la implementación de estas directivas para asegurarte de que proteges tus aplicaciones y datos contra hackers que han obtenido acceso a la red. Ten en cuenta que la directiva de protección de aplicaciones de Intune recomendada para Windows 10 habilita Windows Information Protection (WIP). WIP protege contra pérdidas accidentales de datos de la organización a través de aplicaciones y servicios, como correo electrónico, redes sociales y la nube pública. |         |![marca de verificación verde](../media/green-check-mark.png)|
|**Deshabilitar el reenvío de correo electrónico externo.** Los hackers que obtienen acceso al buzón de un usuario pueden robar su correo estableciendo el buzón para reenviar automáticamente el correo electrónico. Esto puede suceder incluso sin el conocimiento del usuario. Puede evitar que esto ocurra configurando una regla de flujo de correo.|![marca de verificación verde](../media/green-check-mark.png) |![marca de verificación verde](../media/green-check-mark.png)|
|**Deshabilitar el uso compartido anónimo de calendario externo.** De forma predeterminada, se permite el uso compartido de calendario anónimo externo. [Deshabilitar el uso compartido de](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) calendarios para reducir posibles pérdidas de información confidencial.|![marca de verificación verde](../media/green-check-mark.png) |![marca de verificación verde](../media/green-check-mark.png)|
|**Configurar directivas de prevención de pérdida de datos para datos confidenciales.** Cree una directiva de prevención de pérdida de datos en el Centro de cumplimiento de seguridad para detectar y proteger datos confidenciales, como números de tarjeta de crédito, números de la Seguridad &amp; Social y números de cuentas bancarias. Microsoft 365 incluye muchos tipos predefinidos de información confidencial que puede usar en las directivas de prevención de pérdida de datos. También puede crear sus propios tipos de información confidencial para datos confidenciales personalizados para su entorno. |![marca de verificación verde](../media/green-check-mark.png)|![marca de verificación verde](../media/green-check-mark.png)|
|**Implementar directivas de clasificación de datos y protección de la información.** Implementar etiquetas de confidencialidad y usarlas para clasificar y aplicar protección a datos confidenciales. También puede usar estas etiquetas en las directivas de prevención de pérdida de datos. Si usa etiquetas de Azure Information Protection, le recomendamos que evite crear nuevas etiquetas en otros centros de administración.|         |![marca de verificación verde](../media/green-check-mark.png)|
|**Proteja los datos de servicios y aplicaciones de terceros mediante Cloud App Security.** Configure las directivas de Cloud App Security para proteger la información confidencial en aplicaciones en la nube de terceros, como Salesforce, Box o Dropbox. Puede usar los tipos de información confidencial y las etiquetas de confidencialidad que creó en las directivas de Cloud App Security y aplicarlos en todas las aplicaciones SaaS. <br><br>Microsoft Cloud App Security le permite aplicar una amplia gama de procesos automatizados. Las directivas se pueden establecer para proporcionar exámenes de cumplimiento continuos, tareas legales de exhibición de documentos electrónicos, DLP para contenido confidencial compartido públicamente y mucho más. Cloud App Security puede supervisar cualquier tipo de archivo en función de más de 20 filtros de metadatos (por ejemplo, nivel de acceso, tipo de archivo). |         |![marca de verificación verde](../media/green-check-mark.png)|
|**Usa [Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) para identificar si los usuarios almacenan información confidencial en sus dispositivos Windows.** |         |![marca de verificación verde](../media/green-check-mark.png)|
|**Use [el escáner AIP para](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) identificar y clasificar información entre servidores y recursos compartidos de archivos.** Use la herramienta de informes AIP para ver los resultados y realizar las acciones adecuadas.|         |![marca de verificación verde](../media/green-check-mark.png)|

En el siguiente diagrama se ilustran estas capacidades.
![Funcionalidades recomendadas para proteger contra infracciones](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Supervisión y auditoría continuas

Por último, pero no menos importante, la supervisión continua y la auditoría del entorno de Microsoft 365 junto con Windows y dispositivos es fundamental para asegurarse de que es capaz de detectar y corregir rápidamente cualquier intrusión. Herramientas como Puntuación de seguridad, Centro de seguridad y análisis avanzado de Microsoft Intelligent Graph proporcionan información valiosa en su espacio empresarial y vinculan grandes cantidades de inteligencia de amenazas y datos de seguridad para proporcionarle protección y detección de amenazas incalculables.


|Recomendación |E3 |E5 |
|---------|---------|---------|
|Asegúrese de **que el registro de auditoría** está activado.|![marca de verificación verde](../media/green-check-mark.png)|![marca de verificación verde](../media/green-check-mark.png)|
|**Revisar puntuación de seguridad semanalmente:** la puntuación de seguridad es una ubicación central para obtener acceso al estado de seguridad de su empresa y realizar acciones basadas en las recomendaciones de puntuación de seguridad. Se recomienda realizar esta comprobación semanalmente.|![marca de verificación verde](../media/green-check-mark.png)|![marca de verificación verde](../media/green-check-mark.png)|
|Use **Las herramientas de Microsoft Defender para Office 365:**<br>* Capacidades de investigación y respuesta de amenazas<br> * Investigación y respuesta automatizadas |         |![marca de verificación verde](../media/green-check-mark.png)|
|Use **Microsoft Defender para endpoint:**<br> *    [Detección y respuesta de puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Investigación automatizada y corrección Puntuación de seguridad <br>*    [Búsqueda avanzada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![marca de verificación verde](../media/green-check-mark.png)|
|Usa **Microsoft Cloud App Security** para detectar comportamientos inusuales en las aplicaciones en la nube para identificar ransomware, usuarios comprometidos o aplicaciones no autorizados, analizar el uso de alto riesgo y corregir automáticamente para limitar el riesgo a la organización.|         |![marca de verificación verde](../media/green-check-mark.png)|
|Use **Microsoft Azure Sentinel o** la herramienta SIEM actual para supervisar las amenazas en su entorno. |         |![marca de verificación verde](../media/green-check-mark.png)|
|**Implemente [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)** para supervisar y proteger contra las amenazas destinadas a su entorno local de Active Directory.   |         |![marca de verificación verde](../media/green-check-mark.png) |
|Use **Azure Defender** _ para supervisar las amenazas en las cargas de trabajo híbridas y en la nube. Azure Defender_ incluye un nivel gratuito de funcionalidades y un nivel estándar de funcionalidades que se pagan en función de las horas de recursos o las transacciones.|         |         |

En el siguiente diagrama se ilustran estas capacidades.
![Funcionalidades recomendadas para supervisión y auditoría continuas](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

Principales acciones de supervisión recomendadas:
- **Revise la puntuación de seguridad de Microsoft** semanalmente: la puntuación de seguridad es una ubicación central para obtener acceso al estado de seguridad de su espacio empresarial y tomar medidas basadas en las recomendaciones principales. Se recomienda realizar esta comprobación semanalmente. La puntuación de seguridad incluye recomendaciones de Azure AD, Intune, Cloud App Security y Microsoft Defender para endpoint, así como Office 365. 
- **Revise semanalmente los inicios de sesión** de riesgo: use el Centro de administración de Azure AD para revisar los inicios de sesión de riesgo semanalmente. El conjunto de reglas de acceso de dispositivo e identidad recomendado incluye una directiva para aplicar el cambio de contraseña en inicios de sesión de riesgo.  
- Revise semanalmente los principales usuarios de malware y **phishing:** use Microsoft Defender para el Explorador de amenazas de Office 365 para revisar los principales usuarios dirigidos con malware y phishing y para averiguar la causa principal de por qué estos usuarios se ven afectados.
