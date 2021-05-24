---
title: Durante y después del movimiento de datos
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: Los movimientos de datos son operaciones back-end que se producen cuando Microsoft mueve los servicios y los datos asociados del inquilino a un nuevo centro de datos geográfico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d3d44ffc1650989e5c39f5f79cb6a07065f9e9f1
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625262"
---
# <a name="during-and-after-your-data-move"></a>Durante y después del movimiento de datos

Los movimientos de datos son una operación back-end con un impacto mínimo para los usuarios finales. No se requiere ninguna acción mientras Microsoft mueve cada servicio y los datos asociados del inquilino a un nuevo centro de datos geográfico. La transferencia y validación de datos se producen en segundo plano con un impacto mínimo para los usuarios.
  
> [!NOTE]
> Los movimientos se producen en momentos diferentes para cada servicio. Como resultado, verá la funcionalidad reducida descrita para cada servicio en un momento diferente. 
  
Vea el Centro Microsoft 365 mensajes para obtener confirmación cuando se mueva para cada Exchange Online, SharePoint Online y Teams servicio de chat completo. Como se muestra en la tabla siguiente, puede tardar hasta 24 meses después del final del período de inscripción para completar los datos principales del cliente en reposo se mueve al nuevo centro de datos geográfico.   

|**Clientes con país de registro en**|**Todos los movimientos completados por**|
|:-----|:-----|
|Australia, Nueva Zelanda, Fiyi  <br/> |1 de julio de 2022  <br/> |
|Japón  <br/> |1 de julio de 2022  <br/> |
|India  <br/> |1 de julio de 2022  <br/> |
|Canadá  <br/> |1 de julio de 2022  <br/> |
|Corea del Sur  <br/> |1 de julio de 2022  <br/> |
|Reino Unido  <br/> |1 de julio de 2022  <br/> |
|Francia  <br/> |1 de julio de 2022  <br/> |
|Emiratos Árabes Unidos  <br/> |1 de julio de 2022  <br/> |
|Sudáfrica  <br/> |1 de julio de 2022  <br/> |
|Suiza, Liechtenstein  <br/> |1 de julio de 2022  <br/> |
|Noruega  <br/> |1 de noviembre de 2022  <br/> |
|Alemania  <br/> |1 de mayo de 2023  <br/> |
|Brasil  <br/> |1 de junio de 2023  <br/> |

## <a name="exchange-online"></a>Exchange Online

Dado que se tarda tiempo en mover cada usuario a la nueva ubicación geográfica del centro de datos para un único inquilino, algunos usuarios seguirán estando en la antigua ubicación geográfica del centro de datos durante el movimiento, mientras que otros estarán en la nueva ubicación geográfica del centro de datos. Esto significa que es posible que algunas características que implican el acceso a varios buzones no funcionen completamente durante un período del proceso de movimiento, que puede durar semanas. Estas características se describen en las secciones siguientes.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Abra "Carpeta compartida" en Outlook Web Access

Algunos usuarios abren una carpeta de correo compartida desde otro buzón (en el que el usuario tiene permisos de lectura o escritura) en Outlook Web Access mediante la característica "Carpeta compartida". En la tabla siguiente se describe cómo funciona el acceso a carpetas compartidas durante un movimiento de buzón. Tenga en cuenta que los usuarios con permisos completos para un buzón compartido pueden abrir el buzón mediante Outlook Web Access durante el movimiento. 
  
|**Configuración**|**Descripción**|
|:-----|:-----|
|El usuario tiene permiso de carpeta de buzón de correo para otro buzón  <br/> |Potencialmente limitado.  <br/> Si el usuario A y el buzón B no están en la misma ubicación geográfica durante el movimiento del inquilino, el usuario A no puede abrir la carpeta del buzón B en Outlook Web Access si el usuario A solo tiene permiso para una carpeta específica en el buzón B.  <br/> Para agregar una carpeta compartida, haga clic con el botón secundario en el nombre de usuario del panel de navegación izquierdo y seleccione **Agregar carpeta compartida.**  <br/> |
|Usuario con permiso de buzón completo para otro buzón  <br/> |Totalmente compatible.  <br/> Si el usuario A tiene permiso de "Acceso total" al buzón B, el usuario A puede hacer clic en la carpeta compartida en el panel de navegación izquierdo de Outlook Web Access para abrir una ventana que muestre el buzón B.  Un usuario puede abrir un buzón compartido mediante Outlook Web Access durante el movimiento sin ningún impacto adverso. La limitación solo se aplica al uso compartido de nivel de carpeta en un buzón.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Cuando SharePoint Online se mueve, también se mueven los datos de los siguientes servicios:
  
- OneDrive para la Empresa
    
- Microsoft 365 Servicios de vídeo
    
- Office en un explorador
    
- Aplicaciones de Microsoft 365 para empresas
    
- Visio Pro para Microsoft 365
    
Una vez que hayamos completado el movimiento de SharePoint datos en línea, es posible que veas algunos de los siguientes efectos.
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 Servicios de vídeo

- El movimiento de datos del vídeo tarda más tiempo que los movimientos del resto del contenido en SharePoint Online.
    
- Después de SharePoint se mueve el contenido en línea, habrá un período de tiempo en el que los vídeos no se puedan reproducir.
    
- Estamos quitando las copias transcodadas del centro de datos anterior y transcodándolos de nuevo en el nuevo centro de datos.
    
### <a name="search"></a>Búsqueda

En el transcurso de mover los datos SharePoint online, migramos el índice de búsqueda y la configuración de búsqueda a una nueva ubicación. Hasta que hayamos **completado el** movimiento de los datos de SharePoint Online, seguiremos atienden a los usuarios desde el índice en la ubicación original. En la nueva ubicación, la búsqueda comienza automáticamente a rastrear el contenido después de que hayamos completado el movimiento de los SharePoint datos en línea. A partir de este momento, se atiende a los usuarios desde el índice migrado. Los cambios en el contenido que se produjeron después de la migración no se incluyen en el índice migrado hasta que el rastreo los recoge. La mayoría de los clientes no se dan cuenta de que los resultados son menos frescos justo después de que hayamos terminado de mover sus datos de SharePoint Online, pero algunos clientes podrían experimentar una actualización reducida en las primeras 24-48 horas 
  
Las siguientes características de búsqueda se ven afectadas:
  
- Resultados de búsqueda y búsqueda elementos web: los resultados no incluyen los cambios que se produjeron después de la migración hasta que el rastreo los recoge. 
    
- Delve: Delve no incluye los cambios que se produjeron después de la migración hasta que el rastreo los retoma.
    
- Informes de popularidad e búsqueda para el sitio: los recuentos de informes de Excel en la nueva ubicación solo incluyen recuentos migrados y recuentos de informes de uso que se han ejecutado después de completar el movimiento de los datos de SharePoint Online. Los recuentos del período provisional se pierden y no se pueden recuperar. Este período suele ser de un par de días. Algunos clientes pueden experimentar pérdidas más cortas o más largas.
    
- Portal de vídeo: los recuentos de vistas y las estadísticas del Portal de vídeo dependen de las estadísticas de los informes de Excel, por lo que los recuentos de vistas y las estadísticas del Portal de vídeo se pierden durante el mismo período de tiempo que para los Excel informes.
    
- eDiscovery: los elementos que cambiaron durante la migración no se muestran hasta que el rastreo recoge los cambios.
    
- Protección contra pérdida de datos (DLP): las directivas no se aplican a los elementos que cambian hasta que el rastreo recoge los cambios.

Como parte de la migración, la región predeterminada cambiará y todo el contenido nuevo se almacenará en reposo en la nueva región predeterminada. El contenido existente se moverá en segundo plano sin ningún impacto hasta 90 días después del primer cambio en la ubicación de datos de SharePoint Online en el Centro de administración.

## <a name="microsoft-teams"></a>Microsoft Teams

Además de Exchange Online, SharePoint Online y OneDrive para la Empresa, Microsoft migrará los Teams del servicio de chat al centro de datos local.

- Teams chat, incluidos los mensajes privados y los mensajes de canal.
- Teams imágenes usadas en chats.

Teams archivos se almacenan en SharePoint Online y Teams archivos de chat se almacenan en OneDrive para la Empresa. El correo de voz, el calendario, el historial de chat y los contactos se almacenan en Exchange Online. En muchos casos, Exchange Online, SharePoint Online y OneDrive para la Empresa ya los usa el cliente en la ubicación geográfica del centro de datos local y también forman parte del programa de migración de Microsoft 365 para los países de clientes elegibles.

## <a name="skype-for-business"></a>Skype Empresarial

Skype Empresarial los movimientos ya no están disponibles.  [Skype Empresarial Online se retirará el](/lifecycle/announcements/skype-for-business-online-retirement) 31 de julio de 2021. Después de ese tiempo, el servicio ya no será accesible. 
  
## <a name="related-topics"></a>Temas relacionados 
 
[Cómo solicitar el movimiento de datos](request-your-data-move.md)
    
[Preguntas más frecuentes sobre el movimiento de datos](data-move-faq.md)
  
[Nuevas geos del centro de datos para Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Servicios de Azure por región](https://azure.microsoft.com/regions/)
