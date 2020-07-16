---
title: Introducción a las directivas de retención y las etiquetas de retención
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
description: ¿Está listo para iniciar la implementación de directivas de retención y de etiquetas de retención para controlar los datos de su organización, pero no está seguro de por dónde empezar? Lea algunas instrucciones prácticas para empezar.
ms.openlocfilehash: 415313ac31fe4ad56f9a476576f14b90d7dd97f4
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127611"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Introducción a las directivas de retención y las etiquetas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

¿Está preparado? Ahora podrá empezar a controlar los datos de su organización, conservando el contenido que necesita mantener y eliminando el que ya no necesita. Utilice la siguiente guía de alto nivel para comenzar:

1. **Obtenga información sobre cómo funciona la retención** en Microsoft 365 y, a continuación, determine si necesita emplear las directivas de retención o las etiquetas de retención, o una combinación de ambas: [Obtenga información sobre la retención](retention.md)

2. **Identifique la configuración de retención y las acciones** que exigen las directivas de su organización o las normativas del sector.
    
    Como parte de esta valoración, determine si usará la [administración de registros](records-management.md).

3. **Cree directivas de retención y etiquetas de retención**, en función de la configuración de retención y de las acciones que haya identificado.
    
    Para las etiquetas de retención, puede que le resulte útil usar el [plan de archivos](file-plan-manager.md) para definir y delimitar las etiquetas de retención en una hoja de cálculo. A continuación, importe la hoja de cálculo para crear las etiquetas.
    
3. **Publique y aplique las etiquetas de retención**. Las directivas de retención se diseñan para poder despreocuparse de la configuración una vez definida, mientras que las etiquetas de retención son bloques de creación reutilizables que se pueden emplear en diferentes directivas y se pueden incorporar a los flujos de trabajo del usuario. Consulte la lista de [escenarios comunes](#common-scenarios-for-retention-policies-and-retention-labels) para ayudarle a entender cómo se pueden usar las etiquetas de retención. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Requisitos de suscripción y de licencias para las directivas de retención y las etiquetas de retención

Varias suscripciones diferentes admiten etiquetas de retención y directivas de retención, y los requisitos de licencias para los usuarios dependen de las características que usted emplee.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de cumplimiento de Microsoft 365, consulte la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD). Para la retención, consulte la sección [Gobernanza de la información](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) y la información relacionada para descarga en PDF o Excel para conocer los requisitos de licencia de nivel de características.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Permisos necesarios para crear y administrar directivas de retención y etiquetas de retención

Los miembros de su equipo de cumplimiento que crearán y administrarán las directivas de retención y las etiquetas de retención necesitan permisos para el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/). De forma predeterminada, el administrador del espacio empresarial (administrador global) tiene acceso a esta ubicación y puede conceder a los responsables de cumplimiento y a otros usuarios el acceso sin concederles todos los permisos de un administrador de espacio empresarial. Para conceder permisos para esta administración limitada, le recomendamos que agregue usuarios al grupo de roles **Administrador de cumplimiento normativo**. Para instrucciones, consulte [Proporcionar a los usuarios acceso al Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Estos permisos sólo son necesarios para crear y aplicar una directiva de retención. La persona que configura la directiva de retención no requiere acceso al contenido.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>Escenarios comunes de directivas de retención y etiquetas de retención

Use la siguiente tabla para ayudarle a asignar los requisitos de su organización a escenarios de retención compatibles con las directivas de retención y las etiquetas de retención.

|Quiero...|Documentación|
|----------------|---------------|
|Establecer de forma eficiente las acciones de conservación y de eliminación en la organización, o bien por ubicación: <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Grupos de Microsoft 365 <br />- Skype Empresarial  <br />- Teams  |[Crear y configurar directivas de retención](create-retention-policies.md)|
|Permitir a los administradores y usuarios aplicar manualmente un conjunto de acciones de conservación y de eliminación de documentos y mensajes de correo electrónico: <br />- SharePoint <br />- OneDrive <br />- Outlook y Outlook en la Web|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permitir a los administradores del sitio aplicar una etiqueta de retención predeterminada a todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permitir a los usuarios aplicar una etiqueta de retención automáticamente a los mensajes de correo electrónico mediante reglas de Outlook|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Aplicar manualmente un conjunto de acciones de conservación y de eliminación a documentos y mensajes de correo electrónico |[Aplicar una etiqueta de retención a contenido automáticamente](apply-retention-labels-automatically.md)|
|Inicie el período de retención cuando tenga lugar un evento, por ejemplo, cuando:  <br />- Algún empleado abandone la organización <br />- Algún contrato expire <br />- Finalice la duración de un producto| [Inicie la retención cuando se produzca un evento](event-driven-retention.md)|
|Utilice una única solución de administración de registros para documentos y mensajes de correo electrónico |[Administración de registros en Microsoft 365](records-management.md) |
|Cumplir con la norma 17a-4 de la SEC|[Usar Exchange Online y el Centro de seguridad y cumplimiento para cumplir con la norma SEC 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md) |
|Antes de eliminar contenido al final de su período de retención, asegúrese de que alguien revise el contenido y dé su aprobación|[Revisiones para eliminación](disposition.md#disposition-reviews) |
|Compruebe la eliminación de contenido cuando se elimine el mismo al final de su período de retención|[Eliminación de registros](disposition.md#disposition-of-records) |

## <a name="end-user-documentation-for-retention-labels"></a>Documentación de usuario final para las etiquetas de retención

Las etiquetas de retención, a diferencia de las directivas de retención, tienen presencia de interfaz de usuario en las aplicaciones de Microsoft 365. Asegúrese de proporcionar instrucciones a los usuarios finales y a su servicio de asistencia antes de implementar etiquetas de retención en la red de producción.

La documentación más eficaz para los usuarios finales serán las instrucciones personalizadas que proporcione para los nombres de etiquetas de retención y para las configuraciones que elija. Sin embargo, puede usar la siguiente información para obtener instrucciones básicas:

- [Aplicar etiquetas de retención manualmente](create-apply-retention-labels.md#manually-apply-retention-labels)
