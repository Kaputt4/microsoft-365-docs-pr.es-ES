---
title: Soluciones de auditoría de Microsoft Purview
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
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
ms.openlocfilehash: c98d1ab6e430d22f5e4c2aad2d881061fcf32c90
ms.sourcegitcommit: 6f36cb8c69090c62a006d461bfc5aa1139cf09a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "67631458"
---
# <a name="auditing-solutions-in-microsoft-purview"></a>Soluciones de auditoría en Microsoft Purview

Las soluciones de auditoría de Microsoft Purview proporcionan una solución integrada para ayudar a las organizaciones a responder eficazmente a eventos de seguridad, investigaciones forenses, investigaciones internas y obligaciones de cumplimiento. Miles de operaciones de usuarios y administradores que se realizan en docenas de servicios y soluciones de Microsoft 365 se capturan, graban y retienen en el registro de auditoría unificado de su organización. Los registros de auditoría de estos eventos pueden ser objeto de búsqueda por las operaciones de seguridad, los administradores de TI, los equipos de riesgos de Insider, así como por los investigadores del cumplimiento y la legislación legal de la organización. Esta funcionalidad permite ver las actividades que se realizan en toda la organización de Microsoft 365.

> [!NOTE]
> La auditoría de Microsoft Purview es el nuevo nombre del registro de auditoría unificado.

## <a name="microsoft-purview-auditing-solutions"></a>Soluciones de auditoría de Microsoft Purview

Microsoft Purview proporciona dos soluciones de auditoría: Auditoría (Estándar) y Auditoría (Premium).

![Funcionalidades clave de Auditoría (Estándar) y Auditoría (Premium).](..\media\AuditingSolutionsComparison.png)

### <a name="audit-standard"></a>Auditoría (estándar)

Auditoría de Microsoft Purview (Estándar) le proporciona la capacidad de registrar y buscar actividades auditadas y potenciar sus investigaciones forenses, de TI, de cumplimiento y legales.

- **Habilitado de forma predeterminada**. Auditoría (Estándar) está activada de forma predeterminada para todas las organizaciones con la suscripción adecuada. Eso significa que los registros de las actividades auditadas se capturarán y podrán ser objeto de búsqueda. La única configuración necesaria es asignar los permisos necesarios para acceder a la herramienta de búsqueda de registros de auditoría (y el cmdlet correspondiente) y asegurarse de que a los usuarios se les asigna la licencia adecuada para las características de Auditoría de Microsoft Purview (Premium).
- **Miles de eventos de auditoría que se pueden buscar**. Puede buscar una amplia gama de actividades auditadas que se producen en la mayoría de los servicios de Microsoft 365 de la organización. Para obtener una lista parcial de las actividades que puede buscar, vea [Actividades auditadas](search-the-audit-log-in-security-and-compliance.md#audited-activities). Para obtener una lista de los servicios y características compatibles con actividades auditadas, vea [Tipos de registros de auditoría](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).
- **Herramienta de búsqueda de Auditoría en el portal de cumplimiento de Microsoft Purview**. Use la herramienta de búsqueda de registros de Auditoría en el portal de cumplimiento para buscar registros de auditoría. Puede buscar actividades específicas, actividades realizadas por usuarios específicos y actividades realizadas en un intervalo de fechas. Aquí tiene una captura de pantalla de la herramienta de búsqueda de auditorías del Centro de cumplimiento.

   ![Herramienta de búsqueda de registros de auditoría en el portal de cumplimiento.](../media/AuditLogSearchToolMCC.png)

- **cmdlet Search-UnifiedAuditLog**. También puede usar el cmdlet **Search-UnifiedAudtLog** en PowerShell de Exchange Online (el cmdlet subyacente de la herramienta de búsqueda) para buscar eventos de auditoría o para usarlo en un script. Para obtener más información, consulte:

  - [Referencia del cmdlet Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog)
  - [Usar un script de PowerShell para buscar en el registro de auditoría](audit-log-search-script.md)

- **Exportar registros de auditoría a un archivo CSV**. Después de ejecutar la herramienta de búsqueda de registros de auditoría del Portal de cumplimiento, puede exportar los registros de auditoría encontrados a un archivo CSV. Esto le permite usar Microsoft Excel para ordenar y filtrar según diferentes propiedades de los registro de auditoría. También puede usar la funcionalidad de transformación de Power Query de Excel para dividir cada propiedad del objeto JSON de AuditData en su propia columna. Esto le permite ver y comparar eficazmente datos similares de diferentes eventos. Para más información, consulte[Exportar, configurar y ver registros de auditoría](export-view-audit-log-records.md).

- **Acceso a registros de auditoría a través de la API de Actividad de administración de Office 365**. Un tercer método para obtener acceso y encontrar registros de auditoría es usar la API de Actividad de administración de Office 365. Esto permite a las organizaciones conservar los datos de auditoría durante períodos superiores a los 90 días predeterminados, y les permite importar sus datos de auditoría a una solución SIEM. Para obtener más información, consulte la [referencia de la API de Actividad de administración de Office 365](/office/office-365-management-api/office-365-management-activity-api-reference).

- **Retención de registros de auditoría de 90 días**. Cuando un usuario o administrador realiza una actividad auditada, se genera un registro de auditoría y se almacena en el registro de auditoría de la organización. En Auditoría (Estándar), los registros se conservan durante 90 días, lo que significa que puede buscar actividades que se hayan producido en los últimos tres meses.

### <a name="audit-premium"></a>Auditoría (Premium)

Auditoría (Premium) se basa en las capacidades de Auditoría (Estándar) al proporcionar directivas de retención de registros de auditoría, una retención más prolongada de registros de auditoría, eventos cruciales de alto valor y un mayor acceso de ancho de banda a la API de actividad de administración de Office 365.

- **Directivas de retención de registros de auditoría**. Puede crear directivas de retención de registros de auditoría personalizadas para conservar los registros de auditoría durante períodos de tiempo de hasta un año (y hasta 10 años para los usuarios con la licencia de complemento necesaria). Puede crear una directiva para conservar los registros de auditoría según el servicio donde se producen las actividades auditadas, según actividades auditadas específicas o en función el usuario que realiza una actividad auditada.

- **Retención prolongada de registros de auditoría**. Los registros de auditoría de Exchange, SharePoint y Azure Active Directory se conservan durante un año de forma predeterminada. Los registros de auditoría del resto de las actividades se conservan durante 90 días de forma predeterminada, pero puede usar directivas de retención de registros de auditoría para configurar períodos de retención más largos.

- **Eventos de Auditoría (Premium) cruciales y de alto valor**. Los registros de auditoría de eventos cruciales pueden ayudar a su organización a llevar a cabo investigaciones forenses y de cumplimiento al proporcionar visibilidad a eventos como cuándo se accedió a los elementos de correo, cuándo se respondieron y reenviaron elementos de correo, o cuándo y qué busca un usuario en Exchange Online y SharePoint Online. Estos eventos cruciales pueden ayudarle a investigar posibles infracciones y a determinar el ámbito del compromiso.

- **Mayor ancho de banda para la API de Actividad de administración de Office 365** Auditoría (Premium) proporciona a las organizaciones más ancho de banda para acceder a los registros de auditoría a través de la API de actividad de administración de Office 365. Aunque a todas las organizaciones, que tienen Auditoría (Estándar) o Auditoría (Premium), se les asigna inicialmente una línea base de 2 000 solicitudes por minuto, este límite aumentará dinámicamente según el número de puestos de una organización y su suscripción de licencia. Esto hace que las organizaciones con Auditoría (Premium) obtengan aproximadamente el doble de ancho de banda que las organizaciones con Auditoría (Estándar).

Para obtener información más detallada sobre las características de Auditoría (Premium), vea [Auditoría (Premium) en Microsoft 365](advanced-audit.md).

## <a name="comparison-of-key-capabilities"></a>Comparación de funcionalidades clave

En la tabla siguiente se comparan las funcionalidades clave disponibles en Auditoría (Estándar) y Auditoría (Premium). Toda la funcionalidad de Auditoría (estándar) se incluye en Auditoría (Premium).

|Funcionalidad|Auditoría (estándar)|Auditoría (Premium)|
|:------|:-------------|:-------------|
|Habilitado de forma predeterminada|![Se admite.](../media/check-mark.png)|![Se admite.](../media/check-mark.png)|
|Miles de eventos de auditoría que se pueden buscar|![Se admite.](../media/check-mark.png)|![Se admite.](../media/check-mark.png)|
|Herramienta de búsqueda de Auditoría en el portal de cumplimiento|![Se admite.](../media/check-mark.png)|![Se admite.](../media/check-mark.png)|
|Cmdlet Search-UnifiedAuditLog|![Se admite.](../media/check-mark.png)|![Se admite.](../media/check-mark.png)|
|Exportar registros de auditoría a un archivo CSV|![Se admite.](../media/check-mark.png)|![Se admite.](../media/check-mark.png)|
|Acceso a registros de auditoría a través de la API de Actividad de administración de Office 365 <sup>1</sup>|![Se admite.](../media/check-mark.png)|![Se admite.](../media/check-mark.png)</sup>|
|Retención de 90 días del registro de auditoría|![Se admite.](../media/check-mark.png)|![Se admite.](../media/check-mark.png)|
|Retención de 1 año de registros de auditoría||![Se admite.](../media/check-mark.png)|
|Retención de 10 años de registros de auditoría <sup>2</sup>||![Compatible](../media/check-mark.png)|
|Directivas de retención de los registros de auditoría||![Compatible](../media/check-mark.png)|
|Eventos cruciales de gran valor||![Compatible](../media/check-mark.png)|

> [!NOTE]
> <sup>1</sup> Auditoría (Premium) incluye un mayor acceso de ancho de banda a la API de actividad de administración de Office 365, lo que proporciona un acceso más rápido a los datos de auditoría.<br/><sup>2</sup> Además de las licencias necesarias para Auditoría (Premium) (descritas en la sección siguiente), a un usuario se le debe asignar una licencia de complemento de retención de registros de auditoría de 10 años para conservar sus registros de auditoría durante 10 años.

## <a name="licensing-requirements"></a>Requisitos de licencias

En las secciones siguientes se identifican los requisitos de licencia para Auditoría (Estándar) y Auditoría (Premium). La funcionalidad de Auditoría (Estándar) se incluye con Auditoría (Premium).

### <a name="audit-standard"></a>Auditoría (estándar)

- Suscripción a Microsoft Empresa Básico
- Suscripción a Microsoft Business Standard
- Suscripción a Aplicaciones de Microsoft 365 para negocios
- Suscripción a Microsoft 365 Enterprise E3
- Microsoft 365 Empresa Premium
- Suscripción a Microsoft 365 Educación A3
- Suscripción a Microsoft 365 Administración Pública G3
- Suscripción a Microsoft 365 Administración Pública G1
- Suscripción a Microsoft 365 Frontline F1 o F3, o al complemento F5 Security
- Suscripción a Office 365 Enterprise E3
- Suscripción a Office 365 Enterprise E1
- Suscripción a Office 365 Educación A1
- Suscripción a Office 365 Educación A3

### <a name="audit-premium"></a>Auditoría (Premium)

- Suscripción a Microsoft 365 Enterprise E5
- Suscripción a Microsoft 365 Enterprise E3 y complemento de Cumplimiento de Microsoft 365 E5
- Suscripción a Microsoft 365 Enterprise E3 y complemento de eDiscovery y auditoría de Microsoft 365 E5
- Suscripción a Microsoft 365 Educación A5
- Suscripción a Microsoft 365 Educación A3 y complemento de Cumplimiento de Microsoft 365 A5
- Suscripción a Microsoft 365 Educación A3 y complemento de eDiscovery y auditoría de Microsoft 365 A5
- Microsoft 365 Administración Pública G5
- Suscripción a Microsoft 365 Administración General G3 y complemento de Cumplimiento de Microsoft 365 G5
- Suscripción a Microsoft 365 Administración Pública G3 y complemento de eDiscovery y auditoría de Microsoft 365 G5
- Microsoft 365 Frontline F5 Compliance o el complemento F5 Security & Compliance
- Suscripción a Office 365 Enterprise E5
- Suscripción a Office 365 Educación A5

## <a name="set-up-microsoft-purview-auditing-solutions"></a>Configuración de soluciones de Auditoría de Microsoft Purview

Para empezar a usar las soluciones de Auditoría de Microsoft Purview, consulte las siguientes instrucciones de configuración.

### <a name="set-up-audit-standard"></a>Configurar Auditoría (estándar)

El primer paso es configurar Auditoría (Estándar) y, a continuación, iniciar la ejecución de búsquedas de registros de auditoría.

![Flujo de trabajo para configurar Auditoría (Estándar).](../media/BasicAuditingWorkflow.png)

1. Compruebe que su organización tiene una suscripción que admita Auditoría (Estándar) y, si procede, una suscripción que admita Auditoría (Premium).

2. Asigne permisos en Exchange Online a las personas de su organización que usarán la herramienta de búsqueda de registros de auditoría en el portal de cumplimiento o usarán el cmdlet **Search-UnifiedAuditLog**. Concretamente, deberá asignar a los usuarios el rol de registros de auditoría de solo lectura o registros de auditoría en Exchange Online.

3. Búsquedas en el registro de auditoría. Después de completar los pasos 1 y 2, los usuarios de la organización pueden usar la herramienta de búsqueda en el registro de auditoría (o el cmdlet correspondiente) para buscar actividades auditadas.

Para obtener instrucciones más detalladas, vea [Configurar Auditoría (Estándar)](set-up-basic-audit.md).

### <a name="set-up-audit-premium"></a>Configurar Auditoría (Premium)

Si su organización tiene una suscripción que admite Auditoría (Premium), realice los pasos siguientes para configurar y usar las funcionalidades adicionales de Auditoría (Premium).

![Flujo de trabajo para configurar Auditoría (Premium).](../media/AdvancedAuditWorkflow.png)

1. Configurar Auditoría (Premium) para los usuarios. Este paso consta de las siguientes tareas:

   - Comprobando que a los usuarios se les asigna la licencia o la licencia de complemento adecuada para Auditoría (Premium).
  
   - La activación del plan de servicio o aplicación de Auditoría (Premium) debe ser para esos usuarios.
  
   - Habilitar la auditoría de eventos cruciales y, después, activar el plan de servicio/aplicación Auditoria (Premium) para esos usuarios.

2. Habilite los eventos de Auditoría (Premium) para que se registren cuando los usuarios realicen búsquedas en Exchange Online y SharePoint Online.

3. Configurar las directivas de retención de registros de auditoría. Además de la directiva predeterminada que conserva los registros de auditoría de Exchange, SharePoint y Azure AD durante un año, puede crear otras directivas de retención de registros de auditoría para cumplir los requisitos de los equipos de operaciones de seguridad, TI y cumplimiento de su organización.

4. Busque eventos de Auditoría (Premium) cruciales y otras actividades al realizar investigaciones forenses. Después de completar los pasos 1 y 2, puede buscar en el registro de auditoría eventos de Auditoría (Premium) y otras actividades durante investigaciones forenses de cuentas en peligro y otros tipos de investigaciones de seguridad o cumplimiento.

Para obtener instrucciones más detalladas, vea [Configurar Auditoría (Premium)](set-up-advanced-audit.md).

<!--
## Encrypt audit records using Customer Key

You can enable Customer Key encryption for audit records. Auditing builds on the [Service encryption with Customer Key](customer-key-overview.md) to encrypt sensitive information in your organization's auditing data. Implementing Customer Key provides extra protection by preventing unauthorized systems or Microsoft data center personnel from viewing your auditing data in the auditing pipeline and at rest. Using Customer Key to encrypt your auditing data also helps you meet regulatory or compliance obligations because your organization provides and controls the encryption keys.

To implement Customer Key for auditing, you have to create a multi-workload Data Encryption Policy (DEP), which defines the encryption hierarchy. For detailed step-by-step instructions, see [Set up Customer Key](customer-key-set-up.md).

> [!NOTE]
> Not all audit records in your organization are encrypted. The Microsoft Purview service that generates specific audit records for activity in that service defines whether the audit record is encrypted or not.
-->

## <a name="training"></a>Formación

Entrenar al equipo de operaciones de seguridad, a los administradores de TI y al equipo de investigadores de cumplimiento en los aspectos básicos de Auditoría (estándar) y Auditoría (Premium) puede ayudar a su organización a empezar a usar la auditoría más rápidamente para ayudar con sus investigaciones. Microsoft Purview proporciona el siguiente recurso para ayudar a estos usuarios de su organización a iniciarse en las auditorías: [describir las capacidades de eDiscovery y auditoría de Microsoft Purview](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365).
