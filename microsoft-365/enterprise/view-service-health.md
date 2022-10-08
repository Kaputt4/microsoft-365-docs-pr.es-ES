---
title: Cómo comprobar el estado del servicio de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- scotvorg
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: Antes de llamar al soporte técnico, consulte el estado de mantenimiento de los servicios de Microsoft 365 para comprobar si existe alguna interrupción del servicio.
ms.openlocfilehash: 210afaa3fc9a3fb247d56baf9172221ad24cced7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68179271"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Cómo comprobar el estado del servicio de Microsoft 365

[![Etiqueta para informarle de que el centro de administración está cambiando y de que puede encontrar más detalles en aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

You can view the health of your Microsoft services, including Office on the web, Yammer, Microsoft Dynamics CRM, and mobile device management cloud services, on the **Service health** page in the [Microsoft 365 admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339). If you are experiencing problems with a cloud service, you can check the service health to determine whether this is a known issue with a resolution in progress before you call support or spend time troubleshooting.

Si no puede iniciar sesión en el centro de administración, puede usar la [página de estado del servicio](https://status.office365.com) para comprobar si hay algún problema conocido que le impida iniciar sesión en el inquilino.  Regístrese y síganos en [@MSFT365status](https://twitter.com/MSFT365Status) en Twitter para ver información sobre determinados eventos.

## <a name="how-to-check-service-health"></a>Cómo comprobar el estado del servicio

1. Vaya al Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) e inicie sesión con una cuenta de administrador.

    > [!NOTE]
    > People who are assigned the global admin or service support admin role can view service health. To allow Exchange, SharePoint, and Skype for Business admins to view service health, they must also be assigned the Service admin role. For more information about roles that can view service health, see [About admin roles](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles).

2. To view service health, in the left-hand navigation of the admin center, go to **Health** > **Service health**, or select the **Service health** card on the **Home dashboard**. The dashboard card indicates whether there is an active service issue and links to the detailed **Service health** page.

3. En la página de **Estado del servicio**, podrá ver el estado de mantenimiento de los servicios en la nube en formato de tabla.

   ![Vista de los problemas actuales del estado del servicio.](../media/shd-landing-page.png)

La pestaña de **Todos los servicios** (vista predeterminada) muestra todos los servicios junto con los estados de mantenimiento y cualquier incidente o aviso activo. El icono y estado en la columna de **Estado** indica cómo está cada servicio.

Si existe un incidente o aviso activo de un servicio, los verá bajo el nombre del servicio en una tabla anidada. En esta vista es posible contraer la tabla anidada para ocultar los incidentes o avisos simplemente haciendo clic en el icono de contenido adicional situado a la izquierda del nombre del servicio.

Para utilizar el filtro de ver todos los incidentes activos, seleccione la pestaña **Incidentes** en la parte superior de la página. Si selecciona la pestaña de **Avisos** se mostrarán únicamente los avisos publicados.

La pestaña **Historial** muestra todos los incidentes y avisos que se han resuelto en los últimos siete o treinta días.

Si tiene un problema con algún servicio de Microsoft 365 y no lo encuentra en **Estado del servicio**, comuníquelo seleccionando **Notificar un problema** y rellenando el correspondiente formulario. Examinaremos datos e informes de otras organizaciones relacionados con su problema para ver qué tan extendido se encuentra y si se originó por nuestro servicio. Si así fuera, lo añadiremos como nuevo incidente o aviso en la página **Estado del servicio** donde podrá darle seguimiento.  La página de **Problemas notificados** le mostrará todos los problemas que el inquilino nos ha notificado desde el formulario y desde el estado.

To customize your view of which services show up on the dashboard, select **Preferences** > **Custom view**,  and clear the checkboxes for the services you want to filter out of your Service health dashboard view. Make sure that the checkbox is selected for each service that you want to monitor.

Si quiere recibir notificaciones por correo electrónico sobre nuevos incidentes que afecten a su inquilino y cambios de estado de un incidente activo, seleccione **Preferencias** > **Correo electrónico**, haga clic en **Recibir notificaciones de estado del servicio en el correo electrónico** y, a continuación, especifique:

- Hasta dos direcciones de correo electrónico.
- Si desea recibir notificaciones de incidentes o avisos
- Sobre qué servicios desea las notificaciones

También puede suscribirse a notificaciones por correo electrónico de eventos individuales y no de cada evento de un servicio. Para ello seleccione el incidente activo sobre el que quiere recibir notificaciones, vaya a **Administrar notificaciones para este problema** y especifique:

- Hasta dos direcciones de correo electrónico.

> [!NOTE]
> El límite es de dos direcciones de correo electrónico por cada administrador. Cada administrador puede establecer sus propias preferencias.

> [!TIP]
> También puede utilizar la [aplicación de administración de Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=627216) en su dispositivo móvil para ver el estado del servicio y mantenerse al día con las notificaciones de inserción.

### <a name="view-details-of-posted-service-health"></a>Ver detalles del estado del servicio publicado

En la vista de **Todos los servicios** seleccione el título del problema y podrá ver una página con información detallada del problema, incluidos los mensajes que iremos publicando mientras trabajamos en la solución.

[![Captura de pantalla de avisos del servicio.](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

En el resumen del aviso o del incidente, se proporciona la siguiente información:

- **TÍtulo**: resumen del problema.
- **ID**: identificador numérico del problema.
- **Servicio**: nombre del servicio afectado.
- **Última actualización**: última vez que se actualizó el mensaje de estado del servicio.
- **Hora estimada de inicio**: hora estimada en que se inició el problema.
- **Estado**: cómo afecta este problema al servicio.
- **Impacto en el usuario**: breve descripción del impacto que tiene el problema en el usuario final.
- **Actualizaciones**: publicamos mensajes con frecuencia para informarle del progreso que estamos haciendo para encontrar una solución.

![Captura de pantalla que muestra los detalles del problema.](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Traducción de los detalles del estado del servicio

Usamos la traducción automática para mostrar los mensajes en su idioma de preferencia de forma automática. Vaya a [Traducción de las publicaciones del Centro de mensajes](lang-service-health.md) para obtener más información sobre cómo establecer su idioma de preferencia.

### <a name="definitions"></a>Definiciones

Most of the time, services will appear as healthy with no further information. When a service is having a problem, the issue is identified as either an advisory or an incident and shows a current status.

> [!TIP]
> Planned maintenance events aren't shown in service health. You can track planned maintenance events by staying up to date with the **Message center**. Filter to messages categorized as Plan for change to find out when the change is going to happen, its effect, and how to prepare for it. See [Message center in Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) for more details.

### <a name="incidents-and-advisories"></a>Incidentes y avisos

| Icono | Descripción |
|:-----|:-----|
|![Icono de información de avisos.](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|If a service has an advisory shown, we are aware of a problem that is affecting some users, but the service is still available. In an advisory, there is often a workaround to the problem and the problem may be intermittent or is limited in scope and user impact.  <br/> |
|![Icono de signo de exclamación de incidentes.](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|If a service has an active incident shown, it's a critical issue and the service or a major function of the service is unavailable. For example, users may be unable to send and receive email or unable to sign-in. Incidents will have noticeable impact to users. When there is an incident in progress, we will provide updates regarding the investigation, mitigation efforts, and confirmation of resolution in the Service health dashboard.  <br/> |

### <a name="status-definitions"></a>Definiciones del estado

| Estado | Definición |
|:-----|:-----|
|**Investigando** | Somos conscientes de que existe un problema potencial y estamos recopilando más información sobre lo que sucede y su ámbito de impacto. |
|**Deterioro del servicio** | We've confirmed that there is an issue that may affect use of a service or feature. You might see this status if a service is performing more slowly than usual, there are intermittent interruptions, or if a feature isn't working, for example. |
|**Interrupción del servicio** | You'll see this status if we determine that an issue affects the ability for users to access the service. In this case, the issue is significant and can be reproduced consistently. |
|**Restaurando el servicio** | Se ha identificado la causa del problema, sabemos qué acción correctiva debemos aplicar y estamos en proceso de restablecer el servicio a un estado correcto. |
|**Recuperación en proceso** | This status indicates that corrective action is in progress to restore service to most users but will take some time to reach all the affected systems. You might also see this status if we've made a temporary fix to reduce impact while we wait to apply a permanent fix. |
|**Investigación suspendida** | If our detailed investigation of a potential issue results in a request for additional information from customers to allow us to investigate further, you'll see this status. If we need you to act, we'll let you know what data or logs we need. |
|**Servicio restaurado** | We've confirmed that corrective action has resolved the underlying problem and the service has been restored to a healthy state. To find out what went wrong, view the issue details. |
|**Falso positivo** | Después de una investigación detallada, hemos confirmado que el servicio se encuentra en buen estado y funciona correctamente. No se observó ningún impacto en el servicio o la causa del incidente se originó fuera del servicio. Los incidentes y avisos con este estado aparecen en la vista de historial hasta que expiran (después del período de tiempo indicado en la publicación final de ese evento). |
|**Publicación del informe posterior al incidente** | Hemos publicado un Informe posterior al incidente para un problema específico que incluye información de las causas principales y procedimientos a seguir para garantizar que no vuelva a reproducirse un problema similar. |

### <a name="message-post-types"></a>Tipos de publicación de mensajes

| Tipo | Definición |
|:-----|:-----|
|**Actualización rápida** | Actualizaciones breves y frecuentes disponibles para todos los clientes para incidentes de alto impacto. |
|**Detalles adicionales** | Estas publicaciones adicionales proporcionan detalles técnicos y de resolución más completos para ofrecer una mayor visibilidad al tratamiento de incidentes. Disponible para inquilinos que cumplen con los mismos requisitos que se detallan en la [supervisión de Exchange Online](/microsoft-365/enterprise/microsoft-365-exchange-monitoring#requirements). |

### <a name="history"></a>Historial

Service health lets you look at your current health status and view the history of any service advisories and incidents that have affected your tenant in the past 30 days. To view the past health of all services, select **History** view.

Para obtener más información sobre nuestro compromiso con el tiempo de actividad, vea [Operaciones transparentes de Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).

## <a name="related-topics"></a>Temas relacionados

- [Informes de actividad del Centro de administración de Microsoft 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
- [Preferencias del centro de mensajes](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)
- [Cómo comprobar el estado de las actualizaciones de Windows en el centro de administración](/windows/deployment/update/check-release-health)
