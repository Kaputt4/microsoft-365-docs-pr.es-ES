---
title: Buscar contenido en un caso de exhibición de documentos electrónicos principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Puede buscar contenido que pueda ser relevante para un caso de exhibición de documentos electrónicos principal.
ms.openlocfilehash: d17a9d16643ec9077e02b5438597237b80f09af5
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224627"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Buscar contenido en un caso de exhibición de documentos electrónicos principal

Una vez que se crea un caso de exhibición de documentos electrónicos principal y se colocan en suspensión personas de interés en el caso, puede crear y ejecutar una o más búsquedas para el contenido relevante para el caso. Las búsquedas asociadas a un caso de eDiscovery principal no aparecen en la página **búsqueda de contenido** en el centro de cumplimiento de Microsoft 365. Estas búsquedas se enumeran en la página **búsquedas** del núcleo eDiscover caso en el que se asocian las búsquedas. Esto también significa que solo se puede tener acceso a las búsquedas asociadas a un caso por los miembros de case.

Para crear una búsqueda de exhibición de documentos electrónicos principal:
  
1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con las credenciales de la cuenta de usuario a la que se le han asignado los permisos de eDiscovery adecuados.

2. En el panel de navegación izquierdo del centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todos**y, a continuación, en **eDiscovery > Core**.

3. En la página **principal de eDiscovery** , seleccione el caso en el que desea crear una búsqueda asociada y, a continuación, haga clic en **abrir caso**.

4. En la página **principal** del caso, haga clic en la ficha **búsquedas** .
  
5. En la página **Buscar** , haga clic en **nueva búsqueda**.

6. En la página **Nueva búsqueda**, puede agregar palabras clave y condiciones para crear la consulta de búsqueda. 

    ![Nueva búsqueda](../media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
   a. Puede especificar palabras clave, propiedades del mensaje, como las fechas de envío y recepción, o propiedades del documento, como nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar consultas más complejas que usen un operador booleano, como **and**, **or**, **Not**o **Near**. Además, puede buscar información confidencial (como los números de la seguridad social) en documentos o buscar en documentos que se han compartido de forma externa. Si deja vacío el cuadro palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se incluirá en los resultados de la búsqueda.

   b. Puede hacer clic en la casilla **Mostrar lista de palabras clave** y escribir una palabra clave en cada fila. Si hace esto, las palabras clave de cada fila están conectadas mediante el operador **or** en la consulta de búsqueda que se crea. Puede escribir un máximo de 20 palabras clave en la lista.

    ![Lista de palabras clave](../media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto le ayudará a identificar rápidamente las palabras clave más (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para saber más sobre las estadísticas de búsqueda, consulte [Ver estadísticas de palabras clave para resultados de búsqueda de contenido](view-keyword-statistics-for-content-search.md).

    Para obtener más información acerca del uso de la lista de palabras clave, vea [Building a Search Query](content-search.md#building-a-search-query).

   c. Puede hacer clic en **condiciones** y agregar condiciones en una consulta de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Con cada condición, se agrega una cláusula a la consulta de búsqueda KQL que se crea y se ejecuta al iniciar la búsqueda. Una condición está conectada de forma lógica con la consulta por palabra clave (especificada en el cuadro de palabra clave) mediante el operador **AND**. Esto significa que los elementos deben cumplir con la consulta de palabras clave y cada condición que se va a incluir en los resultados. De esta manera, las condiciones permiten restringir los resultados.

    Para obtener más información sobre cómo crear una consulta de búsqueda y el uso de las condiciones, consulte [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).

7. En **ubicaciones: ubicaciones en espera**, elija las ubicaciones de contenido en las que desea realizar la búsqueda. Puede buscar buzones de correo, sitios y carpetas públicas en la misma búsqueda.

    ![Ubicaciones, ubicaciones en suspensión](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Todas las ubicaciones**. Seleccione esta opción para buscar en todas las ubicaciones de contenido de la organización. Si selecciona esta opción, puede elegir buscar todos los buzones de Exchange (que incluye los buzones de todos los grupos de Microsoft Teams, Yammer y Office 365), todos los sitios de SharePoint y OneDrive para la empresa (que incluye los sitios de todos los grupos de Microsoft Teams, Yammer y Office 365) y todas las carpetas públicas.
    
    - **Todas las ubicaciones en espera**. Seleccione esta opción para buscar en todas las ubicaciones de contenido que se han colocado en la suspensión de exhibición de documentos electrónicos en el caso. Si el caso contiene varias suspensiones, se buscará en las ubicaciones de contenido de todas las suspensiones. Además, si se colocó una ubicación de contenido en una suspensión basada en consulta, solo se buscará en los elementos que están en espera cuando ejecute la búsqueda de contenido que está creando en este paso. Por ejemplo, si un usuario se colocó en la suspensión de casos basada en consultas y conserva los elementos que se enviaron o se crearon antes de una fecha específica, sólo se buscará en esos elementos. Esto se logra conectando la consulta de suspensión de casos y la consulta de búsqueda de contenido por un operador **and** . Para obtener más información, vea [ubicaciones de búsqueda en la retención de exhibición de](create-ediscovery-holds.md#search-locations-on-ediscovery-hold)documentos electrónicos.
    
    - **Ubicaciones específicas**. Seleccione esta opción para seleccionar los buzones y sitios en los que desea buscar. Cuando seleccione esta opción y haga clic en **modificar**, aparecerá una lista de ubicaciones. Puede elegir buscar en cualquiera o todos los usuarios, grupos, equipos o ubicaciones de sitio. También puede buscar en las carpetas públicas de su organización.
    
      ![Seleccionar ubicaciones específicas](../media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
     Si selecciona esta opción y busca en cualquier ubicación de contenido que esté en espera, las consultas de una suspensión de casos basada en consultas no se aplicarán a la consulta de búsqueda. En otras palabras, se busca en todo el contenido, no solo en el contenido que conserva una retención de casos basada en la consulta.

8. Una vez seleccionadas las ubicaciones de contenido para buscar, haga clic en **listo** y, a continuación, en **Guardar**.

9. En la página **nueva búsqueda** , haga clic en **Guardar & ejecutar** y, a continuación, escriba un nombre para la búsqueda. Las búsquedas asociadas a un caso de eDiscovery principal deben tener nombres únicos en la organización de Office 365.

10. Haga clic en **Guardar** para guardar la configuración de la búsqueda e iniciar la búsqueda.

  Una vez finalizada la búsqueda, puede obtener una vista previa de los resultados de la búsqueda. Si es necesario, haga clic en **Actualizar** en la página **búsquedas** para mostrar la búsqueda que ha creado en la lista.

11. Haga clic en la búsqueda para mostrar la página de flotante, que contiene estadísticas sobre la búsqueda y realizar otras tareas, como ver estadísticas de búsqueda y exportar los resultados de la búsqueda.

## <a name="more-information-about-searching-content-locations"></a>Más información sobre la búsqueda de ubicaciones de contenido

- Al hacer clic en **elegir usuarios, grupos o equipos** para especificar los buzones en los que se va a buscar, el selector de buzones que se muestra está vacío. Esto se ha diseñado así para mejorar el rendimiento. Para agregar destinatarios a esta lista, haga clic en **elegir usuarios, grupos o equipos**, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda, active la casilla de verificación situada junto al nombre y, a continuación, haga clic en **elegir**.

- Puede Agregar buzones inactivos, Microsoft Teams, grupos de Yammer, grupos de Office 365 y grupos de distribución a la lista de buzones de correo para la búsqueda. No se admiten grupos de distribución dinámicos. Si agrega Microsoft Teams, grupos de Yammer o grupos de Office 365, se busca en el buzón de grupo o de equipo; no se busca en los buzones de los miembros del grupo.

- Para agregar sitios, haga clic en **elegir sitios**, haga clic en **elegir sitios** de nuevo y, a continuación, escriba la dirección URL de cada sitio que desee buscar. También puede Agregar la dirección URL del sitio de SharePoint para un equipo de Microsoft, un grupo de Yammer o un grupo de Office 365.
