---
title: Soluciones de auditoría de Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- m365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo auditar las actividades de los usuarios y administradores de su organización de Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d4a753a640b98125bc6ad02bd6043f28336e29b7
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256764"
---
# <a name="auditing-solutions-in-microsoft-365"></a>Soluciones de auditoría en Microsoft 365

Las soluciones de auditoría de Microsoft 365 proporcionan una solución integrada que permite a las organizaciones responder de forma eficaz a eventos de seguridad, investigaciones forenses, investigaciones internas y obligaciones de cumplimiento. Miles de operaciones de usuarios y administradores que se realizan en docenas de servicios y soluciones de Microsoft 365 se capturan, graban y retienen en el registro de auditoría unificado de su organización. Los registros de auditoría de estos eventos pueden ser objeto de búsqueda por las operaciones de seguridad, los administradores de TI, los equipos de riesgos de Insider, así como por los investigadores del cumplimiento y la legislación legal de la organización. Esta funcionalidad permite ver las actividades que se realizan en toda la organización de Microsoft 365.

## <a name="microsoft-365-auditing-solutions"></a>Soluciones de auditoría de Microsoft 365

Microsoft 365 ofrece dos soluciones de auditoría: auditoría básica y auditoría avanzada.

![Funcionalidades clave de auditoría básica y auditoría avanzada](..\media\AuditingSolutionsComparison.png)

### <a name="basic-audit"></a>Auditoría básica

La auditoría básica le proporciona la capacidad de registrar y buscar actividades auditadas y reforzar su análisis forense, TI, cumplimiento e investigaciones legales.

- **Habilitado de forma predeterminada**. La auditoría básica está activada de forma predeterminada para todas las organizaciones con la suscripción adecuada. Eso significa que los registros de las actividades auditadas se capturarán y podrán ser objeto de búsqueda. La única configuración necesaria es asignar los permisos necesarios para tener acceso a la herramienta de búsqueda de registros de auditoría (y el cmdlet correspondiente) y asegurarse de que a los usuarios se les ha asignado la licencia adecuada para las características de auditoría avanzada.
- **Miles de eventos de auditoría que se pueden buscar**. Puede buscar una amplia gama de actividades auditadas que se producen en la mayoría de los servicios de Microsoft 365 de la organización. Para obtener una lista parcial de las actividades que puede buscar, vea [Actividades auditadas](search-the-audit-log-in-security-and-compliance.md#audited-activities). Para obtener una lista de los servicios y características compatibles con actividades auditadas, vea [Tipos de registros de auditoría](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).
- **Herramienta de búsqueda de auditorías del Centro de cumplimiento de Microsoft 365**. Use la herramienta de búsqueda de registros de auditoría del Centro de cumplimiento de Microsoft 365 para buscar registros de auditoría. Puede buscar actividades específicas, actividades realizadas por usuarios específicos y actividades realizadas en un intervalo de fechas. Aquí tiene una captura de pantalla de la herramienta de búsqueda de auditorías del Centro de cumplimiento.

   ![Herramienta de búsqueda de registros de auditoría del Centro de cumplimiento de Microsoft 365](../media/AuditLogSearchToolMCC.png)

- **cmdlet Search-UnifiedAuditLog**. También puede usar el cmdlet **Search-UnifiedAudtLog** en PowerShell de Exchange Online (el cmdlet subyacente de la herramienta de búsqueda) para buscar eventos de auditoría o para usarlo en un script. Para más información vea:

  - [Referencia del cmdlet Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)
  - [Usar un script de PowerShell para buscar en el registro de auditoría](audit-log-search-script.md)

- **Exportar registros de auditoría a un archivo CSV**. Después de ejecutar la herramienta de búsqueda de registros de auditoría del Centro de cumplimiento, puede exportar los registros de auditoría encontrados a un archivo CSV. Esto le permite usar Microsoft Excel para ordenar y filtrar según diferentes propiedades de los registro de auditoría. También puede usar la funcionalidad de transformación de Power Query de Excel para dividir cada propiedad del objeto JSON de AuditData en su propia columna. Esto le permite ver y comparar eficazmente datos similares de diferentes eventos. Para más información, consulte[Exportar, configurar y ver registros de auditoría](export-view-audit-log-records.md).

- **Acceso a registros de auditoría a través de la API de Actividad de administración de Office 365**. Un tercer método para obtener acceso y encontrar registros de auditoría es usar la API de Actividad de administración de Office 365. Esto permite a las organizaciones conservar los datos de auditoría durante períodos superiores a los 90 días predeterminados, y les permite importar sus datos de auditoría a una solución SIEM. Para obtener más información, consulte la [referencia de la API de Actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).

- **Retención de registros de auditoría de 90 días**. Cuando un usuario o administrador realiza una actividad auditada, se genera un registro de auditoría y se almacena en el registro de auditoría de la organización. En la auditoría básica los registros se conservan durante 90 días, lo que significa que puede buscar actividades que se produjeron en los últimos tres meses.

### <a name="advanced-audit"></a>Auditoría avanzada

La auditoría avanzada se desarrolla a partir de las funcionalidades de la auditoría básica proporcionando directivas de retención de registros de auditoría, una retención más larga de los registros de auditoría, eventos cruciales de alto valor y un acceso con mayor ancho de banda a la API de Actividad de administración de Office 365.

- **Directivas de retención de registros de auditoría**. Puede crear directivas de retención de registros de auditoría personalizadas para conservar los registros de auditoría durante períodos de tiempo de hasta un año (y hasta 10 años para los usuarios con la licencia de complemento necesaria). Puede crear una directiva para conservar los registros de auditoría según el servicio donde se producen las actividades auditadas, según actividades auditadas específicas o en función el usuario que realiza una actividad auditada.

- **Retención prolongada de registros de auditoría**. Los registros de auditoría de Exchange, SharePoint y Azure Active Directory se conservan durante un año de forma predeterminada. Los registros de auditoría del resto de las actividades se conservan durante 90 días de forma predeterminada, pero puede usar directivas de retención de registros de auditoría para configurar períodos de retención más largos.

- **Eventos cruciales de gran valor**. Los registros de auditoría de eventos cruciales pueden ayudar a su organización a llevar a cabo investigaciones forenses y de cumplimiento proporcionando visibilidad de eventos como, por ejemplo, cuándo se accede a los elementos de correo o cuándo se responde a, y se reenvían los elementos de correo, y cuándo y qué ha buscado un usuario en Exchange Online y SharePoint Online. Estos eventos cruciales pueden ayudarle a investigar posibles infracciones y a determinar el ámbito del compromiso.

- **Mayor ancho de banda para la API de Actividad de administración de Office 365** La auditoría avanzada proporciona a las organizaciones más ancho de banda para tener acceso a los registros de auditoría a través de la API de Actividad de administración de Office 365. Aunque inicialmente todas las organizaciones (que tienen auditoría básica o auditoría avanzada) asignan una línea base de 2 000 solicitudes por minuto, este límite aumentará dinámicamente según el recuento de puestos de una organización y su suscripción a las licencias. El resultado es que las organizaciones con auditoría avanzada pueden obtener aproximadamente el doble de ancho de banda que las organizaciones con auditoría básica.

Para obtener más información sobre las características de la auditoría avanzada vea [auditoría avanzada en Microsoft 365](advanced-audit.md).

## <a name="comparison-of-key-capabilities"></a>Comparación de funcionalidades clave

En la tabla siguiente se comparan las funcionalidades clave disponibles en auditoría básica y en auditoría avanzada. Todas las funciones de auditoría básica se incluyen en la auditoría avanzada.

|Funcionalidad|Auditoría básica|Auditoría avanzada|
|:------|:-------------|:-------------|
|Habilitado de forma predeterminada|![Compatible](../media/check-mark.png)|![Compatible](../media/check-mark.png)|
|Miles de eventos de auditoría que se pueden buscar|![Compatible](../media/check-mark.png)|![Compatible](../media/check-mark.png)|
|Herramienta de búsqueda de auditorías del Centro de cumplimiento de Microsoft 365|![Compatible](../media/check-mark.png)|![Compatible](../media/check-mark.png)|
|cmdlet Search-UnifiedAuditLog|![Compatible](../media/check-mark.png)|![Compatible](../media/check-mark.png)|
|Exportar registros de auditoría a un archivo CSV|![Compatible](../media/check-mark.png)|![Compatible](../media/check-mark.png)|
|Acceso a registros de auditoría a través de la API de Actividad de administración de Office 365 <sup>1</sup>|![Compatible](../media/check-mark.png)|![Compatible](../media/check-mark.png)</sup>|
|Retención de 90 días del registro de auditoría|![Compatible](../media/check-mark.png)|![Compatible](../media/check-mark.png)|
|Retención de 1 año de registros de auditoría||![Compatible](../media/check-mark.png)|
|Retención de 10 años de registros de auditoría <sup>2</sup>||![Compatible](../media/check-mark.png)|
|Directivas de retención de los registros de auditoría||![Compatible](../media/check-mark.png)|
|Eventos cruciales de gran valor||![Compatible](../media/check-mark.png)|
||||
> [!NOTE]
> <sup>1</sup> La auditoría avanzada incluye un acceso con mayor ancho de banda a la API de Actividad de administración de Office 365, lo que proporciona un acceso más rápido a los datos de auditoría.<br/><sup>2</sup> Además de las licencias necesarias para auditoría avanzada (que se describen en la sección siguiente), a un usuario se le debe asignar una licencia de complemento de retención de registro de auditoría de 10 años para conservar sus registros de auditoría durante 10 años.

## <a name="licensing-requirements"></a>Requisitos de licencias

En las secciones siguientes se identifican los requisitos de licencia para auditoría básica y auditoría avanzada. La auditoría avanzada incluye las funcionalidades de la auditoría básica.

### <a name="basic-audit"></a>Auditoría básica

- Suscripción a Microsoft 365 Enterprise E3
- Microsoft 365 Empresa Premium
- Suscripción a Microsoft 365 Educación A3
- Suscripción a Microsoft 365 Administración Pública G3
- Suscripción a Microsoft 365 Administración Pública G1
- Suscripción a Office 365 Enterprise E3
- Suscripción a Office 365 Enterprise E1
- Suscripción a Office 365 Educación A1
- Suscripción a Office 365 Educación A3

### <a name="advanced-audit"></a>Auditoría avanzada

- Suscripción a Microsoft 365 Enterprise E5
- Suscripción a Microsoft 365 Enterprise E3 y complemento de Cumplimiento de Microsoft 365 E5
- Suscripción a Microsoft 365 Enterprise E3 y complemento de eDiscovery y auditoría de Microsoft 365 E5
- Suscripción a Microsoft 365 Educación A5
- Suscripción a Microsoft 365 Educación A3 y complemento de Cumplimiento de Microsoft 365 A5
- Suscripción a Microsoft 365 Educación A3 y complemento de eDiscovery y auditoría de Microsoft 365 A5
- Microsoft 365 Administración Pública G5
- Suscripción a Microsoft 365 Administración General G5 y complemento de Cumplimiento de Microsoft 365 G5
- Suscripción a Microsoft 365 Administración Pública G5 y complemento de eDiscovery y auditoría de Microsoft 365 G5
- Suscripción a Office 365 Enterprise E5
- Suscripción a Office 365 Educación A5
- Suscripción a Office 365 Enterprise E3 y complemento de Cumplimiento avanzado de Office 365 (ya no está disponible para las suscripciones nuevas)

## <a name="set-up-microsoft-365-auditing-solutions"></a>Configurar soluciones de auditoría en Microsoft 365

Para empezar a usar las soluciones de auditoría de Microsoft 365 vea las siguientes instrucciones de configuración.

### <a name="set-up-basic-audit"></a>Configurar la auditoría básica

El primer paso es configurar la auditoría básica y, después, empezar a ejecutar las búsquedas de registros de auditoría.

![Flujo de trabajo para configurar la auditoría básica](../media/BasicAuditingWorkflow.png)

1. Compruebe que su organización tiene una suscripción compatible con auditoría básica y, si procede, una suscripción que admita auditoría avanzada.

2. Asigne permisos en Exchange Online a las personas de su organización que usarán la herramienta de búsqueda de registros de auditoría del Centro de cumplimiento de Microsoft 365 o el cmdlet **Search-UnifiedAsignlog**. Concretamente, deberá asignar a los usuarios el rol de registros de auditoría de solo lectura o registros de auditoría en Exchange Online.

3. Búsquedas en el registro de auditoría. Después de completar los pasos 1 y 2, los usuarios de la organización pueden usar la herramienta de búsqueda en el registro de auditoría (o el cmdlet correspondiente) para buscar actividades auditadas.

Para obtener instrucciones más detalladas, consulte [Configurar la auditoría básica](set-up-basic-audit.md).

### <a name="set-up-advanced-audit"></a>Configurar la auditoría avanzada

Si su organización tiene una suscripción compatible con la auditoría avanzada, realice los pasos siguientes para configurar y usar las funcionalidades adicionales de auditoría avanzada.

![Flujo de trabajo para configurar la auditoría avanzada](../media/AdvancedAuditWorkflow.png)

1. Configurar la auditoría avanzada para usuarios Este paso consta de las siguientes tareas:

   - Comprobar que los usuarios tienen asignada la licencia o la licencia del complemento adecuada para la auditoría avanzada.
  
   - Activar el plan de aplicación/servicio de auditoría avanzada para esos usuarios.
  
   - Habilitar la auditoría de eventos cruciales y, después, activar el plan de servicio/aplicación de auditoría avanzada para esos usuarios.

2. Habilitar los eventos cruciales que se registrarán cuando los usuarios realicen búsquedas en Exchange Online y SharePoint Online.

3. Configurar las directivas de retención de registros de auditoría. Además de la directiva predeterminada que conserva los registros de auditoría de Exchange, SharePoint y Azure AD durante un año, puede crear otras directivas de retención de registros de auditoría para cumplir los requisitos de los equipos de operaciones de seguridad, TI y cumplimiento de su organización.

4. Busque eventos cruciales y otras actividades al llevar a cabo investigaciones forenses. Después de completar los pasos 1 y 2 puede buscar en el registro de auditoría eventos cruciales y otras actividades durante investigaciones exhaustivas de cuentas comprometidas y otros tipos de investigaciones de seguridad o cumplimiento.

Para obtener instrucciones más detalladas, consulte [Configurar la auditoría avanzada](set-up-advanced-audit.md).

## <a name="training"></a>Formación

La formación de su equipo de operaciones de seguridad, de los administradores de TI y del equipo de investigadores de cumplimiento en los fundamentos de la Auditoría básica y la Auditoría avanzada puede ayudar a su organización a empezar a utilizar más rápidamente la auditoría para ayudar en sus investigaciones. Microsoft 365 proporciona el siguiente recurso para ayudar a estos usuarios de su organización a iniciarse en la auditoría: [describir las capacidades de eDiscovery y auditoría de Microsoft 365](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365).
