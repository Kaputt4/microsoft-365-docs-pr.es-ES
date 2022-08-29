---
title: Pruebas de aplicaciones de Windows Server
description: Validación con pruebas de aplicaciones de Windows Server
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
ms.openlocfilehash: 5d111b680105628ab1351a2cc45eeba01c41aa68
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67316016"
---
# <a name="windows-server-application-testing"></a>Pruebas de aplicaciones de Windows Server

Con Test Base para Microsoft 365, ahora puede validar las aplicaciones en Windows Server 2016 y 2019, incluido Server Core.

Para empezar a validar las aplicaciones cargadas con las actualizaciones de versión preliminar para sistemas operativos de Windows Server 2016 y 2019 en Test Base para Microsoft 365, siga estos pasos:

1. Inicie sesión en nuestro portal de incorporación de autoservicio. En el menú de navegación izquierdo, seleccione `Upload new package` debajo `Package catalogue` y rellene los detalles de la prueba.

2. Seleccione `Security updates` como tipo de actualización del sistema operativo:

   ![Seleccione actualizaciones de seguridad.](Media/selecting-security-updates.png)

3. En Versiones del sistema operativo que se van a probar, seleccione las versiones del sistema operativo aplicables. Puede seleccionar versiones del sistema operativo Windows Server o una combinación de versiones del sistema operativo de servidor y cliente.

   ![Seleccione Versión del sistema operativo.](Media/selecting-OS-versions.png)

4. Proporcione otra información necesaria, revise los detalles proporcionados y cargue el paquete de aplicación. Después de cargar, puede ver el estado del paquete en la pestaña del menú Administrar paquetes.

5. Para ver los resultados de las pruebas y la información de la validación de la aplicación con respecto a las actualizaciones de seguridad anteriores a la versión preliminar de Windows Server 2016 y 2019, vaya a la página Resumen de pruebas o a la página Resultados de la actualización de seguridad.

   ![Ver los resultados de las pruebas.](Media/access-test-results.png)

Pase al siguiente artículo para empezar a trabajar con **las pruebas funcionales**.
> [!div class="nextstepaction"]
> [Paso siguiente](functional.md)
