---
title: Cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Puede cambiar el tamaño predeterminado de los archivos PST que se descargan en el equipo al exportar los resultados de búsqueda de exhibición de documentos electrónicos.
ms.openlocfilehash: 7ba11dbb24af46c72321f2f0f514aa4a40616e4b
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64950299"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de eDiscovery

Cuando se usa la herramienta de exportación de eDiscovery para exportar los resultados de correo electrónico de una búsqueda de exhibición de documentos electrónicos desde las distintas herramientas de Microsoft eDiscovery, el tamaño predeterminado de un archivo PST que se puede exportar es de 10 GB. Si desea cambiar este tamaño predeterminado, puede editar el Registro de Windows en el equipo que use para exportar los resultados de la búsqueda. Una razón para hacerlo es que un archivo PST puede caber en medios extraíbles, como un DVD, un disco compacto o una unidad USB. 
  
> [!NOTE]
> La herramienta eDiscovery Export se usa para exportar los resultados de búsqueda cuando se usa la herramienta de búsqueda de contenido en el portal de cumplimiento de Microsoft Purview.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Crear una configuración del Registro para cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos

Realice el procedimiento siguiente en el equipo que usará para exportar los resultados de una búsqueda de exhibición de documentos electrónicos.
  
1. Cierre la herramienta eDiscovery Export si está abierta. 
    
2. Guarde el texto siguiente en un archivo del Registro de ventana con un sufijo de nombre de archivo .reg; por ejemplo, PstExportSize.reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    En el ejemplo anterior, el  `PstSizeLimitInBytes` valor se establece en 1.073.741.824 bytes o aproximadamente 1 GB. Estos son algunos otros valores de ejemplo para la  `PstSizeLimitInBytes` configuración. 
    
    |**Tamaño en GB (aprox.)**|**Tamaño en bytes**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Cambie el `PstSizeLimitInBytes` valor al tamaño máximo deseado de un archivo PST al exportar los resultados de búsqueda y, a continuación, guarde el archivo. 
    
4. En Windows Explorador, haga clic o haga doble clic en el archivo .reg que creó en los pasos anteriores.
    
5. En la ventana Usuario Access Control, haga clic en **Sí** para permitir que el Editor del Registro realice el cambio. 
    
6. Cuando se le pida que continúe, haga clic en **Sí**.
    
    El Editor del Registro muestra un mensaje que indica que la configuración se agregó correctamente al Registro.
    
7. Puede repetir los pasos del 3 al 6 para cambiar el valor de la configuración del  `PstSizeLimitInBytes` Registro. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Preguntas más frecuentes sobre cómo cambiar el tamaño predeterminado de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos

 **¿Por qué el tamaño predeterminado es 10 GB?**
  
El tamaño predeterminado de 10 GB se basaba en los comentarios del cliente; 10 GB es un buen equilibrio entre la cantidad óptima de contenido en un único PST y con una mínima probabilidad de daños en los archivos.
  
 **¿Debo aumentar o reducir el tamaño predeterminado de los archivos PST?**
  
Los clientes tienden a reducir el límite de tamaño para que los resultados de la búsqueda quepan en medios extraíbles que puedan enviar físicamente a otras ubicaciones de su organización. No se recomienda aumentar el tamaño predeterminado porque los archivos PST de más de 10 GB pueden tener problemas de daños.
  
 **¿En qué equipo tengo que hacer esto?**
  
Debe cambiar la configuración del Registro en cualquier equipo local en el que ejecute la herramienta eDiscovery Export.
  
 **Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**
  
No, no es necesario reiniciar el equipo. Sin embargo, si la herramienta de exportación de eDiscovery se está ejecutando, tendrá que cerrarla y reiniciarla después de cambiar esta configuración.
  
 **¿Se edita una clave del Registro existente o se crea una nueva clave?**
  
Se crea una nueva clave del Registro la primera vez que se ejecuta el archivo .reg que creó en este procedimiento. A continuación, la configuración se edita cada vez que cambia y vuelve a ejecutar el archivo de edición .reg.
