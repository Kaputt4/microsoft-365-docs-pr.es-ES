---
title: Clonación de un paquete existente
description: Clonación de un paquete existente
search.appverid: MET150
author: Tinacyt
ms.author: tinachen
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 05/27/2022
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: Tinacyt
f1.keywords: NOCSH
ms.openlocfilehash: 1e0f4ca8939a965347126076f5fef7e85a103c9c
ms.sourcegitcommit: 1fa0b15f86470c49dddf0d6de59d553a38ae259b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65863747"
---
# <a name="clone-an-existing-package"></a>Clonación de un paquete existente

En esta sección, aprenderá a crear un nuevo paquete duplicando el paquete publicado anteriormente como punto de partida. Hay varias entradas en el portal de Test Base para que pueda iniciar el recorrido del paquete clonado.

> [!IMPORTANT]
> Para usar la función clonar paquete, debe tener al menos un paquete cargado correctamente en Test Base. 

## <a name="starting-from-the-new-package-page"></a>A partir de la página Nuevo paquete

> [!div class="mx-imgBorder"]
> [![](Media/clonepackage01_guidance.png) Guía para clonar ](Media/clonepackage01_guidance.png#lightbox)

1. En la página **Nuevo paquete** , puede seleccionar en **Clonar paquete existente**. A continuación, seleccione un paquete de la lista de paquetes existente y haga clic en **"Clonar"**. 

   > [!div class="mx-imgBorder"]
   > [![Clonación del paquete](Media/clonepackage02_clone_package.png) existente ](Media/clonepackage02_clone_package.png#lightbox)

2. Se le dirigirá a los pasos de creación del nuevo paquete con toda la información y la configuración rellenadas previamente igual que el paquete clonado. La única información que debe cambiar es la versión del **paquete** en la sección **Información básica** . 

   > [!NOTE]
   > La combinación del nombre y la versión del paquete debe ser única dentro de la cuenta base de prueba. 

   > [!div class="mx-imgBorder"]
   > [![Información](Media/clonepackage03_basic_information.png) básica del paquete ](Media/clonepackage03_basic_information.png#lightbox)

3. Puede hacer lo siguiente:

   - obtener una vista previa de toda la información de configuración del paquete rellenado previamente que se duplica desde el paquete clonado. 
   - realice los cambios del paso 1 al paso 4 (consulte Carga del paquete zip precompilado para obtener instrucciones más detalladas). 
   - revisar y publicar en Test Base. 


## <a name="starting-from-the-manage-packages-page"></a>A partir de la página Administrar paquetes

En la página **Administrar paquetes** , puede clonar un paquete seleccionando el icono **"Clonar"** en la columna Acciones rápidas. 

> [!div class="mx-imgBorder"]
> [![Página Administrar paquetes](Media/clonepackage04_manage_packages.png) ](Media/clonepackage04_manage_packages.png#lightbox)

También puede ir a la página **Información general** del paquete específico que ha seleccionado en la página **Administrar paquetes** y seleccionar en el icono **Clonar paquete** del menú de acción superior.

> [!div class="mx-imgBorder"]
> [![Clonación desde la página](Media/clonepackage05_overview.png) de información general ](Media/clonepackage05_overview.png#lightbox)

