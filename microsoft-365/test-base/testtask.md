---
title: Establecer las tareas de prueba
description: Establecer las tareas de prueba
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322948"
---
# <a name="step-4-the-tasks-tab"></a>Paso 4: pestaña Tareas

En la pestaña tareas, se espera que proporcione las rutas de acceso a los scripts de prueba que se encuentran en la carpeta zip que ha cargado en la pestaña archivos binarios.

  - **Scripts de pruebas sin formato:** Escriba las rutas de acceso relativas a los scripts de instalación, inicio, cierre y desinstalación. También tiene la opción de seleccionar opciones adicionales para el script de instalación.
  - **Scripts de prueba funcionales:** Escriba la ruta de acceso relativa a cada script de prueba funcional cargado. Se pueden agregar scripts de prueba funcionales adicionales con el ```Add Script``` botón. Necesita un mínimo de un script (1) y puede agregar hasta ocho (8) scripts de prueba funcionales. 
  
    Los scripts se ejecutan en secuencia de carga y un error en un script determinado impedirá que se ejecuten scripts posteriores.
    También tiene la opción de seleccionar opciones adicionales para cada script proporcionado.

## <a name="set-script-path"></a>Establecer ruta de acceso de script

![Imagen de la tarea de prueba](Media/testtask.png)

A continuación se muestra un ejemplo de cómo proporcionar la ruta de acceso relativa en una estructura de carpetas:

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** habría sido así. _ScriptX.ps1_ como la ruta de acceso relativa.
  - **Script.ps1** _carpeta1/script.ps1_ como ruta de acceso relativa.


## <a name="next-steps"></a>Pasos siguientes

Vea los detalles de la pestaña Opciones de prueba en el siguiente artículo 
> [!div class="nextstepaction"]
> [Paso siguiente](testoptions.md)
