---
title: Auditoría avanzada en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: La Auditoría avanzada en Microsoft 365 proporciona nuevas características de auditoría que ayudarán a su organización a realizar investigaciones forenses y de cumplimiento.
ms.openlocfilehash: 51ec75cc8d8ae554ea9cbef3a9ea2aa18171e70a
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "48950999"
---
# <a name="advanced-audit-in-microsoft-365"></a>Auditoría avanzada en Microsoft 365

La funcionalidad de [auditoría unificada](search-the-audit-log-in-security-and-compliance.md) en Microsoft 365 le proporciona visibilidad a las organizaciones en los distintos tipos de actividades de auditoría de diversos servicios de Microsoft 365. La Auditoría avanzada ayuda a las organizaciones a realizar investigaciones forenses y de cumplimiento al incrementar la retención de registros de auditoría necesaria para realizar la investigación, proporcionando acceso a los eventos fundamentales que ayudan a determinar el alcance del compromiso y agilizando el acceso a la API de Actividad de administración de Office 365.

> [!NOTE]
> La Auditoría avanzada está disponible para las organizaciones que tengan una suscripción de Office 365 E5 o Microsoft 365 Enterprise E5. Además, también puede asignarse una licencia de Cumplimiento de Microsoft 365 E5 o y una licencia de complemento de Auditoría E5 de eDiscovery a los usuarios, cuando se requiera una licencia por usuario para las características de Auditoría avanzada, como es el caso de la retención a largo plazo de los registros de auditoría y el acceso a eventos fundamentales para las investigaciones. Para obtener más información acerca de las licencias, consulte la [guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit).

Este artículo ofrece una visión general de las funciones de la Auditoría avanzada.

## <a name="long-term-retention-of-audit-logs"></a>Retención a largo plazo de los registros de auditoría

La Auditoría avanzada retiene todos los registros de auditoría de Exchange, SharePoint y Azure Active Directory por un año. Esto se logra a través de la directiva de retención predeterminada del registro de auditoría que retiene cualquier registro de auditoría que contenga el valor **Exchange** , **SharePoint** o **AzureActiveDirectory** para la propiedad de la **Carga de trabajo** (la cual indica el servicio en que ocurrió dicha actividad) por un año. Retener los registros de auditoría por períodos más extensos puede ser de utilidad para las investigaciones forenses o de cumplimiento continuas. Para obtener más información, consulte la sección “Directiva de retención predeterminada para los registros de auditoría” en [Administración de las directivas de retención de los registros de auditoría](audit-log-retention-policies.md#default-audit-log-retention-policy).

También lanzaremos la funcionalidad para retener registros de auditoría durante 10 años. La retención de los registros de auditoría por 10 años ofrece soporte para investigaciones de larga ejecución y para responder a los compromisos reglamentarios, jurídicos e internos.

> [!NOTE]
> Para la retención de los registros de auditoría por 10 años, es necesario tener una licencia adicional del complemento. Esta nueva licencia estará disponible a principios de 2021. Para obtener más información, consulte la sección de [Preguntas frecuentes de la Auditoría avanzada](#faqs-for-advanced-audit) en este artículo.

### <a name="audit-log-retention-policies"></a>Directivas de retención de los registros de auditoría

Todos los registros de auditoría generados en otros servicios que no estén cubiertos por la directiva de retención predeterminada de los registros de auditoría (descrita en la sección anterior) se conservarán por 90 días. Sin embargo, podrá crear directivas de retención personalizadas para retener otros registros de auditoría por períodos más largos de hasta 10 años. Puede crear una directiva para retener los registros de auditoría de acuerdo con más de uno o varios de los siguientes criterios:

- El servicio de Microsoft 365 en donde se realizan las actividades auditadas.

- Especificar las actividades auditadas.

- Ser el usuario que realiza la actividad auditada.

También puede especificar por cuánto tiempo desea retener los registros de auditoría que coincidan con la directiva y el nivel de prioridad, de forma que ciertas directivas específicas tengan mayor prioridad sobre otras directivas. Considere también que cualquier directiva de retención del registro de auditoría predeterminado tendrá prioridad sobre la directiva de retención de auditoría predeterminada, en caso de que necesite retener los registros de auditoría de Exchange, SharePoint o Azure Active Directory por menos de un año (o por 10 años) para algunos o todos los usuarios en su organización. Para obtener más información, consulte [Administrar las directivas de retención del registro de auditoría](audit-log-retention-policies.md).

## <a name="access-to-crucial-events-for-investigations"></a>Acceso a eventos fundamentales para las investigaciones

La Auditoría avanzada ayuda a las organizaciones a dirigir investigaciones forenses y de cumplimiento al proporcionar acceso a eventos fundamentales como cuando se accede a un elemento del correo o cuando se responde o se reenvían determinados elementos del correo, así como también, el momento y el usuario que realizó la búsqueda en Exchange Online y SharePoint Online. Estos eventos fundamentales pueden ayudarle a investigar las posibles brechas y determinar el alcance de la intromisión. La Auditoría avanzada le proporciona los siguientes eventos fundamentales:

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a>MailItemsAccessed

El evento MailItemsAccessed es una acción de auditoría del buzón de correo que se activa cuando se obtiene acceso a datos de correo electrónico a través de los protocolos y los clientes de correo electrónico. La acción MailItemsAccessed puede ayudar a los investigadores a identificar infracciones de datos y determinar el alcance de los mensajes que puedan haberse visto comprometidos. Si un atacante obtiene acceso a los mensajes del correo, la acción MailItemsAccessed se activará, independientemente de si hay alguna señal explícita de que los mensajes se hayan leído realmente (es decir, el tipo de acceso, como un enlace o una sincronización, se registra en el registro de auditoría).

La acción del buzón MailItemsAccessed reemplaza a MessageBind en el registro de auditoría del buzón de Exchange Online y proporciona las siguientes mejoras:

- MessageBind solo se podía configurar para el tipo de inicio de sesión del usuario AuditAdmin, no era aplicable para las acciones de delegado o propietario. MailItemsAccessed aplica para todos los tipos de inicio de sesión.

- MessageBind solo cubría el acceso por un cliente de correo. No era aplicable a las actividades de sincronización. Los eventos de MailItemsAccessed se activan a través de los tipos de acceso de enlace y sincronización.

- Las acciones de MessageBind generarían la creación de diversos registros de auditoría cuando se accedía al mismo mensaje de correo electrónico, lo que producía “ruido” en la auditoría. Por el contrario, los eventos MailItemsAccessed se agregan a menos registros de auditoría.

Para obtener información sobre los registros de auditoría de las actividades de MailItemsAccessed, consulte [Usar la Auditoría avanzada para investigar cuentas comprometidas](mailitemsaccessed-forensics-investigations.md).

Para buscar registros de auditoría de MailItemsAccessed, puede buscar la actividad **elementos del buzón a los que se ha accedido** en la lista desplegable **actividades de buzón de Exchange** en la [herramienta de búsqueda de registros de auditoría](search-the-audit-log-in-security-and-compliance.md) en el centro de cumplimiento de Microsoft 365.

![Buscar acciones MailItemsAccessed en la herramienta de búsqueda de registros de auditoría](../media/AdvAudit_MailItemsAccessed.png)

También puede ejecutar los comandos [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) o [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) en Exchange Online PowerShell.

### <a name="send"></a>Enviar

El evento Enviar también es una acción de auditoría del buzón de correo y se activa cuando un usuario realiza una de las acciones siguientes:

- Envía un mensaje de correo electrónico

- Responde a un mensaje de correo electrónico

- Reenvía un mensaje de correo electrónico

Los investigadores pueden usar el evento Enviar para identificar los correos electrónicos que se envíen desde una cuenta en peligro. El registro de auditoría para un evento de Enviar contiene información acerca del mensaje, como el momento en que fue enviado, el id. del InternetMessage, la línea de asunto y si el mensaje contiene datos adjuntos. Esta información de auditoría puede ayudar a los investigadores a identificar información acerca de los mensajes de correo electrónico enviados desde una cuenta en peligro o enviados por el atacante. Además, los investigadores pueden usar una herramienta eDiscovery de Microsoft 365 para buscar el mensaje (al usar la línea de asunto o el id. del mensaje) para identificar a los destinatarios del mensaje y su contenido real.

Para buscar los registros de auditoría de Enviados, puede buscar la actividad de **Mensaje enviado** en la lista desplegable **Actividades del buzón de Exchange** de la [herramienta de búsqueda en el registro de auditoría](search-the-audit-log-in-security-and-compliance.md) en el Centro de cumplimiento de Microsoft 365.

![Buscar acciones de mensaje enviado en la herramienta de búsqueda de registros de auditoría](../media/AdvAudit_SentMessage.png)

También puede ejecutar los comandos [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) o [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) en Exchange Online PowerShell.

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

El evento SearchQueryInitiatedExchange se activa cuando una persona usa la barra de Búsqueda de Outlook en la Web (OWA) para buscar elementos en el buzón de correo. Los investigadores pueden usar el evento SearchQueryInitiatedExchange para determinar si un atacante que pueda haber puesto en peligro una cuenta ha buscado o intentado tener acceso a la información confidencial en el buzón de correo. El registro de auditoría para un evento SearchQueryInitiatedExchange contiene información como el texto real de la consulta de búsqueda. Al observar las consultas de búsqueda que pudo haber realizado el atacante, el investigador puede comprender mejor el propósito de los datos del correo electrónico que se buscaron.

Para buscar los registros de auditoría de SearchQueryInitiatedExchange, puede buscar la actividad de **Búsqueda de mensaje realizada** en la lista desplegable de **Actividades de búsqueda** de la [herramienta de búsqueda de registros de auditoría](search-the-audit-log-in-security-and-compliance.md) en el Centro de cumplimiento.

![Buscar acciones de búsqueda de mensaje enviado en la herramienta de búsqueda de registros de auditoría](../media/AdvAudit_SearchExchange.png)

También puede ejecutar [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) en Exchange Online PowerShell.

> [!NOTE]
> Debe ejecutar el comando siguiente en Exchange Online PowerShell para que los eventos SearchQueryInitiatedExchange (llevados a cabo por el usuario de E5 especificado) se incluyan en los resultados de la búsqueda en el registro de auditoría: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

Al igual que con la búsqueda de elementos del buzón, el evento SearchQueryInitiatedSharePoint se activa cuando una persona busca elementos en el sitio principal de SharePoint de su organización. Los investigadores pueden usar el evento SearchQueryInitiatedSharePoint para determinar si el atacante intentó buscar información confidencial en SharePoint (y posiblemente acceder a ella). El registro de auditoría para un evento SearchQueryInitiatedSharePoint también contiene el texto real de la consulta de búsqueda. Al revisar las consultas de búsqueda que pueda haber realizado el atacante, el investigador puede comprender mejor el propósito y el alance de los datos de archivo que fueron buscados.

Para buscar los registros de auditoría de SearchQueryInitiatedSharePoint, puede buscar la actividad de **Búsqueda de SharePoint realizada** en la lista desplegable de **Actividades de búsqueda** de la [herramienta de búsqueda de registros de auditoría](search-the-audit-log-in-security-and-compliance.md) en el Centro de cumplimiento.

![Buscar acciones de búsqueda de SharePoint realizadas en la herramienta de búsqueda de registros de auditoría](../media/AdvAudit_SearchSharePoint.png)

También puede ejecutar [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) en Exchange Online PowerShell.

> [!NOTE]
> Debe ejecutar el comando siguiente en Exchange Online PowerShell para que los eventos SearchQueryInitiatedSharePoint (llevados a cabo por el usuario de E5 especificado) se incluyan en los resultados de la búsqueda en el registro de auditoría: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`.

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Acceso de banda ancha a la API de Actividad de administración de Office 365

Las organizaciones con acceso a los registros de auditoría a través de la API de Actividad de administración de Office 365 fueron restringidas con límites en el nivel de editor. Esto quiere decir que cuando un editor extrae datos en nombre de varios clientes, todos los clientes comparten el mismo límite.

Con el lanzamiento de la Auditoría avanzada, cambiamos el límite desde el nivel del editor al nivel del espacio empresarial. El resultado es que cada organización obtendrá su propia cuota de ancho de banda completamente asignada para acceder a sus datos de auditoría. El ancho de banda no es un límite estático y predefinido, sino que se modela a partir de una combinación de factores que incluyen el número de puestos en la organización y que las organizaciones E5 tendrán un mayor ancho de banda que las organizaciones que no son E5.

Inicialmente se le asigna un ancho de banda a todas las organizaciones de 2,000 solicitudes por minuto. Este límite irá aumentando de forma dinámica de acuerdo con la cantidad de puestos de la organización y con su suscripción de licencias. Las organizaciones E5 obtendrán el doble del ancho de banda que el que obtendrán las organizaciones que no son E5. También habrá un límite en el máximo del ancho de banda para proteger el estado del servicio.

Para obtener más información, consulte la sección "límite de la API" en la [referencia de la API de Actividad de administración de Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).

## <a name="faqs-for-advanced-audit"></a>Preguntas más frecuentes sobre las auditorías avanzadas

**¿Todos los usuarios necesitan una licencia de E5 para beneficiarse de la Auditoría avanzada?**

Para beneficiarse de las funciones de la Auditoría avanzada de nivel de usuario, debe asignársele una licencia E5 al usuario. Hay algunas funciones que comprueban la existencia de la licencia correspondiente para mostrar la característica al usuario. Por ejemplo, si está intentando retener por más de 90 días los registros de auditoría de un usuario que no tiene asignada ninguna licencia E5, el sistema le devolverá un mensaje de error.

**Si mi organización tiene una suscripción a E5, ¿necesito hacer algo para acceder a los registros de auditoría de los eventos fundamentales?**

Para los clientes que cumplan los requisitos y los usuarios a los que se les asigne la licencia adecuada, no hay ninguna acción que deban ejercer para acceder a los eventos de auditoría fundamentales.

**¿Cuándo estará disponible la nueva licencia del complemento de retención del registro de auditoría de 10 años?**

La compra del nuevo complemento de retención de registro de auditoría de 10 años estará disponible para los clientes que tengan suscripciones a E5 a principios de 2021.

**¿Qué ocurre con los datos de registro de auditoría de mi organización si creo una directiva de retención de registro de auditoría de 10 años, la característica se ha publicado para disponibilidad general, pero antes de que esté disponible la licencia de complemento necesaria a principios de 2021?**

Todos los datos del registro de auditoría cubiertos por una directiva de retención de registro de auditoría de 10 años creada después de la disponibilidad general se conservarán durante 10 años. Cuando la licencia del complemento de retención del registro de auditoría de 10 años esté disponible a principios de 2021, tendrá que adquirir licencias de complemento para los usuarios cuyos datos de auditoria se retengan por una directiva de retención de auditoria existente de 10 años. Asimismo, una vez que la licencia del complemento esté disponible a principios de 2021, las licencias adecuadas se aplicarán cuando cree nuevas directivas de retención de registro de auditoría de 10 años.

**¿Están disponibles los nuevos eventos de la auditoría avanzada en la API de Actividad de administración de Office 365?**

Sí. Siempre que los registros de auditoría se generen para los usuarios con la licencia apropiada, podrá obtener acceso a estos registros a través de la API de Actividad de administración de Office 365.

**¿Un ancho de banda mayor significa una mayor latencia o un SLA mayor?**

En este momento, un ancho de banda alto ofrece una canalización más eficaz, especialmente para las organizaciones con un alto volumen de señales de auditoría y patrones de consumo significativos. Más ancho de banda puede dar lugar a una mejor latencia. Sin embargo, no hay un SLA asociado con el ancho de banda alto. Se documentan las latencias estándar y no se modifican con la versión de la auditoría avanzada.
