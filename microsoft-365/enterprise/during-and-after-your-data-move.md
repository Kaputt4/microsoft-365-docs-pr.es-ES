---
title: Durante y después del movimiento de datos
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/02/2022
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- scotvorg
- SPO_Content
search.appverid:
- MET150
ms.localizationpriority: medium
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: Los movimientos de datos son operaciones de back-end que se producen cuando Microsoft mueve los servicios y los datos asociados del inquilino a una nueva ubicación geográfica del centro de datos.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX
ms.openlocfilehash: 436e8f52940dd4ab036b0356da9c10b4785bd467
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807659"
---
# <a name="during-and-after-your-data-move"></a>Durante y después del movimiento de datos

Los movimientos de datos son una operación de back-end con un impacto mínimo para los usuarios finales. No se requiere ninguna acción mientras Microsoft mueve cada servicio y datos asociados del inquilino a una nueva ubicación geográfica del centro de datos. La transferencia y validación de datos se producen en segundo plano de antemano con un impacto mínimo para los usuarios.
  
> [!NOTE]
> Los movimientos se producen en momentos diferentes para cada servicio. Como resultado, verá la funcionalidad reducida descrita para cada servicio en un momento diferente.
  
Vea el Centro de mensajes de Microsoft 365 para obtener confirmación cuando se completen los movimientos de cada Exchange Online, SharePoint Online y el servicio de chat de Teams. Como se muestra en la tabla siguiente, puede tardar hasta 24 meses después del final del período de inscripción en completar los datos básicos del cliente en reposo que se mueven a la nueva ubicación geográfica del centro de datos.

| Clientes con país de registro en | Todos los movimientos completados por |
|:-----|:-----|
|Australia, Nueva Zelanda, Fiji  <br/> |viernes, 1 de julio de 2022  <br/> |
|Japón  <br/> |viernes, 1 de julio de 2022  <br/> |
|India  <br/> |viernes, 1 de julio de 2022  <br/> |
|Canada  <br/> |viernes, 1 de julio de 2022  <br/> |
|Corea del Sur  <br/> |viernes, 1 de julio de 2022  <br/> |
|Reino Unido  <br/> |viernes, 1 de julio de 2022  <br/> |
|Francia  <br/> |viernes, 1 de julio de 2022  <br/> |
|Emiratos Árabes Unidos  <br/> |viernes, 1 de julio de 2022  <br/> |
|Sudáfrica  <br/> |viernes, 1 de julio de 2022  <br/> |
|Suiza, Liechtenstein  <br/> |viernes, 1 de julio de 2022  <br/> |
|Noruega  <br/> |1 de noviembre de 2022  <br/> |
|Alemania  <br/> |1 de mayo de 2023  <br/> |
|Brasil  <br/> |jueves, 1 de junio de 2023  <br/> |
|Suecia  <br/> |1 de junio de 2024  <br/> |
|Qatar  <br/> |1 de marzo de 2025  <br/> |

## <a name="exchange-online"></a>Exchange Online

Dado que se tarda tiempo en mover cada usuario a la nueva ubicación geográfica del centro de datos para un único inquilino, algunos usuarios seguirán estando en la ubicación geográfica del centro de datos anterior durante el traslado, mientras que otros estarán en la nueva ubicación geográfica del centro de datos. Esto significa que es posible que algunas características que implican el acceso a varios buzones no funcionen por completo durante un período del proceso de traslado, que puede durar semanas. Estas características se describen en las secciones siguientes.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Abrir "Carpeta compartida" en Outlook Web Access

Algunos usuarios abren una carpeta de correo compartido desde otro buzón (en el que el usuario tiene permisos de lectura o escritura) en Outlook Web Access mediante la característica "Carpeta compartida". En la tabla siguiente se describe cómo funciona el acceso a carpetas compartidas durante el traslado de un buzón. Tenga en cuenta que los usuarios con permisos completos para un buzón compartido pueden abrir el buzón mediante Outlook Web Access durante el traslado.
  
| Configuración | Descripción |
|:-----|:-----|
|El usuario tiene permiso de carpeta de buzón para otro buzón  <br/> |Potencialmente limitado.  <br/> Si el usuario A y el buzón B no están en la misma ubicación geográfica durante el traslado del inquilino, el usuario A no puede abrir la carpeta del buzón B en Outlook Web Access si el usuario A solo tiene permiso para una carpeta específica en el buzón B.  <br/> Para agregar una carpeta compartida, haga clic con el botón derecho en el nombre de usuario en el panel de navegación izquierdo y seleccione **Agregar carpeta compartida**.  <br/> |
|Usuario con permiso de buzón completo para otro buzón  <br/> |Totalmente compatible.  <br/> Si el usuario A tiene permiso de "acceso completo" al buzón B, el usuario A puede hacer clic en la carpeta compartida en el panel de navegación izquierdo de Outlook Web Access para abrir una ventana que muestre el buzón B.  Un usuario puede abrir un buzón compartido con Outlook Web Access durante el traslado sin ningún impacto adverso. La limitación solo se aplica al uso compartido de nivel de carpeta en un buzón de correo.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Cuando se mueve SharePoint Online, también se mueven los datos de los siguientes servicios:
  
- OneDrive para la Empresa

- Servicios de vídeo de Microsoft 365

- Office en un explorador

- Microsoft 365 Apps para empresas

- Visio Pro para Microsoft 365

Una vez completado el movimiento de los datos de SharePoint Online, es posible que vea algunos de los siguientes efectos.
  
### <a name="microsoft-365-video-services"></a>Servicios de vídeo de Microsoft 365

- El movimiento de datos del vídeo tarda más que los movimientos del resto del contenido en SharePoint Online.

- Después de mover el contenido de SharePoint Online, habrá un período de tiempo en el que los vídeos no se puedan reproducir.

- Vamos a quitar las copias codificadas trans del centro de datos anterior y a transcodificarlas de nuevo en el nuevo centro de datos.

### <a name="search"></a>Búsqueda

En el curso de mover los datos de SharePoint Online, migramos el índice de búsqueda y la configuración de búsqueda a una nueva ubicación. Hasta que hayamos **completado** el traslado de los datos de SharePoint Online, seguiremos atendiendo a los usuarios desde el índice en la ubicación original. En la nueva ubicación, la búsqueda comienza automáticamente a rastrear el contenido después de haber completado el movimiento de los datos de SharePoint Online. A partir de este punto y en adelante, atenderemos a los usuarios desde el índice migrado. Los cambios en el contenido que se produjeron después de la migración no se incluyen en el índice migrado hasta que el rastreo los recoge. La mayoría de los clientes no se da cuenta de que los resultados son menos frescos justo después de haber completado el traslado de sus datos de SharePoint Online, pero algunos clientes podrían experimentar una actualización reducida en las primeras 24-48 horas.
  
Las siguientes características de búsqueda se ven afectadas:
  
- Resultados de búsqueda y elementos web de búsqueda: los resultados no incluyen los cambios que se produjeron después de la migración hasta que el rastreo los recoge. 

- Delve: Delve no incluye los cambios que se produjeron después de la migración hasta que el rastreo los recoge.

- Informes de popularidad y búsqueda para el sitio: los recuentos de informes de Excel en la nueva ubicación solo incluyen recuentos y recuentos migrados de informes de uso que se han ejecutado después de haber completado el movimiento de los datos de SharePoint Online. Los recuentos del período provisional se pierden y no se pueden recuperar. Este período suele ser de un par de días. Algunos clientes pueden experimentar pérdidas más cortas o más largas.

- Portal de vídeo: los recuentos de vistas y las estadísticas del Portal de vídeo dependen de las estadísticas de los informes de Excel, por lo que los recuentos de vistas y las estadísticas de Video Portal se pierden durante el mismo período de tiempo que para los informes de Excel.

- eDiscovery: los elementos que cambiaron durante la migración no se muestran hasta que el rastreo recoge los cambios.

- Protección contra pérdida de datos (DLP): las directivas no se aplican en los elementos que cambian hasta que el rastreo recoge los cambios.

Como parte de la migración, la región predeterminada cambiará y todo el contenido nuevo se almacenará en reposo en la nueva región predeterminada. El contenido existente se moverá en segundo plano sin ningún impacto durante un máximo de 90 días después del primer cambio en la ubicación de datos de SharePoint Online en el centro de administración.

## <a name="microsoft-teams"></a>Microsoft Teams

### <a name="files-tab"></a>Pestaña Archivo

Una vez completada la migración, la pestaña Archivos puede tardar más tiempo (hasta 7 segundos) en cargarse completamente cuando el usuario intenta usarla por primera vez. 

### <a name="read-only-period"></a>Período de solo lectura

Los servicios de chat de Teams mueven cada subproceso individualmente.  El subproceso está bloqueado en un estado de solo lectura durante el movimiento, que dura unos segundos por subproceso.  Los subprocesos siguen siendo accesibles durante la migración.

## <a name="skype-for-business"></a>Skype Empresarial

Skype Empresarial movimientos ya no están disponibles.  [Skype Empresarial Online se retirará](/lifecycle/announcements/skype-for-business-online-retirement) el 31 de julio de 2021. Después de ese momento, ya no se podrá acceder al servicio.
  
## <a name="related-topics"></a>Temas relacionados

[Cómo solicitar el movimiento de datos](request-your-data-move.md)

[Preguntas más frecuentes sobre el movimiento de datos](data-move-faq.md)
  
[Nuevas zonas geográficas del centro de datos para Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Servicios de Azure por región](https://azure.microsoft.com/regions/)
