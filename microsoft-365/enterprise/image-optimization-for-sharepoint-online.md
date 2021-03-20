---
title: Optimización de imágenes para sitios de publicación clásica de SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
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
description: Obtenga información sobre cómo usar representaciones y sprites para mejorar el rendimiento de la imagen en los sitios de publicación clásicos de SharePoint Online.
ms.openlocfilehash: 0f0dd078ce28b86fc998b2f83ac19d04b1a3ab02
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907485"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>Optimización de imágenes para sitios de publicación clásica de SharePoint Online

La velocidad de carga de una página web depende del tamaño combinado de todos los componentes necesarios para representar la página, incluidas imágenes, HTML, JavaScript y CSS. Las imágenes son una excelente manera de hacer que el sitio sea más atractivo, pero su tamaño puede afectar al rendimiento. Al optimizar las imágenes con compresión y cambiar el tamaño y usar sprites, puedes compensar los efectos de imágenes muy grandes. Con representaciones de imágenes de SharePoint, puede cargar una sola imagen grande y mostrar secciones de la imagen, lo que permite reutilizarla en lugar de volver a cargarla.

>[!NOTE]
>Este tema se aplica a los sitios de publicación clásicos de SharePoint Online, no a los sitios de portal modernos. Para obtener información sobre la optimización de imágenes en sitios de portal modernos de SharePoint Online, vea Optimizar imágenes en páginas [de portal modernas de SharePoint Online.](modern-image-optimization.md)
  
## <a name="using-sprites-to-speed-up-image-loading"></a>Uso de sprites para acelerar la carga de imágenes

|||
|:-----|:-----|
| Un sprite de imagen contiene muchas imágenes más pequeñas. Con CSS, se selecciona una parte de la imagen compuesta para mostrar en una parte determinada de la página con posicionamiento absoluto. Básicamente, mueves una sola imagen alrededor de la página en lugar de cargar varias imágenes y haces que una pequeña parte de esa imagen sea visible a través de una pequeña ventana donde se muestra al usuario final la parte necesaria de la imagen sprite. SharePoint Online usa sprites para mostrar sus diversos iconos en el objeto sprite spcommon.png.  <br/>  Lo que se trata aquí:  <br/>  Compresión de imágenes  <br/>  Optimización de imágenes  <br/>  Representaciones de imágenes de SharePoint  <br/> |![Captura de pantalla de spcommon](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
Esto puede aumentar el rendimiento porque solo se descarga una imagen en lugar de varias y, a continuación, se almacena en caché y se reutiliza esa imagen. Incluso si la imagen no permanece almacenada en caché, al tener una sola imagen en lugar de varias imágenes, este método reduce el número total de solicitudes HTTP al servidor, lo que reducirá los tiempos de carga de página. Esto es realmente una forma de agrupación de imágenes. Se trata de una técnica muy útil si las imágenes no cambian muy a menudo, por ejemplo, iconos, como se muestra en el ejemplo de SharePoint proporcionado anteriormente. Puede usar [Web Essentials](https://vswebessentials.com/), un proyecto basado en la comunidad de código abierto de terceros para lograrlo fácilmente en Microsoft Visual Studio. Para obtener más información, vea [Minification and bundling in SharePoint Online](./minification-and-bundling-in-sharepoint-online.md).
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>Uso de la compresión y optimización de imágenes para acelerar la carga de páginas

La compresión y optimización de imágenes se trata de reducir el tamaño del archivo de las imágenes que se usan en el sitio. A menudo, la mejor técnica para reducir el tamaño de una imagen es cambiar el tamaño de la imagen a las dimensiones máximas que se verán en el sitio. No tiene sentido tener una imagen más grande de la que se verá. Asegurarse de que las imágenes tienen las dimensiones correctas mediante un editor de imágenes es una forma rápida y fácil de reducir el tamaño de la página.
  
Una vez que las imágenes tienen el tamaño correcto, el siguiente paso es optimizar la compresión de estas imágenes. Hay varias herramientas disponibles para la compresión y optimización, incluidas la Galería de fotos y las herramientas de terceros. La clave de la compresión es reducir el tamaño del archivo tanto como sea posible sin perder ninguna calidad perceptible para los usuarios finales. Asegúrese de probar los archivos comprimidos en una pantalla de alta definición para asegurarse de que seguirán teniendo un buen aspecto.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>Acelerar las descargas de páginas mediante representaciones de imágenes de SharePoint

Las representaciones de imágenes son una característica de SharePoint Online que permite servir diferentes versiones de imágenes en función de dimensiones de imagen predefinidas. Esto es especialmente importante cuando hay contenido de imagen generado por el usuario o las dimensiones de imagen, como el ancho y el alto, se fijan por el CSS en el sitio. Incluso si css fija una imagen, la imagen de resolución completa se sigue cargando. En este caso, el tamaño del archivo se puede reducir mediante representaciones de imagen.
  
> [!NOTE]
> Las representaciones solo están disponibles para SharePoint cuando la publicación está habilitada. Puede habilitar la publicación en Configuración del sitio \> Administrar características del sitio \> \> SharePoint Server Publishing. De lo contrario, la opción no aparecerá.
  
El cambio de tamaño de la representación de imagen funciona tomando la dimensión más pequeña que definas, ya sea el ancho o el alto, y luego cambia el tamaño de la imagen para que la otra dimensión cambie automáticamente de tamaño en función de la relación de aspecto bloqueada. De forma predeterminada, recortará la imagen del centro en las dimensiones restantes. Por ejemplo, si define una representación de 100 píxeles de ancho y 50 píxeles de alto y la imagen original tiene 1000 píxeles de ancho y 800 píxeles de alto, se ajustará para que la dimensión de 800 píxeles tenga ahora 50 píxeles y la dimensión de 1000 píxeles (ahora 62,5 px) se recorta desde el centro de la imagen.
  
Los pasos son relativamente sencillos, pero para que las imágenes usen las representaciones, las representaciones deben estar en el sitio de SharePoint antes de agregar las imágenes. Además, también debe tener activadas las características Infraestructura de publicación de SharePoint Server (nivel de colección de sitios) y Publicación de SharePoint Server (nivel de sitio).
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>Agregar una representación de imagen para acelerar la carga de páginas
  
1. Compruebe que la cuenta de usuario que realiza este procedimiento tiene, como mínimo, permisos de diseño en el sitio de nivel superior de la colección de sitios y que el sitio se está publicando en una página web.

2. En un explorador web, vaya al sitio de nivel superior de la colección de sitios de publicación.

3. Elija el icono **Configuración**.

4. En la **página Configuración del** sitio, en la sección **Aspecto,** verá las representaciones de imágenes integradas.

    Puedes usar las representaciones listas para usar o elegir **Representaciones** de imagen para crear una nueva.

    ![Captura de pantalla de representación de imágenes](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. En la página **Representaciones de imágenes**, elija **Agregar nuevo elemento**.

    ![Captura de pantalla de Agregar nuevo elemento](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. En la página **Nueva representación de imagen**, en el cuadro **Nombre**, escriba un nombre para la representación.

7. En los cuadros de texto **Ancho** y **Alto**, escriba el ancho y alto, en píxeles, de la representación y luego elija **Guardar**.

    ![Captura de pantalla del nombre de la representación de imagen](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>Recorte personalizado con representaciones de imágenes

De forma predeterminada, se genera una representación de imágenes desde el centro de la imagen. Puede ajustar la representación de imagen para imágenes individuales al recortar la parte de la imagen que desea usar. Puede recortar las imágenes de forma individual, por representación. Recortar las imágenes acelera la carga de páginas mediante la memoria caché de blobs de SharePoint para crear una versión de la imagen para cada representación. De esta forma, la carga del servidor se reduce porque la imagen solo cambia de tamaño una vez y, a continuación, está lista para servir a los usuarios finales varias veces. Para obtener más información sobre cómo recortar una representación de imagen, vea [Recortar una representación de imagen.](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels)
