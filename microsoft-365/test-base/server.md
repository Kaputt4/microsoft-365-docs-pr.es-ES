---
title: Windows Pruebas de aplicaciones de servidor
description: Cómo validar con pruebas de aplicaciones de windows server
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
ms.openlocfilehash: 99868e53e98bded9139ecedea9c9d62e9d48fd2f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211758"
---
# <a name="windows-server-application-testing"></a>Windows Pruebas de aplicaciones de servidor

Con Test Base para Microsoft 365, ahora puede validar las aplicaciones en Windows Server 2016 y 2019, incluido Server Core.

Para empezar a validar las aplicaciones cargadas con actualizaciones previas a la versión de los sistemas operativos Windows Server 2016 y 2019 en Test Base para Microsoft 365, siga los pasos siguientes:

1. Inicie sesión en nuestro portal de incorporación de autoservicio. En el menú de navegación del lado izquierdo, seleccione `Upload new package` debajo `Package catalogue` y rellene los detalles de la prueba.

2. Seleccione `Security updates` como tipo de actualización del sistema operativo:

   ![Seleccione actualizaciones de seguridad.](Media/selecting-security-updates.png)

3. En Versiones del sistema operativo para probar, seleccione las versiones del sistema operativo aplicables. Puede seleccionar Windows del sistema operativo del servidor o una combinación de versiones del sistema operativo de servidor y cliente.

   ![Seleccione Versión del sistema operativo.](Media/selecting-OS-versions.png)

4. Proporcione otra información necesaria, revise los detalles proporcionados y cargue el paquete de la aplicación. Después de cargarlo, puedes ver el estado del paquete en la pestaña de menú Administrar paquetes.

5. Para ver los resultados de las pruebas y las perspectivas de la validación de la aplicación en las actualizaciones de seguridad previas a la versión Windows Server 2016 y 2019, vaya a la página Resumen de prueba o a la página De resultados de actualización de seguridad.

   ![Ver los resultados de la prueba.](Media/access-test-results.png)

Avance al siguiente artículo para empezar con las **pruebas funcionales**
> [!div class="nextstepaction"]
> [Paso siguiente](functional.md)
