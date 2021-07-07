---
title: Revisar
description: Sección Revisar después de la incorporación.
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323288"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>Paso 6: Revisar las selecciones para crear el paquete.

1.  En esta pestaña, el servicio muestra los detalles de la prueba y ejecuta una comprobación de integridad rápida. 

    A ```Validation passed``` o message shows whether you can proceed to next steps or ```Validation failed``` not.

2.  Revise los detalles de la prueba y, si se cumple, haga clic en el ```Create``` botón. 

![Ver validación](Media/validation.png)

3.  Esto incorporará el paquete al entorno base de prueba. Si el paquete se crea correctamente, se desencadenará una prueba automatizada que compruebe si el paquete se puede ejecutar correctamente en Azure.

![Resultado correcto](Media/successful.png)

> [!Note]
> Recibirá una notificación de Azure Portal para notificarle sobre el éxito o el error de la comprobación del paquete. 
>
> Tenga en cuenta que el proceso puede tardar hasta 24 horas, por lo que es probable que la página web agote el tiempo de espera si no está activo en él y, por lo tanto, la notificación no le informará de la finalización de esta ejecución a petición. 

  - Peradventure esto sucede, puedes ver el estado del paquete en la ```Manage packages``` pestaña.

![Imagen para administrar paquetes](Media/managepackages.png)

  - Para las pruebas de éxito, sus resultados se pueden ver a través de las páginas y a intervalos programados, a menudo a partir de unos días ```Test Summary``` ```Security Updates Results``` después de la ```Feature Updates Results``` carga.
  
  - Si bien se han fallado las pruebas, es necesario cargar un nuevo paquete. 
  
    Puede descargar el ```test logs``` análisis para obtener más información desde las páginas ' ```Security update results``` ```Feature updates results``` y.

  - Si experimenta errores de prueba repetidos, póngase en contacto testbasepreview@microsoft.com con los detalles del error. 

## <a name="next-steps"></a>Pasos siguientes

Descubra nuestras Directrices de contenido a través del siguiente vínculo.
> [!div class="nextstepaction"]
> [Paso siguiente](contentguideline.md)
