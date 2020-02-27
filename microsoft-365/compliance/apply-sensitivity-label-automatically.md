---
title: Aplicar automáticamente una etiqueta de confidencialidad al contenido
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: Al crear una etiqueta de confidencialidad, puede asignar automáticamente una etiqueta a un documento o correo electrónico, o bien puede pedir a los usuarios que seleccionen la etiqueta recomendada.
ms.openlocfilehash: a1ea81bf8c65d3f54d26b19eae3b590f11283c30
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277217"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>Aplicar automáticamente una etiqueta de confidencialidad al contenido

Al crear una etiqueta de confidencialidad, puede asignar automáticamente esa etiqueta a contenido con información confidencial, o bien puede solicitar a los usuarios que apliquen la etiqueta recomendada.

La capacidad de aplicar automáticamente etiquetas de confidencialidad al contenido es importante por estos motivos:

- No es necesario proporcionar aprendizaje a los usuarios para que conozcan todas las clasificaciones.

- No es necesario depender de los usuarios para clasificar todo el contenido correctamente.

- Los usuarios ya no necesitan conocer las directivas de gobierno de datos; en su lugar, pueden centrarse en su trabajo.

El etiquetado automático en las aplicaciones de Office para Windows es compatible con el cliente de etiquetado unificado de Azure Information Protection. Para las etiquetas integradas en las aplicaciones de Office, esta funcionalidad está [en versión preliminar para algunas aplicaciones](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

La configuración de autoetiquetado para las aplicaciones de Office está disponible cuando [crea o edita una etiqueta de confidencial](create-sensitivity-labels.md):

![Opciones de etiquetado automático para etiquetas de confidencialidad](../media/sensitivity-labels-auto-labeling-options.png)

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>Cómo configurar el etiquetado automático para las aplicaciones de Office

Una de las características más eficaces de las etiquetas de confidencialidad es la capacidad de aplicarlas automáticamente al contenido que coincide con determinadas condiciones. En este caso, no es necesario que las personas de la organización apliquen las etiquetas de confidencialidad: Office 365 realiza el trabajo por ellos.

Puede optar por aplicar las etiquetas de confidencial al contenido automáticamente cuando el contenido contenga determinados tipos de información confidencial. Elija una opción de la lista de tipos de información confidencial o clasificadores:

![Condiciones de etiquetas para el etiquetado automático en las aplicaciones de Office](../media/sensitivity-labels-conditions.png)

> [!NOTE]
> Actualmente, la opción de **Clasificadores** está en versión preliminar limitada y requiere que el usuario envíe un formulario a Microsoft para habilitar esta función para su espacio empresarial. Para obtener más información, consulte la entrada del blog que [anuncia el etiquetado automático en las aplicaciones de Office mediante el uso de clasificadores integrados: versión preliminar limitada](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/announcing-automatic-labeling-in-office-apps-using-built-in/ba-p/1192889).

Cuando esta etiqueta de confidencialidad se aplica automáticamente, el usuario ve una notificación en su aplicación de Office. Pueden elegir **Aceptar** para descartar la notificación.

![Notificar que un documento tiene una etiqueta aplicada automáticamente](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>Configuración de tipos de información confidencial para una etiqueta

Si selecciona la opción **tipos de información confidencial**, verá la misma lista de tipos de información confidencial que cuando crea una directiva de prevención de pérdida de datos (DLP). Por ejemplo, puede aplicar automáticamente una etiqueta de altamente confidencial a cualquier contenido que incluya información de identificación personal (PII) de los clientes, como números de tarjeta de crédito o números de la seguridad social:

![Tipos de información confidencial para etiquetado automático en las aplicaciones de Office](../media/sensitivity-labels-sensitive-info-types.png)

Después de seleccionar los tipos de información confidencial, puede restringir la condición al cambiar el recuento de instancias o la precisión de coincidencia. Para obtener más información, vea [Ajustar reglas para hacer más fácil o más difícil la coincidencia](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).

Además, puede elegir si una condición debe detectar todos los tipos de información confidencial o solo uno de ellos. Y para hacer que las condiciones sean más flexibles o complejas, puede agregar grupos y usar operadores lógicos entre los grupos. Para obtener más información, vea [Operadores lógicos y de agrupación](data-loss-prevention-policies.md#grouping-and-logical-operators).

![Opciones de precisión de coincidencia y recuento de instancias](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-classifers-for-a-label"></a>Configuración de clasificadores para una etiqueta

Si selecciona la opción **Clasificadores**, seleccione uno o más de los clasificadores predefinidos:

![Opciones de clasificadores y etiquetas de confidencialidad](../media/sensitivity-labels-classifers.png)

Para obtener más información sobre estos clasificadores, consulte [Introducción al entrenamiento de clasificadores (vista previa)](classifier-getting-started-with.md).

Durante el período de versión preliminar, las siguientes aplicaciones son compatibles con clasificadores para las etiquetas de confidencial:

- Las aplicaciones de escritorio de Office 365 ProPlus para Windows, de [Office Insider](https://office.com/insider):
    - Word
    - Excel
    - PowerPoint

- Aplicaciones de Office para la web, si ha [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (versión preliminar pública)](sensitivity-labels-sharepoint-onedrive-files.md):
    - Word
    - Excel
    - PowerPoint
    - Outlook

## <a name="recommend-that-the-user-apply-a-sensitivity-label"></a>Recomendación para que el usuario aplique una etiqueta de confidencialidad

Si lo prefiere, puede recomendar a los usuarios que apliquen la etiqueta. Con esta opción, los usuarios pueden aceptar la clasificación y cualquier protección asociada, o descartar la recomendación si la etiqueta no es adecuada para su contenido.

Las etiquetas recomendadas son compatibles con Word, PowerPoint y Excel.

![Opción para recomendar una etiqueta de confidencialidad a los usuarios](../media/Sensitivity-labels-Recommended-label-option.png)

Este es un ejemplo de un mensaje que se muestra al configurar una condición para aplicar una etiqueta como acción recomendada con una sugerencia de directiva personalizada. Puede elegir el texto que se muestra en la sugerencia de directiva.

![Mensaje para aplicar una etiqueta recomendada](../media/Sensitivity-label-Prompt-for-required-label.png)

## <a name="how-automatic-or-recommended-labels-are-applied"></a>Forma de aplicar etiquetas recomendadas o automáticas

- El etiquetado automático se aplica a Word, Excel y PowerPoint al guardar un documento, y a Outlook al enviar un correo electrónico. Estas condiciones detectan información confidencial en el texto de cuerpo de los documentos y correos electrónicos, y en los encabezados y pies de página, pero no en la línea de asunto o los datos adjuntos de correo electrónico.

- No puede usar el etiquetado automático para documentos y mensajes de correo electrónico que se etiquetaron previamente de forma manual o de forma automática con una confidencialidad más alta. Recuerde, solo se puede aplicar una etiqueta de confidencialidad a un documento o correo electrónico, (además de una sola etiqueta de retención).

- El etiquetado recomendado se aplica a Word, Excel y PowerPoint al guardar documentos.

- No puede usar el etiquetado recomendado para documentos que anteriormente se etiquetaron con una confidencialidad más alta. Cuando el contenido ya está etiquetado con una confidencialidad más alta, el usuario no verá el mensaje con la recomendación y la sugerencia de directiva.

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>Forma en que se evalúan varias condiciones cuando se aplican en más de una etiqueta

Las etiquetas se ordenan para su evaluación según la posición que especifique en la directiva: la primera etiqueta colocada tiene la posición inferior (menor confidencialidad) y la última etiqueta colocada tiene la posición superior (mayor confidencialidad). Para obtener más información sobre la prioridad, vea [Prioridad de etiqueta (el orden importa)](sensitivity-labels.md#label-priority-order-matters).

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>No configure una etiqueta principal para que se aplique o recomiende automáticamente

Recuerde, no se puede aplicar una etiqueta principal (una etiqueta con subetiquetas) al contenido. Asegúrese de no configurar una etiqueta principal para que se aplique o recomiende automáticamente, ya que la etiqueta principal no se aplicará al contenido en las aplicaciones de Office que usan el cliente de etiquetado unificado de Azure Information Protection. Para obtener más información sobre las etiquetas principales y las subetiquetas, consulte [Subetiquetas (agrupación de etiquetas)](sensitivity-labels.md#sublabels-grouping-labels).
