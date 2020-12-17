---
title: Cree etiquetas de confidencialidad
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Obtenga información sobre cómo crear y administrar las etiquetas de confidencialidad.
ms.openlocfilehash: ff3f7eb5ffddf797e254fac0ed8fc87d96940455
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703216"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Proteger documentos con etiquetas de confidencialidad

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Las etiquetas de confidencialidad le permiten clasificar y proteger el contenido que sea sensible a su empresa.

## <a name="try-it"></a>¿Se atreve?

1. En el [centro de administración](https://admin.microsoft.com), seleccione el centro de administración de **cumplimiento** .
1. Seleccione **clasificación** y, a continuación, **etiquetas de sensibilidad**.
1. Seleccione **crear una etiqueta** y, cuando aparezca la advertencia, seleccione **sí**.
1. Escriba un **nombre de etiqueta**, **información sobre herramientas** y **Descripción**. Seleccione **Siguiente**.
1. Active el **cifrado**. Elija Cuándo desea asignar permisos, si desea que el acceso de los usuarios al contenido expire y si desea permitir el acceso sin conexión.
1. **Seleccione asignar permisos** y, a continuación, **Agregue estas direcciones de correo electrónico o dominios**.
1. Escriba una dirección de correo electrónico o un nombre de dominio (por ejemplo, Contoso.org).  Seleccione **Agregar** y repita el para cada dirección de correo electrónico o dominio que quiera agregar.
1. Seleccione **elegir permisos en preestablecido o personalizado**.
1. Use la lista desplegable para seleccionar los permisos preestablecidos, como **Revisor** o **visor**, o seleccione permisos **personalizados** . Si elige **personalizado**, seleccione los permisos de la lista. Seleccione **Guardar**, **Guardar** y, a continuación, **siguiente**.
1. Active la **marcación de contenido** y elija los marcadores que desea usar.
1. Para cada marcación que elija, seleccione **personalizar texto**. Escriba el texto que desea que aparezca en el documento y establezca las opciones de fuente y diseño. Seleccione **Guardar** y, a continuación, repita el procedimiento para los marcados adicionales. Seleccione **Siguiente**.
1. Opcionalmente, active la **prevención de pérdida de datos de extremos**. Seleccione **Siguiente**.
1. Opcionalmente, active la **etiqueta automática**. Agregar una condición. Por ejemplo, en **detectar contenido que contiene**, seleccione **Agregar una condición**. Especifique la condición; por ejemplo, agregue una condición que si se detecta Passport, la seguridad social o cualquier otra información confidencial, se agregará la etiqueta. Seleccione **Siguiente**.
1. Revise la configuración y seleccione **crear**. Se ha creado la etiqueta. Repita este proceso para las etiquetas adicionales que desee.
1. De forma predeterminada, las etiquetas aparecen en las aplicaciones de Office en este orden: **confidencial**, **interno** y **público**. Para cambiar el orden, para cada etiqueta, seleccione **más acciones** (los puntos suspensivos) y, a continuación, mueva la etiqueta hacia arriba o hacia abajo. Normalmente, los permisos se enumeran desde el menor hasta el nivel más alto de permisos.
1. Para agregar una subetiqueta a una etiqueta, seleccione **más acciones** y, a continuación, **Agregar sub-nivel**.
1. Cuando termine, elija **publicar etiquetas**, **Elija etiquetas para publicar** y, a continuación, **Agregar**. Seleccione las etiquetas que desea publicar y, a continuación, seleccione **Agregar**, **listo** y, a continuación, **siguiente**.
1. De forma predeterminada, la nueva Directiva de etiqueta se aplica a todos los usuarios. Si desea limitar la persona a la que se aplica la Directiva, seleccione **elegir usuarios o grupos** y, a continuación, **Agregar**. Seleccione a quién desea que se aplique la Directiva y, a continuación, seleccione **Agregar**, **listo** y, a continuación, **siguiente**.
1. Si desea una etiqueta predeterminada para los documentos y el correo electrónico, seleccione la etiqueta que desee en la lista desplegable. Revise la configuración restante, ajústela según sea necesario y, a continuación, seleccione **siguiente**.
1. Escriba un **nombre** y una **Descripción** para la Directiva. Seleccione **Siguiente**.
1. Revise la configuración y, después, seleccione **publicar**.

Para que las etiquetas funcionen, cada usuario debe descargar el cliente de etiquetado Unificado de Azure Information Protection. Busque **AzinfoProtection_UL.exe** en el sitio web, descárguelo desde el centro de descarga de Microsoft y ejecútelo en los equipos de los usuarios.

La próxima vez que abra una aplicación de Office como Word, verá las etiquetas de confidencialidad que se crearon. Para cambiar o aplicar una etiqueta, seleccione confidencial y elija una etiqueta.

