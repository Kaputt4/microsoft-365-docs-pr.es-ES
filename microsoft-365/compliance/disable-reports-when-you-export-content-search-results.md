---
title: Deshabilitar informes al exportar los resultados de búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Edite el Windows en el equipo local para deshabilitar los informes al exportar los resultados de una búsqueda de contenido desde el Centro de seguridad & cumplimiento.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817859"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>Deshabilitar informes al exportar los resultados de búsqueda de contenido

Cuando se usa la herramienta de exportación de exhibición de documentos electrónicos para exportar los resultados de una búsqueda de contenido en el Centro de cumplimiento de seguridad &, la herramienta crea y exporta automáticamente dos informes que contienen información adicional sobre el contenido exportado. Estos informes son el archivo Results.csv y el archivo [](#frequently-asked-questions-about-disabling-export-reports) Manifest.xml (consulte la sección Preguntas más frecuentes sobre cómo deshabilitar informes de exportación en este tema para obtener descripciones detalladas de estos informes). Dado que estos archivos pueden ser muy grandes, puede acelerar el tiempo de descarga y ahorrar espacio en disco al impedir que estos archivos se exporten. Para ello, cambie el registro de Windows en el equipo que use para exportar los resultados de la búsqueda. Si desea incluir los informes más adelante, puede editar la configuración del Registro. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Crear la configuración del Registro para deshabilitar los informes de exportación

Realice el siguiente procedimiento en el equipo que usará para exportar los resultados de una búsqueda de contenido.
  
1. Cierre la herramienta de exportación de exhibición de documentos electrónicos si está abierta.
    
2. Realice uno o ambos de los pasos siguientes, según el informe de exportación que desee deshabilitar.
    
    - **Results.csv**
    
      Guarde el texto siguiente en un archivo Windows del Registro mediante un sufijo de nombre de archivo de .reg; por ejemplo, DisableResultsCsv.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      Guarde el texto siguiente en un archivo Windows del Registro mediante un sufijo de nombre de archivo de .reg; por ejemplo, DisableManifestXml.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. En Windows, haga clic o haga doble clic en el archivo .reg que creó en los pasos anteriores.
    
4. En la ventana Control de acceso de usuario, haga clic **en Sí** para permitir que el Editor del Registro realice el cambio. 
    
5. Cuando se le pida que continúe, haga clic **en Sí**.
    
    El Editor del Registro muestra un mensaje que indica que la configuración se agregó correctamente al Registro.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Editar la configuración del Registro para volver a habilitar los informes de exportación

Si deshabilitó los informes Results.csv y Manifest.xml mediante la creación de los archivos .reg en el procedimiento anterior, puede editar esos archivos para volver a habilitar un informe para que se exporte con los resultados de la búsqueda. De nuevo, realice el siguiente procedimiento en el equipo que usará para exportar los resultados de una búsqueda de contenido.
  
1. Cierre la herramienta de exportación de exhibición de documentos electrónicos si está abierta.
    
2. Edite uno o ambos archivos de edición .reg que creó en el procedimiento anterior.
    
    - **Results.csv**
    
        Abra el archivo DisableResultsCsv.reg en Bloc de notas, cambie el valor a y, a `False` continuación, guarde el `True` archivo. Por ejemplo, después de editar el archivo, tiene este aspecto:
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        Abra el archivo DisableManifestXml.reg en Bloc de notas, cambie el valor a y, a `False` continuación, guarde el `True` archivo. Por ejemplo, después de editar el archivo, tiene este aspecto:
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. En Windows, haga clic o haga doble clic en un archivo .reg que editó en el paso anterior.
    
4. En la ventana Control de acceso de usuario, haga clic **en Sí** para permitir que el Editor del Registro realice el cambio. 
    
5. Cuando se le pida que continúe, haga clic **en Sí**.
    
    El Editor del Registro muestra un mensaje que indica que la configuración se agregó correctamente al Registro.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Preguntas más frecuentes sobre cómo deshabilitar informes de exportación

 **¿Cuáles son Results.csv y Manifest.xml informes?**
  
Los Results.csv archivos Manifest.xml contienen información adicional sobre el contenido exportado.
  
- **Results.csv** Un Excel que contiene información sobre cada elemento que se descarga como resultado de la búsqueda. Para el correo electrónico, un registro de resultados contiene información acerca de cada mensaje, incluidos: 
    
  - La ubicación del mensaje en el buzón de origen (incluido si el mensaje se encuentra en el buzón de archivo o en el principal).
    
  - La fecha en que se envió o se recibió el mensaje.
    
  - La línea Asunto del mensaje.
    
  - El remitente y los destinatarios del mensaje.
    
  - Si el mensaje es un mensaje duplicado si habilitó la desduplicación al exportar los resultados de la búsqueda. Los mensajes duplicados tendrán un valor en la **columna ItemId** principal que identifica el mensaje como duplicado. El valor de la **columna ItemId** primario es el mismo que el valor de la columna **Item DocumentId** del mensaje exportado. 
    
    Para los documentos de SharePoint y OneDrive para la Empresa, el registro de resultados contiene información sobre cada documento, incluidos:
    
  - La dirección URL del documento.
    
  - La dirección URL de la colección de sitio donde se ubica el documento.
    
  - La fecha en la que el documento se modificó por última vez.
    
  - El nombre del documento (que está ubicado en la columna Asunto del registro de resultados).
    
- **Manifest.xml** Un archivo de manifiesto (en formato XML) que contiene información sobre cada elemento incluido en los resultados de la búsqueda. La información de este informe es la misma que el informe Results.csv, pero está en el formato especificado por el Modelo de referencia de detección electrónica (EDRM). Para obtener más información acerca de EDRM, vaya a [https://www.edrm.net](https://www.edrm.net) .
    
 **¿Cuándo debo deshabilitar la exportación de estos informes?**
  
Depende de sus necesidades específicas. Muchas organizaciones no requieren información adicional sobre los resultados de búsqueda y no necesitan estos informes.
  
 **¿En qué equipo tengo que hacerlo?**
  
 Debe cambiar la configuración del Registro en cualquier equipo local en el que ejecute la herramienta de exportación de exhibición de documentos electrónicos. 
  
 **Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**
  
No, no es necesario reiniciar el equipo. Pero si la herramienta de exportación de exhibición de documentos electrónicos se está ejecutando, debe cerrarla y reiniciarla después de cambiar la configuración del Registro.
  
 **¿Se edita una clave del Registro existente o se crea una clave nueva?**
  
Se crea una nueva clave del Registro la primera vez que se ejecuta el archivo .reg que creó en el procedimiento de este tema. A continuación, la configuración se modifica cada vez que cambia y vuelve a ejecutar el archivo de edición .reg.
