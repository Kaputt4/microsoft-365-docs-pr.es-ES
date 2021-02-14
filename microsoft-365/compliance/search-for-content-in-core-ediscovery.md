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
description: Puede buscar contenido que pueda ser relevante para un caso de eDiscovery principal.
ms.openlocfilehash: d17a9d16643ec9077e02b5438597237b80f09af5
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224627"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Buscar contenido en un caso de exhibición de documentos electrónicos principal

Una vez creado un caso de exhibición de documentos electrónicos principal y las personas de interés en el caso se colocan en espera, puede crear y ejecutar una o más búsquedas de contenido relevante para el caso. Las búsquedas asociadas a un caso de  exhibición de documentos electrónicos principal no aparecen en la página Búsqueda de contenido en el Centro de cumplimiento de Microsoft 365. Estas búsquedas se enumeran en la **página Búsquedas** del caso de eDiscover principal al que están asociadas las búsquedas. Esto también significa que solo los miembros del caso pueden tener acceso a las búsquedas asociadas a un caso.

Para crear una búsqueda de exhibición de documentos electrónicos principal:
  
1. Vaya e inicie sesión con las credenciales de la cuenta de usuario a la que se han asignado los permisos de exhibición de [https://compliance.microsoft.com](https://compliance.microsoft.com) documentos electrónicos adecuados.

2. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en Mostrar todo y, a continuación, haga clic en **eDiscovery > Principal.**

3. En la **página eDiscovery** principal, seleccione el caso en el que desea crear una búsqueda asociada y, a continuación, haga clic **en Abrir caso.**

4. En la **página principal** del caso, haga clic en la **pestaña** Búsquedas.
  
5. En la **página Buscar,** haga clic **en Nueva búsqueda.**

6. En la página **Nueva búsqueda**, puede agregar palabras clave y condiciones para crear la consulta de búsqueda. 

    ![Nueva búsqueda](../media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
   a. Puede especificar palabras clave, propiedades de mensaje, como fechas de envío y recibido, o propiedades de documento, como nombres de archivo o la fecha en que se modificó por última vez un documento. Puede usar consultas más complejas que usen un operador booleano, como **AND**, **OR**, **NOT** o **NEAR**. Además, puede buscar información confidencial (como los números de la seguridad social) en documentos o buscar en documentos que se han compartido de forma externa. Si deja vacío el cuadro de palabras clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se incluirá en los resultados de la búsqueda.

   b. Puede hacer clic en la casilla **Mostrar lista** de palabras clave y escribir una palabra clave en cada fila. Si lo hace, las palabras clave de cada fila se conectan mediante el operador **OR** en la consulta de búsqueda que se crea. Puede escribir un máximo de 20 palabras clave en la lista.

    ![Lista de palabras clave](../media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto le ayudará a identificar rápidamente las palabras clave más (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para saber más sobre las estadísticas de búsqueda, consulte [Ver estadísticas de palabras clave para resultados de búsqueda de contenido](view-keyword-statistics-for-content-search.md).

    Para obtener más información acerca del uso de la lista de palabras clave, vea [Creación de una consulta de búsqueda.](content-search.md#building-a-search-query)

   c. Puede hacer clic **en Condiciones** y agregar condiciones a una consulta de búsqueda para restringir una búsqueda y devolver un conjunto de resultados más refinado. Con cada condición, se agrega una cláusula a la consulta de búsqueda KQL que se crea y se ejecuta al iniciar la búsqueda. Una condición está conectada de forma lógica con la consulta por palabra clave (especificada en el cuadro de palabra clave) mediante el operador **AND**. Esto significa que los elementos deben satisfacer tanto la consulta de palabra clave como cada condición que se incluirá en los resultados. De esta manera, las condiciones permiten restringir los resultados.

    Para obtener más información sobre cómo crear una consulta de búsqueda y el uso de las condiciones, consulte [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).

7. En **Ubicaciones: ubicaciones en espera,** elija las ubicaciones de contenido en las que desea buscar. Puede buscar buzones, sitios y carpetas públicas en la misma búsqueda.

    ![Ubicaciones, ubicaciones en espera](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Todas las ubicaciones**. Seleccione esta opción para buscar en todas las ubicaciones de contenido de la organización. Al seleccionar esta opción, puede elegir buscar en todos los buzones de Exchange (incluidos los buzones de todos los grupos de Microsoft Teams, Yammer y Office 365), todos los sitios de SharePoint y OneDrive para la Empresa (que incluyen los sitios de todos los grupos de Microsoft Teams, Yammer y Office 365) y todas las carpetas públicas.
    
    - **Todas las ubicaciones en espera.** Seleccione esta opción para buscar en todas las ubicaciones de contenido que se han colocado en retención de exhibición de documentos electrónicos en el caso. Si el caso contiene varias retenciones, se buscarán las ubicaciones de contenido de todas las retenciones. Además, si una ubicación de contenido se colocó en una retención basada en consultas, solo se buscarán los elementos que están en retención cuando ejecute la búsqueda de contenido que está creando en este paso. Por ejemplo, si un usuario se coloca en conservación de casos basada en consulta que conserva los elementos que se enviaron o crearon antes de una fecha específica, solo se buscarían esos elementos. Esto se logra conectando la consulta de retención de casos y la consulta de búsqueda de contenido mediante un **operador AND.** Para obtener más información, vea [Ubicaciones de búsqueda en retención de exhibición de documentos electrónicos.](create-ediscovery-holds.md#search-locations-on-ediscovery-hold)
    
    - **Ubicaciones específicas**. Seleccione esta opción para seleccionar los buzones y sitios en los que desea buscar. Al seleccionar esta opción y hacer **clic** en Modificar, aparece una lista de ubicaciones. Puede elegir buscar en cualquiera o todos los usuarios, grupos, equipos o ubicaciones de sitios. También puede buscar en las carpetas públicas de su organización.
    
      ![Seleccionar ubicaciones específicas](../media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
     Si selecciona esta opción y busca en cualquier ubicación de contenido que esté en espera, cualquier consulta de una retención de casos basada en consulta no se aplicará a la consulta de búsqueda. En otras palabras, se busca todo el contenido, no solo el contenido que se conserva mediante una retención de casos basada en consultas.

8. Después de seleccionar las ubicaciones de contenido para buscar, haga clic **en Listo** y, a continuación, haga clic en **Guardar**.

9. En la **página Nueva búsqueda,** haga clic en **& ejecutar** y, a continuación, escriba un nombre para la búsqueda. Las búsquedas asociadas a un caso de exhibición de documentos electrónicos principal deben tener nombres únicos en la organización de Office 365.

10. Haga **clic en** Guardar para guardar la configuración de búsqueda e iniciar la búsqueda.

  Una vez finalizada la búsqueda, puede obtener una vista previa de los resultados de la búsqueda. Si es necesario, haga **clic en Actualizar** en la página **Búsquedas** para mostrar la búsqueda que creó en la lista.

11. Haga clic en la búsqueda para mostrar la página desplegable, que contiene estadísticas sobre la búsqueda y para realizar otras tareas, como ver estadísticas de búsqueda y exportar los resultados de la búsqueda.

## <a name="more-information-about-searching-content-locations"></a>Más información sobre la búsqueda de ubicaciones de contenido

- Al hacer clic **en Elegir usuarios, grupos** o equipos para especificar los buzones en los que buscar, el selector de buzones que se muestra está vacío. Esto se ha diseñado así para mejorar el rendimiento. Para agregar destinatarios a esta lista, haga clic en Elegir **usuarios,** grupos o equipos , escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda, active la casilla situada junto al nombre y, a continuación, haga clic en Elegir **.**

- Puede agregar buzones inactivos, Microsoft Teams, Grupos de Yammer, Grupos de Office 365 y grupos de distribución a la lista de buzones para buscar. No se admiten grupos de distribución dinámicos. Si agrega Microsoft Teams, Grupos de Yammer u Grupos de Office 365, se busca en el buzón de grupo o equipo; No se busca en los buzones de los miembros del grupo.

- Para agregar sitios, haga **clic en Elegir** sitios, vuelva **a** hacer clic en Elegir sitios y, a continuación, escriba la dirección URL de cada sitio en el que desee buscar. También puede agregar la dirección URL del sitio de SharePoint para un equipo de Microsoft, un grupo de Yammer o un grupo de Office 365.
