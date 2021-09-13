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
ms.openlocfilehash: fa046aa0a488b11f172d9ac7182b67e705aad69b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59166531"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>Paso 6: Revisar las selecciones para crear el paquete.

1. En esta pestaña, el servicio muestra los detalles de la prueba y ejecuta una comprobación de integridad rápida.

    Un **mensaje De validación pasada** **o** Error de validación muestra si puede continuar con los pasos siguientes o no.

2. Revise los detalles de la prueba y, si se cumple, haga clic en el **botón** Crear.

    :::image type="content" alt-text="Ver validación." source="Media/validation.png" lightbox="Media/validation.png":::

3. Esto incorporará el paquete al entorno base de prueba. Si el paquete se crea correctamente, se activará una prueba automatizada que compruebe si el paquete se puede ejecutar correctamente en Azure.

    ![Resultado correcto.](Media/successful.png)

    > [!NOTE]
    > Recibirá una notificación de Azure Portal para notificarle sobre el éxito o el error de la comprobación del paquete.
    >
    > Tenga en cuenta que el proceso puede tardar hasta 24 horas, por lo que es probable que la página web agote el tiempo de espera si no está activo en él y, por lo tanto, la notificación no le informará de la finalización de esta ejecución a petición.

    - Peradventure esto sucede, puedes ver el estado del paquete en la pestaña Administrar **paquetes.**

      :::image type="content" alt-text="Imagen para administrar paquetes." source="Media/managepackages.png" lightbox="Media/managepackages.png":::

    - Para las pruebas correctas, sus resultados  se pueden  ver a través de las páginas Resumen de **prueba,** Resultados de actualizaciones de seguridad y Resultados de actualizaciones de características a intervalos programados, a menudo a partir de unos días después de la carga.
  
    - Si bien se han fallado las pruebas, es necesario cargar un nuevo paquete. 

      Puede descargar los registros **de prueba para** realizar más análisis desde las páginas De **resultados** de actualización de seguridad y **Actualizaciones de** características.

    - Si experimenta errores de prueba repetidos, póngase en contacto testbasepreview@microsoft.com con los detalles del error.

## <a name="next-steps"></a>Pasos siguientes

Descubra nuestras Directrices de contenido a través del siguiente vínculo.

> [!div class="nextstepaction"]
> [Paso siguiente](contentguideline.md)
