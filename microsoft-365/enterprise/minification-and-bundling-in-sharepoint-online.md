---
title: Minificación y agrupación en SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Obtenga información sobre cómo usar técnicas de minificación y agrupación con Web Essentials para reducir las solicitudes HTTP y el tiempo que tarda en cargar páginas en SharePoint Online.
ms.openlocfilehash: 7214d396dc39147f6864144420f8fa3fd61195b0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166963"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>Minificación y agrupación en SharePoint Online

En este artículo se describe cómo usar técnicas de minificación y agrupación con Web Essentials para reducir el número de solicitudes HTTP y reducir el tiempo necesario para cargar páginas en SharePoint Online.
  
Al personalizar el sitio web, puede terminar agregando un gran número de archivos adicionales al servidor para admitir la personalización. Agregar JavaScript, CSS e imágenes adicionales aumenta el número de solicitudes HTTP al servidor, lo que a su vez aumenta el tiempo necesario para mostrar una página web. Si tiene varios archivos del mismo tipo, puede agrupar estos archivos para que la descarga de estos archivos sea más rápida.
  
Para los archivos JavaScript y CSS, también puede usar un enfoque denominado minification, donde se reduce el tamaño total de los archivos quitando espacios en blanco y otros caracteres que no son necesarios.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Minification and bundling JavaScript and CSS files with Web Essentials

Puede usar software de terceros como Web Essentials para empaquetar archivos CSS y JavaScript.
  
> [!IMPORTANT]
> Web Essentials es un proyecto basado en la comunidad de código abierto de terceros. El software es una extensión para Visual Studio 2012 y Visual Studio 2013 es compatible con Microsoft. Para descargar Web Essentials, visite el sitio web en [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) . 
  
Web Essentials ofrece dos formas de agrupación:
  
- .bundle: para archivos CSS y JavaScript
    
- .sprite: para imágenes (solo disponible en Visual Studio 2013)
    
Puede usar Web Essentials si tiene una característica existente con algunos elementos de personalización de marca a los que se hace referencia dentro de una página maestra personalizada, como:
  
![Captura de pantalla del elemento brand en la página maestra personalizada.](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Para crear un paquete TE000127218 y CSS en Web Essentials**
  
1. En Visual Studio, en el Explorador de soluciones, seleccione los archivos que desea incluir en la agrupación.
    
2. Haga clic con el botón secundario en los archivos seleccionados y, a continuación, seleccione **Web Essentials** Crear archivo de agrupación de \> **JavaScript** en el menú contextual. Por ejemplo: 
    
    ![Captura de pantalla que muestra las opciones de menú de Web Essentials.](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>Visualización de los resultados de la agrupación de archivos JavaScript y CSS

Al crear una agrupación de JavaScript y CSS, Web Essentials crea un archivo XML denominado archivo de receta que identifica los archivos JavaScript y CSS, así como otra información de configuración: 
  
![Captura de pantalla del archivo de recetas de JavaScript y CSS.](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Además, si la marca de minify se establece en true en la receta de agrupación, los archivos se reducen en tamaño y se agrupan juntos. Esto significa que se crearon nuevas versiones minificadas de los archivos JavaScript a las que puede hacer referencia en la página maestra.
  
![Captura de pantalla de la marca de minify establecida en true.](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
Al cargar una página desde el sitio web, puede usar las herramientas de desarrollo del explorador web, como Internet Explorer 11, para ver el número de solicitudes enviadas al servidor y el tiempo que tardó cada archivo en cargarse.
  
La siguiente figura es el resultado de cargar los archivos JavaScript y CSS antes de la minificación.
  
![Captura de pantalla que muestra 80 elementos que se descargan.](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
Después de agrupar los archivos CSS y JavaScript, el número de solicitudes se redujo a 74 y cada archivo tardó un poco más que los archivos originales en descargarse individualmente:
  
![Captura de pantalla que muestra 74 elementos que se descargan.](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
Después de la agrupación, el archivo de agrupación de JavaScript se reduce significativamente de 815 KB a 365 KB:
  
![Captura de pantalla que muestra el tamaño de descarga reducido.](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Agrupación de imágenes mediante la creación de un sprite de imagen

De forma similar a la forma en que agrupa archivos JavaScript y CSS, puede combinar muchos iconos pequeños y otras imágenes comunes en una hoja de sprites más grande y, a continuación, usar CSS para revelar las imágenes individuales. En lugar de descargar cada imagen individual, el explorador web del usuario descarga la hoja de sprites una vez y, a continuación, la almacena en caché en el equipo local. Esto mejora el rendimiento de carga de página al reducir el número de descargas y viajes de ida y vuelta al servidor web.
  
 **Para crear un sprite de imagen en Web Essentials**
  
1. En Visual Studio, en el Explorador de soluciones, seleccione los archivos que desea incluir en la agrupación.
    
2. Haga clic con el botón secundario en los archivos seleccionados y, a continuación, seleccione **Web Essentials** Crear sprite de imagen \>  en el menú contextual. Por ejemplo: 
    
    ![Captura de pantalla que muestra cómo crear un sprite de imagen.](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Elija una ubicación para guardar el archivo sprite. El archivo .sprite es un archivo XML que describe la configuración y los archivos del sprite. Las siguientes figuras muestran un ejemplo de un archivo PNG sprite y su correspondiente archivo XML .sprite.
    
    ![Captura de pantalla de un archivo sprite.](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Captura de pantalla del archivo XML sprite.](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

