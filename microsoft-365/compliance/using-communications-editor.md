---
title: Usar el editor de comunicaciones
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use el Editor de comunicaciones para cambiar el texto y combinar variables de campo al dar formato al contenido.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769165"
---
# <a name="use-the-communications-editor"></a>Usar el editor de comunicaciones

Al definir el contenido del portal, las notificaciones de retención legal y los avisos o escalaciones relacionados, puede usar el Editor de comunicaciones para dar formato y personalizar dinámicamente el contenido.

## <a name="rich-text-editor"></a>Editor de texto enriquecido

El Editor de comunicaciones permite al usuario personalizar el texto mediante las opciones del editor. Por ejemplo, los usuarios pueden cambiar los tipos de fuente, crear listas con viñetas, resaltar contenido y mucho más.

## <a name="merge-field-variables"></a>Combinar variables de campo

Puede usar variables de combinación de correo electrónico desde el Editor de comunicaciones para insertar atributos de administrador personalizados en el texto del cuerpo de una comunicación. Cuando se envía al administrador, el campo de combinación se rellenará con el campo correspondiente. Por ejemplo, cuando se envía al administrador John Smith, el campo de combinación [Nombre de administrador] se traduciría con el nombre correspondiente.

Puede usar los campos de combinación de correo electrónico seleccionando los iconos **de** campo combinar en la parte superior del control del editor de texto enriquecido. El marcador de posición se agregará en función de la ubicación del cursor de los usuarios.

### <a name="list-of-merge-field-variables"></a>Lista de variables de campo de combinación

| Nombre del campo                  | Detalles del campo |
| :------------------- | :------------------- |
| Nombre para mostrar  | Nombre y apellidos del administrador. | 
| Vínculo de confirmación | Un vínculo personalizado para registrar el acuse de recibo de cada administrador.|                 |
| Vínculo del portal     | Un vínculo personalizado para el Portal de cumplimiento del administrador.|                |
| Oficial emisor                   | La dirección de correo electrónico del responsable emisor especificado.|                   |
| Fecha de emisión                   | La fecha en que se emitió el aviso (UTC).              |
|||
