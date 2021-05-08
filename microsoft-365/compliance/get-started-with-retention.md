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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: ¿Está listo para iniciar la implementación de directivas de retención y de etiquetas de retención para controlar los datos de su organización, pero no está seguro de por dónde comenzar? Lea algunas instrucciones prácticas para empezar.
ms.openlocfilehash: b39f6246fc9265319e0d4e5b053db6dfddc0d43a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244593"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Introducción a las directivas de retención y las etiquetas de retención

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

¿Preparado para empezar a controlar los datos de su organización, conservando el contenido que necesita mantener y eliminando el que ya no necesita? Use las siguientes instrucciones para comenzar:

1. **Obtenga información sobre cómo funciona la retención** en Microsoft 365 y, a continuación, determine si necesita emplear las directivas de retención o las etiquetas de retención, o una combinación de ambas: [Obtenga información sobre la retención](retention.md)

2. **Identifique la configuración de retención y las acciones** que exigen las directivas de su organización o las normativas del sector.
    
    Como parte de esta valoración, determine si usará la [administración de registros](records-management.md).

3. **Cree directivas de retención y etiquetas de retención**, en función de la configuración de retención y de las acciones que haya identificado.
    
    Para las etiquetas de retención, puede que le resulte útil usar el [plan de archivos](file-plan-manager.md) para definir y delimitar las etiquetas de retención en una hoja de cálculo. A continuación, importe la hoja de cálculo para crear las etiquetas.
    
3. **Publique y aplique las etiquetas de retención**. Las directivas de retención se diseñan para poder despreocuparse de la configuración una vez definida, mientras que las etiquetas de retención son bloques de creación reutilizables que se pueden emplear en diferentes directivas y se pueden incorporar a los flujos de trabajo del usuario. Consulte la lista de [escenarios comunes](#common-scenarios-for-retention-policies-and-retention-labels) para ayudarle a entender cómo se pueden usar las etiquetas de retención. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Requisitos de suscripción y de licencias para las directivas de retención y las etiquetas de retención

Varias suscripciones diferentes admiten etiquetas de retención y directivas de retención, y los requisitos de licencias para los usuarios dependen de las características que usted emplee.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de cumplimiento de Microsoft 365, consulte la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Para la retención, consulte la sección [Gobernanza de la información](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) y la información relacionada para descarga en PDF o Excel para conocer los requisitos de licencia de nivel de características.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Permisos necesarios para crear y administrar directivas de retención y etiquetas de retención

Los miembros de su equipo de cumplimiento que crearán y administrarán las directivas de retención y las etiquetas de retención necesitan permisos para el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/). De forma predeterminada, el administrador del espacio empresarial (administrador global) tiene acceso a esta ubicación y puede conceder a los responsables de cumplimiento y a otros usuarios el acceso sin concederles todos los permisos de un administrador de espacio empresarial. Para conceder permisos para esta administración limitada, le recomendamos que agregue usuarios al grupo de roles **Administrador de cumplimiento normativo**.

De manera alternativa al uso de estos roles predeterminados, puede crear un nuevo grupo de roles y agregar el rol de **Administración de retención** a este grupo. Para el rol de solo vista, use **Administración de retención de solo vista**. 

Para más información sobre estos roles y grupos de roles, vea [Permisos en el Centro de seguridad y cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center).

Para obtener instrucciones sobre cómo agregar usuarios a grupos de roles y asignar roles, vea [Proporcionar acceso a los usuarios al Centro de seguridad y cumplimiento](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

Estos permisos son necesarios solo para crear, configurar y aplicar etiquetas y directivas de retención. La persona que configura estas etiquetas y directivas no requiere acceso al contenido.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>Escenarios comunes de directivas de retención y etiquetas de retención

Use la siguiente tabla para ayudarle a asignar los requisitos de su organización a escenarios de retención compatibles con las directivas de retención y las etiquetas de retención.

|Quiero...|Documentación|
|----------------|---------------|
|Establezca eficientemente las acciones de retención y eliminación en el servicio Microsoft 365: <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Grupos de Microsoft 365 <br />- Skype Empresarial  <br />- Microsoft Teams <br />- Red de Yammer |[Crear y configurar directivas de retención](create-retention-policies.md)|
|Permitir que los administradores y usuarios apliquen de forma manual acciones de retención y eliminación de documentos y mensajes de correo electrónico: <br />- SharePoint <br />- OneDrive <br />- Outlook y Outlook en la Web|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permita que los administradores del sitio establezcan acciones predeterminadas de retención y eliminación para todo el contenido de una biblioteca, carpeta o conjunto de documentos de SharePoint|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permita a los usuarios aplicar automáticamente acciones de retención y eliminación a los correos electrónicos mediante el uso de las reglas de Outlook|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Permitir a los administradores aplicar acciones de retención y eliminación en un documento con información sobre el modelo, para que sean aplicado automáticamente a los documentos identificados en una biblioteca de SharePoint|[Crear etiquetas de retención y aplicarlas en aplicaciones](create-apply-retention-labels.md)|
|Aplicar acciones de retención y eliminación automáticamente a documentos y mensajes de correo electrónico |[Aplicar una etiqueta de retención automáticamente al contenido](apply-retention-labels-automatically.md)|
|Inicie el período de retención cuando tenga lugar un evento, por ejemplo, cuando:  <br />- Algún empleado abandone la organización <br />- Algún contrato expire <br />- Finalice la duración de un producto| [Inicie la retención cuando se produzca un evento](event-driven-retention.md)|
|Restrinja los cambios de las directivas para ayudar a cumplir los requisitos reglamentarios o medidas de seguridad frente a administradores no autorizados| [Usar el Bloqueo de conservación para restringir los cambios en directivas de retención y directivas de etiquetas de retención](retention-preservation-lock.md)
|Antes de eliminar contenido al final de su período de retención, asegúrese de que alguien revise el contenido y dé su aprobación|[Revisiones para eliminación](disposition.md#disposition-reviews) |
| Supervise cómo y cuándo se aplican las opciones de conservar y eliminar la configuración de los elementos | [Supervisar las etiquetas de retención](retention.md#monitoring-retention-labels) |
|Utilice una única solución de administración de registros para documentos y mensajes de correo electrónico |[Más información sobre la administración de registros](records-management.md) |

Si usa etiquetas de retención para la administración de registros, hay escenarios adicionales que son únicos para las etiquetas de retención que marcan el contenido como un registro. Consulte [Escenarios comunes para la administración de registros](get-started-with-records-management.md#common-scenarios-for-records-management).

## <a name="end-user-documentation-for-retention"></a>Documentación de usuario final para la retención

La mayoría de las directivas de retención funcionan de forma discreta en segundo plano y no requieren interacción del usuario. Por ello, los usuarios no necesitan apenas documentación. Las directivas de retención de Teams informan a los usuarios cuando se han eliminado sus mensajes con un vínculo a los mensajes de [Teams sobre las directivas de retención](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

Dado que las etiquetas de retención tienen una presencia de interfaz de usuario en las aplicaciones de Microsoft 365, asegúrese de que proporciona instrucciones a los usuarios finales y al servicio de asistencia antes de implementar estas etiquetas en la red de producción. Para ayudar a los usuarios a aplicar etiquetas de retención en SharePoint y OneDrive, vea [Aplicar etiquetas de retención a archivos en SharePoint o OneDrive](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df).

Sin embargo, la documentación más eficaz para los usuarios finales serán la guía y las instrucciones personalizadas que proporcione para los nombres de etiquetas de retención y las configuraciones que elija. Consulte la siguiente entrada de blog para obtener un paquete de descarga que puede usar para entrenar a los usuarios e impulsar la adopción: [Formación de usuarios finales para las etiquetas de retención en M365: Cómo acelerar la adopción](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861).