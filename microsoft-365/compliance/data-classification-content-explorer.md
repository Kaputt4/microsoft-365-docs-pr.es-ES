---
title: Usar el explorador de contenido de clasificación de datos (vista previa)
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
description: El explorador de contenido le permite ver elementos etiquetados de forma nativa.
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268658"
---
# <a name="using-data-classification-content-explorer-preview"></a>Usar el explorador de contenido de clasificación de datos (vista previa)

El explorador de contenido de la clasificación de datos le permite ver de forma nativa los elementos que se resumiendo en la página información general.

## <a name="content-explorer"></a>Explorador de contenido

El explorador de contenido es una instantánea actual de los elementos que tienen una etiqueta de sensibilidad, una etiqueta de retención o que se han clasificado como un tipo de información confidencial en la organización.

![Captura de pantalla contraída de Content Explorer](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a>Permisos

Hay dos roles que otorgan acceso al explorador de contenido:

- **Visor de listas del explorador de contenido**: la pertenencia a este rol permite ver cada elemento y su ubicación.

- **Visor de contenido del explorador de contenido**: la pertenencia a este rol permite ver el contenido de cada elemento de la lista.

La cuenta que use para tener acceso al explorador de contenido debe estar en uno de los roles o en ambos. Este es un rol independiente y no es acumulativa. Por ejemplo, si desea conceder a una cuenta la capacidad para ver los elementos y sus ubicaciones únicamente, conceda a los derechos de visores de listas de explorador de contenido. Si desea que esa misma cuenta también pueda ver el contenido de los elementos de la lista, conceda los derechos de visor de contenido de explorador de contenido.

### <a name="how-to-use-content-explorer"></a>Cómo usar el explorador de contenido

1. Abra **Centro de cumplimiento de Microsoft 365 **  > **de la clasificación de datos ** > **El explorador de contenido**.
2. Si sabe el nombre de la etiqueta o el tipo de información confidencial, puede escribirlo en el cuadro de búsqueda.
3. De forma alternativa, puede buscar el elemento expandiendo el tipo de etiqueta y seleccionando la etiqueta de la lista; a continuación se muestra un elemento de la parte de la lista correspondiente a la etiqueta de retención.
4. Seleccione una ubicación en **todas las ubicaciones** y profundice en la estructura de carpetas hasta el elemento.
5. Haga doble clic para abrir el elemento de forma nativa en el explorador de contenido.

## <a name="see-also"></a>Vea también

- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](labels.md)
- [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)
- [Información general sobre las directivas de retención](retention-policies.md)
