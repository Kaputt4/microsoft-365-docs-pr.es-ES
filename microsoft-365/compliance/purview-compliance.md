---
title: Soluciones de cumplimiento y riesgo de Microsoft Purview
description: Use este artículo para obtener más información sobre las soluciones de riesgo y cumplimiento de Microsoft Purview.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, soluciones
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: m365-security-compliance
ms.openlocfilehash: 96b1efdddcf8a0b2e1034c392c27f160137379de
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66998387"
---
# <a name="microsoft-purview-risk-and-compliance-solutions"></a>Soluciones de cumplimiento y riesgo de Microsoft Purview

Las soluciones de cumplimiento y riesgo de [Microsoft Purview](/purview/purview) le ayudan a administrar y supervisar los datos, proteger la información, minimizar los riesgos de cumplimiento y cumplir los requisitos normativos. Este artículo le ayudará a obtener información sobre las soluciones de riesgo y cumplimiento de Microsoft Purview y a empezar a implementar rápidamente estas soluciones para satisfacer las necesidades específicas de cumplimiento de su organización.

## <a name="protect-sensitive-data-across-clouds-apps-and-devices"></a>Protección de datos confidenciales en nubes, aplicaciones y dispositivos

La estrategia de protección de la información debe basarse en sus necesidades empresariales, pero cada organización tiene un requisito para proteger algunos o todos sus datos. Use las funcionalidades de [Microsoft Purview Information Protection](/microsoft-365/compliance/information-protection) (anteriormente Microsoft Information Protection) para ayudarle a detectar, clasificar, proteger y controlar la información confidencial dondequiera que viva o viaje.

### <a name="know-your-data"></a>Conocer los datos

Tiene información que reside en todos los servicios de Microsoft 365 y en el entorno local. Identificar qué elementos son confidenciales y obtener visibilidad sobre cómo se usan es fundamental para la práctica de protección de la información. Microsoft Purview incluye:

- [Tipos de información confidencial](/microsoft-365/compliance/sensitive-information-type-learn-about) para identificar elementos confidenciales mediante expresiones regulares integradas o personalizadas, o una función.
- [Clasificadores entrenables](/microsoft-365/compliance/classifier-learn-about) para identificar elementos confidenciales mediante ejemplos de los datos que le interesan en lugar de identificar elementos en el elemento.
- [La clasificación de datos](/microsoft-365/compliance/data-classification-overview) proporciona una identificación gráfica de los elementos de la organización que tienen una etiqueta de confidencialidad, una etiqueta de retención o que se han clasificado y las acciones que los usuarios están llevando a cabo en ellos.

### <a name="protect-your-data"></a>Proteger los datos

Hay muchas funcionalidades que puede usar desde la solución Microsoft Purview Information Protection para ayudar a proteger los datos, dondequiera que se almacenen y a los que se acceda. Sin embargo, las etiquetas de confidencialidad son la funcionalidad fundamental que proporciona acciones de protección e interactúa con otras soluciones y funcionalidades de Purview.

Las etiquetas de confidencialidad proporcionan a los usuarios y administradores visibilidad sobre la confidencialidad de los datos que usan y las propias etiquetas pueden aplicar acciones de protección que incluyen cifrado, restricciones de acceso y marcas visuales. Para obtener más información sobre la gama de escenarios de etiquetado admitidos, consulte la sección [Escenarios comunes para etiquetas de confidencialidad](/microsoft-365/compliance/get-started-with-sensitivity-labels#common-scenarios-for-sensitivity-labels) de la documentación de introducción. Para obtener más información sobre las etiquetas de confidencialidad, consulte [Información sobre las etiquetas de confidencialidad](/microsoft-365/compliance/sensitivity-labels).

### <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

El uso compartido involuntario de elementos confidenciales puede causar daños financieros a su organización y puede dar lugar a una infracción de las leyes y las regulaciones. [Prevención de pérdida de datos de Microsoft Purview](/microsoft-365/compliance/dlp-learn-about-dlp) puede ayudar a proteger su organización contra el uso compartido accidental o accidental de información confidencial dentro y fuera de la organización. En una directiva de prevención de pérdida de datos, haga lo siguiente:

- Defina la información confidencial que desea supervisar, como los datos financieros, de salud, médicos y de privacidad.
- Dónde supervisar, como los servicios de Microsoft 365 o los dispositivos Windows y macOS.
- Condiciones que deben coincidir para que una directiva se aplique a un artículo, como artículos que contengan tarjeta de crédito, licencia de conducir o números de seguro social.
- Las acciones que se deben realizar cuando se encuentra una coincidencia, como la auditoría, bloquean la actividad y bloquean la actividad con invalidación.

### <a name="manage-your-data-lifecycle"></a>Administrar el ciclo de vida de los datos

[Administración del ciclo de vida de Microsoft Purview](/microsoft-365/compliance/manage-data-governance#microsoft-purview-data-lifecycle-management) (anteriormente Microsoft Information Governance) proporciona herramientas y funcionalidades para conservar y eliminar contenido en Exchange, SharePoint, OneDrive, Grupos de Microsoft 365, Teams y Yammer. La retención y eliminación de correos electrónicos, documentos y mensajes suele ser necesaria para cumplir los requisitos normativos. Sin embargo, la eliminación de contenido que ya no tiene valor empresarial también reduce la superficie expuesta a ataques.

Para obtener más información, consulte [Más información sobre la administración del ciclo de vida de los datos](/microsoft-365/compliance/data-lifecycle-management).

### <a name="encrypt-your-data-and-control-your-encryption-keys"></a>Cifrar los datos y controlar las claves de cifrado

[El cifrado](/microsoft-365/compliance/encryption) es una parte importante de la estrategia de protección de archivos y protección de la información. El proceso de cifrado codifica los datos (denominados texto no cifrado) en texto cifrado. A diferencia del texto no cifrado, los usuarios o equipos no pueden usar texto cifrado a menos que y hasta que se descifre el texto cifrado. El descifrado requiere una clave de cifrado que solo tienen los usuarios autorizados. El cifrado ayuda a garantizar que solo los destinatarios autorizados puedan descifrar el contenido.

[El cifrado de doble clave de Microsoft Purview](/microsoft-365/compliance/double-key-encryption) ayuda a proteger los datos más confidenciales que están sujetos a los requisitos de protección más estrictos. [La clave de cliente de Microsoft Purview](/microsoft-365/compliance/customer-key-overview) le ayuda a cumplir las obligaciones normativas o de cumplimiento para controlar las claves raíz. Autoriza explícitamente a los servicios de Microsoft 365 a usar las claves de cifrado para proporcionar servicios en la nube de valor agregado, como eDiscovery, antimalware, antispam, indexación de búsqueda, etc.

## <a name="identify-data-risks-and-manage-regulatory-compliance-requirements"></a>Identificar los riesgos relacionados con los datos y administrar los requisitos de cumplimiento normativo

Los riesgos internos son una de las principales preocupaciones de los profesionales de seguridad y cumplimiento en el área de trabajo moderna. Los estudios del sector han demostrado que los riesgos internos a menudo se asocian a eventos o actividades específicos del usuario. La protección de su organización frente a estos riesgos puede ser difícil de identificar y difícil de mitigar. Los riesgos internos incluyen vulnerabilidades en varias áreas y pueden causar problemas importantes para su organización, desde la pérdida de propiedad intelectual hasta el acoso en el lugar de trabajo, etc.

Microsoft Purview ofrece las siguientes soluciones de cumplimiento para ayudar a su organización a administrar los requisitos de cumplimiento y riesgo de datos:

- [Administración de riesgos internos](#detect-and-act-on-risk-activities-with-insider-risk-management)
- [Cumplimiento de las comunicaciones](#detect-and-act-on-inappropriate-and-sensitive-messages-with-communication-compliance)
- [Barreras de información](#restrict-communication-and-collaboration-between-users-with-information-barriers)
- [Administración de registros](#manage-business-legal-or-regulatory-record-keeping-requirements-with-records-management)
- [Auditoría (Premium) y Auditoría (estándar)](#log-and-search-for-audited-activities-in-sharepoint-and-onedrive-with-audit-premium-or-audit-standard)
- [eDiscovery (Premium) y eDiscovery (estándar)](#identify-and-manage-data-for-legal-cases-with-ediscovery-premium-or-ediscovery-standard)

### <a name="detect-and-act-on-risk-activities-with-insider-risk-management"></a>Detectar y actuar sobre actividades de riesgo con la administración de riesgos internos

[Administración de riesgos internos de Microsoft Purview](/microsoft-365/compliance/insider-risk-management) usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, evaluar y actuar rápidamente sobre la actividad de usuario de riesgo en su organización. Mediante el uso de registros de Microsoft 365 y Microsoft Graph, la administración de riesgos internos le permite definir directivas específicas para identificar indicadores de riesgo. Después de identificar actividades de riesgo, puede tomar medidas para mitigar estos riesgos.

### <a name="detect-and-act-on-inappropriate-and-sensitive-messages-with-communication-compliance"></a>Detectar y actuar sobre mensajes inadecuados y confidenciales con cumplimiento de comunicaciones

La protección de información confidencial y la detección y actuación sobre incidentes de acoso en el lugar de trabajo es una parte importante del cumplimiento de las directivas y estándares internos. [Cumplimiento de comunicaciones de Microsoft Purview](/microsoft-365/compliance/communication-compliance-policies) ayuda a minimizar estos riesgos, ya que le ayuda a detectar, capturar y tomar acciones de corrección rápidas para el correo electrónico y las comunicaciones de Microsoft Teams. Estas incluyen comunicaciones inapropiadas que contienen palabras soeces, amenazas y acoso y comunicaciones que comparten información confidencial dentro y fuera de su organización.

### <a name="restrict-communication-and-collaboration-between-users-with-information-barriers"></a>Restricción de la comunicación y colaboración entre usuarios con barreras de información

[Microsoft Purview Information Barriers (IB)](/microsoft-365/compliance/information-barriers) es una solución de cumplimiento que permite restringir la comunicación bidireccional y la colaboración entre grupos y usuarios en Microsoft Teams, SharePoint Online y OneDrive para la Empresa. A menudo utilizado en sectores altamente regulados, el IB puede ayudar a evitar conflictos de interés y a proteger la información interna entre los usuarios y las áreas organizativas.

### <a name="manage-business-legal-or-regulatory-record-keeping-requirements-with-records-management"></a>Administrar los requisitos de mantenimiento de registros empresariales, legales o normativos con la administración de registros

[Administración de registros de Microsoft Purview](/microsoft-365/compliance/manage-data-governance#microsoft-purview-records-management) ayuda a una organización a administrar sus obligaciones legales, proporciona la capacidad de demostrar el cumplimiento de las regulaciones y aumenta la eficacia con la eliminación regular de los elementos que ya no tienen que conservarse, ya no tienen valor o ya no son necesarios para fines empresariales. Para más información, vea [Más información sobre la administración de registros](/microsoft-365/compliance/records-management).

### <a name="log-and-search-for-audited-activities-in-sharepoint-and-onedrive-with-audit-premium-or-audit-standard"></a>Registro y búsqueda de actividades auditadas en SharePoint y OneDrive con Auditoría (Premium) o Auditoría (estándar)

Las [soluciones de auditoría de Microsoft Purview](/microsoft-365/compliance/auditing-solutions-overview) proporcionan soluciones integradas para ayudar a las organizaciones a responder eficazmente a eventos de seguridad, investigaciones forenses, investigaciones internas y obligaciones de cumplimiento. Miles de operaciones de usuarios y administradores que se realizan en docenas de servicios y soluciones de Microsoft 365 se capturan, graban y retienen en el registro de auditoría unificado de su organización. Los registros de auditoría de estos eventos pueden ser objeto de búsqueda por las operaciones de seguridad, los administradores de TI, los equipos de riesgos de Insider, así como por los investigadores del cumplimiento y la legislación legal de la organización. Esta funcionalidad permite ver las actividades que se realizan en toda la organización de Microsoft 365.

Para obtener más información sobre las soluciones de auditoría, vea [Auditoría (Premium)](/microsoft-365/compliance/advanced-audit) y [Auditoría (estándar).](/microsoft-365/compliance/set-up-basic-audit)

### <a name="identify-and-manage-data-for-legal-cases-with-ediscovery-premium-or-ediscovery-standard"></a>Identificación y administración de datos para casos legales con eDiscovery (Premium) o eDiscovery (estándar)

La detección electrónica, o eDiscovery, es el proceso de identificación, recopilación y auditoría de información electrónica por motivos legales, normativos o empresariales. Puede usar [soluciones de Microsoft Purview eDiscovery](/microsoft-365/compliance/ediscovery) para buscar datos y contenido en equipos de Exchange Online, OneDrive para la Empresa, SharePoint Online, Microsoft Teams, Grupos de Microsoft 365 y Yammer. Puede buscar buzones y sitios en la misma búsqueda de exhibición de documentos electrónicos y, a continuación, exportar los resultados de la búsqueda para su análisis y revisión.

Para obtener más información sobre las soluciones de [eDiscovery, vea eDiscovery (Premium)](/microsoft-365/compliance/overview-ediscovery-20) y [eDiscovery (Estándar).](/microsoft-365/compliance/get-started-core-ediscovery)

## <a name="get-started-with-regulatory-compliance"></a>Introducción al cumplimiento normativo

Las organizaciones deben cumplir con una red compleja y evolutiva de directivas, estándares del sector y regulaciones regionales, y también hacer frente al costo creciente de posibles incumplimientos. De hecho, hay cientos de actualizaciones al día de miles de organismos reguladores, lo que dificulta mantenerse al día con el panorama de cumplimiento que cambia rápidamente. El Administrador de cumplimiento de Microsoft Purview y una colección detallada de ofertas de cumplimiento pueden ayudar a su organización a administrar estos requisitos normativos.

### <a name="get-started-with-compliance-manager"></a>Introducción al Administrador de cumplimiento

[El Administrador de cumplimiento de Microsoft Purview](/microsoft-365/compliance/compliance-manager) es una característica de la portal de cumplimiento Microsoft Purview que le ayuda a administrar los requisitos de cumplimiento de su organización con mayor facilidad y comodidad. El Administrador de cumplimiento puede ayudarle a lo largo del proceso de cumplimiento, desde realizar un inventario de los riesgos de protección de datos hasta administrar las complejidades de la implementación de controles, estar al corriente de las normativas y certificaciones e informar a los auditores.

### <a name="learn-about-microsoft-regulatory-compliance-offerings"></a>Más información sobre las ofertas de cumplimiento normativo Microsoft

Microsoft ofrece un conjunto completo de [ofertas de cumplimiento](/compliance/regulatory/offering-home) para ayudar a su organización a cumplir con los requisitos nacionales, regionales, internacionales y específicos del sector que rigen la recopilación y el uso de datos.

## <a name="deploy-purview-compliance-solutions"></a>Implementar soluciones de cumplimiento Purview

Las soluciones específicas del área reúnen las instrucciones técnicas que necesita para comprender, planear e implementar soluciones de cumplimiento integradas para una colaboración de datos segura y compatible:

- [Protección de datos con Confianza cero](/security/zero-trust/deploy/data)
- [Implementación de una solución de protección de la información](/microsoft-365/compliance/information-protection-solution)
- [Implementación de una solución de gobierno de datos](/microsoft-365/compliance/data-governance-solution)
- [Implementación de protección de la información para las normativas de privacidad de datos](/microsoft-365/solutions/information-protection-deploy)
- [Exploración de ilustraciones de cumplimiento de & de protección de la información](/microsoft-365/solutions/productivity-illustrations)

## <a name="next-steps-for-organizations-new-to-risk-and-compliance-solutions"></a>Pasos siguientes para las organizaciones nuevas en soluciones de riesgo y cumplimiento

- [Más información sobre la versión de prueba de la solución Microsoft Purview](/microsoft-365/compliance/compliance-easy-trials)
- [Tareas rápidas para empezar a trabajar con el cumplimiento en Microsoft Purview](/microsoft-365/compliance/compliance-quick-tasks)
