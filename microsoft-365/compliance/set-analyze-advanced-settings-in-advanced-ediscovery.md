---
title: Establecer la configuración avanzada de ANALYZE en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: 'Obtenga información acerca de cómo configurar las opciones avanzadas, incluidos los mensajes casi duplicados, los subprocesos de correo electrónico y los temas, para analizar el proceso en eDiscovery avanzado. '
ms.openlocfilehash: 91faf9e39fe7b8a7fada7b05ccd88351d813b148
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631277"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a>Establecer la configuración avanzada de ANALYZE en eDiscovery avanzado

> [!NOTE]
> Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
EDiscovery avanzado proporciona parámetros avanzados predeterminados para la configuración del módulo de análisis. En el procedimiento siguiente se describe la configuración que se puede especificar.
  
1. En la **ficha \> preparar \> la configuración de ANALYZE** , haga clic en **Configuración avanzada** (en la parte inferior de la página). Se muestra el siguiente panel. 
    
    ![Establecer la configuración avanzada del análisis](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. En **parámetros casi duplicados y de subprocesos de correo electrónico**, seleccione valores para las siguientes opciones, según sea necesario:
    
  - **Número mínimo de palabras**: número mínimo de palabras, por debajo del cual no se envía un archivo para análisis casi duplicados. 
    
  - **Número máximo de palabras**: número máximo de palabras, por encima de las cuales no se envía un archivo para análisis casi duplicados.
    
  - **Similitud de correo electrónico**: el nivel mínimo de semejanza de dos correos electrónicos se considerará similar. El valor es siempre igual a o mayor que el de la similitud del documento. El valor predeterminado es 90%.
    
3. En **los parámetros de los temas**, active la casilla **incluir números en el análisis del tema** para incluir números en el procesamiento de temas durante el análisis. 
    
4. Haga clic en **Guardar**. 
    
## <a name="see-also"></a>Vea también

[Advanced eDiscovery (clásico)](office-365-advanced-ediscovery.md)
  
[Descripción de la similitud de documentos](understand-document-similarity-in-advanced-ediscovery.md)
  
[Configuración de las opciones de análisis](set-analyze-options-in-advanced-ediscovery.md)
  
[Configuración de omitir texto](set-ignore-text-in-advanced-ediscovery.md)
  
[Visualización de los resultados del análisis](view-analyze-results-in-advanced-ediscovery.md)

