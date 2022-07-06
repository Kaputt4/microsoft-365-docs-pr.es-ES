---
title: Usar el editor de comunicaciones
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el Editor de comunicaciones para cambiar el texto y combinar variables de campo al aplicar formato al contenido.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 910d25b80775284b8b12d803e722579d987558cd
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66636973"
---
# <a name="use-the-communications-editor"></a>Usar el editor de comunicaciones

A medida que defina el contenido del portal, las notificaciones de suspensión legal y los avisos o escalaciones relacionados, puede usar el Editor de comunicaciones para dar formato y personalizar dinámicamente el contenido.

## <a name="rich-text-editor"></a>Editor de texto enriquecido

El Editor de comunicaciones permite al usuario personalizar el texto mediante las opciones del editor. Por ejemplo, los usuarios pueden cambiar los tipos de fuente, crear listas con viñetas, resaltar contenido y mucho más.

## <a name="merge-field-variables"></a>Combinar variables de campo

Puede usar variables de combinación de correo electrónico desde el Editor de comunicaciones para insertar atributos de custodio personalizados en el texto del cuerpo de una comunicación. Cuando se envía al custodio, el campo de combinación se rellenará con el campo correspondiente. Por ejemplo, cuando se envía al custodio John Smith, el campo de combinación [Nombre del custodio] se traduciría con el nombre correspondiente.

Para usar los campos de combinación de correo electrónico, seleccione los iconos **De combinar campos** en la parte superior del control del editor de texto enriquecido. El marcador de posición se agregará en función de la ubicación del cursor de los usuarios.

### <a name="list-of-merge-field-variables"></a>Lista de variables de campo de combinación

<br>

****

|Nombre del campo|Detalles del campo|
|---|---|
|Nombre para mostrar|El nombre y apellidos del custodio.|
|Vínculo de confirmación|Un vínculo personalizado para registrar la confirmación de cada custodio.|
|Vínculo del portal|Un vínculo personalizado para el portal de cumplimiento del custodio.|
|Oficial emisor|Dirección de correo electrónico del emisor especificado.|
|Fecha de emisión|Fecha en que se emitió el aviso (UTC).|
|
