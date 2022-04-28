---
title: Optimización de imágenes para SharePoint sitios de publicación clásicos en línea
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 9/18/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: Obtenga información sobre cómo usar representaciones y sprites para mejorar el rendimiento de las imágenes en los sitios de publicación clásicos de SharePoint Online.
ms.openlocfilehash: d309d2c0d725988ec9958d96ae812b760e8a16e4
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095716"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>Optimización de imágenes para SharePoint sitios de publicación clásicos en línea

La velocidad de carga de una página web depende del tamaño combinado de todos los componentes necesarios para representar la página, incluidas las imágenes, HTML, JavaScript y CSS. Las imágenes son una excelente manera de hacer que su sitio sea más atractivo, pero su tamaño puede afectar al rendimiento. Mediante la optimización de las imágenes con compresión y cambio de tamaño, y el uso de sprites, puede compensar los efectos de imágenes muy grandes. Con SharePoint representaciones de imágenes, puede cargar una sola imagen grande y mostrar las secciones de la imagen, lo que permite reutilizarla en lugar de volver a cargarla.

>[!NOTE]
>Este tema se aplica a SharePoint sitios de publicación clásicos en línea, no a sitios de portal modernos. Para obtener información sobre la optimización de imágenes en SharePoint sitios del portal moderno en línea, vea [Optimizar imágenes en SharePoint páginas del portal moderno en línea](modern-image-optimization.md).
  
## <a name="using-sprites-to-speed-up-image-loading"></a>Uso de sprites para acelerar la carga de imágenes

![Captura de pantalla de spcommon.](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)

Un sprite de imagen contiene muchas imágenes más pequeñas. Con CSS, selecciona una parte de la imagen compuesta para mostrarla en una parte determinada de la página con un posicionamiento absoluto. Básicamente, mueve una sola imagen alrededor de la página en lugar de cargar varias imágenes y hace que una pequeña parte de esa imagen sea visible a través de una ventana pequeña donde la parte necesaria de la imagen sprite se muestra al usuario final. SharePoint Online usa sprites para mostrar sus distintos iconos en el archivo de spcommon.png sprite.

Lo que se trata aquí:
- Compresión de imágenes
- Optimización de imágenes
- SharePoint representaciones de imágenes
   
Esto puede aumentar el rendimiento porque solo se descarga una imagen en lugar de varias y, a continuación, se almacena en caché y se reutiliza esa imagen. Incluso si la imagen no permanece almacenada en caché, al tener una sola imagen en lugar de varias imágenes, este método reduce el número total de solicitudes HTTP al servidor, lo que reducirá los tiempos de carga de páginas. Esta es realmente una forma de agrupación de imágenes. Se trata de una técnica muy útil si las imágenes no cambian con mucha frecuencia, por ejemplo, iconos, como se muestra en el ejemplo de SharePoint proporcionado anteriormente. Puede usar [Web Essentials](https://vswebessentials.com/), un proyecto de código abierto y basado en la comunidad de terceros para lograrlo fácilmente en Microsoft Visual Studio. Para obtener más información, vea [Minification and bundling in SharePoint Online(Minification and bundling in SharePoint Online](./minification-and-bundling-in-sharepoint-online.md)).
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>Uso de la compresión y optimización de imágenes para acelerar la carga de páginas

La compresión y optimización de imágenes consiste en reducir el tamaño de archivo de las imágenes que se usan en el sitio. A menudo, la mejor técnica para reducir el tamaño de una imagen es cambiar el tamaño de la imagen a las dimensiones máximas que se verán en el sitio. No tiene sentido tener una imagen más grande de lo que nunca se verá. Asegurarse de que las imágenes son de las dimensiones correctas mediante un editor de imágenes es una manera rápida y sencilla de reducir el tamaño de la página.
  
Una vez que las imágenes tienen el tamaño correcto, el siguiente paso es optimizar la compresión de estas imágenes. Hay varias herramientas disponibles para su compresión y optimización, como Photo Gallery y herramientas de terceros. La clave para la compresión es reducir el tamaño del archivo tanto como sea posible sin perder ninguna calidad discernible para los usuarios finales. Asegúrese de probar los archivos comprimidos en una pantalla de alta definición para asegurarse de que seguirán teniendo un buen aspecto.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>Acelerar las descargas de páginas mediante SharePoint representaciones de imágenes

Las representaciones de imágenes son una característica de SharePoint Online que permite ofrecer diferentes versiones de imágenes basadas en dimensiones de imagen predefinidas. Esto es especialmente importante cuando hay contenido de imagen generado por el usuario o las dimensiones de imagen, como el ancho y el alto, se fijan mediante CSS en el sitio. Incluso si CSS fija una imagen, la imagen de resolución completa se sigue cargando. En este caso, el tamaño del archivo se puede reducir mediante representaciones de imágenes.
  
> [!NOTE]
> Las representaciones solo están disponibles para SharePoint cuando la publicación está habilitada. Puede habilitar la publicación en Configuración \> sitio Configuración \> Administrar características \> del sitio SharePoint Server Publishing. De lo contrario, la opción no aparecerá.
  
El cambio de tamaño de la representación de imágenes funciona tomando la dimensión más pequeña que defina, ya sea ancho o alto, y, a continuación, cambiando el tamaño de la imagen para que la otra dimensión cambie de tamaño automáticamente en función de la relación de aspecto bloqueada. De forma predeterminada, recortará la imagen del centro por las dimensiones restantes. Por ejemplo, si define una representación de 100 píxeles de ancho y 50 píxeles de alto y la imagen original tiene 1000 px de ancho y 800 px de alto, se cambiará el tamaño para que la dimensión de 800 px sea ahora de 50 px y la dimensión de 1000 px (ahora 62,5 px) se recorte desde el centro de la imagen.
  
Los pasos son relativamente sencillos, pero para que las imágenes usen las representaciones, las representaciones deben estar en el sitio SharePoint antes de agregar las imágenes. Además, también debe tener activadas las características SharePoint Server Publishing Infrastructure (Site Collection Level) y SharePoint Server Publishing (Site Level).
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>Adición de una representación de imágenes para acelerar la carga de páginas
  
1. Compruebe que la cuenta de usuario que realiza este procedimiento tiene, como mínimo, permisos de diseño para el sitio de nivel superior de la colección de sitios y que el sitio se está publicando en una página web.

2. En un explorador web, vaya al sitio de nivel superior de la colección de sitios de publicación.

3. Elija el icono **Configuración**.

4. En la página **Sitio Configuración**, en la sección **Apariencia**, verá las representaciones de imágenes integradas.

    Puede usar las representaciones predefinidas o elegir **Representaciones** de imágenes para crear una nueva.

    ![Captura de pantalla de representación de imágenes.](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. En la página **Representaciones de imágenes**, elija **Agregar nuevo elemento**.

    ![Captura de pantalla de Agregar nuevo elemento.](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. En la página **Nueva representación de imagen**, en el cuadro **Nombre**, escriba un nombre para la representación.

7. En los cuadros de texto **Ancho** y **Alto**, escriba el ancho y alto, en píxeles, de la representación y luego elija **Guardar**.

    ![Captura de pantalla del nombre de representación de imágenes.](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>Recorte personalizado con representaciones de imágenes

De forma predeterminada, se genera una representación de imágenes desde el centro de la imagen. Puede ajustar la representación de imagen para imágenes individuales al recortar la parte de la imagen que desea usar. Puede recortar las imágenes de forma individual, por representación. Recortar las imágenes acelera la carga de páginas mediante la caché de blobs de SharePoint para crear una versión de la imagen para cada representación. De este modo, se reduce la carga del servidor porque la imagen solo cambia de tamaño una vez y, a continuación, está lista para servir a los usuarios finales varias veces. Para obtener más información sobre cómo recortar una representación de imágenes, vea [Recortar una representación de imágenes](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels).
