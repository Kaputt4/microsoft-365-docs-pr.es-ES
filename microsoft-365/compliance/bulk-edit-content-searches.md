---
title: Edición masiva de búsquedas de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/29/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
ms.custom:
- seo-marvel-apr2020
description: Use el editor de búsqueda en masa en el centro de seguridad y cumplimiento para cambiar rápidamente las ubicaciones de consulta y contenido de una o más búsquedas de contenido.
ms.openlocfilehash: 2bbe8248a82356a217557469b6639e28607be13e
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035528"
---
# <a name="bulk-edit-content-searches"></a>Edición masiva de búsquedas de contenido

Puede usar el editor de búsqueda en masa en la herramienta de búsqueda de contenido para editar varias búsquedas al mismo tiempo. El uso de esta herramienta le permite cambiar rápidamente las ubicaciones de consultas y contenido para una o más búsquedas. A continuación, puede volver a ejecutar las búsquedas y obtener los nuevos resultados de búsqueda estimados para las búsquedas revisadas. El editor también le permite copiar y pegar consultas y ubicaciones de contenido de un archivo de texto o de un archivo de Microsoft Excel. Esto significa que puede usar la herramienta de estadísticas de búsqueda para ver las estadísticas de una o más búsquedas, exportar las estadísticas a un archivo CSV, donde puede editar las consultas y las ubicaciones de contenido en Excel. A continuación, use el editor de búsqueda en masa para agregar las consultas revisadas y las ubicaciones de contenido a las búsquedas. Una vez que haya revisado una o más búsquedas, puede reiniciarlas y obtener nuevos resultados de búsqueda estimados.
  
Para obtener más información acerca del uso de la herramienta de estadísticas de búsqueda, consulte [View keyword Statistics for Content Search Results](view-keyword-statistics-for-content-search.md).
  
## <a name="use-the-bulk-search-editor-to-change-queries"></a>Usar el editor de búsqueda en masa para cambiar las consultas

1. Vaya a [https://protection.office.com](https://protection.office.com)y, a continuación, seleccione búsqueda de **contenido**de **búsqueda** \> .
    
2. En la lista de búsquedas, seleccione una o más búsquedas y, a continuación **, seleccione** ![el botón](../media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png)editor de búsqueda en masa del editor de búsqueda masiva.
    
    ![Selecciona una o más búsquedas y, a continuación, selecciona el editor de búsqueda masiva.](../media/600c9716-89a2-4451-b111-fa7cfaad2006.png)
  
    La siguiente información se muestra en la página **consultas** del editor masivo de búsqueda. 
    
    ![La página editor de búsqueda en masa muestra las consultas de las búsquedas seleccionadas](../media/189659af-cc78-4479-b0bc-a93decad2f6c.png)
  
    a. La columna **Buscar** muestra el nombre de la búsqueda de contenido. Como se mencionó anteriormente, puede editar la consulta para varias búsquedas. 
    
    b. La columna **consulta** muestra la consulta de la búsqueda de contenido que aparece en la columna **búsqueda** . Si la consulta se ha creado mediante la característica lista de palabras clave, las palabras clave se separan con el texto * * `(c:s)` **. Esto indica que las palabras clave están conectadas por el operador **or** . Además, si la consulta incluye condiciones, las palabras clave y las condiciones están separadas por el texto * `(c:c)`* **. Esto indica que las palabras clave (o las fases de palabra clave) están conectadas a las condiciones por el operador **and** . Por ejemplo, en la captura de pantalla anterior, el para búsqueda ContosoSearch1, la consulta de KQL `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)` equivale a `(customer OR pricing) AND (date=2002-01-01..2016-09-30)`.
    
3. Para editar una consulta, seleccione en la celda de la consulta que desea cambiar y realice una de las acciones siguientes. La celda está rodeada por un cuadro azul cuando la selecciona.
    
   - Escriba la nueva consulta en la celda. No se puede editar una parte de la consulta. Tiene que escribir toda la consulta.
    
      O bien:
    
    - Pega una nueva consulta en la celda. En este ejemplo se supone que se ha copiado el texto de la consulta desde un archivo, como un archivo de texto o un archivo de Excel.
    
4. Una vez que haya editado una o más consultas en la página **consultas** , seleccione **Guardar**.
    
    La consulta revisada se muestra en la columna **consulta** de la búsqueda seleccionada. 
    
5. Seleccione **cerrar** para cerrar el editor de búsqueda masiva. 
    
6. En la página **búsqueda de contenido** , seleccione la búsqueda que editó y, a continuación, seleccione **iniciar** búsqueda para reiniciar la búsqueda con la consulta revisada. 
    
Estas son algunas sugerencias para editar consultas con el editor de búsqueda en masa:
  
- Copie la consulta existente (usando **Ctrl C** ) en un archivo de texto. Edite la consulta en el archivo de texto y, a continuación, copie la consulta revisada y péguela (mediante **Ctrl V** ) en la celda de la página **consultas** . 
    
- También puede copiar consultas de otras aplicaciones (como Microsoft Word o Microsoft Excel). Sin embargo, podría agregar involuntariamente caracteres no admitidos a una consulta con el editor masivo de búsqueda. La mejor forma de evitar caracteres no admitidos es simplemente escribir la consulta en una celda de la página **consultas** . O bien, puede copiar una consulta desde Word o Excel y, a continuación, pegarla en un archivo en un editor de texto sin formato, como el Bloc de notas de Microsoft. A continuación, guarde el archivo de texto y seleccione **ANSI** en la lista desplegable **Codificación**. Esto quita el formato y los caracteres no admitidos. A continuación, puede copiar y pegar la consulta desde el archivo de texto a la página **consultas** . 
    
  
## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Usar el editor de búsqueda en masa para cambiar las ubicaciones de contenido

1. En el editor de búsqueda en masa de una o varias búsquedas seleccionadas, seleccione **Habilitar el editor de ubicación en masa**y, a continuación, seleccione el vínculo **ubicaciones** que se muestra en la página. 
    
    La siguiente información se muestra en la página **ubicaciones** del editor masivo de búsqueda. 
    
    ![Seleccione habilitar el editor de ubicación en masa y, a continuación, seleccione ubicaciones para agregar o quitar ubicaciones de contenido](../media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)
  
    a. **Buzones de correo para buscar** En esta sección se muestra una columna para cada búsqueda de contenido seleccionada y una fila para cada buzón de correo que se incluye en la búsqueda. Una marca de verificación indica que el buzón de correo se incluye en la búsqueda. Puede Agregar buzones a una búsqueda escribiendo la dirección de correo electrónico del buzón en una fila en blanco y, a continuación, activando la casilla de verificación de la búsqueda de contenido a la que desea agregarla. O bien, puede quitar un buzón de una búsqueda desactivando la casilla de verificación.
    
    b. **Sitios de SharePoint para buscar** En esta sección se muestra una fila para cada sitio de SharePoint y OneDrive que se incluye en cada búsqueda de contenido seleccionada. Una marca de verificación indica que el sitio está incluido en la búsqueda. Puede Agregar sitios a una búsqueda escribiendo la dirección URL del sitio en una fila en blanco y, a continuación, activando la casilla de verificación de la búsqueda de contenido a la que desea agregarla. O bien, puede quitar un sitio de una búsqueda desactivando la casilla de verificación.
    
    c. **Otras opciones de búsqueda** En esta sección se indica si los elementos sin indexar y las carpetas públicas se incluyen en la búsqueda. Para incluirlos, asegúrese de que está activada la casilla de verificación. Para quitarlos, desactive la casilla.
    
2. Una vez que haya editado una o varias secciones en la página **ubicaciones** , seleccione **Guardar**.
    
    Las ubicaciones de contenido revisadas se muestran en la sección correspondiente para las búsquedas seleccionadas.
    
3. Seleccione **cerrar** para cerrar el editor de búsqueda masiva. 
    
4. En la página **búsqueda de contenido** , seleccione la búsqueda que editó y seleccione **iniciar** búsqueda para reiniciar la búsqueda con las ubicaciones de contenido revisadas. 
    
Estas son algunas sugerencias para editar ubicaciones de contenido con el editor de búsqueda en masa:
  
- Puede editar las búsquedas de contenido para buscar en todos los buzones o sitios de la organización; para ello, escriba **todo** en una fila en blanco en la sección **buzones de correo para buscar** o **sitios de SharePoint** y, a continuación, active la casilla. 
    
- Puede agregar varias ubicaciones de contenido a una o más búsquedas si copia varias filas de un archivo de texto o un archivo de Excel y, a continuación, las pega en una sección de la página **ubicaciones** . Después de agregar nuevas ubicaciones, asegúrese de activar la casilla de verificación para cada búsqueda a la que desea agregar la ubicación. 
    
    > [!TIP]
    > Para generar una lista de direcciones de correo electrónico para todos los usuarios de la organización, ejecute el comando de PowerShell en el paso 2 del [paso 2: generar una lista de usuarios](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step-2-generate-a-list-of-users). O bien, siga los pasos que se indican en [obtener una lista de todas las direcciones URL de onedrive del usuario en la organización](https://docs.microsoft.com/onedrive/list-onedrive-urls) para generar una lista de todos los sitios de onedrive para la empresa de su organización. Tenga en cuenta que tendrá que anexar la dirección URL para el dominio de mi sitio de la organización https://contoso-my.sharepoint.com) (por ejemplo, a los sitios de OneDrive para la empresa creados por el script. Una vez que tenga una lista de direcciones de correo electrónico o sitios de OneDrive para la empresa, puede copiarlos y pegarlos en la página **ubicaciones** del editor de búsqueda en masa. 
  
- Después de seleccionar **Guardar** para guardar los cambios en el editor de búsqueda en masa, se validará la dirección de correo electrónico para los buzones que agregó a la búsqueda. Si no existe la dirección de correo electrónico, aparecerá un mensaje de error que indica que no se encuentra el buzón. Las direcciones URL de los sitios no se validan. 
  

