---
title: Creación y ejecución de una búsqueda de contenido en el portal de cumplimiento de Microsoft Purview
description: Utilice la herramienta de búsqueda de contenido de eDiscovery en el centro de cumplimiento de Microsoft para buscar contenido en diferentes servicios de Microsoft 365.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- tier1
- purview-compliance
- ediscovery
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
ms.openlocfilehash: 80049d041bce7c959eb9d0b00d4fec86a94ad1de
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68688395"
---
# <a name="create-a-content-search"></a>Crear una búsqueda de contenido

You can use the Content search eDiscovery tool in the Microsoft Purview compliance portal to search for in-place content such as email, documents, and instant messaging conversations in your organization. Use this tool to search for content in these cloud-based Microsoft 365 data sources:
  
- Buzones de correo de Exchange Online
- Sitios de SharePoint Online y cuentas de OneDrive para la Empresa
- Microsoft Teams
- Grupos de Microsoft 365
- Grupos de Yammer

Después de ejecutar una búsqueda, se mostrará el número de ubicaciones de contenido y un número estimado de resultados de la búsqueda en la página flotante de búsqueda. Puede ver rápidamente estadísticas como las ubicaciones de contenido con la mayor cantidad de elementos encontrados por la consulta de búsqueda. Después de ejecutar una búsqueda, puede obtener una vista previa de los resultados o exportarlos a un equipo local.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-run-a-search"></a>Antes de ejecutar una búsqueda

- To access to the Content search tool in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">compliance portal</a> (to run searches and preview results and export results), an administrator, compliance officer, or eDiscovery manager must be a member of the eDiscovery Manager role group in the compliance portal. For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).
- En una implementación de Exchange híbrida, no puede usar la herramienta de búsqueda de contenido para buscar correos en buzones locales. Solo puede usar la herramienta para buscar buzones basados en la nube.
- En una implementación híbrida de Exchange, puede buscar datos de chat de Teams en buzones locales. Para más información, vea [Datos de chat de Teams para usuarios locales](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users).

## <a name="create-and-run-a-search"></a>Crear y ejecutar una búsqueda
  
1. Vaya al [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) e inicie sesión con las credenciales de una cuenta a la que se han asignado los permisos adecuados.

2. En el panel de navegación izquierdo del portal de cumplimiento, seleccione **Búsqueda de contenido**.

3. En la página **Búsqueda de contenido** , seleccione **Nueva búsqueda**.

4. En la página **Nombre y descripción** , escriba un nombre para la búsqueda, una descripción opcional que ayude a identificar la búsqueda. El nombre de la búsqueda debe ser único en la organización.

5. En la página **Ubicaciones**, elija las ubicaciones de contenido que quiere buscar. Puede buscar en buzones, sitios y carpetas públicas.

    ![Elija las ubicaciones de contenido que desea buscar.](../media/ContentSearchLocations.png)
  
   1. **Buzones de Exchange**: establezca el botón de alternancia **en Activado** y, a continuación **, seleccione Elegir usuarios, grupos o equipos** para especificar los buzones de correo que se van a buscar. Use el cuadro de búsqueda para buscar buzones de usuario y grupos de distribución. También puede buscar en el buzón asociado a un equipo de Microsoft (para mensajes de canal), grupo de Microsoft 365 y grupo de Yammer. Para más información sobre los datos de la aplicación almacenados en buzones, vea [Contenido almacenado en buzones de eDiscovery](what-is-stored-in-exo-mailbox.md).

   2. **Sitios de SharePoint**: establezca el botón de alternancia **en Activado** y, a continuación, seleccione **Elegir sitios** para especificar sitios de SharePoint y cuentas de OneDrive para buscar. Escriba la dirección URL de cada sitio en el que quiera buscar. También puede agregar la dirección URL del sitio de SharePoint para un equipo de Microsoft, un grupo de Microsoft 365 o un grupo de Yammer.
  
   3. **Carpetas públicas de Exchange**: establezca el botón de alternancia **en Activado** para buscar en todas las carpetas públicas de la organización de Exchange Online. No puede elegir carpetas públicas específicas para buscar. Deje desactivado el botón de alternancia si no quiere buscar en todas las carpetas públicas.
  
   4. Mantenga esta casilla seleccionada para buscar contenido de Teams para los usuarios locales. Por ejemplo, si busca en todos los buzones de Exchange de la organización y también selecciona esta casilla, el almacenamiento basado en la nube que se usa para almacenar los datos de chats de Teams para usuarios locales se incluirá en el ámbito de la búsqueda. Para más información, consulte [Buscar los datos de chat de Teams de usuarios locales](search-cloud-based-mailboxes-for-on-premises-users.md).

6. En la página **Condiciones** , escriba una consulta de palabra clave y agregue condiciones a la consulta de búsqueda si es necesario.

   ![Configurar la consulta de búsqueda.](../media/ContentSearchQuery.png)

   1. Especifique palabras clave, propiedades del mensaje como la fecha de envío y de recepción, o propiedades del documento como nombres de archivo o la fecha de la última modificación de un documento. También puede usar consultas más complejas con operadores booleanos como **Y**, **O**, **NOT** y **NEAR**. Si deja el cuadro de la palabra clave en blanco, todo el contenido en las ubicaciones especificadas se incluye en los resultados de la búsqueda. Para más información, consulte [Consultas de palabras clave y condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md).

   2. Como alternativa, puede seleccionar la casilla **Mostrar lista de palabras clave** y escribir una palabra clave en cada fila. En este caso, las palabras clave de cada fila estarán conectadas por un operador lógico (**c:s**) funcionalmente similar al operador **O** en la consulta de búsqueda creada.

      **¿Por qué usar la lista de palabras clave**? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto le ayudará a identificar rápidamente las palabras clave más (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para más información sobre la lista de palabras clave y las estadísticas de búsqueda, consulte [Obtener estadísticas de palabras clave para las búsquedas](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Existe un límite máximo de 20 filas en la lista de palabras clave, con el fin de reducir los problemas causados por listas de palabras clave demasiado grandes.

   3. You can add search conditions to narrow a search and return a more refined set of results. Each condition adds a clause to the search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by a logical operator (**c:c**) that is similar in functionality to the **AND** operator. That means that items have to satisfy both the keyword query and one or more conditions to be included in the results. This is how conditions help to narrow your results. For a list and description of conditions that you can use in a search query, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions).

7. Revise la configuración de búsqueda (y edite si es necesario) y, a continuación, seleccione **Enviar** para iniciar la búsqueda.
  
Para acceder de nuevo a esta búsqueda de contenido o acceder a otras búsquedas de contenido enumeradas en la página **Búsqueda de contenido** , seleccione una búsqueda para ver el resumen de búsqueda y las estadísticas de búsqueda.

Para obtener más información sobre la búsqueda de contenido, como buscar contenido en distintos servicios de Microsoft 365, vea [Referencia de características para la búsqueda de contenido](content-search-reference.md).

## <a name="next-steps"></a>Siguientes pasos

A continuación se ofrece una lista de los pasos siguientes que debe realizar después de crear y ejecutar una búsqueda de contenido.

- [Vista previa de los resultados de búsqueda](preview-ediscovery-search-results.md)
- [Ver estadísticas de resultados de búsqueda](view-keyword-statistics-for-content-search.md)
- [Exportar resultados de la búsqueda](export-search-results.md)
- [Exportar un informe de búsqueda](export-a-content-search-report.md)
