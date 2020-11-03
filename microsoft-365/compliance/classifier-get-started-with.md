---
title: Introducción a los clasificadores que se pueden entrenar (versión preliminar)
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
description: Un clasificador de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo volver a entrenarlos para aumentar la precisión.
ms.openlocfilehash: 4475456e7116acbc705a3121079391a571fcca8a
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841237"
---
# <a name="get-started-with-trainable-classifiers-preview"></a>Introducción a los clasificadores que se pueden entrenar (versión preliminar)

Un clasificador entrenado de 365 de Microsoft es una herramienta que puede entrenar para que reconozca varios tipos de contenido proporcionándoles ejemplos para mirar. Una vez preparado, puede usarlo para identificar el elemento para la aplicación de las etiquetas de confidencialidad de Office, las directivas de cumplimiento de comunicaciones y las directivas de etiquetas de retención.

La creación de un clasificador personalizado personalizado en primer lugar implica dar a los ejemplos que se seleccionan y que cumplen de forma positiva la categoría. A continuación, después de procesarlos, pruebe la capacidad de los clasificadores para predecir dándole una mezcla de muestras positivas y negativas. En este artículo se muestra cómo crear y entrenar un clasificador personalizado y cómo mejorar el rendimiento de los clasificadores capacitados personalizados y los clasificadores preparados previamente durante su ciclo de vida mediante la formación.

Para obtener más información acerca de los diferentes tipos de clasificadores, consulte [información sobre los clasificadores que se puedan entrenar (versión preliminar)](classifier-learn-about.md).

## <a name="prerequisites"></a>Requisitos previos

### <a name="licensing-requirements"></a>Requisitos de licencia

Los clasificadores son una característica de cumplimiento de Microsoft 365 E5 o E5. Debe tener una de estas suscripciones para poder usarla.

### <a name="permissions"></a>Permisos

Para acceder a los clasificadores en la interfaz de usuario: 

- el administrador global debe participar en el inquilino para crear clasificadores personalizados.
- el rol de administrador de cumplimiento, el rol de investigación de datos o el administrador de datos de cumplimiento es necesario para entrenar a un clasificador.

Necesitará cuentas con estos permisos para usar clasificadores en estos escenarios:

- Escenario de directiva de etiqueta de retención: funciones de administración de registros y retención 
- Escenario de directiva de etiqueta de confidencialidad: administrador de seguridad, administrador de cumplimiento, administrador de datos de cumplimiento
- Escenario de directiva de cumplimiento de comunicaciones: administrador de administración de riesgos de Insider, administrador de revisión de supervisión 

> [!IMPORTANT]
> De forma predeterminada, solo el usuario que crea un clasificador personalizado puede entrenar y revisar las predicciones realizadas por ese clasificador. Si desea que otros usuarios puedan entrenar y revisar las predicciones del clasificador, consulte [conceder a otros entrenar y revisar derechos](#give-others-train-and-review-rights).

## <a name="prepare-for-a-custom-trainable-classifier"></a>Preparar un clasificador personalizado para la formación 

Es útil comprender lo que implica la creación de un clasificador que se puede personalizar de forma personalizada antes de profundizar. 

### <a name="timeline"></a>Escala de tiempo

Esta escala de tiempo refleja una implementación de ejemplo de clasificadores que se capacitan.

![trainable-Classifier-Timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> La suscripción es necesaria la primera vez para los clasificadores que se deben entrenar. Se necesitan doce días para Microsoft 365 para completar una evaluación de línea de base del contenido de su organización. Póngase en contacto con el administrador global para que inicie el proceso de suscripción.

### <a name="overall-workflow"></a>Flujo de trabajo general

Para obtener más información acerca del flujo de trabajo general sobre la creación de clasificadores que se puedan entrenar de forma personalizada, vea [flujo del proceso para crear clasificadores capacitados para clientes](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).

### <a name="seed-content"></a>Contenido de inicialización

Cuando quiera que un clasificador capacitado identifique de forma independiente y precisa un elemento en una categoría de contenido concreta, primero tiene que presentarlo con muchos ejemplos del tipo de contenido que se encuentran en la categoría. Esta alimentación de muestras al clasificador que se pueda entrenar se conoce como *inicialización*. El contenido de inicialización se selecciona por un hombre y se juzga para representar la categoría de contenido.

> [!TIP]
> Debe tener al menos 50 ejemplos positivos y hasta 500. El clasificador que se pueda entrenar procesará hasta las muestras creadas más recientes de 500 (según la fecha de creación del archivo y la marca de tiempo). Cuanto más ejemplos proporcione, más precisas serán las predicciones que realizará el clasificador.

### <a name="testing-content"></a>Pruebas de contenido

Una vez que el clasificador que se puede entrenar haya procesado suficientes ejemplos positivos para crear un modelo de predicción, debe probar las predicciones que realiza para ver si el clasificador puede distinguir correctamente entre los elementos que coinciden con la categoría y los elementos que no lo hacen. Para ello, seleccione otro conjunto de contenido seleccionado humano que consista en muestras que deben incluirse en la categoría y en ejemplos que no lo hagan. Debe probar con datos diferentes de los datos de inicialización iniciales que ha proporcionado por primera vez. Una vez que los procese, revise manualmente los resultados y compruebe si cada predicción es correcta, incorrecta o no está seguro. El clasificador capacitado usa estos comentarios para mejorar su modelo de predicción.

> [!TIP]
> Para obtener los mejores resultados, tenga al menos 200 elementos en el conjunto de muestras de prueba con una distribución equitativa de las coincidencias negativas y positivas.

## <a name="how-to-create-a-trainable-classifier"></a>Cómo crear un clasificador que se pueda entrenar

1. Recopilar entre 50-500 elementos de contenido de inicialización. Estos deben ser solo ejemplos que representen de forma segura el tipo de contenido que desea que el clasificador capacitado identifique como en la categoría de clasificación. Vea las [extensiones de nombre de archivo y los tipos de archivo analizados predeterminados en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo compatibles.

   > [!IMPORTANT]
   > Los elementos de la muestra de inicialización y de prueba no deben cifrarse y deben estar en inglés.

   > [!IMPORTANT]
   > Asegúrese de que los elementos del conjunto de SEED son ejemplos **fuertes** de la categoría. El clasificador que se puede entrenar crea inicialmente su modelo en función de su inicialización. El clasificador presupone que todas las muestras de inicialización son positivos y no tienen forma de saber si una muestra es una coincidencia débil o negativa con la categoría.

2. Colocar el contenido de inicialización en una carpeta de SharePoint Online que esté dedicada exclusivamente a contener *el contenido de inicialización*. Tome nota de la dirección URL del sitio, la biblioteca y la carpeta.

   > [!TIP]
   > Si crea un sitio y una carpeta nuevos para los datos de inicialización, deje que se indexe al menos una hora para que esa ubicación se Indice antes de crear el clasificador que va a entrenar que usará esos datos de inicialización.

3. Inicie sesión en el centro de cumplimiento de Microsoft 365 con el administrador de cumplimiento o con el rol de administrador de seguridad y abra el **centro de cumplimiento** de Microsoft 365 o la clasificación de datos del **centro de seguridad de Microsoft 365**  >  **Data classification**.

4. Elija la pestaña **clasificadores** que se puede entrenar.

5. Elija **crear clasificador capacitado**.

6. Rellene los valores apropiados para `Name` los `Description` campos y de la categoría de elementos que desea que identifique este clasificado que se puede entrenar.

7. Seleccione el sitio de SharePoint Online, la biblioteca y la dirección URL de la carpeta para el sitio de contenido semilla del paso 2. Elija `Add` .

8. Revisa la configuración y elige `Create trainable classifier` .

9. En un plazo de 24 horas, el clasificador con formación procesará los datos de inicialización y creará un modelo de predicción. El estado del clasificador es `In progress` mientras procesa los datos de inicialización. Cuando el clasificador termina de procesar los datos de inicialización, el estado cambia a `Need test items` .

10. Ahora puede ver la página de detalles eligiendo el clasificador.

    > [!div class="mx-imgBorder"]
    > ![clasificador entrenado preparado para pruebas](../media/classifier-trainable-ready-to-test-detail.png)

11. Recopile al menos 200 elementos de contenido de prueba (10.000 máx.) para obtener los mejores resultados. Debe tratarse de una mezcla de elementos que son fuertes positivos, negativos fuertes y algunos que son un poco menos obvios en su naturaleza. Vea las [extensiones de nombre de archivo y los tipos de archivo analizados predeterminados en SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para los tipos de archivo compatibles.

    > [!IMPORTANT]
    > Los elementos de ejemplo no deben estar cifrados y deben estar en inglés.

12. Colocar el contenido de prueba en una carpeta de SharePoint Online que esté dedicada a contener *el contenido de prueba únicamente*. Anote la dirección URL del sitio, la biblioteca y la carpeta de SharePoint Online.

    > [!TIP]
    > Si crea un nuevo sitio y una carpeta para los datos de prueba, permita al menos una hora para indizar esa ubicación antes de crear el clasificador que va a formar parte de la información que usará esos datos de inicialización.

13. Elija `Add items to test` .

14. Seleccione el sitio de SharePoint Online, la biblioteca y la dirección URL de la carpeta para el sitio de contenido de prueba del paso 12. Elija `Add` .

15. Para finalizar el asistente, elija `Done` . El clasificador que se pueda entrenar tardará hasta una hora en procesar los archivos de prueba.

16. Cuando el clasificador que se pueda entrenar termine de procesar los archivos de prueba, el estado de la página Detalles cambiará a `Ready to review` . Si necesita aumentar el tamaño de la muestra de prueba, elija `Add items to test` y permita que el clasificador que se puede entrenar procese los elementos adicionales.

    > [!div class="mx-imgBorder"]
    > ![captura de pantalla de listo para revisar](../media/classifier-trainable-ready-to-review-detail.png)

17. Elija `Tested items to review` Tab para revisar los elementos.

18. Microsoft 365 presentará 30 elementos a la vez. Revise y, en el `We predict this item is "Relevant". Do you agree?` cuadro, elija `Yes` o `No` o `Not sure, skip to next item` . La precisión del modelo se actualiza automáticamente después de cada 30 elementos.

    > [!div class="mx-imgBorder"]
    > ![cuadro revisar elementos](../media/classifier-trainable-review-detail.png)

19. Revise *al menos* 200 elementos. Una vez que la puntuación de precisión se ha estabilizado, la opción **publicar** estará disponible y el estado del clasificador se dirá `Ready to use` .

    > [!div class="mx-imgBorder"]
    > ![puntuación de precisión y lista para publicar](../media/classifier-trainable-review-ready-to-publish.png)

20. Publique el clasificador.

21. Una vez publicado el clasificador estará disponible como condición en el [etiquetado automático de Office con etiquetas de confidencialidad](apply-sensitivity-label-automatically.md), [aplicar automáticamente una directiva de etiqueta de retención basada en una condición](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) y en el cumplimiento de la [comunicación](communication-compliance.md).

## <a name="give-others-train-and-review-rights"></a>Proporcionar a otros usuarios los derechos de aprendizaje y revisión

Use este procedimiento para conceder a otros usuarios permisos para entrenar, revisar y ajustar el clasificador que se ha personalizado para su formación.  
 
1. Como creador del clasificador, un administrador global o administrador de exhibición de documentos electrónicos se conecta al centro de cumplimiento mediante PowerShell usando los procedimientos descritos en [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).

2. Ejecute este comando:

   ```powershell
   Add-ComplianceCaseMember -Case "<classifier name>" -Member "<user or role group>"
   ```
   
   Por ejemplo:
   
   `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`

   Puede ejecutar este comando varias veces para agregar varios usuarios. Tenga en cuenta que solo puede agregar grupos de roles de Exchange Online Protection (EOP) y no grupos de roles de Azure.
