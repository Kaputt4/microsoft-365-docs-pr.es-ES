---
title: Retrasar la carga de imágenes y JavaScript en SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/3/2019
audience: Admin
ms.topic: troubleshooting
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
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
ms.openlocfilehash: 0914b318554badac3cb5ea28e4db641cbb6370e7
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68194805"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Retrasar la carga de imágenes y JavaScript en SharePoint Online

En este artículo se describe cómo puede reducir el tiempo de carga de las páginas de SharePoint Online mediante JavaScript para retrasar la carga de imágenes y también al esperar a cargar JavaScript no esencial hasta que se cargue la página.
  
Las imágenes pueden afectar negativamente a las velocidades de carga de página en SharePoint Online. De forma predeterminada, la mayoría de los exploradores de Internet modernos capturan previamente imágenes al cargar una página HTML. Esto puede hacer que la página sea innecesariamente lenta para cargarse si las imágenes no son visibles en la pantalla hasta que el usuario se desplaza hacia abajo. Las imágenes pueden impedir que el explorador cargue la parte visible de la página. Para solucionar este problema, puede usar JavaScript para omitir primero la carga de las imágenes. Además, la carga de JavaScript no esencial también puede ralentizar los tiempos de descarga en las páginas de SharePoint. En este tema se describen algunos métodos que puede usar para mejorar los tiempos de carga de páginas con JavaScript en SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Mejora de los tiempos de carga de páginas retrasando la carga de imágenes en páginas de SharePoint Online mediante JavaScript

Puede usar JavaScript para evitar que un explorador web capture imágenes previamente. Esto acelera la representación general de documentos. Para ello, quite el valor del atributo src de la \<img\> etiqueta y reemplácelo por la ruta de acceso a un archivo en un atributo de datos como: data-src. Por ejemplo:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

Con este método, el explorador no descarga las imágenes inmediatamente. Si la imagen ya está en la ventanilla, JavaScript indica al explorador que recupere la dirección URL del atributo de datos e insérela como el valor del atributo src. La imagen solo se carga a medida que el usuario se desplaza y entra en vista.
  
Para que todo esto suceda, deberá usar JavaScript.
  
En un archivo de texto, defina la función **isElementInViewport()** para comprobar si un elemento está en la parte del explorador que es visible para el usuario.
  
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

A continuación, use **isElementInViewport()** en la función **loadItemsInView().** La función **loadItemsInView()** cargará todas las imágenes que tengan un valor para el atributo data-src si se encuentran en la parte del explorador que es visible para el usuario. Agregue la siguiente función al archivo de texto:
  
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

Por último, llame a **loadItemsInView()** desde **window.onscroll()** como se muestra en el ejemplo siguiente. Esto garantiza que las imágenes que se encuentran en la ventanilla se carguen a medida que el usuario las necesite, pero no antes. Agregue lo siguiente al archivo de texto:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

Para SharePoint Online, debe adjuntar la siguiente función al evento de desplazamiento en la etiqueta #s4-workspace \<div\> . Esto se debe a que los eventos de ventana se invalidan para asegurarse de que la cinta de opciones permanece adjunta a la parte superior de la página.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Guarde el archivo de texto como un archivo JavaScript con la extensión .js, por ejemplo, delayLoadImages.js.
  
Una vez que haya terminado de escribir delayLoadImages.js, puede agregar el contenido del archivo a una página maestra en SharePoint Online. Para ello, agregue un vínculo de script al encabezado de la página maestra. Una vez que esté en una página maestra, JavaScript se aplicará a todas las páginas del sitio de SharePoint Online que usen ese diseño de página maestra. Como alternativa, si solo tiene previsto usar esta opción en una página del sitio, use el elemento web del editor de scripts para insertar JavaScript en la página. Consulte estos temas para obtener más información:
  
- [Aplicar una página maestra a un sitio de SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [Cómo crear un diseño de página en SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Ejemplo: Hacer referencia al archivo de delayLoadImages.js de JavaScript desde una página maestra en SharePoint Online
  
Para que esto funcione, también debe hacer referencia a jQuery en la página maestra. En el ejemplo siguiente, puede ver en la carga de página inicial que solo hay una imagen cargada, pero hay varias más en la página.
  
![Captura de pantalla que muestra una imagen cargada en la página.](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
En la captura de pantalla siguiente se muestra el resto de las imágenes que se descargan después de desplazarse a la vista.
  
![Captura de pantalla que muestra varias imágenes cargadas en la página.](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Retrasar la carga de imágenes mediante JavaScript puede ser una técnica eficaz para aumentar el rendimiento; sin embargo, si la técnica se aplica en un sitio web público, los motores de búsqueda no pueden rastrear las imágenes de la misma manera que rastrearían una imagen con formato regular. Esto puede afectar a las clasificaciones en los motores de búsqueda porque los metadatos de la propia imagen no están realmente ahí hasta que se carga la página. Los rastreadores del motor de búsqueda solo leen el HTML y, por lo tanto, no verán las imágenes como contenido en la página. Las imágenes son uno de los factores que se usan para clasificar las páginas en los resultados de búsqueda. Una manera de solucionar esto es usar texto introductorio para las imágenes.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>Ejemplo de código de GitHub: Inserción de JavaScript para mejorar el rendimiento

No se pierda el artículo y el ejemplo de código sobre [la inyección de JavaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759) proporcionados en GitHub.
  
## <a name="see-also"></a>Vea también

[Exploradores admitidos en Office 2013 y Aplicaciones Microsoft 365 para empresas](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Aplicar una página maestra a un sitio de SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[Cómo crear un diseño de página en SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)