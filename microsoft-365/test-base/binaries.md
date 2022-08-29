---
title: Carga de archivos binarios de la aplicación
description: Introducción al uso de Test Base para Microsoft 365
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
ms.openlocfilehash: fdb5bfed0eb103be68e1a8967dc97f9fbe64683e
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316411"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>Paso 3: Carga de archivos binarios, dependencias y scripts

En esta pestaña, cargará un único paquete zip que contiene los archivos binarios, las dependencias y los scripts usados para ejecutar el conjunto de pruebas.

> [!NOTE]
> El tamaño del paquete zip debe estar comprendido entre un mínimo de 10 MB y un máximo de 2 GB.

## <a name="upload-package-zip-file"></a>Carga del archivo ZIP del paquete

:::image type="content" alt-text="Cargue los archivos binarios." source="Media/AddBinaries.png":::

  - Las dependencias cargadas pueden incluir marcos de pruebas, motores de scripting o datos a los que se accederá para ejecutar la aplicación o los casos de prueba. Por ejemplo, puede cargar Selenium y un instalador de controlador web para ayudar a ejecutar pruebas basadas en explorador.
  - Se recomienda asegurarse de que las actividades de script se mantienen modulares.
    - El `Install` script solo realiza operaciones de instalación.
    - El `Launch` script solo inicia la aplicación.
    - El `Close` script solo cierra la aplicación.
    - El script opcional `Uninstall` solo desinstala la aplicación.

**Actualmente, el portal solo admite scripts de PowerShell.**


## <a name="next-steps"></a>Siguientes pasos 

Vaya al siguiente artículo para ir al paso 4: **Establecer las tareas de prueba**.
> [!div class="nextstepaction"]
> [Volver](uploadApplication.md)
> [!div class="nextstepaction"]
> [Paso siguiente](testtask.md)

