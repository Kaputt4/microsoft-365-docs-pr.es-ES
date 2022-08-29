---
title: Establecer las tareas de prueba
description: Establecer las tareas de prueba
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
ms.openlocfilehash: 3356fc09609601d1974cb3daea7ea7aeb6ac979e
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316345"
---
# <a name="step-4-the-tasks-tab"></a>Paso 4: pestaña Tareas

En la pestaña tareas, se espera que proporcione las rutas de acceso a los scripts de prueba que se encuentran en la carpeta zip que cargó en la pestaña archivos binarios.

  - **Scripts de prueba de fábrica:** Escriba las rutas de acceso relativas a los scripts de instalación, inicio, cierre y desinstalación. También puede seleccionar la configuración adicional para el script de instalación.
  - **Scripts de prueba funcionales:** Escriba la ruta de acceso relativa a cada script de prueba funcional cargado. Los scripts de prueba funcionales adicionales se pueden agregar con el ```Add Script``` botón . Necesita un script mínimo de (1) y puede agregar hasta ocho (8) scripts de prueba funcionales. 
  
    Los scripts se ejecutan en la secuencia en la que aparecen. Un error en un script determinado impide que se ejecuten scripts posteriores.
    También tiene la opción de seleccionar la configuración adicional para cada script proporcionado.

## <a name="set-script-path"></a>Establecer ruta de acceso de script

![Imagen de la tarea de prueba.](Media/testtask.png)

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


## <a name="next-steps"></a>Siguientes pasos

Ver los detalles de la pestaña Opciones de prueba en el siguiente artículo 
> [!div class="nextstepaction"]
> [Paso siguiente](testoptions.md)
