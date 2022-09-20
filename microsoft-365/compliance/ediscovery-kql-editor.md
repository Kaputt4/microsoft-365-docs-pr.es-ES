---
title: Uso del editor de KQL para crear consultas de búsqueda
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Puede usar el editor de KQL para configurar consultas de búsqueda de exhibición de documentos electrónicos en Búsqueda de contenido, eDiscovery (estándar) y eDiscovery (Premium).
ms.openlocfilehash: 60dd9506beaebbb45d795c58f4f04b39d5c4b665
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67826761"
---
# <a name="use-the-kql-editor-to-build-search-queries"></a>Uso del editor de KQL para crear consultas de búsqueda

La nueva experiencia de consulta de KQL en la búsqueda de herramientas de exhibición de documentos electrónicos de Microsoft 365 proporciona comentarios e instrucciones al compilar consultas de búsqueda en Búsqueda de contenido, Microsoft Purview eDiscovery (Estándar) y eDiscovery (Premium). Al escribir consultas en el editor, proporciona autocompletar para las propiedades y condiciones que se pueden buscar admitidas y proporciona listas de valores admitidos para las propiedades y condiciones estándar. Por ejemplo, si especifica la propiedad email en la `kind` consulta, el editor presentará una lista de valores admitidos que puede seleccionar. El editor de KQL también muestra posibles errores de consulta en tiempo real que puede corregir antes de ejecutar la búsqueda. Lo mejor de todo es que puede pegar consultas complejas directamente en el editor sin tener que compilar manualmente consultas mediante las tarjetas de palabras clave y condiciones del generador de condiciones estándar.
  
Estas son las principales ventajas de usar el editor de KQL:

- Proporciona instrucciones y le ayuda a crear consultas de búsqueda desde cero.

- Permite pegar rápidamente consultas largas y complejas directamente en el editor. Por ejemplo, si recibe una consulta compleja de un abogado contrario, puede pegarla en el editor de KQL en lugar de tener que usar el generador de condiciones.

- Identifica rápidamente posibles errores y muestra sugerencias sobre cómo resolver problemas.

El editor de KQL también está disponible cuando se crean retenciones basadas en consultas en eDiscovery (Estándar) y eDiscovery (Premium).

## <a name="displaying-the-kql-editor"></a>Mostrar el editor de KQL

Al crear o editar una búsqueda de exhibición de documentos electrónicos, la opción para mostrar y usar el editor de KQL se encuentra en la página **Condiciones** del Asistente para búsquedas o colecciones.

### <a name="kql-editor-in-content-search-and-ediscovery-standard"></a>Editor de KQL en Búsqueda de contenido y exhibición de documentos electrónicos (estándar)

![Editor de KQL en Búsqueda de contenido y exhibición de documentos electrónicos (estándar)](../media/KQLEditorCore.png)

### <a name="kql-editor-in-ediscovery-premium"></a>Editor de KQL en eDiscovery (Premium)

![Editor de KQL en eDiscovery (Premium)](../media/KQLEditorAdvanced.png)

## <a name="using-the-kql-editor"></a>Uso del editor de KQL

En las secciones siguientes se muestran ejemplos de cómo el editor de KQL proporciona sugerencias y detecta posibles errores.

### <a name="autocompletion-of-search-properties-and-operators"></a>Autocompletar de propiedades y operadores de búsqueda

Al empezar a escribir una consulta de búsqueda en el editor de KQL, el editor muestra la autocompletación sugerida de las propiedades de búsqueda *admitidas (también denominadas restricciones de propiedades*) que puede seleccionar. Tiene que escribir un mínimo de dos caracteres para mostrar una lista de propiedades admitidas que comiencen por esos dos caracteres. Por ejemplo, en la captura de pantalla siguiente se muestran las propiedades de búsqueda sugeridas que comienzan por `Se`.

![El editor de KQL sugiere propiedades admitidas](../media/KQLEditorAutoCompleteProperties.png)

Además, el editor también sugiere proporcionar una lista de operadores admitidos (como `:`, `=` y `<>`) al escribir un nombre de propiedad completo. Por ejemplo, en la captura de pantalla siguiente se muestran los operadores sugeridos para la `Date` propiedad .

![El editor de KQL sugiere operadores](../media/KQLEditorOperatorSuggestions.png)

Para obtener más información sobre las propiedades y operadores de búsqueda admitidos, vea [Consultas de palabras clave y condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md).

### <a name="property-value-suggestions"></a>Sugerencias de valor de propiedad

El editor de KQL proporciona sugerencias para los posibles valores de algunas propiedades. Por ejemplo, en la captura de pantalla siguiente se muestran los valores sugeridos para la `Kind` propiedad .

![El editor de KQL sugiere valores para algunas propiedades](../media/KQLEditorValueSuggestions.png)

El editor también sugiere una lista de usuarios (en formato UPN) al escribir propiedades de destinatario de correo electrónico, como `From`, `To``Recipients` y `Participants`.

![El editor de KQL sugiere a los usuarios las propiedades de correo electrónico del destinatario](../media/KQLEditorRecipientSuggestions.png)

### <a name="detection-of-potential-errors"></a>Detección de posibles errores

El editor de KQL detecta posibles errores en las consultas de búsqueda y proporciona una sugerencia de lo que provoca el error para ayudarle a resolver el error. El editor también indica un posible error cuando una propiedad no tiene una operación o un valor correspondientes. Los posibles errores de la consulta se resaltan en texto rojo y las explicaciones y posibles correcciones para el error se muestran en la sección desplegable **Posibles errores** . Por ejemplo, si pega la siguiente consulta en el editor de KQL, se detectarán cuatro posibles errores.

![Detección de errores del editor de KQL](../media/KQLEditorErrorDetection.png)

En este caso, puede usar las posibles sugerencias de error para solucionar problemas y corregir la consulta.

## <a name="more-information"></a>Más información

- Puede alternar entre el generador de condiciones y el editor de KQL. Por ejemplo, si usa el generador de condiciones para configurar una consulta mediante el cuadro Palabras clave y varias tarjetas de condición, puede mostrar la consulta resultante en el editor de KQL. Sin embargo, si crea una consulta compleja (con palabras clave y condiciones) en el editor de KQL, la consulta resultante solo se muestra en el cuadro Palabras clave cuando se ve en el generador de condiciones.

- Si pega una consulta compleja en el editor de KQL, el editor detecta posibles errores y sugiere posibles soluciones para resolver errores.
