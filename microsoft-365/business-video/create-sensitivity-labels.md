---
title: Cree etiquetas de confidencialidad
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo crear y administrar etiquetas de confidencialidad.
ms.openlocfilehash: 997b05ba549d3dc57e1793585331dfcfae1e277b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578944"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Proteger documentos con etiquetas de confidencialidad

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Las etiquetas de confidencialidad le permiten clasificar y proteger el contenido que es confidencial para su empresa.

## <a name="try-it"></a>¿Se atreve?

1. En el [Centro de administración,](https://admin.microsoft.com)seleccione el **Centro de administración** de cumplimiento.
1. Seleccione **Clasificación** y, a continuación, **Etiquetas de confidencialidad.**
1. Seleccione **Crear una etiqueta** y, cuando aparezca la advertencia, seleccione **Sí**.
1. Escriba un **nombre de etiqueta,** **Información sobre herramientas** y **Descripción**. Seleccione **Siguiente**.
1. Activar **cifrado**. Elija cuándo desea asignar permisos, si desea que expire el acceso de los usuarios al contenido y si desea permitir el acceso sin conexión.
1. **Seleccione Asignar permisos y,** a continuación, **Agregue estas direcciones de correo electrónico o dominios**.
1. Escriba una dirección de correo electrónico o un nombre de dominio (como Contoso.org).  Seleccione **Agregar** y repita cada dirección de correo electrónico o dominio que desee agregar.
1. Seleccione **Elegir permisos de preestablecida o personalizada.**
1. Use la lista desplegable para seleccionar permisos preestablecidos, como **Revisor** o **Visor,** o seleccione **Permisos** personalizados. Si elige **Personalizado**, seleccione los permisos de la lista. Seleccione **Guardar**, **Guardar** y, a continuación, **Siguiente**.
1. Activa el **marcado de** contenido y elige las marcas que quieras usar.
1. Para cada marcado que elija, seleccione **Personalizar texto**. Escriba el texto que desea que aparezca en el documento y establezca las opciones de fuente y diseño. Seleccione **Guardar** y, a continuación, repita las marcas adicionales. Seleccione **Siguiente**.
1. Opcionalmente, active La **prevención de pérdida de datos de punto de conexión**. Seleccione **Siguiente**.
1. Opcionalmente, activa el **etiquetado automático**. Agregue una condición. Por ejemplo, en **Detectar contenido que contiene**, seleccione Agregar una **condición**. Escriba la condición; por ejemplo, agregue una condición de que si se detecta passport, Seguridad Social u otra información confidencial, se agregará la etiqueta. Seleccione **Siguiente**.
1. Revise la configuración y seleccione **Crear**. Se ha creado la etiqueta. Repita este proceso para las etiquetas adicionales que desee.
1. De forma predeterminada, las etiquetas aparecen en las aplicaciones de Office en este orden: **Confidencial,** **Interna** y **Pública**. Para cambiar el orden, para cada etiqueta, seleccione **Más acciones** (puntos suspensivos) y, a continuación, mueva la etiqueta hacia arriba o hacia abajo. Normalmente, los permisos se enumeran del nivel más bajo al más alto de permisos.
1. Para agregar una subtiqueta a una etiqueta, seleccione **Más acciones** y, a continuación, **Agregar subdominio**.
1. Cuando haya terminado, elija **Publicar etiquetas**, **Elegir etiquetas para publicar** y, a continuación, **Agregar**. Seleccione las etiquetas que desea publicar y, a continuación, **seleccione Agregar**, **Listo** y, a continuación, **Siguiente**.
1. De forma predeterminada, la nueva directiva de etiqueta se aplica a todos los usuarios. Si desea limitar a quién se aplica la directiva, seleccione **Elegir usuarios o grupos** y, a continuación, **Agregar**. Seleccione a quién desea que se aplique la directiva y, a continuación, **seleccione Agregar**, **Listo** y, a continuación, **Siguiente**.
1. Si desea una etiqueta predeterminada para documentos y correo electrónico, seleccione la etiqueta que desee en la lista desplegable. Revise la configuración restante, ajuste según sea necesario y, a continuación, seleccione **Siguiente**.
1. Escriba un **nombre** y **una descripción** para la directiva. Seleccione **Siguiente**.
1. Revise la configuración y, a continuación, **seleccione Publicar**.

Para que las etiquetas funcionen, cada usuario debe descargar el cliente de etiquetado unificado de Azure Information Protection. Busque en la **webAzinfoProtection_UL.exe** y, a continuación, descárbala desde el Centro de descarga de Microsoft y la ejecute en los equipos de los usuarios.

La próxima vez que abra una aplicación de Office como Word, verá las etiquetas de confidencialidad que se crearon. Para cambiar o aplicar una etiqueta, seleccione Confidencialidad y elija una etiqueta.

