---
title: Administrar la configuración de Relevancia en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
ROBOTS: NOINDEX, NOFOLLOW
description: Lea las recomendaciones para configurar el entrenamiento de Relevancia en eDiscovery (Premium) con el fin de puntuar archivos según su relevancia y generar resultados de análisis.
ms.openlocfilehash: d66db4fc4a03aab2e63e093eb91a33267f66414e
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67820225"
---
# <a name="manage-relevance-setup-in-ediscovery-premium-classic"></a>Administrar la configuración de Relevancia en eDiscovery (Premium) (clásico)

> [!NOTE]
> Para usar eDiscovery (Premium) de Microsoft Purview, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery (Premium), puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 La tecnología Relevancia de eDiscovery (Premium) utiliza software guiado por expertos para puntuar archivos según su relevancia. Relevancia de eDiscovery (Premium) puede usarse para la evaluación temprana de casos (ECA), la selección y la revisión de archivos de muestra. 
  
 En eDiscovery (Premium), se incluyen componentes para el entrenamiento de Relevancia y para el etiquetado de archivos relevantes para un caso. eDiscovery (Premium) aprende de las muestras entrenadas de archivos relevantes y no relevantes para asignar puntuaciones de relevancia a cada archivo y, además, genera resultados de análisis que pueden usarse durante y después del proceso de revisión de archivos. 
  
## <a name="guidelines-for-setting-up-relevance-training"></a>Directrices para configurar el entrenamiento de Relevancia

 En eDiscovery avanzado, en la ventana **Casos**, seleccione un caso y haga clic en **Ir al caso**. Haga clic en **Relevancia** \> **Configuración de relevancia**. Siga las recomendaciones para configurar Relevancia. 
  
- **Etiquetado**: la efectividad del proceso de entrenamiento iterativo de Relevancia depende de la capacidad del experto de etiquetar archivos de muestra con precisión y coherencia.

- **Asuntos de casos**:
  
  - Para cada asunto, use el mismo experto en todo el proceso de entrenamiento de Relevancia. No se permite el etiquetado simultánea del mismo asunto por varios expertos.
  
  - Determine si cada grupo de archivos es relevante solo para un asunto específico.

  - Si se describe un problema de forma demasiado amplia, es posible que eDiscovery (Premium) muestre demasiados archivos que no sean relevantes. Si se describe un problema de forma demasiado reducida, es posible que el proceso de entrenamiento de Relevancia tarde más tiempo en completarse. 

  - Durante cada ciclo de entrenamiento de Relevancia, eDiscovery (Premium) se centra en un único asunto activo y, en consecuencia, muestra los resultados de ejemplo provisionales.

  - En un escenario de varios asuntos, el modo Muestreo permite seleccionar los archivos que se incluirán en el procesamiento. Los asuntos definidos como “Desactivados” no se procesarán hasta que se cambie el modo de Muestreo. Un asunto puede estar “inactivo” o “activo” para solo un experto.

  - eDiscovery (Premium) puede usarse para generar archivos de privilegios de candidatos. Configure un asunto separado por privilegio. Si es posible, entrene y seleccione primero para relevancia y, después, realice el entrenamiento para privilegios solo en el conjunto seleccionado (vuelva a cargar el conjunto seleccionado como un caso separado). 

  - El cálculo por lotes solo puede realizarse cuando no haya muestras abiertas (al hacer clic en Cálculo por lotes, se mostrará una lista de usuarios con muestras abiertas). Para “cerrar” las muestras de otros usuarios (esto solo puede realizarse si los usuarios no están etiquetando esas muestras), un administrador puede usar la utilidad “Modificar relevancia” con la opción “Muestra de todos los usuarios”.

- **Metadatos**: eDiscovery (Premium) se centra en el contenido. No tiene en cuenta los metadatos como parte de los criterios de relevancia.

- **Riqueza**: si la riqueza de un asunto es inferior al 3 % después de la evaluación, puede inicializar el entrenamiento de Relevancia con archivos conocidos que sean relevantes y no relevantes.

- **Tamaño de archivo**: Archivos de gran tamaño (con más de 5 242 880 caracteres de texto extraído) se omiten en Relevancia. Los archivos no se incluyen en el proceso de entrenamiento de Relevancia y no reciben una puntuación de Relevancia después del cálculo de lote. Los archivos con un tamaño superior a 5 MB se pueden incluir en el conjunto de evaluaciones.

## <a name="setting-up-case-issues"></a>Configurar asuntos de casos

Los parámetros descritos en esta sección están disponibles en **Relevancia** \> **Configuración de Relevancia** de eDiscovery (Premium).
  
- Los asuntos tienen que asignarse a un usuario que entrenará los archivos.

- Después, los archivos importados tienen que agregarse a la carga que vaya a procesarse.

- Defina y organice asuntos cuidadosamente, ya que esto puede afectar a los resultados de entrenamiento de Relevancia.

Después de establecer los parámetros, el revisor o experto puede empezar a entrenar los archivos en la pestaña **Relevancia**.
