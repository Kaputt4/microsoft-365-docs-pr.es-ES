---
title: Auditoría avanzada en Microsoft 365
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
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: La auditoría avanzada en Microsoft 365 proporciona nuevas características de auditoría que ayudarán a su organización a realizar investigaciones forenses y de cumplimiento.
ms.openlocfilehash: 49d2e2bbf7d1c19bb4c282920008a0ca9a34188d
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862425"
---
# <a name="advanced-audit-in-microsoft-365"></a>Auditoría avanzada en Microsoft 365

La [funcionalidad de auditoría unificada](search-the-audit-log-in-security-and-compliance.md) en Microsoft 365 proporciona a las organizaciones la visibilidad de muchos tipos de actividades auditadas a través de los distintos servicios de Microsoft 365. Con el lanzamiento de la auditoría avanzada en Microsoft 365, agregamos nuevas características de auditoría que ayudarán a su organización a realizar investigaciones forenses y de cumplimiento.

> [!NOTE]
> La auditoría avanzada está disponible para organizaciones que tengan una suscripción a Office 365 o Microsoft 365 Enterprise E5. Además, se puede asignar a los usuarios una suscripción al complemento de cumplimiento de Microsoft 365 E5 para cuando se requiera una licencia por usuario para las funciones avanzadas de auditoría, como es el caso de la retención a largo plazo de los registros de auditoría y de los eventos de auditoría de alto valor.

Este artículo ofrece una visión general de las características de la auditoría avanzada.

## <a name="long-term-retention-of-audit-logs"></a>Retención a largo plazo de los registros de auditoría

La auditoría avanzada conserva todos los registros de auditoría de Exchange, SharePoint y Azure Active Directory durante un año. Esto se logra mediante la directiva de retención de registros de auditoría predeterminada que conserva durante un año cualquier registro de auditoría que contenga el valor de **Exchange** ,**SharePoint** o **AzureActiveDirectory** para la propiedad de la **carga de trabajo** (que indica el servicio en el que se produjo la actividad). Esto puede ser de utilidad para las investigaciones forenses y de cumplimiento en curso. Para más información, vea la sección "Directiva predeterminada de retención de registros de auditoría" en [administrar las directivas de retención de registros de auditoría](audit-log-retention-policies.md#default-audit-log-retention-policy).

## <a name="audit-log-retention-policies"></a>Directivas de retención de registros de auditoría

Todos los registros de auditoría generados en otros servicios que no estén cubiertos por la directiva predeterminada de retención de registros de auditoría (descrita en la sección anterior) se conservarán durante 90 días. Sin embargo, ahora puede crear directivas de retención de registro personalizados de auditoría para conservar otros registros de auditoría de hasta un año. Puede crear una directiva para conservar registros de auditoría en función de uno o varios de los siguientes criterios:

- Las actividades auditadas se realizan en el servicio de Microsoft 365

- Especificar las actividades auditadas

- Ser el usuario que realiza la actividad auditada

También puede especificar el tiempo de retención de los registros de auditoría que coincidan con la directiva y el nivel de prioridad, de modo que ciertas políticas específicas tengan prioridad sobre otras. También debe tener en cuenta que cualquier directiva de retención de registros personalizados de auditoría tendrán prioridad sobre la directiva predeterminada de retención de auditorías en caso de que necesite conservar los registros de auditoría de Exchange, SharePoint o Azure Active Directory durante menos de un año para todos o algunos de los usuarios de su organización. Para obtener más información, vea [administrar directivas de retención de los registros de auditoría](audit-log-retention-policies.md).

## <a name="high-value-audit-events"></a>Eventos de auditoría de alto valor

Los eventos de auditoría de alto valor relacionados con la seguridad y el cumplimiento son aquellos que pueden ayudarle a investigar las posibles infracciones u otras investigaciones forenses. El primero de estos eventos de alto valor que estamos lanzando es el evento de auditoría del buzón *MailItemsAccessed* Este evento se desencadena cuando se obtiene acceso a los datos del correo mediante protocolos y clientes de correo. El evento MailItemsAccess puede ayudar a los investigadores a identificar las vulneraciones de datos y determinar el ámbito de los mensajes que han estado en peligro. Si un atacante obtuvo acceso a los mensajes de correo electrónico, se desencadenará el evento MailItemsAccessed aunque no haya ninguna señal explícita de que se haya leído realmente (es decir, el tipo de acceso como, por ejemplo, mediante enlace o sincronización, se graba en el registro de auditoría).

La nueva acción de buzón MailItemsAccessed reemplaza a MessageBind en el registro de auditoría de buzón de Exchange Online y proporciona las siguientes mejoras:

- MessageBind sólo era configurable para el tipo de inicio de sesión de usuario AuditAdmin; no se aplicaba a las acciones de los delegados o los propietarios. MailItemsAccessed se aplica a todos los tipos de inicio de sesión.

- MessageBind sólo cubre el acceso de un cliente de correo. No se aplicó a las actividades de sincronización. Los eventos MailItemsAccessed se desencadena con los tipos de acceso enlazar y sincronizar.

- Las acciones de MessageBind desencadenarían la creación de múltiples registros de auditoría cuando se accediera al mismo mensaje de correo electrónico, lo que daría lugar a un "ruido" de auditoría. En cambio, los eventos de MailItemsAccessed se agregan en menos registros de auditoría.

Para obtener más información sobre el registro de auditoría de buzones de correo, vea [Administrar la auditoría de buzones](enable-mailbox-auditing.md).

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Acceso de banda ancha a la API de Actividad de administración de Office 365

Las organizaciones que tienen acceso a registros de auditoría a través de la API de Actividad de administración de Office 365 se restringieron con límites en el nivel de publicador. Esto significa que para un publicador que extraía datos en nombre de múltiples clientes, el límite era compartido por todos esos clientes.

Con el lanzamiento de la auditoría avanzada, pasamos de un límite de nivel de publicador a un límite de nivel de inquilino. El resultado es que cada organización obtendrá su propia cuota de ancho de banda totalmente asignada para acceder a los datos de auditoría. El ancho de banda no es un límite estático y predefinido, sino que se basa en una combinación de factores que incluyen el número de puestos en la organización y que las organizaciones E5 obtendrán más ancho de banda que las organizaciones que no son E5.

Se asigna inicialmente una línea base de 2000 solicitudes por minuto a todas las organizaciones. Este límite se incrementará de forma dinámica dependiendo del número de puestos de la organización y su suscripción de licencias. Las organizaciones E5 obtendrán aproximadamente el doble de ancho de banda que las organizaciones no son E5. También habrá un límite en el ancho de banda máximo para proteger el estado del servicio.

Para obtener más información, vea la sección "límite de la API" en la [referencia de la API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).
