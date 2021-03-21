---
title: Introducción a los clasificadores que se pueden entrenar
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Un clasificador de Microsoft 365 es una herramienta que puede entrenar para reconocer varios tipos de contenido, ya que le proporciona ejemplos para que los vea. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo volver a entrenarlos para aumentar la precisión.
ms.openlocfilehash: 90e47ec94528bbadeb98dc9eb590929e25ae6ff1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918184"
---
# <a name="get-started-with-trainable-classifiers"></a>Introducción a los clasificadores que se pueden entrenar

Un clasificador entrenable de Microsoft 365 es una herramienta que puede entrenar para reconocer varios tipos de contenido, ya que le proporciona ejemplos para que los vea. Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.

Crear un clasificador personalizado para entrenar primero implica darle muestras que son humanas seleccionada y coinciden positivamente con la categoría. A continuación, después de procesarlos, se prueba la capacidad de los clasificadores para predecir al darle una combinación de muestras positivas y negativas. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo mejorar el rendimiento de clasificadores personalizados y clasificadores previamente formados a lo largo de su vida a través de la readaptación.

Para obtener más información sobre los diferentes tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).

Vea este vídeo para ver un resumen rápido de la creación de un clasificador que se puede entrenar. Todavía tendrá que leer este artículo completo para obtener los detalles.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a>Requisitos previos

### <a name="licensing-requirements"></a>Requisitos de licencia

Los clasificadores son una característica de cumplimiento de Microsoft 365 E5 o E5. Debe tener una de estas suscripciones para poder usarlas.

### <a name="permissions"></a>Permisos

Para obtener acceso a clasificadores en la interfaz de usuario: 

- El administrador global debe participar para que el inquilino cree clasificadores personalizados.
- El rol Administrador de cumplimiento es necesario para entrenar a un clasificador.

Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:

- Escenario de directiva de etiqueta de retención: roles de administración de registros y administración de retención 
- Escenario de directiva de etiqueta de confidencialidad: Administrador de seguridad, Administrador de cumplimiento, Administrador de datos de cumplimiento
- Escenario de directiva de cumplimiento de comunicaciones: Administrador de administración de riesgos de Insider, Administrador de revisión de supervisión 

> [!IMPORTANT]
> De forma predeterminada, solo el usuario que crea un clasificador personalizado puede entrenar y revisar las previsiones realizadas por ese clasificador.

## <a name="prepare-for-a-custom-trainable-classifier"></a>Prepararse para un clasificador personalizado que se puede entrenar 

Es útil comprender lo que implica la creación de un clasificador personalizado para entrenar antes de profundizar. 

### <a name="timeline"></a>Escala de tiempo

Esta escala de tiempo refleja una implementación de ejemplo de clasificadores entrenables.

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> El opt-in es necesario la primera vez para clasificadores que se pueden entrenar. Microsoft 365 tarda doce días en completar una evaluación de línea base del contenido de la organización. Póngase en contacto con el administrador global para iniciar el proceso de suscripción.

### <a name="overall-workflow"></a>Flujo de trabajo general

Para obtener más información sobre el flujo de trabajo general de creación de clasificadores personalizados, vea [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).

### <a name="seed-content"></a>Contenido de la ed.

Cuando desea que un clasificador entrenable identifique de forma independiente y precisa un elemento como una categoría concreta de contenido, primero debe presentarlo con muchas muestras del tipo de contenido que hay en la categoría. Esta alimentación de muestras al clasificador que se puede entrenar se conoce como *edificación*. Un humano selecciona el contenido de la seed y se considera que representa la categoría de contenido.

> [!TIP]
> Debe tener al menos 50 muestras positivas y hasta 500. El clasificador que se puede entrenar procesará hasta los 500 ejemplos creados más recientes (por marca de fecha y hora creada por archivo). Entre más muestras proporciones, más precisas serán las previsiones que realizará el clasificador.

### <a name="testing-content"></a>Probar contenido

Una vez que el clasificador capacitado haya procesado suficientes ejemplos positivos para crear un modelo de predicción, debe probar las previsiones que realiza para ver si el clasificador puede distinguir correctamente entre los elementos que coinciden con la categoría y los elementos que no lo hacen. Para ello, selecciona otro conjunto de contenido seleccionado por humanos, que se espera que sea más grande, que consta de muestras que deben incluirse en la categoría y muestras que no lo hagan. Debe probar con datos diferentes a los datos iniciales de inicialización que proporcionó por primera vez. Una vez que los procesa, se pasan manualmente por los resultados y se comprueba si cada predicción es correcta, incorrecta o no está seguro. El clasificador que puede entrenar usa estos comentarios para mejorar su modelo de predicción.

> [!TIP]
> Para obtener mejores resultados, tenga al menos 200 elementos en el conjunto de muestras de prueba con una distribución uniforme de coincidencias positivas y negativas.

## <a name="how-to-create-a-trainable-classifier"></a>Cómo crear un clasificador que se puede entrenar

1. Recopilar entre 50 y 500 elementos de contenido de ed. Estos deben ser solo ejemplos que representen fuertemente el tipo de contenido que desea que el clasificador capacitado identifique positivamente como en la categoría de clasificación. Consulte Extensiones de nombre de archivo rastreadas predeterminadas y tipos de archivo analizadas en [SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo admitidos.

   > [!IMPORTANT]
   > Los elementos de ejemplo de seed y test no deben cifrarse y deben estar en inglés.

   > [!IMPORTANT]
   > Asegúrese de que los elementos del conjunto de posiciones **son ejemplos** sólidos de la categoría. El clasificador que se puede entrenar crea inicialmente su modelo en función de con qué lo edificó. El clasificador asume que todas las muestras de ed.0 son positivos fuertes y no tiene forma de saber si una muestra es una coincidencia débil o negativa con la categoría.

2. Coloque el contenido de la ed.ed en una carpeta de SharePoint Online dedicada a mantener *el contenido de ed.* Anote la dirección URL del sitio, la biblioteca y la carpeta.

   > [!TIP]
   > Si crea un nuevo sitio y una carpeta para los datos de edificadores, permita al menos una hora para que esa ubicación se indexe antes de crear el clasificador que se puede entrenar que usará los datos de ed.

3. Inicie sesión en el Centro de cumplimiento de Microsoft 365 con acceso al rol de administrador de seguridad o administrador de cumplimiento y abra el Centro de cumplimiento de **Microsoft 365** o la clasificación de datos del centro de seguridad de **Microsoft 365.**  >  

4. Elija la **pestaña Clasificadores que se pueden entrenar.**

5. Elija **Create trainable classifier**.

6. Rellene los valores adecuados para los campos y de la categoría de elementos que desea que identifique este `Name` `Description` clasificador entrenable.

7. Elija la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online para el sitio de contenido de ed. del paso 2. Elija `Add` .

8. Revise la configuración y elija `Create trainable classifier` .

9. En un plazo de 24 horas, el clasificador que se puede entrenar procesará los datos de ed. y compilará un modelo de predicción. El estado del clasificador `In progress` es mientras procesa los datos de ed. Cuando el clasificador termina de procesar los datos de ed. `Need test items`

10. Ahora puede ver la página de detalles eligiendo el clasificador.

    > [!div class="mx-imgBorder"]
    > ![clasificador trainable listo para pruebas](../media/classifier-trainable-ready-to-test-detail.png)

11. Recopile al menos 200 elementos de contenido de prueba (10 000 como máximo) para obtener mejores resultados. Estos deben ser una combinación de elementos que son positivos fuertes, negativos fuertes y algunos que son un poco menos obvios en su naturaleza. Consulte Extensiones de nombre de archivo rastreadas predeterminadas y tipos de archivo analizadas en [SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo admitidos.

    > [!IMPORTANT]
    > Los elementos de ejemplo no deben cifrarse y deben estar en inglés.

12. Coloque el contenido de prueba en una carpeta de SharePoint Online dedicada únicamente a contener *el contenido de prueba.* Anote la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online.

    > [!TIP]
    > Si crea un nuevo sitio y una carpeta para los datos de prueba, permita al menos una hora para que esa ubicación se indexe antes de crear el clasificador que se puede entrenar que usará los datos de ed.

13. Elija `Add items to test` .

14. Seleccione la dirección URL del sitio, biblioteca y carpeta de SharePoint Online para el sitio de contenido de prueba del paso 12. Elija `Add` .

15. Para finalizar el asistente, elija `Done` . El clasificador que se puede entrenar llevará hasta una hora procesar los archivos de prueba.

16. Cuando el clasificador capacitado termine de procesar los archivos de prueba, el estado de la página de detalles cambiará a `Ready to review` . Si necesita aumentar el tamaño de la muestra de prueba, elija y permita que el clasificador capacitado `Add items to test` procese los elementos adicionales.

    > [!div class="mx-imgBorder"]
    > ![listo para revisar la captura de pantalla](../media/classifier-trainable-ready-to-review-detail.png)

17. Elija `Tested items to review` la pestaña para revisar los elementos.

18. Microsoft 365 presentará 30 elementos a la vez. Repase y, en `We predict this item is "Relevant". Do you agree?` el cuadro, `Yes` elija o `No` `Not sure, skip to next item` . La precisión del modelo se actualiza automáticamente después de cada 30 elementos.

    > [!div class="mx-imgBorder"]
    > ![cuadro revisar elementos](../media/classifier-trainable-review-detail.png)

19. Revise *al menos* 200 elementos. Una vez estabilizada la puntuación de precisión, la **opción de** publicación estará disponible y el estado del clasificador dirá `Ready to use` .

    > [!div class="mx-imgBorder"]
    > ![puntuación de precisión y lista para publicar](../media/classifier-trainable-review-ready-to-publish.png)

20. Publique el clasificador.

21. Una vez publicado, el clasificador estará disponible como una condición en el etiquetado automático de [Office](apply-sensitivity-label-automatically.md)con etiquetas de confidencialidad, [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automáticamente la directiva de etiquetas de retención según una condición y en Cumplimiento de [comunicaciones.](communication-compliance.md)