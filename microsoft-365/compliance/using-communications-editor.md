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
description: Use el editor de comunicaciones para cambiar el texto y combinar variables de campo al dar formato al contenido.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0cb415da9aa09452176bd8aa9be4575cfc827582
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034482"
---
# <a name="use-the-communications-editor"></a>Usar el editor de comunicaciones

Al definir el contenido del contenido del portal, las notificaciones de retención legal y los avisos/escalas relacionados, puede aprovechar el editor de comunicaciones para formatear y personalizar el contenido de forma dinámica.

## <a name="rich-text-editor"></a>Editor de texto enriquecido 

El editor de comunicaciones permite al usuario personalizar el texto con las opciones del editor. Por ejemplo, los usuarios pueden cambiar los tipos de fuente, crear listas con viñetas, resaltar contenido, etc. 

## <a name="merge-field-variables"></a>Combinar variables de campo

Puede aprovechar las variables de combinación de correo electrónico del editor de comunicaciones para incrustar atributos de custodios personalizados en el texto del cuerpo de una comunicación. Cuando se envía al custodio, el campo de combinación se rellenará con el campo correspondiente. Por ejemplo, cuando se envía a custodio Andrés Díaz, el campo de combinación [nombre del custodio] se convertiría con el nombre correspondiente. 

Puede usar los campos de combinación de correo electrónico seleccionando los iconos de **campo de combinación** en la parte superior del control del editor de texto enriquecido. El marcador de posición se agregará en función de la ubicación del cursor de los usuarios. 

### <a name="list-of-merge-field-variables"></a>Lista de variables de campo de combinación

| Nombre del campo                  | Detalles de campo | 
| :------------------- | :------------------- |
| Nombre para mostrar  | Nombre y apellido del custodio. | 
| Vínculo de confirmación | Un vínculo personalizado para registrar la confirmación de cada custodio.|                 |
| Vínculo al portal     | Un vínculo personalizado para el portal de cumplimiento de la custodio.|                |
| Responsable de la expedición                   | La dirección de correo electrónico del oficial de expedición especificado.|                   |
| Fecha de emisión                   | La fecha en que se emitió el aviso (UTC).              |
