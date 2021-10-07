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
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 200da9ca73bc666f3f11fc3fda95493d2c0954fb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60180644"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>Paso 3: Upload archivos binarios, dependencias y scripts

En esta pestaña, cargará un único paquete zip que contenga los archivos binarios, dependencias y scripts usados para ejecutar el conjunto de pruebas.

> [!NOTE]
> El tamaño del paquete zip debe estar entre un mínimo de 10 MB y un máximo de 2 GB.

## <a name="upload-package-zip-file"></a>Upload archivo zip del paquete

:::image type="content" alt-text="Upload los archivos binarios." source="Media/AddBinaries.png":::

  - Las dependencias cargadas pueden incluir marcos de prueba, motores de scripting o datos a los que se tendrá acceso para ejecutar los casos de prueba o aplicación. Por ejemplo, puede cargar Selenio y un instalador de controladores web para ayudar a ejecutar pruebas basadas en explorador.
  - Es una práctica recomendada asegurarse de que las actividades de script se mantienen modulares, por ejemplo. 
    - El `Install` script solo realiza operaciones de instalación.
    - El `Launch` script solo inicia la aplicación.
    - El `Close` script solo cierra la aplicación.
    - El `Uninstall` script opcional solo desinstala la aplicación.

**Actualmente, el portal solo admite scripts de PowerShell.**


## <a name="next-steps"></a>Pasos siguientes 

Vaya al siguiente artículo para ir al Paso 4: **Establecer las tareas de prueba**.
> [!div class="nextstepaction"]
> [Volver](uploadApplication.md)
> [!div class="nextstepaction"]
> [Paso siguiente](testtask.md)

