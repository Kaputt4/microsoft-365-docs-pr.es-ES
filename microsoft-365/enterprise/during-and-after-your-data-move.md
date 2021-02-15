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
description: Los movimientos de datos son operaciones back-end que se producen cuando Microsoft mueve los servicios y los datos asociados de su espacio empresarial a una nueva ubicación geográfica del centro de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca3159aeb951fb0cb3bf3aba953979dabc6ba024
ms.sourcegitcommit: 1db81b85d327fe423695ce675ad325e538417211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349261"
---
# <a name="during-and-after-your-data-move"></a>Durante y después del movimiento de datos

Los movimientos de datos son una operación back-end con un impacto mínimo para los usuarios finales. No se requiere ninguna acción mientras Microsoft mueve cada servicio y los datos asociados de su espacio empresarial a una nueva ubicación geográfica del centro de datos. La transferencia y validación de datos se realiza en segundo plano con un impacto mínimo para los usuarios.
  
> [!NOTE]
> Los movimientos se producen en momentos diferentes para cada servicio. Como resultado, verá la funcionalidad reducida descrita para cada servicio en un momento diferente. 
  
Vea el Centro de mensajes de Microsoft 365 para obtener confirmación cuando se completen los movimientos de cada servicio de chat de Exchange Online, SharePoint Online y Teams. Como se muestra en la tabla siguiente, pueden tardar hasta 24 meses después del final del período de inscripción para completar los datos principales de los clientes en reposo que se trasladan a la nueva ubicación geográfica del centro de datos.   

|**Clientes con país de suscripción en**|**Todos los movimientos completados por**|
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

Dado que se necesita tiempo para mover cada usuario a la nueva ubicación geográfica del centro de datos para un único inquilino, algunos usuarios seguirán estando en la antigua ubicación geográfica del centro de datos durante el movimiento, mientras que otros estarán en la nueva ubicación geográfica del centro de datos. Esto significa que es posible que algunas características que implican el acceso a varios buzones no funcionen completamente durante un período del proceso de movimiento, que puede durar semanas. Estas características se describen en las secciones siguientes.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Abrir "Carpeta compartida" en Outlook Web Access

Algunos usuarios abren una carpeta de correo compartida desde otro buzón (para el que el usuario tiene permisos de lectura o escritura) en Outlook Web Access mediante la característica "Carpeta compartida". En la tabla siguiente se describe cómo funciona el acceso a carpetas compartidas durante un movimiento de buzón. Tenga en cuenta que los usuarios con permisos completos para un buzón compartido pueden abrir el buzón mediante Outlook Web Access durante el movimiento. 
  
|**Configuración**|**Descripción**|
|:-----|:-----|
|El usuario tiene permiso de carpeta de buzón para otro buzón  <br/> |Potencialmente limitada.  <br/> Si los usuarios A y B no están en la misma ubicación geográfica durante el movimiento del espacio empresarial, el usuario A no puede abrir la carpeta del buzón B en Outlook Web Access si el usuario A solo tiene permiso para una carpeta específica del buzón B.  <br/> Para agregar una carpeta compartida, haga clic con el botón secundario en el nombre de usuario en el panel de navegación izquierdo y seleccione **Agregar carpeta compartida.**  <br/> |
|Usuario con permiso de buzón completo para otro buzón  <br/> |Totalmente compatible.  <br/> Si el usuario A tiene el permiso "Acceso completo" al buzón B, el usuario A puede hacer clic en la carpeta compartida del panel de navegación izquierdo de Outlook Web Access para abrir una ventana que muestre el buzón B.  Un usuario puede abrir un buzón compartido con Outlook Web Access durante el movimiento sin ningún impacto negativo. La limitación solo se aplica al uso compartido de nivel de carpeta en un buzón.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Cuando se mueve SharePoint Online, también se mueven los datos de los siguientes servicios:
  
- OneDrive para la Empresa
    
- Servicios de vídeo de Microsoft 365
    
- Office en un explorador
    
- Aplicaciones de Microsoft 365 para empresas
    
- Visio Pro para Microsoft 365
    
Cuando hayamos terminado de mover los datos de SharePoint Online, es posible que vea algunos de los siguientes efectos.
  
### <a name="microsoft-365-video-services"></a>Servicios de vídeo de Microsoft 365

- El movimiento de datos para el vídeo tarda más que los movimientos para el resto del contenido en SharePoint Online.
    
- Después de mover el contenido de SharePoint Online, habrá un período de tiempo en el que no se podrán reproducir vídeos.
    
- Estamos quitando las copias transcodificación del centro de datos anterior y transcodificación de nuevo en el nuevo centro de datos.
    
### <a name="search"></a>Búsqueda

En el transcurso de mover los datos de SharePoint Online, migramos el índice de búsqueda y la configuración de búsqueda a una nueva ubicación. Hasta que hayamos **completado el** movimiento de los datos de SharePoint Online, seguiremos atienden a los usuarios desde el índice en la ubicación original. En la nueva ubicación, la búsqueda comienza automáticamente a rastrear el contenido una vez que hayamos terminado de mover los datos de SharePoint Online. A partir de este momento, atenderemos a los usuarios desde el índice migrado. Los cambios en el contenido que se produjeron después de la migración no se incluirán en el índice migrado hasta que el rastreo los resalte. La mayoría de los clientes no se da cuenta de que los resultados son menos nuevos justo después de que hayamos terminado de mover sus datos de SharePoint Online, pero algunos clientes podrían experimentar una actualización reducida en las primeras 24-48 horas 
  
Se ven afectadas las siguientes características de búsqueda:
  
- Resultados de la búsqueda elementos web búsqueda: los resultados no incluyen los cambios que se produjeron después de la migración hasta que el rastreo los resalte. 
    
- Delve: Delve no incluye los cambios que se produjeron después de la migración hasta que el rastreo los resalte.
    
- Popularidad e informes de búsqueda para el sitio: los recuentos de los informes de Excel en la nueva ubicación solo incluyen recuentos migrados y recuentos de informes de uso que se han ejecutado después de completar el traslado de los datos de SharePoint Online. Los recuentos del período provisional se pierden y no se pueden recuperar. Este período suele ser de un par de días. Algunos clientes pueden experimentar pérdidas más cortas o más largas.
    
- Portal de vídeo: ver recuentos y estadísticas del Portal de vídeo dependen de las estadísticas de Informes de Excel, por lo que los recuentos de vistas y las estadísticas del Portal de vídeo se pierden durante el mismo período de tiempo que para los informes de Excel.
    
- Exhibición de documentos electrónicos: los elementos que cambiaron durante la migración no se mostrarán hasta que el rastreo resalte los cambios.
    
- Protección de pérdida de datos (DLP): las directivas no se aplican a los elementos que cambian hasta que el rastreo retoma los cambios.

## <a name="microsoft-teams"></a>Microsoft Teams

Además de Exchange Online, SharePoint Online y OneDrive para la Empresa, Microsoft migrará los datos del servicio de chat de Teams al centro de datos local.

- Mensajes de chat de Teams, incluidos mensajes privados y mensajes de canal.
- Imágenes de Teams usadas en chats.

Los archivos de Teams se almacenan en SharePoint Online y los archivos de chat de Teams se almacenan en OneDrive para la Empresa. El correo de voz, el calendario, el historial de chat y los contactos se almacenan en Exchange Online. En muchos casos, Exchange Online, SharePoint Online y OneDrive para la Empresa ya los usa el cliente en la ubicación geográfica del centro de datos local y también forman parte del programa de migración de Microsoft 365 para los países de clientes elegibles.

## <a name="skype-for-business"></a>Skype Empresarial

Los movimientos de Skype Empresarial ya no están disponibles.  [Skype Empresarial Online se retirará el](https://docs.microsoft.com/lifecycle/announcements/skype-for-business-online-retirement) 31 de julio de 2021. Después de ese tiempo, el servicio ya no será accesible. 
  
## <a name="related-topics"></a>Temas relacionados 
 
[Cómo solicitar el movimiento de datos](request-your-data-move.md)
    
[Preguntas más frecuentes sobre el movimiento de datos](data-move-faq.md)
  
[Nuevas ubicaciones geográficas de centro de datos Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Servicios de Azure por región](https://azure.microsoft.com/regions/)
