---
title: Cómo comprobar el estado del servicio de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: Vea el estado de mantenimiento de los servicios de Microsoft 365 antes de llamar al soporte técnico para ver si hay una interrupción del servicio activa.
ms.openlocfilehash: 3802ca01902d5b0d457d2a3d75b784d38f71bd42
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924689"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Cómo comprobar el estado del servicio de Microsoft 365

[![Etiqueta para informarle que el centro de administración está cambiando y puede encontrar más detalles en aka.ms/aboutM365preview.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

Puede ver el estado de los servicios microsoft, incluidos Office en la web, Yammer,  Microsoft Dynamics CRM y servicios en la nube de administración de dispositivos móviles, en la página Estado del servicio en el Centro de administración de [Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). Si experimenta algún problema con un servicio en la nube, antes de llamar al soporte técnico o de invertir tiempo intentando solucionarlo, puede comprobar el estado del servicio para determinar si se trata de un problema conocido que ya tenga una resolución en curso.

Si no puede iniciar sesión en el Centro [](https://status.office365.com) de administración, puede usar la página de estado del servicio para comprobar si hay problemas conocidos que le impidan iniciar sesión en el espacio empresarial.  También regístrate para seguirnos en [@MSFT365status](https://twitter.com/MSFT365Status) en Twitter para ver información sobre determinados eventos.

  
### <a name="how-to-check-service-health"></a>Cómo comprobar el estado del servicio

1. Vaya al Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) y inicie sesión con una cuenta de administrador.

    > [!NOTE]
    > Los usuarios que tienen asignado el rol de administrador de servicios o administrador global pueden ver el estado del servicio. Para que los administradores de Exchange, SharePoint y Skype Empresarial puedan ver el estado del servicio, también se les debe asignar el rol Administrador de servicios. Para obtener más información acerca de los roles que pueden ver el estado del servicio, vea [About admin roles](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#roles-available-in-the-microsoft-365-admin-center).
  
2. Si no usa el nuevo centro  de administración,  en la página Principal, seleccione el botón de alternancia Probar el nuevo centro de administración en la esquina superior derecha.

3. Para ver el estado del servicio, en el Centro de administración, vaya a Estado del servicio de mantenimiento o seleccione la tarjeta de estado del servicio  >  en el panel  **Inicio**. La tarjeta de panel indica si hay un problema de servicio activo y vínculos a la página de estado del **servicio** detallada.
  
4. En la **página Estado del** servicio, el estado de mantenimiento de cada servicio en la nube se muestra en un formato de tabla.

   ![View of current issues in service health](../media/service-health-all-services.png)

La **pestaña Todos los** servicios (vista predeterminada) muestra todos los servicios y su estado de mantenimiento actual. Un icono y la **columna Estado** indican el estado de cada servicio. 

Para filtrar la vista a los servicios que están experimentando actualmente un incidente, seleccione **la** pestaña Incidentes en la parte superior de la página. Al seleccionar la **pestaña** Asesores, solo se mostrarán los servicios que actualmente tienen un aviso publicado. 

La **pestaña** Historial muestra el historial de incidentes y avisos que se han resuelto.

Si tiene un problema con un servicio de Microsoft 365 y no  lo ve en la página Estado del servicio, díganoslo seleccionando Informar de un problema y completando el formulario corto. Veremos los datos e informes relacionados de otras organizaciones para ver qué tan extendido es el problema y si se originó con nuestro servicio. Si lo hizo, lo agregaremos como un nuevo  incidente o aviso en la página Estado del servicio, donde puede realizar un seguimiento de su resolución. Si no ve que aparezca en la lista en unos 30 minutos, considere la posibilidad de ponerse en contacto con el soporte técnico para resolver el problema.

Para personalizar la vista de los servicios que se muestran en el panel, seleccione Preferencias Vista personalizada y desactive las casillas de los servicios que desea filtrar fuera de la vista Panel de mantenimiento  >  del servicio. Asegúrese de que la casilla está activada para cada servicio que desee supervisar.    

Para registrarse para recibir notificaciones por correo electrónico de nuevos incidentes que afectan a su inquilino y a los cambios de estado de un incidente activo, seleccione Preferencias correo electrónico , haga clic en  >   **Enviarme** notificaciones de salud de servicio en correo electrónico y, a continuación, especifique:

- Hasta dos direcciones de correo electrónico.
- Si desea notificaciones para incidentes o avisos
- Los servicios para los que desea recibir notificaciones

> [!NOTE]
> Cada administrador puede tener sus preferencias establecidas y el límite anterior de dos direcciones de correo electrónico es por cuenta de administrador.

> [!TIP]
> También puedes usar la aplicación de administración de [Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=627216) en tu dispositivo móvil para ver el estado del servicio, que es una excelente manera de mantenerse al día con las notificaciones push. 
  
### <a name="view-details-of-posted-service-health"></a>Ver detalles del estado del servicio publicado

En la **vista Todos los** servicios, al seleccionar el estado del servicio, se abrirá una vista resumida de avisos o incidentes.
  
[![Captura de pantalla que muestra el aviso de servicio ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

En el resumen del aviso o del incidente, se proporciona la siguiente información:

- **Título:** un resumen del problema.
- **Servicio:** el nombre del servicio afectado.
- **ID:** identificador numérico del problema.
- **Estado:** cómo afecta este problema al servicio.
- **Hora de inicio:** hora en la que se inició el problema.
- **Last updated:** la última vez que se actualizó el mensaje de estado del servicio. Publicamos mensajes frecuentes para que sepa el progreso que estamos realizando en la aplicación de una solución.

Seleccione el título del problema para ver la página de detalles [](#history) del problema, que muestra más información sobre el problema, incluido el historial de todos los mensajes publicados mientras trabajamos en una solución.

![Una captura de pantalla que muestra los detalles del problema](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Detalles del estado del servicio de traducción

Como las explicaciones del estado del servicio se publican en tiempo real, no se traducen automáticamente a su idioma y los detalles de los eventos de servicio se muestran solo en inglés. Para traducir la explicación, siga estos pasos:
  
1. Vaya a [Traductor](https://www.bing.com/translator/).

2. En la página **Estado del servicio**, seleccione un incidente o un aviso. En **Mostrar detalles**, copie el texto sobre el problema.

3. En el traductor, pegue el texto y elija **Traducir**.

### <a name="definitions"></a>Definiciones

La mayoría de las veces, los servicios aparecerán en buen estado sin más información. Cuando un servicio experimenta un problema, este se identifica como aviso o incidente y se muestra el estado actual.
  
> [!TIP]
> Los eventos de mantenimiento planeados se muestran en el estado del servicio. Puede realizar un seguimiento de los eventos de mantenimiento planeados manteniéndose al día con el **Centro de mensajes**. Filtre por los mensajes de la categoría Planear el cambio para descubrir cuándo sucederá el cambio, el efecto que tendrá y cómo debe prepararse para afrontarlo. Consulta [Centro de mensajes en Microsoft 365](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093) para obtener más información.
  
### <a name="incidents-and-advisories"></a>Incidentes y avisos

| Icono | Descripción |
|:-----|:-----|
|![Information icon for advisory](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|Si se muestra un aviso en un servicio, significa que somos conscientes de que existe un problema que está afectando a algunos usuarios, pero el servicio todavía está disponible. En los avisos, suele haber una solución alternativa para el problema y es posible que este se produzca de forma intermitente o que esté limitado a unas consecuencias para el usuario y a un ámbito específicos.  <br/> |
|![Exclamation point icon for incident](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|Si, en un servicio, se muestra un incidente activo, significa que existe un problema crítico y que el servicio o una de las características principales del servicio no está disponible. Por ejemplo, es posible que los usuarios no puedan enviar ni recibir correo electrónico o que no puedan iniciar sesión. Los incidentes tendrán un impacto notable sobre los usuarios. Cuando haya un incidente en curso, ofreceremos actualizaciones en relación con la investigación, las acciones llevadas a cabo y la confirmación de la resolución en el panel Estado del servicio.  <br/> |

### <a name="status-definitions"></a>Definiciones de estado

| Estado | Definición |
|:-----|:-----|
|**Investigación** | Somos conscientes de que existe un problema potencial y estamos recopilando más información sobre lo que sucede y el ámbito de impacto. |
|**Degradación del servicio** | Hemos confirmado que existe un problema que puede afectar al uso de un servicio o una característica. Es posible que vea este estado si un servicio está funcionando más lento de lo normal, si hay interrupciones intermitentes o si una característica no funciona, por ejemplo. |
|**Interrupción del servicio** | Verá este estado si se determina que un problema afecta a posibilidad de los usuarios de obtener acceso al servicio. En este caso, el problema es importante y se puede reproducir de forma coherente. |
|**Restaurando el servicio** | Se ha identificado la causa del problema, sabemos qué acción correctiva debemos aplicar y estamos en proceso de restablecer el servicio a un estado correcto. |
|**Recuperación extendida** | Este estado indica que se están llevando a cabo acciones correctivas para restablecer el servicio para la mayoría de los usuarios, pero que llevará algún tiempo llegar a todos los sistemas afectados. También es posible que vea este estado en caso de que hayamos aplicado una solución temporal para reducir el impacto a la espera de aplicar una permanente. |
|**Investigación suspendida** | Si nuestra investigación detallada sobre un problema potencial resulta en una solicitud de información adicional por parte de los clientes para permitirnos investigar de forma más exhaustiva, verá este estado. Si necesitamos su ayuda, le haremos saber qué datos y registros necesitamos. |
|**Servicio restaurado** | Hemos confirmado que una acción correctiva ha resuelto el problema subyacente y el servicio se ha restaurado al estado correcto. Para averiguar qué ha fallado, vea los detalles del problema. |
|**Falso positivo** | Después de una investigación detallada, hemos confirmado que el servicio está en buen estado y funciona según lo diseñado. No se observó ningún impacto en el servicio ni la causa del incidente se originó fuera del servicio. |
|**Informe posterior al incidente publicado** | Hemos publicado un informe de incidentes posteriores para un problema específico que incluye información de causa raíz y los siguientes pasos para garantizar que un problema similar no vuelva a ocurrir. |

### <a name="history"></a>Historial

El estado del servicio le permite ver el estado de mantenimiento actual y ver el historial de los avisos e incidentes de servicio que han afectado a su inquilino en los últimos 30 días. Para ver el estado anterior de todos los servicios, seleccione **Ver historial** en la página de detalles del problema.
  
![Show link to health history](../media/service-health-view-history.png)
  
Se muestra una lista de todos los mensajes del estado del servicio publicados en el período de tiempo seleccionado, como se puede ver a continuación:
  
![View service health history](../media/service-health-history.png)
  
Expanda cualquier fila para ver más detalles sobre el problema.
  
Para obtener más información sobre nuestro compromiso con el tiempo de actividad, vea [Operaciones transparentes de Microsoft 365](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity).

## <a name="related-topics"></a>Temas relacionados

Informes de actividad en el Centro de administración de [Microsoft 365](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) 
 [Preferencias del centro de mensajes](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences11)