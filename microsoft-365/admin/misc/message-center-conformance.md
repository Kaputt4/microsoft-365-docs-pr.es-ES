---
title: Metadatos de conformidad para las publicaciones del Centro de mensajes
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: Obtener información general sobre los metadatos de conformidad para las publicaciones del Centro de mensajes
ms.openlocfilehash: 1205c5429427741f6383fd48205730db1ccbfc98
ms.sourcegitcommit: 1f4c51d022d1cfb6c194bf0f0af9c2841c781d68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2022
ms.locfileid: "68573953"
---
# <a name="conformance-metadata-for-message-center-posts"></a>Metadatos de conformidad para las publicaciones del Centro de mensajes

> [!IMPORTANT]
> Este documento privado solo está destinado a los usuarios de metadatos de conformidad de Administración de cambios. No comparta este documento más allá de los que están directamente implicados en el piloto.

Al planear nuevas características o implementaciones de servicio, le gustaría comprender y evaluar los cambios para la conformidad con su sector, región y país. Hemos escuchado sus comentarios cuando no hay suficiente información de conformidad sobre una característica nueva o cambiante, tiene que realizar su propia investigación sobre la característica o ponerse en contacto con el Programa de cumplimiento con preguntas.  

En este programa piloto, queremos proporcionar de forma proactiva metadatos para las características y servicios nuevos y actualizados de Microsoft 365. Nuestro objetivo es ayudarle a evaluar de forma eficaz sus requisitos de cumplimiento y ayudarle con las decisiones de adopción y administración de cambios.  

Por ejemplo, si para una característica los metadatos tienen los siguientes valores, la decisión de adopción de características debe ser rápida.  

- ¿Se almacenan los datos del cliente? **No**

- ¿Cambiar al almacenamiento de datos del cliente? **No**

- ¿Cambios en el flujo de datos existente? **No**

- ¿La característica se integra con servicios de terceros? **No**

> [!NOTE]
> La lista anterior es ligeramente diferente de lo que vio anteriormente en las publicaciones de conformidad piloto. Hemos actualizado la lista en función de los comentarios que hemos recibido de los clientes piloto.

Para las características en las que los metadatos son diferentes de la lista anterior, la publicación del Centro de mensajes puede proporcionarle documentación.

## <a name="understanding-conformance-metadata"></a>Descripción de los metadatos de conformidad

|**Nombre de metadatos**|**Valores**|**Definición y preguntas formuladas**|**Ejemplo: Sí**|**Ejemplo: No**|
|---|---|---|---|
|**Los datos del cliente se almacenan**|Sí/No|¿Almacena o procesa este cambio los datos nuevos netos (clasificados como datos personales o de cliente) que no se almacenaron o procesaron previamente por el servicio o la versión anterior de esta característica?|Las grabaciones de reuniones de Teams capturan y recopilan datos de clientes y ahora se almacenan en .|La característica usuarios activos mensuales (MAU) del servicio de Message Center muestra los usuarios activos mensuales del servicio agregado para un identificador de inquilino que no se clasifica como datos personales o de cliente.|
|**Cambio al almacenamiento de datos del cliente**|Sí/No|¿Usa este cambio un servicio nuevo o diferente para almacenar datos?|Las grabaciones de reuniones de Teams capturan o recopilan datos o contenido del cliente y ahora se almacenan en .|Reacciones expandidas en Teams. Ampliación de las reacciones de mensajes en Teams a un conjunto más grande. Las reacciones más recientes que se almacenan son datos del cliente, pero no hay ningún cambio en la forma en que se almacenan o procesan los datos.|
|**Cambios en el flujo de datos existente**|Sí/No|¿Procesa esta característica datos a través de una canalización de procesamiento nueva o diferente? <br> O bien <br> ¿La característica solo amplía una canalización de procesamiento existente a datos más recientes o expone los datos ya expuestos en una superficie a otra? (**Respuesta = No**).|Cuando Bing for Business comenzó a usar texto de Word para enviar a Bing y, a continuación, devolver datos a Word, el flujo de datos cambió.|La puntuación de productividad que se usa en la página Conclusiones de experiencia del Centro de administración, los datos se muestran en una nueva superficie, pero el almacenamiento y el procesamiento son los mismos. <br> La respuesta sugerida en chats de grupo en el escritorio de Teams (una extensión de chats 1:1) no tiene datos nuevos en la red. Es una extensión de la canalización ya configurada para la respuesta sugerida en los chats 1:1.|
|**La característica se integra con servicios de terceros**|Sí/No|¿Usa esta característica un servicio o una aplicación net new (de primera persona o de terceros) que los datos de los clientes podrían almacenarse o procesarse fuera de Microsoft 365?|Bing for Business puede recibir contenido del cliente en forma de datos de "búsqueda" para presentar a un usuario información o contenido potencialmente relevante.|La característica usuarios activos mensuales (MAU) del Servicio del Centro de mensajes muestra los usuarios activos mensuales del servicio mediante el informe de uso Graph API que está dentro del límite de Microsoft 365.|
|

## <a name="join-the-pilot-program"></a>Unirse al programa piloto

Puede unirse completando este [cuestionario](https://go.microsoft.com/fwlink/p/?linkid=2211581).

Cuando se entrega una publicación del Centro de mensajes, recibirá una publicación adicional del Centro de mensajes que indica: **Información adicional de conformidad para MC#######**. Esta publicación contiene más metadatos de conformidad. Puede proporcionar comentarios directamente en la publicación adicional o puede enviar un correo electrónico a: MCSHDPMS@Microsoft.com. También puede enviar comentarios en el [canal de Teams](https://go.microsoft.com/fwlink/p/?linkid=2211676).

> [!NOTE]
> Comenzaremos con las características de Microsoft Teams, OneDrive para la Empresa y SharePoint Online.
