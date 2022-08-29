---
title: Validación de actualización de características
description: Detalles sobre cómo cargar la aplicación para la validación de actualizaciones de características
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
ms.openlocfilehash: 02693d1dc9637b97d6d567a6bc362eaef24adc5d
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315512"
---
# <a name="windows-feature-update-validation"></a>Validación de actualización de características de Windows

¿Necesita información sobre cómo funcionarán las aplicaciones con la próxima versión de Windows 10 o Windows 11, sin mantener un entorno para validar nuevas características de Windows? 

¿Desea ejecutar las pruebas de validación en compilaciones del Programa Windows Insider en nuestro entorno de Azure?

La validación de **actualizaciones de características** en Test Base para M365 puede ayudarle a lograr todo esto y mucho más.

Consulte el siguiente esquema paso a paso para obtener información sobre cómo acceder a esta nueva funcionalidad en test base para el servicio M365.

Para empezar a trabajar con ```Feature update validation``` en Test Base for M365, cargue las aplicaciones (y los archivos relacionados) a través del portal de incorporación de autoservicio. 

A continuación, se resaltan los pasos que debe seguir al rellenar los **detalles** de la prueba:

1. Seleccione **Actualización de características** como tipo de actualización del sistema operativo:

![Tipo de sistema operativo de validación de actualización de características.](Media/Feature-update-validation-01.png)

2. Elija el canal de Windows Insider en el que desea validar la aplicación.  

![Validación de actualización de características. Elegir el canal beta de Insider.](Media/Feature-update-validation-02.png)

3. Seleccione una versión en el mercado de Windows 10 o Windows 11 como línea base para la prueba (y la información resultante) y proporcione los demás detalles necesarios para incorporar el paquete correctamente.

![Validación de actualización de características con versiones publicadas de Windows 10 y Windows 11.](Media/Feature-update-validation-03.png)

4. Para ver los resultados de la validación de la aplicación con las actualizaciones de características Windows 10 publicadas previamente, visite .```Feature Updates Test Results```

![La validación de actualizaciones de características le permite revisar los resultados rápidamente.](Media/Feature-update-validation-04.png)


## <a name="next-steps"></a>Siguientes pasos

Pase al siguiente artículo para empezar a comprender el análisis de regresión de memoria.
> [!div class="nextstepaction"]
> [Paso siguiente](memory.md)

<!---
Add button for next page
-->
