---
title: Subir un paquete
description: Cómo cargar la aplicación, los archivos binarios y las dependencias en Test Base
search.appverid: MET150
author: mansipatel-usl
ms.author: rshastri
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd0d463e234c439d8b57576375fd6a91e512f753
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64995289"
---
# <a name="upload-your-test-base-package-zip"></a>Upload el paquete base de prueba (Zip) 

En la página Probar base del portal, vaya a la opción **Nuevo paquete** de la barra de navegación izquierda y, a continuación, haga clic en **Experiencia de carga heredada** para habilitar la experiencia de carga zip como se muestra a continuación:

:::image type="content" alt-text="Upload un nuevo paquete." source="Media/testapplication01.png" lightbox="Media/testapplication01.png":::

:::image type="content" alt-text="Aplique la operación." source="Media/testapplication21.png" lightbox="Media/testapplication21.png":::

Una vez allí, siga los pasos siguientes para cargar un nuevo paquete.

## <a name="enter-details-for-your-package"></a>Escriba los detalles del paquete.

En la pestaña Detalles de la prueba, escriba el nombre, la versión y otros detalles del paquete según lo solicitado.

**Las** pruebas integradas y **funcionales** se pueden realizar a través de este panel.

Los pasos siguientes proporcionan una guía sobre cómo rellenar los detalles del paquete:

1. Escriba el nombre que se va a asignar al paquete en el `Package name` campo .

    > [!NOTE]
    > El nombre del paquete y la combinación de versión especificados deben ser únicos dentro de la organización. Esto se valida mediante la marca de verificación, como se muestra a continuación.

    - Si decide reutilizar el nombre de un paquete, el número de versión debe ser único (es decir, nunca se ha usado con un paquete con ese nombre en particular).

    - Si la combinación del nombre del paquete y la versión no pasa la comprobación de unicidad, verá un mensaje de error que indica *que "El paquete con esta versión del paquete ya existe"*.

    :::image type="content" alt-text="Imagen para cargar las instrucciones del paquete." source="Media/Instructions.png":::

2. Escriba una versión en el campo "Versión del paquete".

    :::image type="content" alt-text="Versión del paquete." source="Media/ApplicationVersion.png":::

3. Seleccione el tipo de prueba que desea ejecutar en este paquete.

    Una prueba lista para usar **(OOB)** realiza una *instalación*, *inicio*, *cierre* y *desinstalación* del paquete. Después de la instalación, la rutina de inicio y cierre se repite 30 veces antes de que se ejecute una sola desinstalación.

    Esta prueba de OOB proporciona telemetría estandarizada en el paquete para compararla entre Windows compilaciones.

    Una **prueba funcional** ejecutaría los scripts de prueba cargados en el paquete. Los scripts se ejecutan en la secuencia de carga y un error en un script determinado impedirá la ejecución de scripts posteriores.

    > [!NOTE]
    > **Todos los** scripts se ejecutan durante 80 minutos como máximo.

4. Seleccione el tipo de actualización del sistema operativo.

    - Las "actualizaciones de seguridad" permiten probar el paquete con renovaciones incrementales de Windows actualizaciones de seguridad mensuales de versión preliminar.
    - Las "actualizaciones de características" permiten probar el paquete con Windows compilaciones de actualizaciones de características bianuales anteriores a la versión del programa Windows Insider.
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="Tipo de actualización del sistema operativo." source="Media/OSUpdateType.png":::

5. Seleccione las versiones del sistema operativo para las pruebas de actualización de seguridad.

    En la lista desplegable de selección múltiple, seleccione las versiones del sistema operativo de Windows en las que se instalará el paquete.

    - Para probar el paquete solo en Windows sistemas operativos cliente, seleccione las versiones del sistema operativo de cliente Windows aplicables en la lista de menús.
    - Para probar el paquete solo en sistemas operativos Windows Server, seleccione las versiones del sistema operativo Windows Server aplicables en la lista de menús.
    - Para probar el paquete con Windows sistemas operativos Cliente y Windows Server, seleccione todos los sistemas operativos aplicables en la lista de menús.

    > [!NOTE]
    > Si selecciona probar el paquete con los sistemas operativos servidor y cliente, asegúrese de que el paquete es compatible y se puede ejecutar en ambos sistemas operativos.

    :::image type="content" alt-text="Selección de una versión del sistema operativo." source="Media/OSVersion.png":::
    <!---
    Change to the correct picture
    -->

6. Seleccione las opciones para las pruebas de actualización de características:

    - En la opción "Seleccionar canal insider", seleccione como `Windows Insider Program Channel` compilación en la que se deben probar los paquetes.

      Actualmente usamos compilaciones piloto en el canal beta de Insider.

    - En la opción "Seleccionar línea base del sistema operativo para Insight", seleccione la versión Windows del sistema operativo que se usará como línea base al comparar los resultados de la prueba.

    > [!NOTE]
    > No se admiten pruebas de actualización de características para sistemas operativos de servidor en este momento
    <!---
    Note to actual note format for markdown
    -->
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="Pruebas de actualización de características." source="Media/FeatureUpdate.png":::

7. Una página de detalles de prueba completada debe tener este aspecto:

    :::image type="content" alt-text="Visualización de los detalles de la prueba." source="Media/TestDetails.png":::

## <a name="next-steps"></a>Siguientes pasos

Nuestro siguiente artículo trata sobre la carga de archivos binarios en nuestro servicio.

> [!div class="nextstepaction"]
> [Paso siguiente](binaries.md)

<!---
Add button for next page
-->
