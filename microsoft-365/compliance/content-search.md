---
title: Crear y ejecutar una búsqueda de contenido en el Centro de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Utilice la herramienta de búsqueda de contenido de eDiscovery en el centro de cumplimiento de Microsoft para buscar contenido en diferentes servicios de Microsoft 365.
ms.openlocfilehash: a058c07d080962723e9f6bc7a150cbfb5074e7db
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311680"
---
# <a name="create-a-content-search"></a>Crear una búsqueda de contenido

Puede usar la herramienta de eDiscovery de búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 para buscar contenido local como correo electrónico, documentos y conversaciones de mensajería instantánea en su organización. Use esta herramienta para buscar contenido en estos orígenes de datos de Microsoft 365:
  
- Buzones de correo de Exchange Online

- Sitios de SharePoint Online y cuentas de OneDrive para la Empresa

- Microsoft Teams

- Grupos de Microsoft 365

- Grupos de Yammer

Después de ejecutar una búsqueda, se mostrará el número de ubicaciones de contenido y un número estimado de resultados de la búsqueda en la página flotante de búsqueda. Puede ver rápidamente estadísticas como las ubicaciones de contenido con la mayor cantidad de elementos encontrados por la consulta de búsqueda. Después de ejecutar una búsqueda, puede obtener una vista previa de los resultados o exportarlos a un equipo local.

## <a name="create-and-run-a-search"></a>Crear y ejecutar una búsqueda

Para acceder a la página de **Búsqueda de contenido** en el Centro de cumplimiento de Microsoft 365 (para buscar, obtener una vista previa o exportar los resultados de búsqueda), es necesario que un administrador, responsable de cumplimento normativo o administrador de eDiscovery sea miembro del grupo de roles de administradores de eDiscovery en el Centro de seguridad y cumplimiento. Para más información, consulte [Asignar permisos de eDiscovery](assign-ediscovery-permissions.md).
  
1. Vaya a <https://compliance.microsoft.com> e inicie sesión con las credenciales de una cuenta a la que se han asignado los permisos adecuados.

2. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todo** y, luego, seleccione **Búsqueda de contenido**.

3. En la página **Búsqueda de contenido**, haga clic en **Nueva búsqueda**.

   > [!NOTE]
   > La opción **Buscar por lista de id.** le permite buscar mensajes de correo específicos y otros elementos del buzón con una lista de Id. de Exchange. Para crear una búsqueda por lista de id., debe enviar un archivo CSV que identifique los elementos de buzón específicos que desee buscar. Para sabe cómo hacerlo, consulte [Preparar un archivo CSV para una búsqueda por lista de id.](csv-file-for-an-id-list-content-search.md)

4. Escriba un nombre y una descripción opcional que le ayude a identificar la búsqueda. El nombre de la búsqueda debe ser único en la organización.

5. En la página **Ubicaciones**, elija las ubicaciones de contenido que quiere buscar. Puede buscar en buzones, sitios y carpetas públicas.

    ![Elegir las ubicaciones de contenido para colocar en suspensión](../media/ContentSearchLocations.png)
  
   1. **Buzones de Exchange**: establezca el botón de alternancia en **Activado** y después haga clic en **Elegir usuarios, grupos o equipos** para especificar los buzones para colocar en suspensión. Use el cuadro de búsqueda para encontrar buzones de usuario y grupos de distribución (para colocar una suspensión en los buzones de miembros de grupo) para suspenderlos. También puede buscar en el buzón asociado a un equipo de Microsoft (para los mensajes del canal), grupo de Office 365 y grupo de Yammer. Para más información sobre los datos de la aplicación almacenados en buzones, vea [Contenido almacenado en buzones de eDiscovery](what-is-stored-in-exo-mailbox.md).

   2. **Sitios de SharePoint**: establezca el botón de alternancia en **Activado** y haga clic en **Elegir sitios** para especificar los sitios de SharePoint y las cuentas de OneDrive que se deben colocar en suspensión. Escriba la dirección URL de cada sitio que quiere colocar en suspensión. También puede agregar la dirección URL del sitio de SharePoint para un equipo de Microsoft, un grupo de Office 365 o un grupo de Yammer.
  
   3. **Carpetas públicas de Exchange**: establezca la opción de alternancia en **Activado** para poner todas las carpetas públicas en su organización de Exchange Online en suspensión. No puede elegir carpetas públicas específicas para poner en suspensión. Deje el botón de alternancia desactivado si no quiere establecer una suspensión en las carpetas públicas.
  
   4. Mantenga esta casilla seleccionada para buscar contenido de Teams para los usuarios locales. Por ejemplo, si busca en todos los buzones de Exchange de la organización y también selecciona esta casilla, el almacenamiento basado en la nube que se usa para almacenar los datos de chats de Teams para usuarios locales se incluirá en el ámbito de la búsqueda. Para más información, consulte [Buscar los datos de chat de Teams de usuarios locales](search-cloud-based-mailboxes-for-on-premises-users.md).

6. En la página **Definir las condiciones de búsqueda**, escriba una consulta de palabra clave y agregue condiciones a la consulta de búsqueda si es necesario.

   ![Configurar la consulta de búsqueda](../media/ContentSearchQuery.png)

   1. Especifique palabras clave, propiedades del mensaje como la fecha de envío y de recepción, o propiedades del documento como nombres de archivo o la fecha de la última modificación de un documento. También puede usar consultas más complejas con operadores booleanos como **Y**, **O**, **NOT** y **NEAR**. Si deja el cuadro de la palabra clave en blanco, todo el contenido en las ubicaciones especificadas se incluye en los resultados de la búsqueda. Para más información, consulte [Consultas de palabras clave y condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md).

   2. También puede marcar la casilla **Mostrar lista de palabras clave** y escribir una palabra clave en cada fila. En este caso, las palabras clave de cada fila estarán conectadas por un operador lógico (**c:s**) funcionalmente similar al operador **O** en la consulta de búsqueda creada.

      ¿Por qué usar la lista de palabras clave? Puede obtener estadísticas que muestran cuántos elementos coinciden con cada palabra clave. Esto le ayudará a identificar rápidamente las palabras clave más (y menos) efectivas. También puede usar una frase de palabras clave (entre paréntesis) en una fila. Para más información sobre la lista de palabras clave y las estadísticas de búsqueda, consulte [Obtener estadísticas de palabras clave para las búsquedas](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Existe un límite máximo de 20 filas en la lista de palabras clave, con el fin de reducir los problemas causados por listas de palabras clave demasiado grandes.

   3. Puede agregar condiciones de búsqueda para recibir un conjunto de resultados más selecto. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición se conecta lógicamente a la consulta de palabras clave (especificada en el cuadro de palabras clave) mediante el operador **c:c**, que tiene una función parecida al operador **Y**. Eso significa que los elementos tienen que satisfacer la consulta de palabra clave y una o más condiciones para que se incluyan en los resultados. De esta manera, las condiciones permiten restringir los resultados. Para obtener una lista y una descripción de las condiciones que puede usar en una consulta de búsqueda, consulte [Condiciones de búsqueda](keyword-queries-and-search-conditions.md#search-conditions).

7. Revise la configuración de búsqueda (y edítela si es necesario) y envíe la búsqueda para iniciarla.
  
Para acceder nuevamente a esta búsqueda de contenido o para ver otras búsquedas de contenido en la página **Búsqueda de contenido**, seleccione la búsqueda y, a continuación, haga clic en **Abrir**.
  
## <a name="next-steps"></a>Siguientes pasos

A continuación se ofrece una lista de los pasos siguientes que debe realizar después de crear y ejecutar una búsqueda de contenido.

- [Vista previa de los resultados de búsqueda](preview-ediscovery-search-results.md)

- [Ver estadísticas de resultados de búsqueda](view-keyword-statistics-for-content-search.md)

- [Exportar resultados de la búsqueda](export-search-results.md)

- [Exportar un informe de búsqueda](export-a-content-search-report.md)
