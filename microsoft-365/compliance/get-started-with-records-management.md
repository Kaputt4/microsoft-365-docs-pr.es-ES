---
title: Introducción a la administración de registros en Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: Pasos prescriptivos para administradores, requisitos de licencia y escenarios comunes que gestionan contenido de alto valor en Microsoft 365 para las obligaciones legales, empresariales o normativas.
ms.openlocfilehash: 4a0de19b7630ad89dadb071b80065ff44fde72bb
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2022
ms.locfileid: "67106829"
---
# <a name="get-started-with-records-management"></a>Introducción a la administración de registros

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

¿Está preparado para empezar a administrar el contenido de alto valor de su organización para las obligaciones legales, empresariales o reglamentarias con una solución de administración de registros en Microsoft 365? Use las siguientes instrucciones para emprezar:

1. **Comprenda cómo funciona la retención y eliminación** en Microsoft 365 e identifique si necesita usar directivas de retención para complementar las etiquetas de retención que administran documentos y correos electrónicos a nivel elemento: [Más información sobre las directivas y etiquetas de retención](retention.md)
    
    Si es necesario, [cree directivas de retención](create-retention-policies.md) para el gobierno de datos de línea base en las cargas de trabajo de Microsoft 365.
    
2. **Comprenda la solución de administración de registros** y cómo se pueden usar las etiquetas de retención para permitir o bloquear acciones cuando se declaran registros de documentos y correos electrónicos: [Más información sobre la administración de registros](records-management.md)

3. **Cree el plan de archivos para las acciones y la configuración de retención y eliminación, y cuando los elementos deben marcarse como registros** mediante la importación de un plan existente si tiene uno, o cree nuevas etiquetas de retención: [Usar el plan de archivos para crear y administrar etiquetas de retención](file-plan-manager.md)

4. **Publicar y aplicar las etiquetas de retención**. Las etiquetas de retención son bloques de creación reutilizables que se pueden usar en varias directivas y se pueden incorporar a flujos de trabajo de usuario:

    - [Publicar etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
    - [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)

> [!TIP]
> Si va a migrar registros a Microsoft 365 y necesita validar que no se han modificado, consulte [Validar registros migrados](records-management.md#validating-migrated-records).

## <a name="subscription-and-licensing-requirements"></a>Requisitos de suscripción y licencias

Distintas suscripciones admiten diferentes administraciones de registros y los requisitos de licencias para los usuarios dependen de las características que use.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de Microsoft Purview, consulte la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Para conocer la administración de registros, consulte la sección [Administración del ciclo de vida de los datos de Microsoft Purview y Administración de registros de Microsoft Purview](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management--microsoft-purview-records-management) para conocer los requisitos de licencia de nivel de característica.

## <a name="permissions"></a>Permisos

Los miembros de su equipo de cumplimiento responsables de la administración de registros necesitan permisos en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Portal de cumplimiento de Microsoft Purview</a>. De forma predeterminada, el administrador del espacio empresarial (administrador global) tiene acceso a esta ubicación y puede dar acceso a los oficiales de cumplimiento y a otras personas sin otorgarles todos los permisos de un administrador de espacio empresarial. Para otorgar permisos para esta administración limitada, recomendamos que agregue usuarios al grupo de funciones de administrador de **Administración de registros**, que otorga permisos para todas las funciones relacionadas con la administración de registros, incluida la [revisión y verificación de la disposición](disposition.md).

En el caso de los roles de solo lectura, puede crear un nuevo grupo de roles y agregar el rol de **Administración de registros de solo vista** a este grupo.

Para obtener instrucciones sobre cómo agregar usuarios a los roles predeterminados o crear sus propios grupos de roles, consulte [Permisos en el Portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md).

Estos permisos son necesarios solo para crear, configurar y aplicar etiquetas de retención para declarar registros y administrar la eliminación. La persona que configura estas etiquetas no requiere acceso al contenido.

## <a name="common-scenarios"></a>Escenarios comunes

Ayúdese de la siguiente tabla para asignar los requisitos empresariales a los escenarios admitidos por la administración de registros.

> [!TIP]
> ¿Necesita cumplir con una normativa específica del sector? Consulte [Requisitos normativos para la gestión del ciclo de vida de los datos y la administración de registros](retention-regulatory-requirements.md) para obtener instrucciones específicas de la normativa.

|Quiero...|Documentación|
|----------------|---------------|
|Declarar un registro |[Use etiquetas de retención para declarar registros](declare-records.md)|
|Actualizar un registro |[Use el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive](record-versioning.md)|
|Permitir que los administradores y usuarios apliquen de forma manual acciones de retención y eliminación de documentos y mensajes de correo electrónico: <br />- SharePoint <br />- OneDrive <br />- Outlook y Outlook en la Web|[Publicar etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permita que los administradores del sitio establezcan acciones predeterminadas de retención y eliminación para todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint|[Publicar etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permita a los usuarios aplicar automáticamente acciones de retención y eliminación a los correos electrónicos mediante el uso de las reglas de Outlook|[Publicar etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permitir a los administradores aplicar acciones de retención y eliminación en un documento con información sobre el modelo, para que sean aplicado automáticamente a los documentos identificados en una biblioteca de SharePoint|[Publicar etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Aplicar acciones de retención y eliminación automáticamente a documentos y mensajes de correo electrónico |[Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)|
|Inicie el período de retención cuando tenga lugar un evento, por ejemplo, cuando:  <br />- Algún empleado abandone la organización <br />- Algún contrato expire <br />- Finalice la duración de un producto| [Inicie la retención cuando se produzca un evento](event-driven-retention.md)|
|Restrinja los cambios de las directivas para ayudar a cumplir los requisitos reglamentarios o medidas de seguridad frente a administradores no autorizados| [Usar el Bloqueo de conservación para restringir los cambios en las directivas de retención y en las directivas de las etiquetas de retención](retention-preservation-lock.md)
|Administrar el ciclo de vida de los distintos tipos de documentos en SharePoint| [Usar las etiquetas de retención para administrar el ciclo de vida de los documentos almacenados en SharePoint](auto-apply-retention-labels-scenario.md)|
|Aplicar una etiqueta de retención a un archivo cuando reciba una alerta que indica que el contenido que contiene datos personales se está almacenando o permanece intacto durante demasiado tiempo| [Investigación y corrección de alertas en la administración de riesgos de privacidad](/privacy/priva/risk-management-alerts)|
|Antes de eliminar contenido al final de su período de retención, asegúrese de que alguien revise el contenido y dé su aprobación|[Revisiones para eliminación](disposition.md#disposition-reviews) |
|Compruebe si el contenido se elimina de forma permanente al final de su período de retención|[Eliminación de registros](disposition.md#disposition-of-records) |
| Supervise cómo y cuándo se aplican las opciones de conservar y eliminar la configuración de los elementos | [Supervisar las etiquetas de retención](retention.md#monitoring-retention-labels) |
| Crear y administrar mediante programación etiquetas de retención, retención basada en eventos y automatizar tareas repetitivas para la administración de registros | [API de Microsoft Graph para la administración de registros (versión preliminar)](compliance-extensibility.md#microsoft-graph-api-for-records-management-preview) |

## <a name="end-user-documentation"></a>Documentación para el usuario final

Si usa directivas de retención para el gobierno de datos de línea base, normalmente funcionan discretamente en segundo plano sin interacción del usuario. Como resultado, necesitan poca documentación para los usuarios. Las directivas de retención de Teams informan a los usuarios cuando se han eliminado sus mensajes con un vínculo a los mensajes de [Teams sobre las directivas de retención](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

En comparación, las etiquetas de retención tienen una presencia de interfaz de usuario en las aplicaciones Microsoft 365, por lo que asegúrese de que proporciona instrucciones a los usuarios finales y al servicio de asistencia antes de implementar estas etiquetas en la red de producción. Para ayudar a los usuarios a aplicar etiquetas de retención en SharePoint y OneDrive, e información sobre el desbloqueo de registros para su edición, consulte [Aplicar etiquetas de retención a archivos en SharePoint o OneDrive](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df).

Sin embargo, la documentación más eficaz para los usuarios finales serán la guía y las instrucciones personalizadas que proporcione para los nombres de etiquetas de retención y las configuraciones que elija. Consulte la siguiente página y descargas que puede usar para formar a los usuarios: [Aprendizaje para el usuario final sobre las etiquetas de retención](https://microsoft.github.io/ComplianceCxE/enduser/retention/).