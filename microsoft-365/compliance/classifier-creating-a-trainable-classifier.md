---
title: Crear un clasificador que se pudiera entrenar (versión preliminar)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Use clasificadores que se puedan entrenar cuando uno de los clasificadores de cuadros listos para usar no satisfaga sus necesidades. Un clasificador de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar. En este tema se muestra cómo crear un clasificador personalizado.
ms.openlocfilehash: bbf2fac4e912e6619f3fe1c9a328aa61782cb640
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078896"
---
# <a name="creating-a-trainable-classifier-preview"></a>Creación de un clasificador capacitado (versión preliminar)

Use clasificadores que se podrán entrenar cuando uno de los clasificadores de salida no satisfaga sus necesidades. Un clasificador de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar. La formación del clasificador implica que, en primer lugar, muestreos de ti que sean de picking humanos y que cumplan la categoría. A continuación, una vez procesadas las pruebas, pruebe las predicciones dándole una mezcla de muestras positivas y negativas.

Para obtener más información acerca de los diferentes tipos de clasificadores, consulte [Getting Started with trainable Classifiers (Preview)](classifier-getting-started-with.md) .

Esta escala de tiempo refleja una implementación de ejemplo.

![trainable-Classifier-Timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> La suscripción es necesaria la primera vez para los clasificadores que se deben entrenar. Se necesitan doce días para Microsoft 365 para completar una evaluación de línea de base del contenido de su organización. Póngase en contacto con el administrador global para que inicie el proceso de suscripción.

## <a name="seed-content"></a>Contenido de inicialización

Cuando quiera que un clasificador capacitado identifique de forma independiente y precisa un elemento en una categoría de contenido concreta, primero tiene que presentarlo con muchos ejemplos del tipo de contenido que se encuentran en la categoría. Esta alimentación de muestras al clasificador que se pueda entrenar se conoce como *inicialización*. El contenido de inicialización se selecciona por un hombre y se juzga para representar la categoría de contenido.

> [!TIP]
> Debe tener al menos 50 ejemplos positivos y hasta 500. El clasificador que se pueda entrenar procesará hasta las muestras creadas más recientes de 500 (según la fecha de creación del archivo y la marca de tiempo). Cuanto más ejemplos proporcione, más precisas serán las predicciones que realizará el clasificador.

## <a name="testing-content"></a>Pruebas de contenido

Una vez que el clasificador que se puede entrenar haya procesado suficientes ejemplos positivos para crear un modelo de predicción, debe probar las predicciones que realiza para ver si el clasificador puede distinguir correctamente entre los elementos que coinciden con la categoría y los elementos que no lo hacen. Para ello, debe alimentarse en un conjunto de contenido seleccionado, con suerte más grande, que consista en muestras que deben incluirse en la categoría y en ejemplos que no lo hagan. Una vez que los procese, revise manualmente los resultados y compruebe si cada predicción es correcta, incorrecta o no está seguro. El clasificador capacitado usa estos comentarios para mejorar su modelo de predicción.

> [!TIP]
> Para obtener los mejores resultados, tenga 10.000 elementos en su conjunto de muestras de prueba con una distribución equitativa de las coincidencias negativas y positivas.

## <a name="how-to-create-a-trainable-classifier"></a>Cómo crear un clasificador que se pueda entrenar

1. Recopilar entre 50-500 elementos de contenido de inicialización. Estos deben ser solo ejemplos que representen de forma segura el tipo de contenido que desea que el clasificador capacitado identifique como en la categoría de clasificación. Vea las [extensiones de nombre de archivo y los tipos de archivo analizados predeterminados en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo compatibles.

> [!IMPORTANT]
> Los elementos de la muestra de inicialización y de prueba no deben cifrarse y deben estar en inglés.

> [!IMPORTANT]
> Asegúrese de que los elementos del conjunto de SEED son ejemplos **fuertes** de la categoría. El clasificador que se puede entrenar crea inicialmente su modelo en función de su inicialización. El clasificador presupone que todas las muestras de inicialización son positivos y no tienen forma de saber si una muestra es una coincidencia débil o negativa con la categoría.

2. Colocar el contenido de inicialización en una carpeta de SharePoint Online que esté dedicada exclusivamente a contener *el contenido de inicialización*. Tome nota de la dirección URL del sitio, la biblioteca y la carpeta.

> [!TIP]
> Si crea un sitio y una carpeta nuevos para los datos de inicialización, deje que se indexe al menos una hora para que esa ubicación se Indice antes de crear el clasificador que va a entrenar que usará esos datos de inicialización.

3. Inicie sesión en el centro de cumplimiento de Microsoft 365 con el administrador de cumplimiento o con el rol de administrador de seguridad y Abra **Microsoft 365 Compliance Center** o la clasificación de > **datos** del **centro de seguridad de Microsoft 365**

4. Elija la pestaña **clasificadores** que se puede entrenar.

5. Elija **crear clasificador capacitado**.

6. Rellene los valores apropiados para `Name`los campos `Description` y de la categoría de los elementos que desea que identifique este clasificador capacitado.

7. Escriba la dirección URL del sitio de SharePoint Online, la biblioteca y la carpeta exactas para el sitio de contenido semilla del paso 2. Elija `Add`.

8. Revisa la configuración y elige `Create trainable classifier`.

9. En un plazo de 24 horas, el clasificador con formación procesará los datos de inicialización y creará un modelo de predicción. El estado del clasificador es `In progress` mientras procesa los datos de inicialización. Cuando el clasificador termina de procesar los datos de inicialización, el `Need test items`estado cambia a.

10. Ahora puede ver la página de detalles eligiendo el clasificador.


![clasificador entrenado preparado para pruebas](../media/classifier-trainable-ready-to-test-detail.png)

11. Recopile al menos 200 elementos de contenido de prueba. Microsoft recomienda 10.000 para obtener los mejores resultados. Debe tratarse de una mezcla de elementos que son fuertes positivos, negativos fuertes y algunos que son un poco menos obvios en su naturaleza. Vea las [extensiones de nombre de archivo y los tipos de archivo analizados predeterminados en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo compatibles.

> [!IMPORTANT]
> Los elementos de ejemplo no deben estar cifrados y deben estar en inglés.

12. Colocar el contenido de prueba en una carpeta de SharePoint Online que esté dedicada a contener *el contenido de prueba únicamente*. Anote la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online.

> [!TIP]
> Si crea un nuevo sitio y una carpeta para los datos de prueba, permita al menos una hora para indizar esa ubicación antes de crear el clasificador que va a formar parte de la información que usará esos datos de inicialización.

13. Elija `Add items to test`.

14. Escriba la dirección URL exacta del sitio de SharePoint Online, la biblioteca y la carpeta para el sitio de contenido de prueba del paso 12. Elija `Add`.

15. Para finalizar el asistente, `Done`elija. El clasificador que se pueda entrenar tardará hasta una hora en procesar los archivos de prueba.

16. Cuando el clasificador que se pueda entrenar termine de procesar los archivos de prueba, el estado de la página `Ready to review`detalles cambiará a. Si necesita aumentar el tamaño de la muestra de prueba, `Add items to test` elija y permita que el clasificador que se puede entrenar procese los elementos adicionales.

![captura de pantalla de listo para revisar](../media/classifier-trainable-ready-to-review-detail.png)

17. Elija `Tested items to review` Tab para revisar los elementos.

18. Microsoft 365 presentará 30 elementos a la vez. Revise y, en el `We predict this item is "Relevant". Do you agree?` cuadro, `Yes` elija o `No` o `Not sure, skip to next item`. La precisión del modelo se actualiza automáticamente después de cada 30 elementos.

![cuadro revisar elementos](../media/classifier-trainable-review-detail.png)

19. Revise *al menos* 200 elementos.

<!-- insert Analyze steps here-->

20. Continuar con la revisión hasta que la precisión alcance al menos el 70 `Publish the classifier` % y `Ready to use`el estado sea.

![precisión y lista para publicar](../media/classifier-trainable-review-ready-to-publish.png)

21. Publique el clasificador.

22. Una vez publicado, el clasificador estará disponible como condición en la [Directiva aplicar automáticamente etiquetas de retención basada en una condición](labels.md#applying-a-retention-label-automatically-based-on-conditions) y en el cumplimiento de la [comunicación](communication-compliance.md).

> [!CAUTION]
> Una vez publicado un clasificador, no puede pasar por ningún entrenamiento adicional, así que asegúrese de que ha probado y revisado el mayor número de elementos posible para asegurarse de que la precisión sea lo más alta posible.

## <a name="see-also"></a>Vea también

- [Introducción al entrenamiento de clasificadores (vista previa)](classifier-getting-started-with.md)
- [Extensiones de nombres de archivo rastreados y tipos de archivo analizados de forma predeterminada en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
