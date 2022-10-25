---
title: Deshabilitar informes al exportar los resultados de búsqueda de contenido
description: Edite el Registro de Windows en el equipo local para deshabilitar los informes al exportar los resultados de una búsqueda de contenido desde el portal de cumplimiento Microsoft Purview.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.collection:
- tier1
- purview-compliance
- content-search
ms.openlocfilehash: 13e47bc69a72ef5ebfcd38f2dee4c0652b0853f2
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687639"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>Deshabilitar informes al exportar los resultados de búsqueda de contenido

Cuando se usa la herramienta eDiscovery Export para exportar los resultados de una búsqueda de contenido en el portal de cumplimiento Microsoft Purview, la herramienta crea y exporta automáticamente dos informes que contienen información adicional sobre el contenido exportado. Estos informes son el archivo Results.csv y el archivo Manifest.xml (consulte la sección [Preguntas más frecuentes sobre cómo deshabilitar los informes de exportación](#frequently-asked-questions-about-disabling-export-reports) de este artículo para obtener descripciones detalladas de estos informes). Dado que estos archivos pueden ser muy grandes, puede acelerar el tiempo de descarga y ahorrar espacio en disco evitando que estos archivos se exporten. Para ello, cambie el Registro de Windows en el equipo que usa para exportar los resultados de la búsqueda. Si desea incluir los informes más adelante, puede editar la configuración del Registro. 
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="create-registry-settings-to-disable-the-export-reports"></a>Creación de la configuración del Registro para deshabilitar los informes de exportación

Realice el procedimiento siguiente en el equipo que usará para exportar los resultados de una búsqueda de contenido.
  
1. Cierre la herramienta eDiscovery Export si está abierta.
  
2. Realice uno o ambos de los pasos siguientes, en función del informe de exportación que quiera deshabilitar.

    - **Results.csv**

      Guarde el texto siguiente en un archivo del Registro de Windows con un sufijo de nombre de archivo .reg; por ejemplo, DisableResultsCsv.reg.

      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**

      Guarde el texto siguiente en un archivo del Registro de Windows con un sufijo de nombre de archivo .reg; por ejemplo, DisableManifestXml.reg.

      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. En el Explorador de Windows, seleccione o haga doble clic en el archivo .reg que creó en los pasos anteriores.

4. En la ventana Usuario Access Control, seleccione **Sí** para permitir que el Editor del Registro realice el cambio. 

5. Cuando se le pida que continúe, seleccione **Sí**.

    El Editor del Registro muestra un mensaje que indica que la configuración se agregó correctamente al Registro.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Edición de la configuración del Registro para volver a habilitar los informes de exportación

Si deshabilitó los informes Results.csv y Manifest.xml mediante la creación de los archivos .reg en el procedimiento anterior, puede editar esos archivos para volver a habilitar un informe para que se exporte con los resultados de la búsqueda. De nuevo, realice el siguiente procedimiento en el equipo que usará para exportar los resultados de una búsqueda de contenido.
  
1. Cierre la herramienta eDiscovery Export si está abierta.

2. Edite uno o ambos archivos de edición .reg que creó en el procedimiento anterior.

    - **Results.csv**

        Abra el archivo DisableResultsCsv.reg en el Bloc de notas, cambie el valor  `False` a y, a  `True`continuación, guarde el archivo. Por ejemplo, después de editar el archivo, tiene este aspecto:

        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**

        Abra el archivo DisableManifestXml.reg en el Bloc de notas, cambie el valor  `False` a y, a  `True`continuación, guarde el archivo. Por ejemplo, después de editar el archivo, tiene este aspecto:

      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. En el Explorador de Windows, seleccione o haga doble clic en un archivo .reg que editó en el paso anterior.

4. En la ventana Usuario Access Control, seleccione **Sí** para permitir que el Editor del Registro realice el cambio. 

5. Cuando se le pida que continúe, seleccione **Sí**.

    El Editor del Registro muestra un mensaje que indica que la configuración se agregó correctamente al Registro.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Preguntas más frecuentes sobre cómo deshabilitar informes de exportación

**¿Cuáles son los informes de Results.csv y Manifest.xml?**
  
Los archivos Results.csv y Manifest.xml contienen información adicional sobre el contenido exportado.
  
- **Results.csv** Documento de Excel que contiene información sobre cada elemento que se descarga como resultado de la búsqueda. Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos: 

  - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
  - La fecha en que se envió o se recibió el mensaje.
  - La línea Asunto del mensaje.
  - El remitente y los destinatarios del mensaje.
  - Si el mensaje es un mensaje duplicado si ha habilitado la desduplicación al exportar los resultados de la búsqueda. Los mensajes duplicados tendrán un valor en la columna **Parent ItemId** que identifica el mensaje como duplicado. El valor de la columna **Parent ItemId** es el mismo que el valor de la columna **Item DocumentId** del mensaje que se exportó.

  En el caso de los documentos de SharePoint y sitios de OneDrive para la Empresa, el registro de resultados contiene información sobre cada documento, incluidos:

  - La dirección URL del documento.
  - La dirección URL de la colección de sitio donde se ubica el documento.
  - La fecha en la que el documento se modificó por última vez.
  - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).

- **Manifest.xml** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda. La información de este informe es la misma que la Results.csv informe, pero está en el formato especificado por el modelo de referencia de detección electrónica (EDRM). Para obtener más información sobre EDRM, vaya a [https://www.edrm.net](https://www.edrm.net).

**¿Cuándo debo deshabilitar la exportación de estos informes?**
  
Depende de sus necesidades específicas. Muchas organizaciones no requieren información adicional sobre los resultados de búsqueda y no necesitan estos informes.
  
**¿En qué equipo tengo que hacer esto?**
  
Tiene que cambiar la configuración del Registro en cualquier equipo local en el que ejecute la herramienta eDiscovery Export. 
  
**Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**
  
No, no es necesario reiniciar el equipo. Pero si se está ejecutando la herramienta eDiscovery Export, debe cerrarla y reiniciarla después de cambiar la configuración del Registro.
  
**¿Se edita una clave del Registro existente o se crea una nueva clave?**
  
Se crea una nueva clave del Registro la primera vez que ejecuta el archivo .reg que creó en el procedimiento de este artículo. A continuación, la configuración se edita cada vez que cambia y vuelve a ejecutar el archivo de edición .reg.
