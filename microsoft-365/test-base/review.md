---
title: Revisar
description: Revisión de la sección después de la incorporación.
search.appverid: MET150
author: mansipatel-usl
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: test-base
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: tinachen
f1.keywords: NOCSH
ms.openlocfilehash: f2c685af5c94260fce717db791eceee6a8a87060
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316564"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a>Paso 6: Revise las selecciones para crear el paquete.

1. En esta pestaña, el servicio muestra los detalles de la prueba y ejecuta una comprobación de integridad rápida.

    Un mensaje **Validación pasada** o **Error de validación** muestra si puede continuar con los pasos siguientes o no.

2. Revise los detalles de la prueba y, si está satisfecho, haga clic en el botón **Crear** .

    :::image type="content" alt-text="Ver validación." source="Media/validation.png" lightbox="Media/validation.png":::

3. Esto incorporará el paquete al entorno base de prueba. Si el paquete se crea correctamente, se desencadenará una prueba automatizada que compruebe si el paquete se puede ejecutar correctamente en Azure.

    ![Resultado correcto.](Media/successful.png)

    > [!NOTE]
    > Recibirá una notificación de la Azure Portal para notificarle si la comprobación del paquete se ha realizado correctamente o no.
    >
    > Tenga en cuenta que el proceso puede tardar hasta 24 horas, por lo que es probable que su página web agote el tiempo de espera si no está activo en ella y, por lo tanto, la notificación no le informará de la finalización de esta ejecución a petición.

    - Si esto sucede, puede ver el estado del paquete en la pestaña **Administrar paquetes** .

      :::image type="content" alt-text="Imagen para administrar paquetes." source="Media/managepackages.png" lightbox="Media/managepackages.png":::

    - En el caso de las pruebas correctas, sus resultados se pueden ver a través de las páginas **Resumen de pruebas**, **Resultados de seguridad Novedades** y **Resultados de la característica Novedades a** intervalos programados, a menudo a partir de unos días después de la carga.
  
    - Aunque se han producido errores en las pruebas, es necesario cargar un nuevo paquete. 

      Puede descargar los **registros de prueba** para realizar un análisis posterior desde las páginas **Resultados de la actualización de seguridad** y **Resultados de actualizaciones de características** .

    - Si experimenta errores de prueba repetidos, póngase en contacto con testbasepreview@microsoft.com con detalles del error.

## <a name="next-steps"></a>Siguientes pasos

Descubra nuestras directrices de contenido a través del vínculo siguiente.

> [!div class="nextstepaction"]
> [Paso siguiente](contentguideline.md)
