---
title: Cambiar el tamaño de los archivos PST al exportar resultados de búsqueda de exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Puede cambiar el tamaño predeterminado de los archivos PST que se descargan en el equipo al exportar los resultados de búsqueda de exhibición de documentos electrónicos.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942923"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Cambiar el tamaño de los archivos PST al exportar resultados de búsqueda de exhibición de documentos electrónicos

Cuando usa la herramienta de exportación de exhibición de documentos electrónicos para exportar los resultados de correo electrónico de una búsqueda de exhibición de documentos electrónicos desde las distintas herramientas de exhibición de documentos electrónicos de Microsoft, el tamaño predeterminado de un archivo PST que se puede exportar es de 10 GB. Si desea cambiar este tamaño predeterminado, puede editar el registro de Windows en el equipo que use para exportar los resultados de búsqueda. Una razón para hacerlo es para que un archivo PST pueda caber en medios extraíbles, como un DVD, un disco compacto o una unidad USB. 
  
> [!NOTE]
> La herramienta de exportación de exhibición de documentos electrónicos se usa para exportar los resultados de búsqueda cuando se usa la herramienta de búsqueda de contenido en el Centro de seguridad y cumplimiento de &, la exhibición de documentos electrónicos In-Place en Exchange Online y el Centro de exhibición de documentos electrónicos en SharePoint Online.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Crear una configuración del Registro para cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos

Realice el siguiente procedimiento en el equipo que usará para exportar los resultados de una búsqueda de exhibición de documentos electrónicos.
  
1. Cierre la herramienta de exportación de exhibición de documentos electrónicos si está abierta. 
    
2. Guarde el texto siguiente en un archivo del Registro de ventana mediante un sufijo de nombre de archivo .reg; por ejemplo, PstExportSize.reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    En el ejemplo anterior, el valor se establece en  `PstSizeLimitInBytes` 1.073.741.824 bytes o aproximadamente 1 GB. Estos son algunos otros valores de ejemplo para la  `PstSizeLimitInBytes` configuración. 
    
    |**Tamaño en GB (aprox.)**|**Tamaño en bytes**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Cambie el valor al tamaño máximo deseado de un archivo PST al exportar los resultados de la búsqueda `PstSizeLimitInBytes` y, a continuación, guarde el archivo. 
    
4. En Windows, haga clic o haga doble clic en el archivo .reg que creó en los pasos anteriores.
    
5. En la ventana Control de acceso de usuario, haga clic **en Sí** para permitir que el Editor del Registro realice el cambio. 
    
6. Cuando se le pida que continúe, haga clic **en Sí**.
    
    El Editor del Registro muestra un mensaje que indica que la configuración se agregó correctamente al Registro.
    
7. Puede repetir los pasos 3 a 6 para cambiar el valor de la configuración  `PstSizeLimitInBytes` del Registro. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Preguntas más frecuentes sobre cómo cambiar el tamaño predeterminado de los archivos PST al exportar los resultados de búsqueda de exhibición de documentos electrónicos

 **¿Por qué el tamaño predeterminado es de 10 GB?**
  
El tamaño predeterminado de 10 GB se basaba en los comentarios de los clientes; 10 GB es un buen equilibrio entre la cantidad óptima de contenido en un solo PST y con una probabilidad mínima de daños en los archivos.
  
 **¿Debo aumentar o disminuir el tamaño predeterminado de los archivos PST?**
  
Los clientes tienden a reducir el límite de tamaño para que los resultados de la búsqueda quepa en medios extraíbles que puedan enviar físicamente a otras ubicaciones de su organización. No se recomienda aumentar el tamaño predeterminado porque los archivos PST de más de 10 GB pueden tener problemas de daños.
  
 **¿En qué equipo tengo que hacerlo?**
  
Debe cambiar la configuración del Registro en cualquier equipo local en el que ejecute la herramienta de exportación de exhibición de documentos electrónicos.
  
 **Después de cambiar esta configuración, ¿tengo que reiniciar el equipo?**
  
No, no es necesario reiniciar el equipo. Pero, si la herramienta de exportación de exhibición de documentos electrónicos se está ejecutando, tendrás que cerrarla y reiniciarla después de cambiar esta configuración.
  
 **¿Se edita una clave del Registro existente o se crea una clave nueva?**
  
Se crea una nueva clave del Registro la primera vez que se ejecuta el archivo .reg que creó en este procedimiento. A continuación, la configuración se modifica cada vez que cambia y vuelve a ejecutar el archivo de edición .reg.
