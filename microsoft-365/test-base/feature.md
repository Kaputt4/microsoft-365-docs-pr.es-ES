---
title: Validación de actualización de características
description: Detalles sobre cómo cargar la aplicación para la validación de actualizaciones de características
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
ms.openlocfilehash: ce048796acd52e6daf8d4694cf72a0bd17c75ab4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323327"
---
# <a name="windows-feature-update-validation"></a>Windows Validación de actualización de características

¿Necesita información sobre el rendimiento de las aplicaciones con la próxima versión de Windows 10 o Windows 11, sin que mantenga un entorno para validar nuevas características Windows aplicaciones? 

¿Desea ejecutar las pruebas de validación en Windows compilaciones del programa Insider en nuestro entorno de Azure?

**La validación de** actualización de características en Test Base para M365 puede ayudarle a lograr todos estos y más resultados.

Consulte el esquema paso a paso siguiente para averiguar cómo obtener acceso a esta nueva funcionalidad en Test Base para el servicio M365.

Para empezar con test base para M365, cargue las aplicaciones (y los archivos relacionados) a través del ```Feature update validation``` portal de incorporación de autoservicio. 

A continuación se indican los pasos que debe seguir al rellenar los detalles **de la prueba:**

1. Seleccione **Actualización de características** como tipo de actualización del sistema operativo:

![Tipo de sistema operativo de validación de actualización de características](Media/Feature-update-validation-01.png)

2. Elija el Windows Insider channel con el que desea que se valide la aplicación.  

![Validación de actualización de características. Elegir el canal beta de Insider](Media/Feature-update-validation-02.png)

3. Seleccione una versión en el mercado de Windows 10 o Windows 11 como línea base para la prueba (y obtener información resultante) y proporcione los demás detalles necesarios para incorporar el paquete correctamente.

![Validación de actualización de características con versiones publicadas de Windows 10 y Windows 11](Media/Feature-update-validation-03.png)

4. Para ver los resultados de la validación de la aplicación en las actualizaciones de características Windows 10 versión anterior, visite ```Feature Updates Test Results``` el archivo .

![La validación de actualización de características le permite revisar los resultados rápidamente](Media/Feature-update-validation-04.png)


## <a name="next-steps"></a>Pasos siguientes

Avance al siguiente artículo para empezar a comprender el análisis de regresión de memoria.
> [!div class="nextstepaction"]
> [Paso siguiente](memory.md)

<!---
Add button for next page
-->
