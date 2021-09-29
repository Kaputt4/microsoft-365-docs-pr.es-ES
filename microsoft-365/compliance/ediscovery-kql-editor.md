---
title: Usar el editor de KQL para crear consultas de búsqueda
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Puede usar el editor de KQL para configurar consultas de búsqueda de exhibición de documentos electrónicos en Búsqueda de contenido, Exhibición de documentos electrónicos principal y Advanced eDiscovery.
ms.openlocfilehash: 185ab0396166d54e4a1e11f03a3e3613d24fff4b
ms.sourcegitcommit: 4b1bf6e4f4a0c016d148cdde7f7880dd774403d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2021
ms.locfileid: "59989159"
---
# <a name="use-the-kql-editor-to-build-search-queries"></a>Usar el editor de KQL para crear consultas de búsqueda

La nueva experiencia de consulta KQL en la búsqueda de herramientas de exhibición de documentos electrónicos de Microsoft 365 proporciona comentarios y instrucciones al crear consultas de búsqueda en búsqueda de contenido, exhibición de documentos electrónicos principales y Advanced eDiscovery. Al escribir consultas en el editor, proporciona autocompletar las propiedades y condiciones compatibles con búsquedas y proporciona listas de valores admitidos para las propiedades y condiciones estándar. Por ejemplo, si especifica la propiedad email en la consulta, el editor presentará una lista de valores admitidos `kind` que puede seleccionar. El editor de KQL también muestra posibles errores de consulta en tiempo real que puede corregir antes de ejecutar la búsqueda. Lo mejor de todo es pegar consultas complejas directamente en el editor sin tener que crear consultas manualmente con las palabras clave y las tarjetas de condiciones del generador de condiciones estándar.
  
Estas son las ventajas clave para usar el editor KQL:

- Proporciona instrucciones y ayuda a crear consultas de búsqueda desde cero.

- Permite pegar rápidamente consultas largas y complejas directamente en el editor. Por ejemplo, si recibe una consulta compleja de un asesor opositor, puede pegarla en el editor de KQL en lugar de tener que usar el generador de condiciones.

- Identifica rápidamente posibles errores y muestra sugerencias sobre cómo resolver problemas.

El editor KQL también está disponible al crear retenciones basadas en consultas en eDiscovery principal y en Advanced eDiscovery.

## <a name="displaying-the-kql-editor"></a>Mostrar el editor de KQL

Al crear o editar una búsqueda de exhibición de documentos electrónicos, la  opción para mostrar y usar el editor KQL se encuentra en la página Condiciones del asistente para búsquedas o colecciones.

### <a name="kql-editor-in-content-search-and-core-ediscovery"></a>Editor de KQL en Búsqueda de contenido y exhibición de documentos electrónicos principales

![Editor de KQL en Búsqueda de contenido y exhibición de documentos electrónicos principales](../media/KQLEditorCore.png)

### <a name="kql-editor-in-advanced-ediscovery"></a>Editor KQL en Advanced eDiscovery

![Editor KQL en Advanced eDiscovery](../media/KQLEditorAdvanced.png)

## <a name="using-the-kql-editor"></a>Uso del editor KQL

En las secciones siguientes se muestran ejemplos de cómo el editor de KQL proporciona sugerencias y detecta posibles errores.

### <a name="autocompletion-of-search-properties-and-operators"></a>Autocompletion of search properties and operators

Al empezar a escribir una consulta de búsqueda en el editor de KQL, el editor muestra la autocompleción sugerida de las propiedades de búsqueda admitidas (también *denominadas restricciones* de propiedades) que puede seleccionar. Debe escribir un mínimo de dos caracteres para mostrar una lista de propiedades admitidas que comiencen por esos dos caracteres. Por ejemplo, la siguiente captura de pantalla muestra las propiedades de búsqueda sugeridas que comienzan por `Se` .

![El editor de KQL sugiere propiedades compatibles](../media/KQLEditorAutoCompleteProperties.png)

Además, el editor también sugiere que se proporciona una lista de operadores compatibles (como , y ) al `:` escribir un nombre de propiedad `=` `<>` completo. Por ejemplo, la siguiente captura de pantalla muestra los operadores sugeridos para la `Date` propiedad.

![El editor de KQL sugiere operadores](../media/KQLEditorOperatorSuggestions.png)

Para obtener más información acerca de las propiedades y operadores de búsqueda admitidos, vea Consultas de palabras clave y condiciones [de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md).

### <a name="property-value-suggestions"></a>Sugerencias de valor de propiedad

El editor de KQL proporciona sugerencias para los posibles valores de algunas propiedades. Por ejemplo, la siguiente captura de pantalla muestra los valores sugeridos para la `Kind` propiedad.

![El editor de KQL sugiere valores para algunas propiedades](../media/KQLEditorValueSuggestions.png)

El editor también sugiere una lista de usuarios (en formato UPN) al escribir propiedades de destinatario de correo electrónico, como `From` , `To` y `Recipients` `Participants` .

![El editor de KQL sugiere a los usuarios propiedades de correo electrónico de destinatarios](../media/KQLEditorRecipientSuggestions.png)

### <a name="detection-of-potential-errors"></a>Detección de posibles errores

El editor de KQL detecta posibles errores en las consultas de búsqueda y proporciona una sugerencia de lo que hace que el error le ayude a resolver el error. El editor también indica un posible error cuando una propiedad no tiene una operación o valor correspondiente. Los posibles errores de la consulta se resaltan en texto rojo y  las explicaciones y posibles correcciones del error se muestran en la sección desplegable Errores potenciales. Por ejemplo, si pega la siguiente consulta en el editor de KQL, se detectarían cuatro errores potenciales.

![Detección de errores del editor KQL](../media/KQLEditorErrorDetection.png)

En este caso, puede usar las sugerencias de error potenciales para solucionar problemas y corregir la consulta.

## <a name="more-information"></a>Más información

- Puede alternar entre el generador de condiciones y el editor KQL. Por ejemplo, si usa el generador de condiciones para configurar una consulta mediante el cuadro Palabras clave y varias tarjetas de condición, puede mostrar la consulta resultante en el editor de KQL. Sin embargo, si crea una consulta compleja (con palabras clave y condiciones) en el editor de KQL, la consulta resultante solo se muestra en el cuadro Palabras clave cuando se ve en el generador de condiciones.

- Si pega una consulta compleja en el editor de KQL, el editor detecta posibles errores y sugiere posibles soluciones para resolver errores.
