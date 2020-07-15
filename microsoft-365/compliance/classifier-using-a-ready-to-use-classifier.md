---
title: Probar clasificadores integrados con etiquetas de retención (versión preliminar)
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
description: Microsoft 365 incluye varios clasificadores integrados que puede usar para identificar y etiquetar el contenido en toda la organización. En este tema se muestra cómo prepararse para usar estos clasificadores.
ms.openlocfilehash: 82155b1dee9ab04dad593ce9ec2da97d3e796e99
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126319"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a>Probar clasificadores integrados con etiquetas de retención (versión preliminar)

Microsoft ha entrenado y probado cinco clasificadores que pueden ayudarle a identificar determinadas categorías de contenido. Estos clasificadores se muestran en el `Ready to use` grupo de forma predeterminada y se han entrenado con conjuntos de datos de ejemplo muy grandes.

> [!IMPORTANT]
> Antes de usar clasificadores integrados en el flujo de trabajo de clasificación y etiquetado, debe probarlo con una muestra del contenido de la organización que considere que la categoría para comprobar que sus predicciones de clasificación satisfacen sus expectativas.

Para obtener más información sobre los clasificadores [interactivos, vea Getting Started with trainable Classifiers (Preview)](classifier-getting-started-with.md).

Microsoft 365 incluye cinco clasificadores integrados recomendados:

> [!CAUTION]
> Estamos desaprobando el clasificador incorporado de **Lenguaje ofensivo** porque ha estado produciendo un alto número de falsos positivos. No lo use y, si actualmente lo está usando, debería mover sus procesos de negocio fuera de él. En su lugar, se recomienda usar los clasificadores de **amenaza**, **blasfemia**y **acoso** integrados.

- **Currículos**: detecta los elementos que son cuentas de texto de la cualificación personal, educativa, profesional, experiencia laboral y otra información de identificación personal del solicitante.
- **Código de origen**: detecta elementos que contienen un conjunto de instrucciones e instrucciones escritas en los 25 principales lenguajes de programación usados del equipo en github

  |nombre del idioma|||||
  |---------|---------|---------|---------|---------|
  |Código|C        |C#       |+     |Clojure  |
  |CoffeeScript|CSS     |Ir       |Haskell |HTML     |
  |Java     |JavaScript|Lua      |MATLAB   |Objective-C|
  |Perl     |PHP      |Python   |R        |Ruby     |
  |Scala    |Consola    |Rápido    |Tex      |Script de VIM|

> [!NOTE]
> El código fuente está entrenado para detectar cuando la mayor parte del texto es código fuente. No detecta texto de código fuente intercalado con texto sin formato.

- **Acosar**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con la conducta ofensiva dirigida a uno o varios individuos en función de los siguientes rasgos: raza, étnico, religión, origen nacional, sexo, orientación sexual, edad, discapacidad
- **Blasfemias**: detecta una categoría específica de elementos de texto de lenguaje ofensivo que contiene expresiones que avergonzan a la mayoría de las personas
- **Amenaza**: detecta una categoría específica de elementos de texto de lenguaje ofensivo relacionados con amenazas para confirmar violencia o daño físico o daño a una persona o propiedad

> [!IMPORTANT]
> Tenga en cuenta que el idioma ofensivo, el acoso, los términos blasfemos y los clasificadores de amenazas solo funcionan con texto que admite búsquedas no es exhaustivo o completo. Además, los estándares de idioma y culturales cambian continuamente y, teniendo en cuenta estas realidades, Microsoft se reserva el derecho de actualizar estos clasificadores según su criterio. Aunque los clasificadores pueden ayudar a su organización a supervisar el uso ofensivo y otros idiomas, los clasificadores no abordan las consecuencias de ese lenguaje y no pretenden proporcionar a los únicos medios de supervisar o responder al uso de ese lenguaje en su organización. Su organización, y no Microsoft o sus subsidiarias, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, la aplicación, el bloqueo, la eliminación y la retención de cualquier contenido identificado por un clasificador previamente entrenado.

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a>Cómo comprobar que un clasificador integrado se ajusta a sus necesidades

1. Recopile los elementos de contenido de pruebas desechables que considera que pertenecen a la categoría del clasificador integrado (coincidencias positivas) y los que no se deben incluir (coincidencias negativas) en la categoría que está probando.

   > [!IMPORTANT]
   > Los elementos de ejemplo no deben estar cifrados y deben estar en inglés.

2. Cree una carpeta dedicada de SharePoint Online; espere al menos una hora para que la carpeta se agregue al índice de búsqueda. Anote la dirección URL de la carpeta.

3. Inicie sesión en el centro de cumplimiento de Microsoft 365 con el administrador de cumplimiento o el rol de administrador de seguridad y abra la ficha directivas de administración de registros del **centro de cumplimiento de Microsoft 365**  >  **(versión preliminar)**  >  **Label policies** .

4. Elija `Auto-apply a label` .

5. Elija `Choose a label to auto-apply` .

6. Elija `Create new labels` y cree una etiqueta para usarla sólo con esta prueba. Cuando lo haga, deje `Retention` set en `off` . No desea activar ninguna retención ni otras acciones. En este caso, utilizará la etiqueta de retención simplemente como una etiqueta de texto, sin aplicar ninguna acción. Por ejemplo, puede crear una etiqueta de retención denominada "SourceCode Classifier test" sin ninguna acción y, a continuación, aplicar automáticamente esa etiqueta de retención a contenido que tiene clasificador de código fuente como condición. Para obtener más información sobre las etiquetas de retención, consulte [información sobre las directivas de retención y las etiquetas de retención](retention.md).
  
7. Elija `Auto-apply a label` y, a continuación, `Choose a label to auto-apply` . Para obtener más información sobre el uso de la aplicación basada en condiciones, aplique automáticamente una etiqueta consulte [configurar las condiciones para aplicar automáticamente etiquetas de retención](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels).

8. Elija su etiqueta de prueba de la lista y elija `Next` .

9. Elija `Apply label to content that matches a trainable classifier` .

   ![selección de clasificador como condición](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

10. Elija su clasificador de la lista, en este caso`Source Code`

11. Asigne un nombre a la Directiva, por ejemplo, "prueba de clasificador del código fuente integrada".

12. Elija `Let me choose specific locations` .

13. Desactive todas las ubicaciones excepto `SharePoint sites` y elija `Choose sites` .

14. Escriba la dirección URL del sitio en el paso 2.

15. Finaliza el asistente y elige`Auto-apply`

16. Ponga los elementos de prueba en la carpeta dedicada de SharePoint Online.

17. Permite aplicar una hora para la etiqueta.

18. Compruebe las propiedades de los documentos para la etiqueta para ver si el clasificador incluyó y excluya el contenido de prueba tal como esperaba.

19. Revise los elementos etiquetados.

20. Elimine el contenido y la Directiva de etiqueta si ya ha terminado con las pruebas.

Vea también:

- [Introducción al entrenamiento de clasificadores (vista previa)](classifier-getting-started-with.md)
- [Obtener información sobre las directivas de retención y las etiquetas de retención](retention.md)
- [Aplicar automáticamente una etiqueta de retención para conservar o eliminar contenido](apply-retention-labels-automatically.md)
