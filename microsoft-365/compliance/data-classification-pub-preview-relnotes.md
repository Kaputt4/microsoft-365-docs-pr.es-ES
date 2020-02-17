---
title: Notas de la versión preliminar de la clasificación de datos (vista previa)
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
description: Notas de la versión preliminar pública de la clasificación de datos
ms.openlocfilehash: 1beae92089833327cedf6090690530d9e5457a37
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42076367"
---
# <a name="data-classification-public-preview-release-notes-preview"></a>Notas de la versión preliminar pública de la clasificación de datos (vista previa)

La versión preliminar pública introduce una nueva funcionalidad en la que se inicia el análisis de su contenido confidencial y etiquetado *antes* de crear cualquier directiva. Esto se denomina **administración de cambios de zero**. Esto le permite ver el impacto que las etiquetas de confidencialidad y retención están teniendo en su entorno para que pueda comenzar con la evaluación de sus necesidades de protección y directivas de gobernanza de datos.

Por favor, revise las notas de la versión para tener una mejor experiencia con la versión preliminar pública. Nos encargaremos de abordar estos puntos a partir de ahora y hasta que exista disponibilidad general (GA).

## <a name="permissions-for-accessing-content-explorer"></a>Permisos para acceder al explorador de contenidos

El acceso al explorador de contenidos está altamente restringido porque permite leer el contenido de los archivos digitalizados. Para acceder al explorador de contenido es necesaria la pertenencia al **visor de listas del explorador de contenido**, y a los grupos de roles del **visor del explorador de contenido**. Ninguna cuenta tiene acceso al explorador de contenido de forma predeterminada. Vea, [usar el explorador de contenido de clasificación de datos (vista previa)](data-classification-content-explorer.md#permissions). Un administrador global, un administrador de cumplimiento o un administrador de datos pueden asignar el **visor de listas del explorador de contenido** cuando sea necesario y la pertenencia al grupo de funciones del **visor del explorador de contenido**.

> [!TIP]
> Es posible que los grupos de roles del **visor de listas de contenido** y del **visor del explorador de contenido**no aparezcan en la página de permisos mientras los controles de acceso basados en roles (RBAC, por sus siglas en inglés) estén siendo implementados globalmente. En caso de que no aparezcan en la página de permisos, deberá crear un grupo de roles personalizados y asignar el `data classification list viewer` rol o los `data classification content viewer`roles a su grupo de roles personalizados.

## <a name="exchange-mailbox-count"></a>Buzón de correo de Exchange

Notará la aparición de información breve sobre herramientas cuando explore en los buzones de correo de Exchange. Esto sirve para llamar la atención sobre el hecho de que el recuento total mostrado sobre el tipo de información confidencial, etiquetas de confidencialidad y retención puede no coincidir exactamente con el número de elementos que se encuentran en el interior del buzón de correo. Esto se debe a la exploración en profundo de la carpeta para obtener la vista en vivo del contenido, que es clasificado, mientras se calcula el conteo agregado.

## <a name="seeing-guids-instead-of-label-names"></a>Ver GUID en lugar de los nombres de las etiquetas

Existen casos en que los clientes de la versión preliminar privada vieron cómo las etiquetas migradas o la eliminación de una etiqueta cuyo contenido ya había sido sellado daba como resultado que los nombres de las etiquetas se resolvieran en un GUID de 32 bits en el explorador de contenido y el explorador de actividades en lugar del nombre de la etiqueta. 

## <a name="rendering-of-encrypted-documents"></a>Representación de documentos codificados

Los archivos cifrados de SharePoint, Exchange y OneDrive no serán representados en el explorador de contenido. Este es un problema de confidencialidad que requiere de un equilibrio entre la necesidad de ver el contenido del archivo en el explorador de contenido y la necesidad de mantener el contenido cifrado. Con los permisos concedidos por los grupos de roles del **visor de listas del explorador de contenido** y el **visor del explorador de contenido**, obtendrá una vista de la lista de los archivos, los metadatos y un vínculo que puede usar para obtener acceso al contenido a través del cliente web.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Caracteres admitidos en los nombres de las etiquetas de retención en la búsqueda de SharePoint

La búsqueda de SharePoint no admite nombres de etiquetas de retención con `-`, o `_`en ellos. Por ejemplo `Label-MIP` y `Label_MIP` no son admitidos. La búsqueda en SharePoint admite el uso de esos caracteres en los nombres de las etiquetas de confidencialidad y en los nombres de los tipos de información confidencial.

## <a name="see-also"></a>Vea también

- [Introducción a la clasificación de datos (vista previa)](data-classification-overview.md)
- [Ver actividad de la etiqueta (vista previa)](data-classification-activity-explorer.md)
- [Ver contenido etiquetado (vista previa)](data-classification-content-explorer.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Etiquetas de retención](labels.md)
- [Información que buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md)

