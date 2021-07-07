---
title: Subir un paquete
description: Cómo cargar la aplicación, los archivos binarios y las dependencias en Test Base
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: e8b4323eda31c55bbf32de0996fc7bd48d54ade2
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323096"
---
# <a name="step-2-uploading-a-package"></a>Paso 2: Cargar un paquete

En la página Del portal base de prueba, vaya a la opción "Upload nuevo paquete en la barra de navegación izquierda, como se muestra a continuación: Upload ![ un nuevo paquete](Media/Upload-New-Package.png)

Una vez allí, siga los pasos siguientes para cargar un nuevo paquete.

## <a name="enter-details-for-your-package"></a>Escriba los detalles del paquete

En la pestaña Detalles de prueba, escriba el nombre, la versión y otros detalles del paquete según lo solicitado. 

**Las pruebas de configuración y** **funcionales** se pueden realizar a través de este panel.

Los pasos siguientes proporcionan una guía sobre cómo rellenar los detalles del paquete:

1.  **Escriba el nombre que se le va a dar al paquete en el ```“Package name``` campo.**

> [!Note]  
> El nombre del paquete y la combinación de versión especificados deben ser únicos dentro de la organización. Esto se valida mediante la marca de verificación como se muestra a continuación.
  
  - Si decide volver a usar el nombre de un paquete, el número de versión debe ser único (es decir, nunca se ha usado con un paquete que tenga ese nombre en particular).
  - Si la combinación del nombre del paquete + versión no pasa la comprobación de unibilidad, verá un mensaje de error que dice: "Paquete con esta versión del paquete *ya existe".* 

![Imagen para cargar instrucciones del paquete](Media/Instructions.png)

2. **Escriba una versión en el campo "Versión del paquete".**

![Versión del paquete](Media/ApplicationVersion.png)

3.  **Seleccione el tipo de prueba que desea ejecutar en este paquete**

    Una **prueba lista para su uso (OOB)** realiza una *instalación,* *inicio,* *cierre* y *desinstalación* del paquete. Después de la instalación, la rutina de inicio y cierre se repite 30 veces antes de ejecutar una sola desinstalación. 
    
    Esta prueba de OOB le proporciona telemetría estandarizada en el paquete para comparar entre Windows compilaciones.

    Una **prueba funcional** ejecutaría los scripts de prueba cargados en el paquete. Los scripts se ejecutan en secuencia de carga y un error en un script determinado impedirá que se ejecuten scripts posteriores.

> [!Note]
> **Todos** los scripts se ejecutan durante 80 minutos como máximo. 
    
4.  **Seleccionar el tipo de actualización del sistema operativo**

   - Las "actualizaciones de seguridad" permiten probar el paquete con las actualizaciones incrementales de Windows actualizaciones de seguridad mensuales previas a la publicación. 
   - Las "actualizaciones de características" permiten probar el paquete con Windows compilaciones de actualizaciones de características binacionales previas Windows Insider Program.
<!---
Change to the correct picture
-->
![Tipo de actualización del sistema operativo](Media/OSUpdateType.png)

5.  **Seleccione las versiones del sistema operativo para las pruebas de actualización de seguridad.**

En la lista desplegable de selección múltiple, seleccione las versiones del sistema operativo Windows en las que se instalará el paquete. 

  - Para probar el paquete solo Windows de cliente, seleccione las 11 versiones del sistema operativo aplicables Windows en la lista de menús.
  - Para probar el paquete solo con Windows de servidor, seleccione las versiones Windows sistema operativo del servidor aplicables en la lista de menús.
  - Para probar el paquete con Windows de cliente y servidor, seleccione todos los sistemas operativo aplicables en la lista de menús. 

> [!Note]
> Si selecciona probar el paquete con los sistemas operativo de servidor y cliente, asegúrese de que el paquete es compatible y puede ejecutarse en ambos SISTEMAS


![Selección de una versión del sistema operativo](Media/OSVersion.png)
<!---
Change to the correct picture
-->
6.  **Seleccione opciones para las pruebas de actualización de características:**

  - En la opción "Seleccionar canal insider", seleccione la compilación con la que deben ```Windows Insider Program Channel``` probarse los paquetes.
  
    Actualmente usamos compilaciones piloto en el Canal beta de Insider.

  - En la opción "Seleccionar línea base del sistema operativo para Insight", seleccione la versión Windows sistema operativo que se usará como línea base para comparar los resultados de la prueba. 

> [!Note]
> No se admiten pruebas de actualización de características para sos de servidor en este momento
<!---
Note to actual note format for markdown
-->
<!---
Change to the correct picture
-->
![Pruebas de actualización de características](Media/FeatureUpdate.png)

7.  Una página de detalles de prueba completada debe tener este aspecto: 

![Visualización de detalles de la prueba](Media/TestDetails.png)
## <a name="next-steps"></a>Pasos siguientes

En el siguiente artículo se describe Cargar los archivos binarios en nuestro serivce.
> [!div class="nextstepaction"]
> [Paso siguiente](binaries.md)

<!---
Add button for next page
-->

