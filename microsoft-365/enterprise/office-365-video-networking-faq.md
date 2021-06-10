---
title: Office 365 Preguntas más frecuentes sobre redes de vídeo
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: Encuentre respuestas a algunas de las preguntas más frecuentes sobre la planeación del ancho de banda, el cifrado & cómo el servicio aprovecha las redes de entrega de contenido (CDN).
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921575"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Office 365 Preguntas más frecuentes sobre redes de vídeo

El Office 365 de vídeo y los servicios de streaming hacen que el almacenamiento y la transmisión de vídeos dentro de la organización sea sencillo. Hay una gran cantidad de información [sobre Office 365 Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50); Estas preguntas frecuentes sobre redes están [diseñadas](content-delivery-networks.md) para responder a las preguntas más comunes sobre la planeación del ancho de banda, el cifrado y cómo el servicio aprovecha las redes de entrega de contenido (CDN).
  
Si aún no tiene una comprensión exhaustiva de lo que sucede cuando se carga o reproduce un vídeo, vea este vídeo que hemos reunido, Qué sucede con un archivo de vídeo cuando se carga en [Office 365 Vídeo](https://www.youtube.com/watch?v=HXSZ0jYBKlM).
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>¿Cuáles son los Office 365 de ancho de banda de vídeo?

Hay varios [formatos de vídeo compatibles](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) que se pueden cargar en Office 365. A continuación, cada archivo de vídeo se codifica en un formato estándar con varias calidades de vídeo diferentes para la reproducción. Office 365 El vídeo usa streaming de velocidad de bits adaptable para seleccionar la mejor calidad de reproducción de vídeo según el ancho de banda de red disponible y el tamaño del reproductor de vídeo. Para ello, el jugador solicita inicialmente la calidad de reproducción más baja. A continuación, el servicio comienza a enviar segmentos de vídeo de 2 segundos al reproductor de vídeo. A continuación, el jugador puede solicitar una calidad de reproducción mayor o inferior en función de la rapidez con la que se entregue cada segmento.
  
El streaming de velocidad de bits adaptable hace todo esto en segundo plano mientras el vídeo se reproduce con la menor cantidad de interrupciones o almacenamiento en búfer. Durante la reproducción de vídeo, el reproductor de vídeo permite al visor invalidar manualmente la calidad de reproducción automática, para seleccionar una calidad de reproducción de vídeo específica.
  
Esta es una tabla rápida que describe los requisitos de red para cada una de las calidades de reproducción de vídeo. El ancho de banda mínimo por persona necesario para reproducir un vídeo es de 802 Kbps.
  
| Calidad de reproducción | Velocidad de red |
|:-----|:-----|
|288p  <br/> |802 Kbps  <br/> |
|360p  <br/> |1,2 Mbps  <br/> |
|576p  <br/> |2,5 Mbps  <br/> |
|720p  <br/> |3,8 Mbps  <br/> |

([Volver a la parte superior](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>¿Cómo ayudan las redes de entrega de contenido (CDN) a la reproducción de vídeo?

Si varias personas de la misma organización dentro de la misma ubicación geográfica están transmitiendo los mismos vídeos, las CDN almacenarán una copia de estos vídeos en una ubicación más cercana a esa región geográfica. Con el vídeo almacenado o almacenado en caché en la ubicación más cercana, cada persona transmite el vídeo desde la ubicación más cercana a ellos en lugar de una ubicación más alejada. Office 365 El vídeo usa Azure Media Services para administrar lo que se almacena en caché en las CDN de Azure y durante cuánto tiempo. Azure Media Services puede usar cualquiera de las Azure CDN [para](/azure/cdn/cdn-pop-locations) almacenar en caché fragmentos de vídeo y manifiestos durante unos días. Si los usuarios de la organización siguen observando los vídeos almacenados en caché, permanecerán en la memoria caché. Si nadie accede al vídeo durante varios días, el vídeo finalmente se retirará de la memoria caché. La próxima vez que alguien intente ver el vídeo, vuelve a almacenarse en caché en la ubicación CDN ubicación.
  
Todos los usuarios que intenten ver el vídeo mientras el contenido se almacena en caché en un CDN cercano se benefician de que el vídeo esté más cerca y, en la mayoría de los casos, menos saltos. Esto mejora la velocidad de reproducción de vídeo; sin embargo, no cambia el requisito de red para reproducir el vídeo.
  
> [!NOTE]
> Hay algunas circunstancias, como el límite de capacidad que se alcanza, donde el vídeo puede quitarse antes de que se alcancen los tres días.
  
([Volver a la parte superior](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>¿Puedo almacenar en caché los vídeos localmente para una reproducción más rápida?

Sí. Office 365 impedirá el uso de un CDN local o un proxy de almacenamiento en caché para traer vídeo u otro contenido Office 365 a la red local para un acceso más rápido. Hay varias maneras de implementar una solución de almacenamiento en caché local en la red, el método más común es usar una solución de proxy que almacena en caché el contenido localmente. Una vez que un proxy o un CDN privado haya almacenado en caché los fragmentos y manifiestos de vídeo, las solicitudes futuras para los archivos que se enrutar a través del proxy o el CDN privado se extraye de la memoria caché local y no se extrayó de una ubicación de Internet. Tenga en cuenta el ancho de banda de red, la capacidad y la simultaneidad de reproducción de vídeo durante la planeación de una solución como esta.
  
([Volver a la parte superior](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>¿Cómo se cifran y protegen los vídeos?

Office 365 El vídeo sabe lo importante que es mantener los datos seguros y privados. [El Centro de confianza](https://products.office.com/business/office-365-trust-center-welcome) de Microsoft describe nuestro compromiso con la privacidad y la seguridad de su contenido. Con la reproducción de vídeo, la velocidad es importante para una buena experiencia; sin embargo, no comprometemos su seguridad o privacidad a cambio de velocidad. Así es como adaptamos la velocidad, la seguridad y la privacidad.
  
Cuando usted o alguien de su organización carga un vídeo nuevo, ese vídeo se transcodifica, se cifra con cifrado AES-128 y se almacena en Azure Media Services. Esto significa que los vídeos se cifran tanto en tránsito como en reposo.
  
Cuando alguien de la organización intenta ver un vídeo nuevo, sigue estos pasos:
  
1. Pregunta SharePoint Online si tienen permiso para ver el vídeo.

2. SharePoint Online usa los permisos de archivo para determinar si la persona puede ver el vídeo.

3. Si se les permite, SharePoint Online recupera un token de Azure para entregarlo al reproductor de vídeo.

4. A continuación, el reproductor de vídeo usa el token para solicitar la clave de descifrado de Azure.

5. Con la clave de descifrado en la mano, el reproductor de vídeo puede transmitir el vídeo.

![Reproducción de vídeo de O365](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Volver a la parte superior](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>¿Cuáles son los requisitos para reproducir Office 365 Vídeo?

Office 365 Los sistemas operativos compatibles con vídeo y los exploradores web son los mismos que los requisitos de SharePoint online en [Office 365 del sistema.](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45) Según la configuración del sistema operativo y del explorador web que tenga, se determinarán las necesidades específicas del reproductor de vídeo. Aquí encontrará más información sobre los requisitos [de reproducción de vídeo.](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
([Volver a la parte superior](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>No puedo hacer que Office 365 vídeo funcione, ¿dónde debo empezar?

La solución de problemas de conectividad Office 365 Vídeo implica solucionar problemas de la red, los ISP y la configuración de Office 365. El primer lugar para empezar es el panel de estado del servicio. Esto le mostrará si Office 365 vídeo tiene un problema o no. Si todo se ve bien allí, estos son algunos recursos adicionales que le ayudarán.
  
- Asegúrese de que puede conectarse a los puntos [de conexión de red necesarios para Office 365 Vídeo](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).

- Compruebe la conectividad de red con nuestra Office 365 de solución de problemas [de red.](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)

- Consulte nuestros [procedimientos recomendados](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)para usar Office 365 en una red lenta .

- [Encuentre ayuda sobre Office 365 configuración de vídeo](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).

([Volver a la parte superior](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Office 365 Recursos de vídeo

Estos son algunos otros recursos que le ayudarán a implementar y usar correctamente Office 365 vídeo:
  
[Buscar ayuda sobre la configuración Office 365 vídeo](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Meet Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) (Conozca Office 365 Video)
  
[Crear y administrar un canal en Office 365 Vídeo](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Manage your Office 365 Video portal](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da) (Administrar el portal de Office 365 Video)
  
[Formatos de vídeo que funcionan en Office 365 Vídeo](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Volver a la parte superior](office-365-video-networking-faq.md))
  
Este es un vínculo breve que se puede usar para volver: [https://aka.ms/video365networkfaq]()