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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: ¿Necesita una solución de administración de registros para Microsoft 365 que administre contenido de alto valor para obligaciones legales, empresariales o reglamentarias, pero no sabe por dónde comenzar? Lea algunas instrucciones prácticas para empezar.
ms.openlocfilehash: 0382c1419654e4c1d2c809b3a9c32252fd50f554
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244349"
---
# <a name="get-started-with-records-management"></a>Introducción a la administración de registros

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

¿Está preparado para empezar a administrar el contenido de alto valor de su organización para las obligaciones legales, empresariales o reglamentarias con una solución de administración de registros en Microsoft 365? Use las siguientes instrucciones para emprezar:

1. **Entienda la solución de administración de registros** y qué acciones se permiten o bloquean cuando se declaran documentos y mensajes de correo electrónico: [Obtenga más información sobre la administración de registros](records-management.md). 

2. **Entienda qué son las etiquetas de retención y cómo funciona la retención** en SharePoint y Exchange. Las etiquetas de retención se usan para declarar registros: [infórmese sobre las directivas de retención y las etiquetas de retención](retention.md).

3. **Cree el plan de archivos para la configuración y las acciones de retención**. Para ello, [importe un plan existente](file-plan-manager.md#import-retention-labels-into-your-file-plan ) si lo tiene, o cree [nuevas etiquetas de retención que declaren registros](declare-records.md).

4. **Publique y aplique las etiquetas de retención**. Las etiquetas de retención son bloques de creación reutilizables que se pueden emplear en diferentes directivas y se pueden incorporar a los flujos de trabajo del usuario: 
    
    - [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
    - [Aplicar una etiqueta de retención a contenido automáticamente](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-records-management"></a>Requisitos de suscripción y licencias para la administración de registros

Distintas suscripciones admiten diferentes administraciones de registros y los requisitos de licencias para los usuarios dependen de las características que use.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de cumplimiento de Microsoft 365, consulte la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Para la administración de registros, vea la sección de [Administración de registros](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) y las descargas relacionadas en PDF o Excel para obtener más información sobre los requisitos de licencias de nivel de características.

## <a name="permissions-required-for-records-management"></a>Permisos necesarios para la administración de registros

Los miembros de su equipo de cumplimiento responsables de la administración de registros necesitan permisos en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/). De forma predeterminada, el administrador del espacio empresarial (administrador global) tiene acceso a esta ubicación y puede dar acceso a los oficiales de cumplimiento y a otras personas sin otorgarles todos los permisos de un administrador de espacio empresarial. Para otorgar permisos para esta administración limitada, recomendamos que agregue usuarios al grupo de funciones de administrador de **Administración de registros**, que otorga permisos para todas las funciones relacionadas con la administración de registros, incluida la [revisión y verificación de la disposición](disposition.md). 

En el caso de los roles de solo lectura, puede crear un nuevo grupo de roles y agregar el rol de **Administración de registros de solo vista** a este grupo. 

Para más información sobre estos roles y grupos de roles, vea [Permisos en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center).

Para obtener instrucciones sobre cómo agregar usuarios a grupos de roles y asignar roles, vea [Proporcionar acceso a los usuarios al Centro de seguridad y cumplimiento](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

Estos permisos son necesarios solo para crear, configurar y aplicar etiquetas de retención para declarar registros y administrar la eliminación. La persona que configura estas etiquetas no requiere acceso al contenido.

## <a name="common-scenarios-for-records-management"></a>Escenarios comunes para la administración de registros

Ayúdese de la siguiente tabla para asignar los requisitos empresariales a los escenarios admitidos por la administración de registros.

> [!NOTE]
> Dado que la administración de registros usa etiquetas de retención para marcar un elemento como registro, en esta tabla muchos de los escenarios se muestran como [escenarios comunes de etiquetas de retención y directivas de retención](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels).

|Quiero...|Documentación|
|----------------|---------------|
|Declarar un registro |[Use etiquetas de retención para declarar registros](declare-records.md)|
|Actualizar un registro |[Use el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive](record-versioning.md)|
|Permitir que los administradores y usuarios apliquen de forma manual acciones de retención y eliminación de documentos y mensajes de correo electrónico: <br />- SharePoint <br />- OneDrive <br />- Outlook y Outlook en la Web|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permita que los administradores del sitio establezcan acciones predeterminadas de retención y eliminación para todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permita a los usuarios aplicar automáticamente acciones de retención y eliminación a los correos electrónicos mediante el uso de las reglas de Outlook|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permitir a los administradores aplicar acciones de retención y eliminación en un documento con información sobre el modelo, para que sean aplicado automáticamente a los documentos identificados en una biblioteca de SharePoint|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Aplicar acciones de retención y eliminación automáticamente a documentos y mensajes de correo electrónico |[Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)|
|Inicie el período de retención cuando tenga lugar un evento, por ejemplo, cuando:  <br />- Algún empleado abandone la organización <br />- Algún contrato expire <br />- Finalice la duración de un producto| [Inicie la retención cuando se produzca un evento](event-driven-retention.md)|
|Restrinja los cambios de las directivas para ayudar a cumplir los requisitos reglamentarios o medidas de seguridad frente a administradores no autorizados| [Usar el Bloqueo de conservación para restringir los cambios en las directivas de retención y en las directivas de las etiquetas de retención](retention-preservation-lock.md)
|Administrar el ciclo de vida de los distintos tipos de documentos en SharePoint| [Usar las etiquetas de retención para administrar el ciclo de vida de los documentos almacenados en SharePoint](auto-apply-retention-labels-scenario.md)|
|Antes de eliminar contenido al final de su período de retención, asegúrese de que alguien revise el contenido y dé su aprobación|[Revisiones para eliminación](disposition.md#disposition-reviews) |
|Compruebe si el contenido se elimina de forma permanente al final de su período de retención|[Eliminación de registros](disposition.md#disposition-of-records) |
| Supervise cómo y cuándo se aplican las opciones de conservar y eliminar la configuración de los elementos | [Supervisar las etiquetas de retención](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>Documentación de usuario final para los registros

Las etiquetas de retención que se usan para la administración de registros tienen una presencia de interfaz de usuario en las aplicaciones de Microsoft 365. Asegúrese de que proporciona instrucciones a los usuarios finales y al servicio de asistencia antes de implementar etiquetas de retención en su red de producción.

Para ayudar a los usuarios a aplicar etiquetas de retención en SharePoint y OneDrive, que incluyen información sobre cómo desbloquear registros para editarlos, vea [Aplicar etiquetas de retención a archivos en SharePoint o OneDrive](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df).

Sin embargo, la documentación más eficaz para los usuarios finales serán la guía y las instrucciones personalizadas que proporcione para los nombres de etiquetas de retención y las configuraciones que elija. Consulte la siguiente entrada de blog para obtener un paquete de descarga que puede usar para entrenar a los usuarios e impulsar la adopción: [Formación de usuarios finales para las etiquetas de retención en M365: Cómo acelerar la adopción](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861).
