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
ms.openlocfilehash: 23c21eae9ad149aea5442c0c8a00f716f3d22506
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099485"
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



## <a name="upload-your-binaries-dependencies-and-scripts"></a>Upload los archivos binarios, las dependencias y los scripts

En esta pestaña, cargará un único paquete zip que contiene los archivos binarios, las dependencias y los scripts usados para ejecutar el conjunto de pruebas.

> [!NOTE]
> El tamaño del paquete zip debe estar comprendido entre un mínimo de 10 MB y un máximo de 2 GB.

**Upload archivo zip del paquete**

:::image type="content" alt-text="Upload los archivos binarios." source="Media/AddBinaries.png":::

  - Las dependencias cargadas pueden incluir marcos de pruebas, motores de scripting o datos a los que se accederá para ejecutar la aplicación o los casos de prueba. Por ejemplo, puede cargar Selenium y un instalador de controlador web para ayudar a ejecutar pruebas basadas en explorador.
  - Se recomienda asegurarse de que las actividades de script se mantienen modulares, es decir, 
    - El `Install` script solo realiza operaciones de instalación.
    - El `Launch` script solo inicia la aplicación.
    - El `Close` script solo cierra la aplicación.
    - El script opcional `Uninstall` solo desinstala la aplicación.

**Actualmente, el portal solo admite scripts de PowerShell.**



## <a name="the-tasks-tab"></a>Pestaña Tareas

En la pestaña tareas, se espera que proporcione las rutas de acceso a los scripts de prueba que se encuentran en la carpeta zip que cargó en la pestaña archivos binarios.

  - **Scripts de prueba de fábrica:** Escriba las rutas de acceso relativas a los scripts de instalación, inicio, cierre y desinstalación. También tiene la opción de seleccionar opciones adicionales para el script de instalación.
  - **Scripts de prueba funcionales:** Escriba la ruta de acceso relativa a cada script de prueba funcional cargado. Se pueden agregar scripts de prueba funcionales adicionales con el ```Add Script``` botón . Necesita un script mínimo de (1) y puede agregar hasta ocho (8) scripts de prueba funcionales. 
  
    Los scripts se ejecutan en la secuencia en la que aparecen. Un error en un script determinado impide que se ejecuten scripts posteriores.
    También tiene la opción de seleccionar opciones adicionales para cada script proporcionado.

**Establecer ruta de acceso de script**

:::image type="content" alt-text="Imagen de la tarea de prueba." source="Media/testtask.png":::

A continuación se muestra un ejemplo de cómo proporcionar la ruta de acceso relativa en una estructura de carpetas:

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** lo habría hecho. _ScriptX.ps1_ como ruta de acceso relativa.
  - **Script.ps1** tendría _folder1/script.ps1_ como ruta de acceso relativa.



## <a name="choose-your-test-options"></a>Elija las opciones de prueba. 

La ```Test Options``` pestaña está destinada a los usuarios que desean realizar pruebas funcionales para indicar cuándo se debe aplicar la revisión de Windows Update en la secuencia de ejecución de sus scripts de prueba funcionales.

:::image type="content" alt-text="Imagen de las opciones de prueba. Pruebas integradas o funcionales." source="Media/testoptions.png":::

Seleccione _**Revisar**_ para ir a la pestaña siguiente y revisar las opciones de prueba seleccionadas.



## <a name="review-your-selections-to-create-your-package"></a>Revise las selecciones para crear el paquete.

1. En esta pestaña, el servicio muestra los detalles de la prueba y ejecuta una comprobación de integridad rápida.

    Un mensaje **Validación pasada** o **Error de validación** muestra si puede continuar con los pasos siguientes o no.

2. Revise los detalles de la prueba y, si está satisfecho, haga clic en el botón **Crear** .

    :::image type="content" alt-text="Ver validación." source="Media/validation.png" lightbox="Media/validation.png":::

3. Esto incorporará el paquete al entorno base de prueba. Si el paquete se crea correctamente, se desencadenará una prueba automatizada que compruebe si el paquete se puede ejecutar correctamente en Azure.

    :::image type="content" alt-text="Resultado correcto." source="Media/successful.png":::

    > [!NOTE]
    > Recibirá una notificación de la Azure Portal para notificarle si la comprobación del paquete se ha realizado correctamente o no.
    >
    > Tenga en cuenta que el proceso puede tardar hasta 24 horas, por lo que es probable que su página web agote el tiempo de espera si no está activo en ella y, por lo tanto, la notificación no le informará de la finalización de esta ejecución a petición.

    - Si esto sucede, puede ver el estado del paquete en la pestaña **Administrar paquetes** .

      :::image type="content" alt-text="Imagen para administrar paquetes." source="Media/managepackages.png" lightbox="Media/managepackages.png":::

    - En el caso de las pruebas correctas, sus resultados se pueden ver a través de las páginas **Resumen de pruebas**, **Resultados de actualizaciones de seguridad** y Resultados de **actualizaciones de características** a intervalos programados, a menudo a partir de unos días después de la carga.
  
    - Aunque se han producido errores en las pruebas, es necesario cargar un nuevo paquete. 

      Puede descargar los **registros de prueba** para realizar un análisis posterior desde las páginas **Resultados de la actualización de seguridad** y **Resultados de actualizaciones de características** .

    - Si experimenta errores de prueba repetidos, póngase en contacto con testbasepreview@microsoft.com con detalles del error.

## <a name="next-steps"></a>Siguientes pasos

Descubra nuestras directrices de contenido a través del vínculo siguiente.

> [!div class="nextstepaction"]
> [Paso siguiente](contentguideline.md)
