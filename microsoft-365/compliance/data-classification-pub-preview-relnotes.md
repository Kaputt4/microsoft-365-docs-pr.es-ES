---
title: Notas de la versión de clasificación de datos
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de la versión para clasificación de datos.
ms.openlocfilehash: bbef6729680db2c9a6aec4caa9036ec23fad6949
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327621"
---
# <a name="data-classification-release-notes"></a>Notas de la versión de clasificación de datos

Por favor, revise las notas de la versión para tener una mejor experiencia con la clasificación de datos.

## <a name="exchange-mailbox-count"></a>Buzón de correo de Exchange

Notará la aparición de información breve sobre herramientas cuando explore en los buzones de correo de Exchange. Esto sirve para llamar la atención sobre el hecho de que el recuento total mostrado sobre el tipo de información confidencial, etiquetas de confidencialidad y retención puede no coincidir exactamente con el número de elementos que se encuentran en el interior del buzón de correo. Esto se debe a la exploración en profundo de la carpeta para obtener la vista en vivo del contenido, que es clasificado, mientras se calcula el conteo agregado.


## <a name="rendering-of-encrypted-documents"></a>Representación de documentos codificados

Los archivos cifrados de SharePoint, Exchange y OneDrive no serán representados en el explorador de contenido. Este es un problema de confidencialidad que requiere de un equilibrio entre la necesidad de ver el contenido del archivo en el explorador de contenido y la necesidad de mantener el contenido cifrado. Con los permisos concedidos por los grupos de roles del **visor de listas del explorador de contenido** y el **visor del explorador de contenido**, obtendrá una vista de la lista de los archivos, los metadatos y un vínculo que puede usar para obtener acceso al contenido a través del cliente web.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Caracteres admitidos en los nombres de las etiquetas de retención en la búsqueda de SharePoint

La búsqueda de SharePoint no admite nombres de etiquetas de retención con `-`, o `_`en ellos. Por ejemplo `Label-MIP` y `Label_MIP` no son admitidos. La búsqueda en SharePoint admite el uso de esos caracteres en los nombres de las etiquetas de confidencialidad y en los nombres de los tipos de información confidencial.

## <a name="onedrive-remains-in-preview"></a>OneDrive permanece en versión preliminar

Hemos escuchado sus valiosos comentarios sobre la integración de OneDrive durante el programa de versión preliminar. Mientras trabajamos en las especificaciones, es posible que se puedan producir datos/flujos incoherentes. Seguiremos mostrando OneDrive en la versión preliminar hasta que todas las correcciones estén en su sitio. Agradecemos su continuado soporte en este aspecto.


## <a name="see-also"></a>Ver también

- [Introducción a la clasificación de datos (vista previa)](data-classification-overview.md)
- [Ver actividad de la etiqueta (vista previa)](data-classification-activity-explorer.md)
- [Ver contenido etiquetado (vista previa)](data-classification-content-explorer.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](labels.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)