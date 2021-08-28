---
title: Upload Binarios de aplicación
description: Cómo empezar a usar Test Base para M365
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
ms.openlocfilehash: 38c21f69680d6e9d6a3231c8bf2dc44f15e057f6
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58556509"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>Paso 3: Upload archivos binarios, dependencias y scripts

En esta pestaña, cargará un único paquete zip que contenga los archivos binarios, dependencias y scripts usados para ejecutar el conjunto de pruebas.

## <a name="upload-package-zip-file"></a>Upload archivo zip del paquete

![Upload los archivos binarios.](Media/AddBinaries.png)

  - Las dependencias cargadas pueden incluir marcos de prueba, motores de scripting o datos a los que se tendrá acceso para ejecutar los casos de prueba o aplicación. Por ejemplo, puede cargar Selenio y un instalador de webdriver para ayudar a ejecutar pruebas basadas en explorador.
  - Es una práctica recomendada asegurarse de que las actividades de script se mantienen modulares, por ejemplo. 
    - El ```Install``` script solo realiza operaciones de instalación.
    - El ```Launch``` script solo inicia la aplicación.
    - El ```Close``` script solo cierra la aplicación.
    - El ```Uninstall``` script opcional solo desinstala la aplicación.

**Actualmente, el portal solo admite scripts de PowerShell.**


## <a name="next-steps"></a>Pasos siguientes 

Vaya al siguiente artículo para ir al Paso 4: **Establecer las tareas de prueba**.
> [!div class="nextstepaction"]
> [Volver](uploadApplication.md)
> [!div class="nextstepaction"]
> [Paso siguiente](testtask.md)

