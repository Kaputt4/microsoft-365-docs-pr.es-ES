---
title: Detección de ataques de ransomware operados por personas con Microsoft 365 Defender
description: En este artículo se describe la detección proactiva de ataques de ransomware nuevos o en curso operados por personas con el portal de Microsoft 365 Defender
search.appverid: MET150
author: nic-name
ms.author: noriordan
manager: dolmont
audience: ITPro
ms.topic: article
ms.date: 05/30/2022
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection: M365-security-compliance.
f1.keywords: NOCSH
ms.openlocfilehash: 95e916c02bc01a2e3e84d05efe4e5f5e66d3d491
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2022
ms.locfileid: "67107093"
---
# <a name="detecting-human-operated-ransomware-attacks-with-microsoft-365-defender"></a>Detección de ataques de ransomware operados por personas con Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Ransomware es un tipo de ataque de extorsión que destruye o cifra archivos y carpetas, impidiendo el acceso a datos críticos o interrumpiendo sistemas empresariales críticos. Hay dos tipos de ransomware:

* Ransomware mercancía es malware que se propaga con phishing o entre dispositivos y cifra los archivos antes de exigir un rescate.
* Ransomware operado por humanos es un ataque planeado y coordinado por cibercriminales activos que emplean varios métodos de ataque. En muchos casos, se usan técnicas y herramientas conocidas para infiltrarse en su organización, encontrar los recursos o sistemas que merece la pena extorsionar y, a continuación, exigir un rescate. Tras poner en peligro una red, el atacante lleva a cabo el reconocimiento de los recursos y sistemas que se pueden cifrar o extorsionar. A continuación, los atacantes cifran o filtran datos antes de exigir un rescate.

En este artículo se describe la detección proactiva de ataques de ransomware nuevos o en curso operados por personas con el portal de Microsoft 365 Defender, una solución de detección y respuesta extendida (XDR) para los siguientes servicios de seguridad:

* Microsoft Defender para punto de conexión
* Microsoft Defender para Office 365
* Microsoft Defender for Identity
* Microsoft Defender for Cloud Apps (incluido el complemento de gobernanza de aplicaciones)
* Microsoft Azure AD Identity Protection
* Microsoft Defender para IoT
* Microsoft 365 Empresa Premium
* Microsoft Defender para Empresas

Para obtener información sobre la prevención de ataques de ransomware, vea [Protección rápida contra ransomware y extorsión](/security/compass/protect-against-ransomware-phase3).

## <a name="the-importance-of-proactive-detection"></a>La importancia de la detección proactiva

Dado que los atacantes activos que podrían estar realizando los pasos para infiltrarse y descubrir sus datos y sistemas más valiosos en tiempo real, el tiempo necesario para detectar ataques de ransomware es fundamental.

Si las actividades previas al rescate se detectan rápidamente, la probabilidad de un ataque grave disminuye. La fase previa al rescate normalmente incluye las siguientes técnicas: acceso inicial, reconocimiento, robo de credenciales, movimiento lateral y persistencia. Estas técnicas pueden parecer inicialmente no relacionadas y a menudo vuelan bajo el radar. Si estas técnicas conducen a la fase de rescate, a menudo es demasiado tarde. Microsoft 365 Defender puede ayudar a identificar esos incidentes pequeños y aparentemente no relacionados como posiblemente parte de una campaña de ransomware más grande.

* Cuando se detecta durante la fase anterior al rescate, se pueden usar mitigaciones de menor escala, como aislar dispositivos infectados o cuentas de usuario, para interrumpir y corregir el ataque.
* Si la detección se produce en una fase posterior, como cuando se implementa el malware usado para cifrar archivos, es posible que sea necesario usar pasos de corrección más agresivos que puedan provocar tiempo de inactividad para interrumpir y corregir el ataque.

Es probable que las interrupciones de las operaciones empresariales respondan a un ataque de ransomware. La fase final de un ataque de ransomware suele ser una opción entre el tiempo de inactividad causado por atacantes con riesgos importantes o un tiempo de inactividad controlado para garantizar la seguridad de la red y darle tiempo para investigar por completo. Nunca recomendamos pagar un rescate. Pagar a los cibercriminales para obtener una clave de descifrado ransomware no proporciona ninguna garantía de que sus datos cifrados se restaurarán. Vea Respuesta [de ransomware: Blog de seguridad de Microsoft](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/).

Esta es la relación cualitativa del impacto de un ataque de ransomware y su tiempo para responder sin detección frente a detección y respuesta proactiva.

![La relación cualitativa del impacto de un ataque de ransomware y su tiempo para responder sin detección frente a detección y respuesta proactiva, mostrando el impacto en su negocio se reduce, cuanto más rápido responda.](../../media/defender/playbook-detecting-ransomware-m365-defender-qualitative-diagram.png)

### <a name="proactive-detection-via-common-malware-tools-and-techniques"></a>Detección proactiva a través de herramientas y técnicas comunes de malware

En muchos casos, los atacantes de ransomware operados por personas usan tácticas, técnicas, herramientas y procedimientos de malware conocidos y probados en el campo, como suplantación de identidad (phishing), riesgo de correo electrónico empresarial (BEC) y robo de credenciales. Los analistas de seguridad deben tener en cuenta y estar familiarizados con la forma en que los atacantes usan métodos comunes de malware y ciberataque para obtener un apoyo en su organización.

Para ver ejemplos de cómo los ataques de ransomware se inician con malware común, consulte estos recursos:

* [Ataques de ransomware operados por personas: un desastre evitable](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
* [Informes de análisis de amenazas de ransomware en el portal de Microsoft 365 Defender](https://sip.security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,exposureLevel,MisconfiguredDevices,VulnerableDevices,reportType,createdOn,lastUpdatedOn,tags,flag)

Estar familiarizado con el malware previo al rescate, las cargas útiles y las actividades ayuda a los analistas a saber qué buscar para evitar las fases posteriores de un ataque.

## <a name="human-operated-ransomware-attack-tactics"></a>Tácticas de ataque de ransomware operadas por humanos

Dado que el ransomware operado por humanos puede usar técnicas y herramientas de ataque conocidas, la comprensión y la experiencia de los analistas con las técnicas y herramientas de ataque existentes serán un recurso valioso al preparar al equipo de SecOps para prácticas de detección de ransomware centradas.

### <a name="attack-tactics-and-methods"></a>Tácticas y métodos de ataque

Estas son algunas de las técnicas y herramientas típicas que usan los atacantes de ransomware para las siguientes tácticas [&CK de MITRE ATT](https://attack.mitre.org/tactics/enterprise/) :

Acceso inicial:

* Fuerza bruta rdp
* Sistema accesible desde Internet vulnerable
* Configuración débil de la aplicación
* Correo de phishing

Robo de credenciales:

* Mimikatz
* Secretos de LSA
* Almacén de credenciales
* Credenciales en texto no cifrado
* Abuso de las cuentas de servicio

Movimiento lateral:

* Golpe de cobalto
* WMI
* Abuso de las herramientas de administración
* PsExec

Persistencia:

* Nuevas cuentas
* Cambios de GPO
* Herramientas de Shadow IT
* Programar tareas
* Registro de servicio

Evasión de defensa:

* Deshabilitación de las características de seguridad
* Borrar archivos de registro
* Eliminación de archivos de artefactos de ataque
* Restablecimiento de marcas de tiempo en archivos modificados

Exfiltración:

* Filtración de datos confidenciales Impacto (apalancamiento financiero):
* Cifrado de datos en contexto y en copias de seguridad
* Eliminación de datos en contexto y copias de seguridad, que pueden combinarse con una filtración anterior
* Amenaza de fuga pública de datos filtrados y confidenciales

### <a name="what-to-look-for"></a>Qué buscar

El desafío para los analistas de seguridad es reconocer cuándo una alerta forma parte de una cadena de ataques mayor con el objetivo de extorsionar sus datos confidenciales o sistemas cruciales. Por ejemplo, un ataque de suplantación de identidad detectado podría ser:

* Un ataque puntual para surtar los mensajes de correo electrónico de alguien en el departamento financiero de una organización.
* La parte anterior al rescate de una cadena de ataques para usar credenciales de cuenta de usuario en peligro para detectar los recursos disponibles para la cuenta de usuario y poner en peligro otras cuentas de usuario con mayores niveles de privilegios y acceso.

En esta sección se proporcionan fases y métodos de ataque comunes y los orígenes de señal que se alimentan en el portal central de Microsoft 365 Defender, que crea alertas e incidentes compuestos de varias alertas relacionadas para el análisis de seguridad. En algunos casos, hay portales de seguridad alternativos para ver los datos de ataque.

#### <a name="initial-attacks-to-gain-entry"></a>Ataques iniciales para obtener entrada

El atacante está intentando poner en peligro una cuenta de usuario, un dispositivo o una aplicación.

Método de ataque |Origen de señal |Portales de seguridad alternativos
|:---|:---|:---
Fuerza bruta rdp|Defender para punto de conexión|Defender for Cloud Apps
Sistema accesible desde Internet vulnerable|Características de seguridad de Windows, Microsoft Defender para servidores|
Configuración débil de la aplicación      |Defender for Cloud Apps, Defender for Cloud Apps con el complemento de gobernanza de aplicaciones|Defender for Cloud Apps |
Actividad de aplicación malintencionada      |Defender for Cloud Apps, Defender for Cloud Apps con el complemento de gobernanza de aplicaciones|Defender for Cloud Apps |
Correo de phishing        |Defender para Office 365
Difusión de contraseñas en cuentas de Azure AD |Azure AD Identity Protection a través de Defender for Cloud Apps      |Defender for Cloud Apps
Difusión de contraseñas en cuentas locales |Microsoft Defender for Identity
Compromiso del dispositivo       |Defender para punto de conexión
Robo de credenciales       |Microsoft Defender for Identity
Elevación de privilegios      |Microsoft Defender for Identity

#### <a name="recent-spike-in-otherwise-typical-behavior"></a>Aumento reciente en el comportamiento típico

El atacante intenta sondear entidades adicionales para poner en peligro.

Categoría de pico        |Origen de señal                 |Portales de seguridad alternativos
|:---                    |:---                              |:---
Inicios de sesión: numerosos intentos fallidos, intentos de inicio de sesión en varios dispositivos en un breve período, varios inicios de sesión por primera vez, etc. |Azure AD Identity Protection a través de Defender for Cloud Apps, Microsoft Defender for Identity |Defender for Cloud Apps
Cuenta de usuario activa recientemente, grupo, cuenta de equipo, aplicación |Azure AD Identity Protection a través de Defender for Cloud Apps (Azure AD), Defender for Identity (Servicios de dominio de Active Directory [AD DS]) |Defender for Cloud Apps
Actividad reciente de la aplicación, como el acceso a datos |Aplicaciones con Defender for Cloud Apps con el complemento de gobernanza de aplicaciones |Defender for Cloud Apps

#### <a name="new-activity"></a>Nueva actividad

El atacante está creando nuevas entidades para ampliar su alcance, instalar agentes de malware o eludir la detección.

Actividad     |Origen de señal           |Portal de seguridad alternativo
|:---                |:---                        |:---
Nuevas aplicaciones instaladas |Defender for Cloud Apps con el complemento de gobernanza de aplicaciones |Defender for Cloud Apps
Nuevas cuentas de usuario    |Azure Identity Protection         |Defender for Cloud Apps
Cambios de rol      |Azure Identity Protection        |Defender for Cloud Apps

#### <a name="suspicious-behavior"></a>Comportamiento sospechoso

El atacante está descargando información confidencial, cifrando archivos o recopilando o dañando los recursos de la organización.

Comportamiento       |Origen de señal
|:---                  |:---
Malware propagado a varios dispositivos |Defender para punto de conexión
Examen de recursos     |Defender para punto de conexión, Defender for Identity
Cambios en las reglas de reenvío de buzones |Defender para Office 365
Filtración y cifrado de datos |Defender para Office 365

**Supervisión de la seguridad de deshabilitación de adversarios** , ya que a menudo forma parte de la cadena de ataques de ransomware (HumOR) operados por humanos

* **Eliminación de registros** de eventos, especialmente el registro de eventos de seguridad y los registros operativos de PowerShell
* **Deshabilitación de herramientas o controles de seguridad** (asociados a algunos grupos)

## <a name="detect-ransomware-attacks-with-the-microsoft-365-defender-portal"></a>Detectar ataques de ransomware con el portal de Microsoft 365 Defender

El portal de Microsoft 365 Defender proporciona una vista centralizada para obtener información sobre las detecciones, los recursos afectados, las acciones automatizadas realizadas y las pruebas relacionadas, una combinación de:

* Una cola de incidentes, que agrupa las alertas relacionadas con un ataque para proporcionar el ámbito de ataque completo, los recursos afectados y las acciones de corrección automatizadas.
* Una cola de alertas, que enumera todas las alertas de las que se realiza el seguimiento por Microsoft 365 Defender.

### <a name="incident-and-alert-sources"></a>Orígenes de incidentes y alertas

Microsoft 365 Defender portal centraliza las señales de:

* Microsoft Defender para punto de conexión
* Microsoft Defender para Office 365
* Microsoft Defender for Identity
* Microsoft Defender for Cloud Apps (incluido el complemento de gobernanza de aplicaciones)
* Microsoft Azure AD Identity Protection
* Microsoft Defender para IoT

En esta tabla se enumeran algunos ataques típicos y su origen de señal correspondiente para Microsoft 365 Defender.

Ataques e incidentes           |Origen de señal
|:---                         |:---
Identidad en la nube: difusión de contraseñas, numerosos intentos fallidos, intentos de iniciar sesión en varios dispositivos en un breve período, varios inicios de sesión por primera vez, cuentas de usuario activas recientemente |Azure AD Identity Protection
Peligro de identidad local (AD DS)       |Defender for Identity
Suplantación de identidad (phishing)              |Defender para Office 365
Aplicaciones malintencionadas             |Defender for Cloud Apps o Defender for Cloud Apps con el complemento de gobernanza de aplicaciones
Peligro de punto de conexión (dispositivo)         |Defender para punto de conexión
Riesgo del dispositivo compatible con IoT          |Defender para IoT

### <a name="filtering-ransomware-identified-incidents"></a>Filtrado de incidentes identificados por ransomware

Puede filtrar fácilmente la cola de incidentes para los incidentes que se han clasificado por Microsoft 365 Defender como ransomware.

1. En el panel de navegación del portal de Microsoft 365 Defender, vaya a la cola de incidentes; para ello, seleccione **Incidentes y alertas > Incidentes**.
2. Seleccione **Filtros**.
3. En **Categorías**, seleccione **Ransomware**, seleccione **Aplicar** y, a continuación, cierre el panel **Filtros** .

Cada configuración de filtro para la cola de incidentes crea una dirección URL que puede guardar y acceder más adelante como vínculo. Estas direcciones URL se pueden marcar o guardar y usar cuando sea necesario con un solo clic. Por ejemplo, puede crear marcadores para:

* Incidentes que contienen la categoría "ransomware". Este es el [vínculo](https://security.microsoft.com/incidents?filters=AlertStatus%3DNew%257CInProgress,category%3Dransomware&page_size=30&fields=expand,name,tags,severity,investigationStates,category,impactedEntities,alertCount,serviceSource,detectionSource,firstEventTime,lastEventTime,sensitivity,status,incidentAssignment,classification,determination,rbacGroup) correspondiente.
* Incidentes con un nombre **de actor** especificado que se sabe que está realizando ataques de ransomware.
* Incidentes con un nombre **de amenaza asociado** especificado que se sabe que se usa en ataques de ransomware.
* Incidentes que contienen una etiqueta personalizada que el equipo de SecOps usa para incidentes que se sabe que forman parte de un ataque de ransomware más grande y coordinado.

### <a name="filtering-ransomware-identified-threat-analytics-reports"></a>Filtrado de informes de análisis de amenazas identificados por ransomware

De forma similar al filtrado de incidentes en la cola de incidentes, puede filtrar los informes de análisis de amenazas para los informes que incluyen ransomware.

1. En el panel de navegación, seleccione **Análisis de amenazas**.
2. Seleccione **Filtros**.
3. En **Etiquetas de amenazas**, seleccione **Ransomware**, seleccione **Aplicar** y, a continuación, cierre el panel **Filtros** .

También puede hacer clic en este vínculo.

En la sección **Detalles de detección** de muchos informes de análisis de amenazas, puede ver una lista de nombres de alertas creados para la amenaza.

### <a name="microsoft-365-defender-apis"></a>Las API de Microsoft 365 Defender

También puede usar las API de Microsoft 365 Defender para consultar los datos de alertas y incidentes de Microsoft 365 Defender en el inquilino. Una aplicación personalizada puede filtrar los datos, filtrarlos según la configuración personalizada y, a continuación, proporcionar una lista filtrada de vínculos a alertas e incidentes que puede seleccionar fácilmente para ir directamente a esa alerta o incidente. Consulte [Enumeración de la API de incidentes en Microsoft 365 Defender | Microsoft Docs](/api-list-incidents.md). También puede integrar SIEM con Microsoft Defender; consulte [Integración de las herramientas SIEM con Microsoft 365 Defender](/configure-siem-defender.md).

### <a name="microsoft-365-defender-sentinel-integration"></a>Integración de Microsoft 365 Defender Sentinel

La integración de incidentes Microsoft 365 Defender de Microsoft Sentinel le permite transmitir todos los incidentes de Microsoft 365 Defender a Microsoft Sentinel y mantenerlos sincronizados entre ambos portales. Los incidentes incluyen todas las alertas asociadas, las entidades y la información pertinente. Una vez en Sentinel, los incidentes permanecerán sincronizados bidireccionalmente con Microsoft 365 Defender, lo que le permite aprovechar las ventajas de ambos portales en la investigación de incidentes. Consulte Microsoft 365 Defender [integración con Microsoft Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).

### <a name="proactive-scanning-with-advanced-hunting"></a>Examen proactivo con búsqueda avanzada

[La búsqueda avanzada](/advanced-hunting-overview.md) es una herramienta de búsqueda de amenazas basada en consultas que le permite explorar e inspeccionar eventos en la red para localizar indicadores de amenazas y entidades. Esta herramienta de análisis flexible y personalizable permite la búsqueda sin restricciones de amenazas conocidas y potenciales. Microsoft 365 Defender también admite el uso de una consulta personalizada para crear [reglas de detección personalizadas](/custom-detections-overview.md), que crean alertas basadas en una consulta que se pueden ejecutar automáticamente y programadas.

Para el análisis proactivo de actividades de ransomware, debe ensamblar un catálogo de consultas de búsqueda avanzadas para métodos de ataque de ransomware de uso frecuente para identidades, puntos de conexión, aplicaciones y datos. Estos son algunos orígenes clave para consultas de búsqueda avanzadas listas para usar:

* El artículo [Búsqueda de ransomware](/advanced-hunting-find-ransomware.md)
* Repositorio de GitHub para consultas de búsqueda avanzadas:
  * [Consultas específicas de ransomware](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Ransomware)
  * [Todas las categorías](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Ransomware) de consultas
* Informes de análisis de amenazas
  * Sección de búsqueda avanzada del ransomware: un informe de analistas de [amenazas generalizado y en curso](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/analystreport)
  * Sección de búsqueda avanzada de otros informes de analistas

### <a name="automated-hunting"></a>Búsqueda automatizada

Las consultas de búsqueda avanzadas también se pueden usar para crear reglas y acciones de detección personalizadas basadas en elementos conocidos de un método de ataque de ransomware (por ejemplo, el uso de comandos de PowerShell inusuales). Las reglas de detección personalizadas crean alertas que los analistas de seguridad pueden ver y abordar.

Para crear una regla de detección personalizada, seleccione **Crear regla de detección personalizada** en la página de una consulta de búsqueda avanzada. Una vez creado, puede especificar:

* Frecuencia con la que se ejecuta la regla de detección personalizada
* Gravedad de la alerta creada por la regla
* Fase de ataque de MITRE para la alerta creada
* Entidades afectadas
* Acciones que se van a realizar en entidades afectadas

## <a name="prepare-your-secops-team-for-focused-ransomware-detection"></a>Preparación del equipo de SecOps para la detección de ransomware centrada

La preparación del equipo de SecOps para la detección proactiva de ransomware requiere lo siguiente:

* Trabajo previo para el equipo y la organización de SecOps
* Formación de analistas de seguridad, según sea necesario
* Trabajo operativo continuo para incorporar los últimos ataques y experiencias de detección de los analistas de seguridad

### <a name="pre-work-for-your-secops-team-and-organization"></a>Trabajo previo para el equipo y la organización de SecOps

Tenga en cuenta estos pasos para preparar el equipo y la organización de SecOps para la prevención de ataques de ransomware centrada:

1. Configure su infraestructura de TI y la nube para la prevención de ransomware con la guía [De protección rápida contra ransomware y extorsión](/security/compass/protect-against-ransomware-phase3) . Las fases y tareas de esta guía se pueden realizar en paralelo con los pasos siguientes.
2. Obtenga las licencias adecuadas para los servicios Defender para punto de conexión, Defender para Office 365, Defender for Identity, Defender for Cloud Apps, el complemento de gobernanza de aplicaciones, Defender para IoT y Azure AD Identity Protection.
3. Ensamblar un catálogo de consultas de búsqueda avanzadas optimizadas para métodos de ataque de ransomware conocidos o fases de ataque.
4. Cree el conjunto de reglas de detección personalizadas para consultas de búsqueda avanzadas específicas que creen alertas para métodos de ataque de ransomware conocidos, incluida su programación, nomenclatura de alertas y acciones automatizadas.
5. Determine el conjunto de [etiquetas o estándares personalizados](/manage-incidents.md) para crear uno nuevo para identificar los incidentes que se sabe que forman parte de un ataque de ransomware más grande y coordinado.
6. Determine el conjunto de tareas operativas para la administración de incidentes y alertas de ransomware. Por ejemplo:

* Procesos para el análisis de analistas de nivel 1 de incidentes entrantes y alertas y asignación a analistas de nivel 2 para su investigación.
* Ejecutar manualmente consultas de búsqueda avanzadas y su programación (diaria, semanal, mensual).
* Cambios continuos basados en experiencias de mitigación y investigación de ataques de ransomware.

### <a name="security-analyst-training"></a>Formación de analistas de seguridad

Según sea necesario, puede proporcionar a los analistas de seguridad formación interna para:

* Cadenas comunes de ataques de ransomware (tácticas de ataque MITRE y técnicas comunes de amenazas y malware)
* Incidentes y alertas y cómo localizarlos y analizarlos en el portal de Microsoft 365 Defender mediante:
  * Alertas e incidentes ya creados por Microsoft 365 Defender
  * Filtros basados en direcciones URL previamente examinadas para el portal de Microsoft 365 Defender
  * Mediante programación a través de la API de incidentes
* Consultas de búsqueda avanzadas que se usan y su programación manual (diaria, semanal, mensual)
* Reglas de detección personalizadas que se van a usar y su configuración
* Etiquetas de incidentes personalizadas
* Los últimos [informes de análisis de amenazas para ataques de ransomware](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag) en el portal de Microsoft 365 Defender

### <a name="ongoing-work-based-on-operational-learning-and-new-threats"></a>Trabajo continuo basado en el aprendizaje operativo y nuevas amenazas

Como parte de la herramienta continua del equipo de SecOps y los procedimientos recomendados de procesos y las experiencias de los analistas de seguridad, debe:

* Actualice el catálogo de consultas de búsqueda avanzadas con:
  * Nuevas consultas basadas en los informes de análisis de amenazas más recientes en el portal de Microsoft 365 Defender o en el [repositorio de GitHub de búsqueda avanzada](<https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Ransomware>).
  * Cambios en los existentes para optimizar la identificación de amenazas o para mejorar la calidad de las alertas.
* Actualice las reglas de detección personalizadas basadas en consultas de búsqueda avanzadas nuevas o modificadas.
* Actualice el conjunto de tareas operativas para la detección de ransomware.
