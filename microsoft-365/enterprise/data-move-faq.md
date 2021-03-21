---
title: Preguntas más frecuentes sobre el movimiento de datos
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: Encuentre respuestas a las preguntas más frecuentes (preguntas frecuentes) sobre cómo mover datos principales a una nueva ubicación geográfica del centro de datos de Office 365.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e66c9f29b47c3f1bc8d6e89ebf2f077eee9f4adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919133"
---
# <a name="data-move-general-faq"></a>Preguntas más frecuentes sobre el movimiento de datos

Estas son las respuestas a preguntas generales sobre cómo mover los datos principales de los clientes en reposo a una nueva ubicación geográfica del centro de datos.
  
## <a name="what-customers-are-eligible-to-request-a-move"></a>¿Qué clientes son aptos para solicitar un movimiento?
  
Los clientes comerciales existentes de Microsoft 365 que seleccionaron un país apto para el nuevo centro de datos geo podrán solicitar un movimiento. El programa solo existe para inquilinos con un código de país elegible asignado al inquilino de Microsoft 365 para migrar datos principales de clientes en reposo para cargas de trabajo elegibles a la ubicación geográfica del centro de datos de Microsoft 365 correspondiente. Consulte la página Cómo solicitar [el](request-your-data-move.md) movimiento de datos para confirmar la elegibilidad del país.   

## <a name="how-do-we-define-core-customer-data"></a>¿Cómo se definen los datos principales del cliente?
 
Datos principales del cliente es un término que hace referencia a un subconjunto de datos de clientes definido en los términos [Microsoft Online Services:](https://aka.ms/ost) 
- Contenido del buzón de Exchange Online (cuerpo del correo electrónico, entradas de calendario y el contenido de los datos adjuntos de correo electrónico)
- Contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio
- Archivos cargados en OneDrive para la Empresa 

## <a name="what-is-in-scope-for-teams-migration"></a>¿Qué hay en el ámbito de la migración de Teams?

Además de Exchange Online, SharePoint Online y OneDrive para la Empresa; Microsoft migrará los datos de Teams al centro de datos local. 
- Mensajes de chat de Teams, incluidos mensajes privados y mensajes de canal. 
- Imágenes de Teams usadas en chats. 

Los archivos de Teams se almacenan en SharePoint Online y los archivos de chat de Teams se almacenan en OneDrive para la Empresa. El correo de voz, el calendario y los contactos se almacenan en Exchange Online. En muchos casos, Exchange Online, SharePoint Online y OneDrive para la Empresa ya los usa el cliente en la ubicación geográfica del centro de datos local y también forman parte del programa de migración de Microsoft 365 para los países de clientes elegibles.

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a>¿En qué momento se completa la migración para que los datos principales del cliente de mi inquilino se almacenen en reposo en mi nueva ubicación geográfica?

Debido a las dependencias compartidas entre Exchange Online y SharePoint Online/OneDrive para la Empresa, cualquier migración no se puede considerar completada hasta que se migren ambos servicios. Exchange Online y SharePoint Online/OneDrive para la Empresa a menudo migran en momentos separados e independientes entre sí. Los administradores de inquilinos de clientes reciben confirmación en el Centro de mensajes cuando se completa cada migración de servicio y pueden ver la tarjeta de ubicación de datos en el Centro de administración en cualquier momento para confirmar los datos principales del cliente en la ubicación de reposo de cada servicio.

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a>¿Cómo se asegura de que mis datos de cliente están seguros durante el movimiento y de que no experimentaré tiempo de inactividad?
  
Los movimientos de datos son una operación de servicio back-end con un impacto mínimo para los usuarios finales. Las características que se pueden ver afectadas se enumeran en [During y after your data move](during-and-after-your-data-move.md). Nos adherimos al Microsoft Online Services de nivel de servicio [(SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) para la disponibilidad, por lo que no hay nada que los clientes necesiten preparar o supervisar durante el movimiento. 
  
Todos los servicios de Microsoft 365 ejecutan las mismas versiones en los centros de datos, por lo que puede tener la seguridad de una funcionalidad coherente. El servicio es totalmente compatible durante todo el proceso.
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a>¿Cuál es el impacto de tener diferentes servicios ubicados en diferentes geos?

Algunos de los servicios de Microsoft 365 pueden encontrarse en diferentes geos para algunos clientes existentes y para clientes que se encuentran en medio del proceso de movimiento. Nuestros servicios se ejecutan de forma independiente entre sí y no hay ningún impacto en la experiencia del usuario si este es el caso. Sin embargo, para fines de residencia de datos, una migración de inquilino no puede considerarse completa hasta que Exchange Online y SharePoint Online/OneDrive para la Empresa se migren a la misma ubicación geográfica del centro de datos.

 ## <a name="where-is-my-core-customer-data-located"></a>¿Dónde se encuentran mis datos principales de cliente?

Los administradores de inquilinos del cliente pueden ver la tarjeta de ubicación de datos en el Centro de administración en cualquier momento para confirmar los datos principales del cliente en la ubicación de reposo para cada servicio, específicamente para su inquilino.  También publicamos la ubicación de geos de centros de datos, centros de datos y ubicación de datos de clientes de Office 365 en los mapas del centro de datos interactivo de [Microsoft 365 ](https://office.com/datamaps) como referencia para los datos de cliente principales predeterminados actuales en ubicaciones de descanso para nuevos inquilinos. Puede comprobar la ubicación de los datos de los clientes en reposo a través de la sección Ubicación de datos de su perfil de organización en el Centro de administración de Microsoft 365.  
 
## <a name="when-will-i-be-able-to-request-a-move"></a>¿Cuándo podré solicitar un movimiento?
  
Consulte la página Cómo solicitar [el](request-your-data-move.md) movimiento de datos para los períodos de tiempo admitidos para la ubicación geográfica del centro de datos.
  
## <a name="how-can-i-request-to-be-moved"></a>¿Cómo puedo solicitar que se traslade?
  
Los clientes elegibles verán una página en su Centro de administración de [Microsoft 365](https://admin.microsoft.com/). Consulta Cómo [solicitar el movimiento de datos](request-your-data-move.md) para obtener instrucciones sobre cómo solicitar un movimiento. 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a>¿Puedo cambiar mi selección después de solicitar un movimiento?
  
No es posible que lo quitemos del proceso después de enviar la solicitud.
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a>¿Qué sucede si no solicito un movimiento antes de la fecha límite?
  
No podemos aceptar solicitudes de migración después del período de inscripción abierto.

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a>¿Qué sucede si deseo mover mis datos para obtener un mejor rendimiento de la red?
  
La proximidad física a un centro de datos de Microsoft 365 no es una garantía para un mejor rendimiento de red. Hay muchos factores y componentes que afectan al rendimiento de la red entre el usuario final y el servicio de Microsoft 365. Para obtener más información acerca de esto y la optimización del rendimiento, vea [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a>¿Todos los servicios mueven sus datos el mismo día?
 
Cada servicio se mueve de forma independiente y es probable que mueva sus datos en momentos diferentes.
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a>¿Puedo elegir cuándo deseo que se mueven mis datos?
 
Los clientes no pueden seleccionar una fecha específica, no pueden retrasar su movimiento y no podemos compartir una fecha o un período de tiempo específicos para los movimientos.
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a>¿Puede compartir cuándo se van a mover mis datos?
  
Los movimientos de datos son una operación back-end con un impacto mínimo para los usuarios finales. La complejidad, precisión y escala a la que debemos realizar movimientos de datos en un entorno automatizado y operado globalmente nos prohíben compartir cuando se espera que se complete un movimiento de datos para su inquilino o cualquier otro inquilino único. Los clientes recibirán una confirmación en el Centro de mensajes por servicio participante cuando se haya completado el movimiento de datos. 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a>¿Qué sucede si los usuarios acceden a los servicios mientras se mueven los datos?

Consulta [Durante y después del movimiento de datos](during-and-after-your-data-move.md) para obtener una lista completa de características que pueden estar limitadas durante partes del movimiento de datos para cada servicio. 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a>¿Cómo sé que se ha completado el movimiento?
  
Vea el Centro de mensajes de Microsoft 365 para confirmar que se ha completado el movimiento de los datos de cada servicio. Cuando se mueven los datos de cada servicio, publicaremos un aviso de finalización para que obtenga tres avisos de finalización: uno para Exchange Online, SharePoint Online y Skype Empresarial Online. También puede comprobar la ubicación de los datos de los clientes en reposo a través de la sección Ubicación de datos de su perfil de organización en el Centro de administración de Microsoft 365.  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a>Soy un cliente de Microsoft 365 en una de las nuevas geos del centro de datos, pero cuando me inscribo, seleccioné un país diferente. ¿Cómo se puede mover a la nueva ubicación geográfica del centro de datos?

No es posible cambiar el país de registro asociado con el inquilino. En su lugar, debe crear un nuevo inquilino de Microsoft 365 con una nueva suscripción y mover manualmente los usuarios y los datos al nuevo inquilino.
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a>¿Qué sucede si estamos en proceso de migración de datos de correo electrónico a Microsoft 365 durante el movimiento de Exchange Online?

Este es un escenario muy común y es totalmente compatible.  La migración en la nube entre las geos del centro de datos no interfiere con las migraciones de buzones de correo locales a la nube.
  
 ## <a name="can-i-pilot-some-users"></a>¿Puedo pilotar algunos usuarios?
  
Puede crear un inquilino de prueba independiente para probar la conectividad, pero el inquilino de prueba no se puede combinar de ninguna manera con el inquilino existente.

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a>No quiero esperar a que Microsoft mueva mis datos. ¿Puedo crear un nuevo inquilino y moverme yo mismo?
  
Sí, pero el proceso no será tan fluido como si Microsoft realizara el movimiento de datos.
  
Si crea un nuevo espacio empresarial después de que la nueva ubicación geográfica del centro de datos esté disponible, el nuevo inquilino se hospedará en la nueva ubicación geográfica. Este nuevo inquilino es completamente independiente del inquilino anterior y sería responsable de mover todos los buzones de usuario, el contenido del sitio, los nombres de dominio y cualquier otro dato. Tenga en cuenta que no puede mover el nombre del inquilino de un inquilino a otro. Te recomendamos que esperes al programa de movimiento proporcionado por Microsoft, ya que nos encargaremos de mover toda la configuración, los datos y las suscripciones de los usuarios.
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a>Los datos de mis clientes ya se han movido a una nueva ubicación geográfica del centro de datos. ¿Puedo volver?
 
No, esto no es posible. Los clientes que se han movido a nuevos centros de datos geográficos no se pueden mover hacia atrás. Como cliente en cualquier geo, experimentará la misma calidad de servicio, rendimiento y controles de seguridad que antes. [Microsoft 365 Multi Geo](https://aka.ms/multi-geo) está disponible para algunos clientes como complemento y permite a un único inquilino crear varias geos de satélite y mover datos de usuario a esas geos con compromisos de residencia de datos.
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a>¿Los inquilinos de Microsoft 365 hospedados en los nuevos centros de datos estarán disponibles para usuarios fuera del país?
  
Sí. Microsoft mantiene una gran red global con conexiones públicas a Internet en más de 130 ubicaciones en 35 países de todo el mundo con acuerdos de emparejamiento con más de 2.700 proveedores de servicios de Internet (ISP). Los usuarios podrán acceder a los centros de datos desde cualquier lugar en Internet.

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a>Mi inquilino ha configurado el [complemento Multi Geo](https://aka.ms/multi-geo). ¿Todavía puedo inscribirme en mi inquilino en el Programa de movimiento de Microsoft 365 para cambiar mi geo predeterminado y mover cualquier usuario que no se encuentra en una región satélite a la nueva geo predeterminada?

Sí, el inquilino es apto para inscribirse, pero hay consideraciones importantes, ya que el movimiento a nivel de inquilino no es totalmente compatible con los clientes que han configurado Multi-Geo.

SharePoint Online y OneDrive para la Empresa no pueden migrar a la nueva ubicación geográfica del centro de datos en el nivel de inquilino a través de este programa. El administrador del cliente puede configurar los recursos compartidos de OneDrive para la Empresa para que se muevan a cualquier región disponible mediante Multi-Geo, pero la ubicación predeterminada del inquilino no se puede cambiar una vez que se haya configurado Multi-Geo para un inquilino.

Para los clientes que optan por la migración: moveremos todos los buzones de Exchange Online de la ubicación geográfica predeterminada actual a la nueva ubicación geográfica del centro de datos local y actualizaremos la región predeterminada de Exchange Online. No moveremos ningún buzón EXO configurado en regiones satélite multigeósticas para seguir respetando la residencia de datos de región satélite como ha previsto. 

## <a name="related-topics"></a>Temas relacionados

[Mover datos principales a nuevas geometrías del centro de datos de Microsoft 365](moving-data-to-new-datacenter-geos.md)

[Cómo solicitar el movimiento de datos](request-your-data-move.md)

[Microsoft 365 Multi Geo](https://aka.ms/multi-geo)

[Mapa de centros de datos interactivos de Microsoft 365](https://office.com/datamaps)

[Soporte técnico de Microsoft 365](../admin/contact-support-for-business-products.md)

[Nuevas geos del centro de datos para Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Servicios de Azure por región](https://azure.microsoft.com/regions/)