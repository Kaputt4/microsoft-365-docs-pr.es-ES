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
description: Un clasificador de Microsoft 365 es una herramienta que puede entrenar para reconocer distintos tipos de contenido, ya que le proporciona ejemplos para que los vea. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo volver a entrenarlo para aumentar la precisión.
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752664"
---
# <a name="get-started-with-trainable-classifiers"></a>Introducción a los clasificadores que se pueden entrenar

Un clasificador que se puede entrenar de Microsoft 365 es una herramienta que puede entrenar para reconocer distintos tipos de contenido, ya que le proporciona ejemplos para que los vea. Una vez formado, puede usarlo para identificar el elemento para la aplicación de etiquetas de confidencialidad de Office, directivas de cumplimiento de comunicaciones y directivas de etiquetas de retención.

La creación de un clasificador personalizado que se puede entrenar primero implica darle muestras que son de selección humana y que coinciden positivamente con la categoría. A continuación, después de procesarlos, se prueba la capacidad de los clasificadores para predecir al darle una combinación de muestras positivas y negativas. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo mejorar el rendimiento de clasificadores y clasificadores formados previamente a lo largo de su ciclo de vida a través de la nueva formación.

Para obtener más información acerca de los distintos tipos de clasificadores, vea [Learn about trainable classifiers](classifier-learn-about.md).

## <a name="prerequisites"></a>Requisitos previos

### <a name="licensing-requirements"></a>Requisitos de licencia

Los clasificadores son una característica de cumplimiento de Microsoft 365 E5 o E5. Debe tener una de estas suscripciones para poder usarlas.

### <a name="permissions"></a>Permissions

Para obtener acceso a clasificadores en la interfaz de usuario: 

- El administrador global debe participar para que el inquilino cree clasificadores personalizados.
- El rol de administrador de cumplimiento es necesario para formar a un clasificador.

Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:

- Escenario de directiva de etiquetas de retención: roles administración de registros y administración de retención 
- Escenario de directiva de etiqueta de confidencialidad: Administrador de seguridad, Administrador de cumplimiento, Administrador de datos de cumplimiento
- Escenario de directiva de cumplimiento de comunicaciones: administrador de administración de riesgos de Insider, administrador de revisión de supervisión 

> [!IMPORTANT]
> De forma predeterminada, solo el usuario que crea un clasificador personalizado puede entrenar y revisar las predicción realizadas por ese clasificador.

## <a name="prepare-for-a-custom-trainable-classifier"></a>Prepararse para un clasificador personalizado que se puede entrenar 

Es útil comprender lo que implica la creación de un clasificador personalizado que se puede entrenar antes de profundizar. 

### <a name="timeline"></a>Escala de tiempo

Esta escala de tiempo refleja una implementación de ejemplo de clasificadores que se pueden entrenar.

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Es necesario participar por primera vez para clasificadores que se pueden entrenar. Microsoft 365 tarda doce días en completar una evaluación de línea base del contenido de la organización. Póngase en contacto con el administrador global para iniciar el proceso de suscripción.

### <a name="overall-workflow"></a>Flujo de trabajo general

Para obtener más información sobre el flujo de trabajo general de creación de clasificadores que se pueden entrenar personalizados, vea Flujo de procesos para crear clasificadores que se pueden entrenar [para el cliente.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)

### <a name="seed-content"></a>Contenido de la ed.

Si desea que un clasificador que se pueda entrenar identifique de forma independiente y precisa un elemento como parte de una categoría concreta de contenido, primero debe presentarlo con muchos ejemplos del tipo de contenido que se encuentran en la categoría. Esta alimentación de muestras al clasificador que se puede entrenar se conoce como *edificador.* Un ser humano selecciona el contenido de la edr., que representa la categoría de contenido.

> [!TIP]
> Debe tener al menos 50 muestras positivas y hasta 500. El clasificador que se puede entrenar procesará hasta las 500 muestras creadas más recientes (por marca de fecha y hora de creación de archivos). Cuando más muestras proporciones, más precisas serán las predicción que realizará el clasificador.

### <a name="testing-content"></a>Prueba de contenido

Una vez que el clasificador que se puede entrenar ha procesado suficientes muestras positivas para crear un modelo de predicción, debes probar las predicción que realiza para ver si el clasificador puede distinguir correctamente entre los elementos que coinciden con la categoría y los elementos que no. Para ello, selecciona otro conjunto de contenido seleccionado humano, con suerte más grande, que consta de muestras que deben incluirse en la categoría y las muestras que no. Debes probar con datos diferentes de los datos iniciales de inicialización que proporcionaste por primera vez. Una vez que los procesa, se pasan manualmente por los resultados y se comprueba si cada predicción es correcta, incorrecta o no está seguro. El clasificador que se puede entrenar usa estos comentarios para mejorar su modelo de predicción.

> [!TIP]
> Para obtener mejores resultados, tenga al menos 200 elementos en el conjunto de muestras de prueba con una distribución uniforme de coincidencias positivas y negativas.

## <a name="how-to-create-a-trainable-classifier"></a>Cómo crear un clasificador que se puede entrenar

1. Recopile entre 50 y 500 elementos de contenido de ed. Solo deben ser ejemplos que representen de forma segura el tipo de contenido que desea que el clasificador que se pueda entrenar identifique de forma positiva como si se encontrara en la categoría de clasificación. Vea las extensiones de nombre de archivo rastreadas predeterminadas y los tipos de archivo analizadas [en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo admitidos.

   > [!IMPORTANT]
   > Los elementos de ejemplo de la ed y la prueba no deben estar cifrados y deben estar en inglés.

   > [!IMPORTANT]
   > Asegúrate de que los elementos del conjunto de elementos de la edr. sean **ejemplos seguros** de la categoría. Inicialmente, el clasificador que se puede entrenar crea su modelo en función de lo que se inicializa. El clasificador presupone que todas las muestras de la edar son positivos y no tiene forma de saber si una muestra es una coincidencia débil o negativa con la categoría.

2. Coloque el contenido de la edr. en una carpeta de SharePoint Online dedicada a contener *solo el contenido de la edr.* Tome nota de la dirección URL del sitio, la biblioteca y la carpeta.

   > [!TIP]
   > Si crea un nuevo sitio y una carpeta para los datos de edr, permita al menos una hora para que esa ubicación se indexe antes de crear el clasificador que se puede entrenar que usará los datos de edr.

3. Inicie sesión en el Centro de cumplimiento de Microsoft 365 con acceso al rol de administrador de seguridad o administrador de cumplimiento y abra el Centro de cumplimiento de **Microsoft 365** o la clasificación de datos del Centro de seguridad de **Microsoft 365.**  >  

4. Elija la **pestaña Clasificadores que se pueden entrenar.**

5. Elija **Crear clasificador que se pueda entrenar.**

6. Rellene los valores adecuados para los campos y los campos de la categoría de elementos que desea que identifique `Name` `Description` este clasificador que se puede entrenar.

7. Elija la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online para el sitio de contenido de edr del paso 2. Elija `Add` .

8. Revise la configuración y elija `Create trainable classifier` .

9. En un plazo de 24 horas, el clasificador que se puede entrenar procesará los datos de la edr. y compilará un modelo de predicción. El estado del clasificador es `In progress` mientras procesa los datos de la ed. Cuando el clasificador termina de procesar los datos de la edr, el estado cambia a `Need test items` .

10. Ahora puede ver la página de detalles eligiendo el clasificador.

    > [!div class="mx-imgBorder"]
    > ![clasificador que se puede entrenar listo para pruebas](../media/classifier-trainable-ready-to-test-detail.png)

11. Recopile al menos 200 elementos de contenido de prueba (10 000 como máximo) para obtener los mejores resultados. Estos deben ser una combinación de elementos que son positivos, negativos fuertes y algunos que son un poco menos obvios en su naturaleza. Vea las extensiones de nombre de archivo rastreadas predeterminadas y los tipos de archivo analizadas [en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo admitidos.

    > [!IMPORTANT]
    > Los elementos de ejemplo no deben estar cifrados y deben estar en inglés.

12. Coloque el contenido de prueba en una carpeta de SharePoint Online dedicada a contener *solo el contenido de prueba.* Tome nota de la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online.

    > [!TIP]
    > Si crea un nuevo sitio y una carpeta para los datos de prueba, deje al menos una hora para que esa ubicación se indexe antes de crear el clasificador que se puede entrenar que usará los datos de edr.

13. Elija `Add items to test` .

14. Elija la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online para el sitio de contenido de prueba del paso 12. Elija `Add` .

15. Para finalizar el asistente, elija `Done` . El clasificador que se puede entrenar llevará hasta una hora procesar los archivos de prueba.

16. Cuando el clasificador que se puede entrenar termine de procesar los archivos de prueba, el estado de la página de detalles cambiará a `Ready to review` . Si necesitas aumentar el tamaño de la muestra de prueba, elige y permite que el clasificador que se puede `Add items to test` entrenar procese los elementos adicionales.

    > [!div class="mx-imgBorder"]
    > ![captura de pantalla lista para revisar](../media/classifier-trainable-ready-to-review-detail.png)

17. Elija `Tested items to review` la pestaña para revisar los elementos.

18. Microsoft 365 presentará 30 elementos a la vez. Repase y, `We predict this item is "Relevant". Do you agree?` en el cuadro, elija `Yes` uno `No` o `Not sure, skip to next item` . La precisión del modelo se actualiza automáticamente después de cada 30 elementos.

    > [!div class="mx-imgBorder"]
    > ![cuadro de elementos de revisión](../media/classifier-trainable-review-detail.png)

19. Revise *al menos* 200 elementos. Una vez que se ha estabilizado la puntuación de precisión, la opción **de** publicación estará disponible y el estado del clasificador dirá `Ready to use` .

    > [!div class="mx-imgBorder"]
    > ![puntuación de precisión y listo para publicar](../media/classifier-trainable-review-ready-to-publish.png)

20. Publique el clasificador.

21. Una vez publicado, el clasificador estará disponible como una condición en el etiquetado automático de [Office](apply-sensitivity-label-automatically.md)con etiquetas de confidencialidad, [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automáticamente la directiva de etiqueta de retención en función de una condición y en el cumplimiento de las [comunicaciones.](communication-compliance.md)
