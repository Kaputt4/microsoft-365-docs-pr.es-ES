---
title: Introducción a la administración de registros
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
description: ¿Necesita una solución de administración de registros para Microsoft 365 que administre contenido de gran valor para obligaciones legales, comerciales o de reglamentación, pero no sabe por dónde empezar? Lea algunas instrucciones prácticas para empezar.
ms.openlocfilehash: bec70df94ce81ee7497b3ec236dca5649ce90cb7
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778649"
---
# <a name="get-started-with-records-management"></a>Introducción a la administración de registros

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

¿Está preparado para empezar a administrar el contenido de alto nivel de su organización para las obligaciones legales, empresariales o reglamentarias con una solución de administración de registros? Utilice la siguiente guía de alto nivel para comenzar:

1. **Entienda la solución de administración de registros** y qué acciones se permiten o bloquean cuando se declaran documentos y mensajes de correo electrónico: [Obtenga más información sobre la administración de registros](records-management.md). 

2. **Entienda qué son las etiquetas de retención y cómo funciona la retención** en SharePoint y Exchange. Las etiquetas de retención se usan para declarar registros: [infórmese sobre las directivas de retención y las etiquetas de retención](retention.md).

3. **Cree el plan de archivos para la configuración y las acciones de retención**. Para ello, [importe un plan existente](file-plan-manager.md#import-retention-labels-into-your-file-plan ) si lo tiene, o cree [nuevas etiquetas de retención que declaren registros](declare-records.md).

4. **Publique y aplique las etiquetas de retención**. Las etiquetas de retención son bloques de creación reutilizables que se pueden emplear en diferentes directivas y se pueden incorporar a los flujos de trabajo del usuario: 
    
    - [Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)
    - [Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Requisitos de suscripción y de licencias para las directivas de retención y las etiquetas de retención

Distintas suscripciones admiten diferentes administraciones de registros y los requisitos de licencias para los usuarios dependen de las características que use.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de cumplimiento de Microsoft 365, consulte la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD). Para la administración de registros, vea la sección de [Administración de registros](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) y las descargas relacionadas en PDF o Excel para obtener más información sobre los requisitos de licencias de nivel de características.

## <a name="permissions-required-for-records-management"></a>Permisos necesarios para la administración de registros

Los miembros de su equipo de cumplimiento responsables de la administración de registros necesitan permisos en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/). De forma predeterminada, el administrador del espacio empresarial (administrador global) tiene acceso a esta ubicación y puede conceder el acceso a los responsables de cumplimiento y a otros usuarios sin darles todos los permisos de un administrador de espacio empresarial. Para conceder permisos para esta administración limitada, le recomendamos que agregue usuarios al grupo de roles **Administración de registros**. Para instrucciones, consulte [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Estos permisos son necesarios solo para crear, configurar y aplicar etiquetas de retención para declarar registros. La persona que configura estas etiquetas no requiere acceso al contenido.

## <a name="common-scenarios-for-records-management"></a>Escenarios comunes para la administración de registros

Ayúdese de la siguiente tabla para asignar los requisitos empresariales a los escenarios admitidos por la administración de registros.

> [!NOTE]
> Dado que la administración de registros usa etiquetas de retención para marcar un elemento como registro, en esta tabla muchos de los escenarios se muestran como [escenarios comunes de etiquetas de retención y directivas de retención](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels).

|Quiero...|Documentación|
|----------------|---------------|
|Declarar un registro |[Use etiquetas de retención para declarar registros](declare-records.md)|
|Actualizar un registro |[Use el control de versiones de registros para actualizar los registros almacenados en SharePoint o OneDrive](record-versioning.md)|
|Permitir a los administradores y usuarios aplicar manualmente un conjunto de acciones de conservación y de eliminación de documentos y mensajes de correo electrónico: <br />- SharePoint <br />- OneDrive <br />- Outlook y Outlook en la Web|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permitir a los administradores del sitio aplicar una etiqueta de retención predeterminada a todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permitir a los usuarios aplicar una etiqueta de retención automáticamente a los mensajes de correo electrónico mediante reglas de Outlook|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Aplicar manualmente un conjunto de acciones de conservación y de eliminación a documentos y mensajes de correo electrónico |[Aplicar una etiqueta de retención a contenido automáticamente](apply-retention-labels-automatically.md)|
|Inicie el período de retención cuando tenga lugar un evento, por ejemplo, cuando:  <br />- Algún empleado abandone la organización <br />- Algún contrato expire <br />- Finalice la duración de un producto| [Inicie la retención cuando se produzca un evento](event-driven-retention.md)|
|Administrar el ciclo de vida de los distintos tipos de documentos en SharePoint| [Usar las etiquetas de retención para administrar el ciclo de vida de los documentos almacenados en SharePoint](auto-apply-retention-labels-scenario.md)|
|Antes de eliminar contenido al final de su período de retención, asegúrese de que alguien revise el contenido y dé su aprobación|[Revisiones para eliminación](disposition.md#disposition-reviews) |
|Obtener comprobación de la eliminación de contenido cuando este se elimine al final de su período de retención|[Eliminación de registros](disposition.md#disposition-of-records) |
| Supervisar cómo y dónde se aplican las etiquetas de retención | [Supervisar las etiquetas de retención](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>Documentación de usuario final para los registros

Las etiquetas de retención que se usan para la administración de registros aparecen en la interfaz de usuario de las aplicaciones de Microsoft 365. Asegúrese de proporcionar instrucciones a los usuarios finales y a su servicio de asistencia antes de implementar etiquetas de retención en la red de producción.

La documentación más eficaz para los usuarios finales serán las instrucciones personalizadas que proporcione para los nombres de etiquetas de retención y para las configuraciones que elija. Sin embargo, puede usar la siguiente información para obtener instrucciones básicas:

- [Aplicar etiquetas de retención manualmente](create-apply-retention-labels.md#manually-apply-retention-labels)
