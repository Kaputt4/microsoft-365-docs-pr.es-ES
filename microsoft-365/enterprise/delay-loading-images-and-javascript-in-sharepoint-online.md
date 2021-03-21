---
title: Retrasar la carga de imágenes y JavaScript en SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
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
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: Obtenga información sobre cómo reducir el tiempo de carga de las páginas de SharePoint Online mediante JavaScript para retrasar la carga de imágenes y JavaScript no esencial.
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919169"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Retrasar la carga de imágenes y JavaScript en SharePoint Online

En este artículo se describe cómo puede reducir el tiempo de carga de las páginas de SharePoint Online mediante JavaScript para retrasar la carga de imágenes y esperar a cargar JavaScript no esencial hasta después de que se cargue la página.
  
Las imágenes pueden afectar negativamente a las velocidades de carga de página en SharePoint Online. De forma predeterminada, la mayoría de los exploradores de Internet modernos capturan previamente imágenes al cargar una página HTML. Esto puede hacer que la página se cargue innecesariamente lentamente si las imágenes no están visibles en la pantalla hasta que el usuario se desplaza hacia abajo. Las imágenes pueden impedir que el explorador cargue la parte visible de la página. Para solucionar este problema, puede usar JavaScript para omitir la carga de las imágenes en primer lugar. Además, la carga de JavaScript no esencial también puede ralentizar los tiempos de descarga en las páginas de SharePoint. En este tema se describen algunos métodos que puede usar para mejorar los tiempos de carga de página con JavaScript en SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Mejorar los tiempos de carga de página retrasando la carga de imágenes en páginas de SharePoint Online mediante JavaScript

Puede usar JavaScript para evitar que un explorador web obtenga imágenes previamente. Esto acelera la representación general de documentos. Para ello, se quita el valor del atributo src de la etiqueta y se reemplaza por la ruta de acceso a un archivo en un atributo de datos \<img\> como: data-src. Por ejemplo:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

Al usar este método, el explorador no descarga las imágenes inmediatamente. Si la imagen ya está en la ventanilla, JavaScript indica al explorador que recupere la dirección URL del atributo data e insértela como el valor del atributo src. La imagen solo se carga a medida que el usuario se desplaza y entra en vista.
  
Para que todo esto suceda, tendrás que usar JavaScript.
  
En un archivo de texto, defina la función **isElementInViewport()** para comprobar si un elemento está o no en la parte del explorador que es visible para el usuario.
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

A continuación, **use isElementInViewport()** en la **función loadItemsInView().** La **función loadItemsInView()** cargará todas las imágenes que tengan un valor para el atributo data-src si están en la parte del explorador que está visible para el usuario. Agregue la siguiente función al archivo de texto:
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

Por último, llama **a loadItemsInView()** desde **dentro de window.onscroll()** como se muestra en el ejemplo siguiente. Esto garantiza que las imágenes que están en la ventanilla se carguen cuando el usuario las necesite, pero no antes. Agregue lo siguiente al archivo de texto:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

Para SharePoint Online, debe adjuntar la siguiente función al evento de desplazamiento en la etiqueta #s4 área de \<div\> trabajo. Esto se debe a que los eventos de ventana se invalidan para garantizar que la cinta de opciones permanece adjunta a la parte superior de la página.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Guarde el archivo de texto como un archivo JavaScript con la extensión .js, por ejemplo, delayLoadImages.js.
  
Una vez que haya terminado de escribir delayLoadImages.js, puede agregar el contenido del archivo a una página maestra en SharePoint Online. Para ello, agregue un vínculo de script al encabezado de la página maestra. Una vez que esté en una página maestra, JavaScript se aplicará a todas las páginas del sitio de SharePoint Online que usen ese diseño de página maestra. Como alternativa, si solo desea usarlo en una página del sitio, use el elemento web editor de scripts para insertar JavaScript en la página. Vea estos temas para obtener más información:
  
- [Aplicar una página maestra a un sitio de SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [Cómo crear un diseño de página en SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Ejemplo: referencia al archivo de delayLoadImages.js JavaScript desde una página maestra en SharePoint Online
  
Para que esto funcione, también debe hacer referencia a jQuery en la página maestra. En el siguiente ejemplo, puede ver en la carga de página inicial que solo hay una imagen cargada, pero hay varias más en la página.
  
![Captura de pantalla que muestra una imagen cargada en la página](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
La siguiente captura de pantalla muestra el resto de las imágenes que se descargan después de desplazarse a la vista.
  
![Captura de pantalla que muestra varias imágenes cargadas en la página](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Retrasar la carga de imágenes mediante JavaScript puede ser una técnica eficaz para aumentar el rendimiento; sin embargo, si la técnica se aplica en un sitio web público, los motores de búsqueda no podrán rastrear las imágenes de la misma manera que rastrearían una imagen formada regularmente. Esto puede afectar a las clasificaciones de los motores de búsqueda porque los metadatos de la imagen en sí no están realmente allí hasta que se carga la página. Los rastreadores del motor de búsqueda solo leen el CÓDIGO HTML y, por lo tanto, no verán las imágenes como contenido en la página. Las imágenes son uno de los factores que se usan para clasificar las páginas en los resultados de búsqueda. Una forma de evitar esto es usar texto introductorio para las imágenes.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>Ejemplo de código de GitHub: insertar JavaScript para mejorar el rendimiento

No se pierda el artículo y el ejemplo de código sobre la inyección [de JavaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759) proporcionado en GitHub.
  
## <a name="see-also"></a>Vea también

[Exploradores compatibles en Office 2013 y Aplicaciones de Microsoft 365 para empresas](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Aplicar una página maestra a un sitio de SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[Cómo crear un diseño de página en SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)