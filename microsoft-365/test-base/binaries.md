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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323168"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>Paso 3: Upload archivos binarios, dependencias y scripts

En esta pestaña, cargará un único paquete zip que contenga los archivos binarios, dependencias y scripts usados para ejecutar el conjunto de pruebas.

## <a name="upload-package-zip-file"></a>Upload archivo zip del paquete

![Upload archivos binarios](Media/AddBinaries.png)

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

