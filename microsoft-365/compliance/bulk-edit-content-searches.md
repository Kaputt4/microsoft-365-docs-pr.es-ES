---
title: Búsquedas de contenido de edición masiva
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
description: Use el Editor de búsqueda masiva en el Centro de seguridad y cumplimiento para cambiar rápidamente las ubicaciones de consulta y contenido de una o más búsquedas de contenido.
ms.openlocfilehash: f6331bad19e95fd1d7039d5da72349906d3614b8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227392"
---
# <a name="bulk-edit-content-searches"></a>Búsquedas de contenido de edición masiva

Puede usar el Editor de búsqueda masiva en la herramienta búsqueda de contenido para editar varias búsquedas al mismo tiempo. El uso de esta herramienta le permite cambiar rápidamente las ubicaciones de consulta y contenido de una o más búsquedas. A continuación, puede volver a ejecutar las búsquedas y obtener nuevos resultados de búsqueda estimados para las búsquedas revisadas. El editor también le permite copiar y pegar consultas y ubicaciones de contenido de un archivo Microsoft Excel archivo o archivo de texto. Esto significa que puede usar la herramienta Estadísticas de búsqueda para ver las estadísticas de una o más búsquedas, exportar las estadísticas a un archivo CSV, donde puede editar las consultas y las ubicaciones de contenido en Excel. A continuación, use el Editor de búsqueda masiva para agregar las consultas revisadas y las ubicaciones de contenido a las búsquedas. Después de revisar una o más búsquedas, puede reiniciarlas y obtener nuevos resultados de búsqueda estimados.

Para obtener más información acerca del uso de la herramienta Estadísticas de búsqueda, vea Ver estadísticas de palabras clave para [los resultados de búsqueda de contenido.](view-keyword-statistics-for-content-search.md)

## <a name="use-the-bulk-search-editor-to-change-queries"></a>Usar el Editor de búsqueda masiva para cambiar consultas

1. Vaya a <https://protection.office.com> y, a continuación, **seleccione Buscar** \> **búsqueda de contenido**.

2. En la lista de búsquedas, seleccione una o más búsquedas y, a continuación, **seleccione** Editor de búsqueda masiva Editor de búsqueda ![ masiva ](../media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png) .

    ![Seleccione una o más búsquedas y, a continuación, seleccione Editor de búsqueda masiva](../media/600c9716-89a2-4451-b111-fa7cfaad2006.png)

    La siguiente información se muestra en la página **Consultas** del Editor de búsqueda masiva.

    ![La página Editor de búsqueda masiva muestra las consultas de las búsquedas seleccionadas](../media/189659af-cc78-4479-b0bc-a93decad2f6c.png)

    a. La **columna** Búsqueda muestra el nombre de la búsqueda de contenido. Como se ha indicado anteriormente, puede editar la consulta para varias búsquedas.

    b. La **columna Consulta** muestra la consulta de la búsqueda de contenido que aparece en la **columna** Búsqueda. Si la consulta se creó con la característica de lista de palabras clave, las palabras clave se separan por el texto **`(c:s)`** . Esto indica que las palabras clave están conectadas por el **operador OR.** Además, si la consulta incluye condiciones, las palabras clave y las condiciones se separan por el texto **`(c:c)`** . Esto indica que las palabras clave (o fases de palabras clave) están conectadas a las condiciones por el **operador AND.** Por ejemplo, en la captura de pantalla anterior la búsqueda ContosoSearch1, la consulta KQL equivalente a `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)` sería  `(customer OR pricing) AND (date=2002-01-01..2016-09-30)` .

3. Para editar una consulta, seleccione en la celda de la consulta que desea cambiar y haga una de las siguientes acciones. La celda está bordeada por un cuadro azul al seleccionarla.

   - Escriba la nueva consulta en la celda. No puede editar una parte de la consulta. Debe escribir la consulta completa.

      O bien

   - Pegue una nueva consulta en la celda. Esto supone que ha copiado el texto de la consulta de un archivo, como un archivo de texto o un Excel archivo.

4. Después de editar una o más  consultas en la página Consultas, seleccione **Guardar**.

    La consulta revisada se muestra en la columna **Consulta** de la búsqueda seleccionada.

5. Seleccione **Cerrar** para cerrar el Editor de búsqueda masiva.

6. En la **página Búsqueda de** contenido, seleccione la búsqueda que ha editado y seleccione **Iniciar** búsqueda para reiniciar la búsqueda mediante la consulta revisada.

Estas son algunas sugerencias para editar consultas con el Editor de búsqueda masiva:

- Copie la consulta existente (mediante **Ctrl C**) en un archivo de texto. Edite la consulta en el archivo de texto y, a continuación, copie la consulta revisada y péguela (mediante **Ctrl V**) de nuevo en la celda de la **página** Consultas.

- También puede copiar consultas de otras aplicaciones (como Microsoft Word o Microsoft Excel). Sin embargo, puede agregar accidentalmente caracteres no admitidos a una consulta mediante el Editor de búsqueda masiva. La mejor manera de evitar caracteres no admitidos es simplemente escribir la consulta en una celda en la **página** Consultas. O puede copiar una consulta de Word o Excel y, a continuación, pegarla en un archivo en un editor de texto sin formato, como Microsoft Bloc de notas. A continuación, guarde el archivo de texto y seleccione **ANSI** en la lista desplegable **Codificación**. Esto quita cualquier formato y caracteres no admitidos. A continuación, puede copiar y pegar la consulta desde el archivo de texto a la **página** Consultas.

## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Usar el Editor de búsqueda masiva para cambiar las ubicaciones de contenido

1. En el Editor de búsqueda masiva para una o más búsquedas  seleccionadas, seleccione Habilitar **editor** de ubicaciones masivas y, a continuación, seleccione el vínculo Ubicaciones que se muestra en la página.

    La siguiente información se muestra en la página **Ubicaciones** del Editor de búsqueda masiva.

    ![Seleccione Habilitar editor de ubicaciones masivas y, a continuación, seleccione Ubicaciones para agregar o quitar ubicaciones de contenido](../media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)

    a. **Buzones para buscar** En esta sección se muestra una columna para cada búsqueda de contenido seleccionada y una fila para cada buzón que se incluye en la búsqueda. Una marca de verificación indica que el buzón está incluido en la búsqueda. Puede agregar buzones a una búsqueda escribiendo la dirección de correo electrónico del buzón en una fila en blanco y, a continuación, seleccionando la casilla de la búsqueda de contenido a la que desea agregarlo. O puede quitar un buzón de una búsqueda desactivando la casilla.

    b. **SharePoint sitios en los que buscar** En esta sección se muestra una fila para cada SharePoint y OneDrive sitio que se incluye en cada búsqueda de contenido seleccionada. Una marca de verificación indica que el sitio está incluido en la búsqueda. Puede agregar sitios a una búsqueda escribiendo la dirección URL del sitio en una fila en blanco y, a continuación, seleccionando la casilla de la búsqueda de contenido a la que desea agregarlo. O puede quitar un sitio de una búsqueda desactivando la casilla.

    c. **Otras opciones de búsqueda** Esta sección indica si los elementos no indexados y las carpetas públicas se incluyen en la búsqueda. Para incluirlos, asegúrese de que la casilla está activada. Para quitarlos, desactive la casilla.

2. Después de editar una o varias de las secciones de la página **Ubicaciones,** seleccione **Guardar**.

    Las ubicaciones de contenido revisadas se muestran en la sección adecuada para las búsquedas seleccionadas.

3. Seleccione **Cerrar** para cerrar el Editor de búsqueda masiva.

4. En la **página Búsqueda de** contenido, seleccione  la búsqueda que ha editado y seleccione Iniciar búsqueda para reiniciar la búsqueda con las ubicaciones de contenido revisadas.

Estas son algunas sugerencias para editar ubicaciones de contenido mediante el Editor de búsqueda masiva:

- Puede editar Búsquedas de contenido para buscar en  todos los buzones  o sitios de la organización escribiendo Todo en una fila en blanco en los buzones para buscar o SharePoint sitios para buscar y, **a** continuación, active la casilla.

- Puede agregar varias ubicaciones de contenido a una o más búsquedas copiando varias filas de un archivo de texto o de un archivo Excel y, a continuación, pegandolas en una sección de la página **Ubicaciones.** Después de agregar nuevas ubicaciones, asegúrese de activar la casilla de cada búsqueda a la que desee agregar la ubicación.

    > [!TIP]
    > Para generar una lista de direcciones de correo electrónico para todos los usuarios de la organización, ejecute el comando de PowerShell en el paso 2 del paso [2: Generar](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step-2-generate-a-list-of-users)una lista de usuarios . O siga los pasos descritos en Obtener una lista de todas las direcciones [URL](/onedrive/list-onedrive-urls) OneDrive usuario de la organización para generar una lista de todos los OneDrive para la Empresa de la organización. Tenga en cuenta que tendrá que anexar la dirección URL del dominio MySite de su organización (por ejemplo, a los sitios OneDrive para la Empresa creados por https://contoso-my.sharepoint.com) el script. Después de tener una lista de direcciones de correo electrónico o  OneDrive para la Empresa, puede copiarlas y pegarlas en la página Ubicaciones del Editor de búsqueda masiva.

- Después de seleccionar **Guardar para** guardar los cambios en el Editor de búsqueda masiva, se validará la dirección de correo electrónico de los buzones que agregó a una búsqueda. Si la dirección de correo electrónico no existe, se muestra un mensaje de error que indica que no se puede encontrar el buzón. Las direcciones URL de los sitios no se validan.
