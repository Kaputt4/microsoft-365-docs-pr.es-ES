---
title: Aumentar la precisión del clasificador
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Aprenda a aumentar la precisión de los clasificadores.
ms.openlocfilehash: 4254571c5b98f18f5c914010d5b2ecd3f814ccd8
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67812628"
---
# <a name="increase-classifier-accuracy-preview"></a>Aumentar la precisión del clasificador (versión preliminar)

Los clasificadores, como los [tipos de información confidencial](sensitive-information-type-learn-about.md) (SIT) y [los clasificadores entrenables](classifier-learn-about.md) , se usan en varios tipos de directivas para identificar información confidencial. Al igual que todos los modelos, a veces identifican un elemento como confidencial que no lo es. O a veces que no identifican un elemento como confidencial cuando realmente lo es. Estos se denominan falsos positivos y falsos negativos. 

En este artículo se muestra cómo confirmar si los elementos coincidentes por un clasificador son verdaderos positivos (una **coincidencia**) o un falso positivo (**no una coincidencia**) y proporcionan comentarios **de coincidencia** o **no de coincidencia** . Puede usar esos comentarios para ajustar los clasificadores para aumentar la precisión. También puede enviar a Microsoft las versiones redactadas del documento, así como los comentarios **de Match**, **Not a Match** si desea ayudar a aumentar la precisión de los clasificadores que proporciona Microsoft. 

La experiencia **Match**, **Not a match** está disponible en:

- Explorador de contenido
- Página Elementos coincidentes de tipo de información confidencial
- Página Trainable Classifier Matched Items (Elementos coincidentes del clasificador entrenable)
- página Alertas de Prevención de pérdida de datos de Microsoft Purview (DLP)

## <a name="applies-to"></a>Se aplica a

|Clasificador |Resumen contextual| Panel de vista previa redactada| Coincidencia y no coincidencia|  
|---------|---------|---------|---------|
|Sentarse     |Sí| Sí|Sí|
|SIT personalizado  | Yes|No | Sí|
|SIT de huella digital| No|No|Sí|
|Coincidencia exacta de datos con SIT|No|No|No|
|Entidades con nombre| No| No| No|
|Clasificadores entrenables integrados|No| Sí| Sí|
|Clasificador personalizado que se puede entrenar |No| No| Sí|

> [!IMPORTANT]
> La experiencia de comentarios de coincidencia o no coincidencia admite elementos en sitios de SharePoint Online, OneDrive para la Empresa sitios y correos electrónicos en Exchange Online.

## <a name="licensing-and-subscriptions"></a>Licencias y suscripciones

Consulte [los requisitos de licencias para análisis de clasificación de datos: Información general del Explorador de actividad & contenido](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer).

## <a name="known-limitations-for-this-preview"></a>Limitaciones conocidas de esta versión preliminar

- El resumen contextual solo muestra un número limitado de coincidencias en cualquier elemento determinado, no todas las coincidencias.
- La experiencia de resumen contextual y comentarios solo está disponible para los elementos creados o actualizados después de habilitar la experiencia de comentarios para el inquilino. Es posible que los elementos que se clasificaron antes de habilitar la característica no tengan disponible el resumen contextual y la experiencia de comentarios.

## <a name="how-to-evaluate-match-accuracy-and-provide-feedback"></a>Cómo evaluar la precisión de la coincidencia y proporcionar comentarios

La experiencia de resumen contextual en la que se indica si un elemento coincidente es un verdadero positivo (**coincidencia**) o un falso positivo (**no una coincidencia**) es similar independientemente de dónde se trate de superficies.

> [!IMPORTANT]
> Ya debe haber implementado directivas DLP que usen SIT o clasificador entrenable en sitios de OneDrive, sitios de SharePoint o buzones de Exchange y que tengan coincidencias de elementos antes de que vea los elementos en la página **Resumen contextual** .

### <a name="using-content-explorer"></a>Uso del Explorador de contenido

En este ejemplo se muestra cómo usar la pestaña **Resumen contextual** para enviar comentarios.

1. Abra la página **explorador de contenido** de **clasificación** >  **de portal de cumplimiento Microsoft Purview** >  Data.
1. Escriba el nombre del clasificador SIT o entrenable para el que desea comprobar las coincidencias en **Filtrar en etiquetas, tipos de información o categorías**.
1. Seleccione sit.
1. Seleccione la ubicación. Asegúrese de que hay un valor distinto de cero en la columna **Archivo** .
1. Abra la carpeta y seleccione un documento.
1. Seleccione el vínculo de la columna **Tipo de información confidencial** de un elemento para ver qué SIT coincide con el elemento y el [nivel de confianza](/microsoft-365/compliance/sensitive-information-type-learn-about.md#more-on-confidence-levels).
1. Seleccione **Cerrar.**
1. Abra un elemento y expanda la página **Resumen contextual** . Seleccione la pestaña **Resumen contextual** .
1. Revise el elemento y confirme si es una coincidencia.
1. Si es una coincidencia, seleccione **Cerrar**. Ya ha terminado.
1. OPCIONAL: seleccione **Acepto proporcionar una copia del archivo a Microsoft** si desea enviar los comentarios de coincidencia a Microsoft y seleccione **Enviar a Microsoft.**
1. Si no es una coincidencia, seleccione los puntos suspensivos junto a **Cerrar** y seleccione **Retirar comentarios**.
1. Seleccione **Not a match (No una coincidencia**).
1. Revise el elemento y redacte o anótese cualquier texto.
1. Opcional: seleccione **Acepto proporcionar una copia del archivo a Microsoft** si desea enviar los comentarios a Microsoft y seleccione **Enviar a Microsoft**.
1. Seleccione **Cerrar**.

Si más adelante decide que los comentarios no coincidentes son incorrectos, puede seleccionar el botón **Retirar comentarios** . Esto vuelve a colocar el elemento en la página **No coincide**, **Coincidencia** .

### <a name="using-sensitive-information-type-matched-items-page"></a>Uso de la página Elementos coincidentes de tipo de información confidencial

Puede acceder a los mismos mecanismos de comentarios en la página **Tipos de información confidencial** .

1. Abra la **página tipos** de **información confidencial** de **clasificación** >  de portal de cumplimiento Microsoft Purview  >  Data.
1. Escriba el nombre del SIT cuya precisión desea comprobar en  **Buscar**.
1. Abra el SIT. Esto abre la pestaña **Información general** . Aquí puede ver el recuento del número de elementos que coinciden, un recuento del número de elementos que no coinciden y el número de elementos con comentarios.
1. Seleccione la pestaña **Elementos coincidentes** .
1. Abra la carpeta y seleccione un documento.
1. Seleccione el vínculo de la columna **Tipo de información confidencial** de un elemento para ver qué SIT coincide con el elemento y el [nivel de confianza](/microsoft-365/compliance/sensitive-information-type-learn-about.md#more-on-confidence-levels).
1. Seleccione **Cerrar**.
1. Abra un elemento y expanda la página **Resumen contextual** . Seleccione la pestaña **Resumen contextual** .
1. Revise el elemento y confirme si es una coincidencia.
1. Si es una coincidencia, seleccione **Cerrar**. Ya ha terminado.
1. Si no es una coincidencia, seleccione los puntos suspensivos junto a **Cerrar** y seleccione **Retirar comentarios**. Esto expone el botón **No coincidir** .
1. Seleccione el botón **No coincide** .
1. Revise el elemento y redacte o anótese cualquier texto.
1. Opcional: seleccione **Acepto proporcionar una copia del archivo a Microsoft** si desea enviar los comentarios a Microsoft y seleccione **Enviar a Microsoft**.
1. Seleccione **Cerrar**.

Si más adelante decide que los comentarios no coincidentes son incorrectos, puede seleccionar el botón **Retirar comentarios** . Esto vuelve a colocar el elemento en la página **No coincide**, **Coincidencia** .

### <a name="using-trainable-classifier-matched-items-page"></a>Uso de la página Elementos coincidentes del clasificador entrenable

1. Abra la página **Clasificadores entrenables** de **clasificación** >  **de portal de cumplimiento Microsoft Purview** >  Data.
1. Seleccione el clasificador que se puede entrenar cuya precisión desea comprobar.
1. Abra el clasificador que se puede entrenar. Esto abre la pestaña **Información general** . Aquí puede ver el recuento del número de elementos que coinciden, un recuento del número de elementos que no coinciden y el número de elementos con comentarios.
1. Seleccione la pestaña **Elementos coincidentes** .
1. Abra la carpeta y abra un documento.
1.Abra un elemento y expanda la página **Resumen contextual** .
1. Revise el elemento y confirme si es una coincidencia.
1. Si es una coincidencia, seleccione **Cerrar**. Ya ha terminado.
1. Si no es una coincidencia, seleccione **Retirar comentarios**. Esto expone **el botón No coincide** .
1. Seleccione el botón **No coincide** .
1. Seleccione **Cerrar**.

Si más adelante decide que los comentarios no coincidentes son incorrectos, puede seleccionar el botón **Retirar comentarios** . Esto vuelve a colocar el elemento en la página **No coincide**, **Coincidencia** .

### <a name="using-data-loss-prevention-alerts-page"></a>Página Usar alertas de prevención de pérdida de datos

1. Abra la página **Alertas** de prevención  >  de **pérdida de** **datos de portal de cumplimiento Microsoft Purview** >  Data.
1. Seleccione una alerta para un elemento que se creó o actualizó después de que se habilitara la funcionalidad **No**/**coincidir** para el inquilino.
1. Seleccione **Ver detalles**.
1. Seleccione la pestaña **Eventos** .
1. Seleccione la pestaña **Resumen contextual** .
1. Revise el elemento y confirme si es una coincidencia.
1. Si es una coincidencia, seleccione **Cerrar**. Ya ha terminado.
1. Si no es una coincidencia, seleccione **Acciones** y **No una coincidencia**.
1. Revise el elemento y redacte o anótese cualquier texto.
1. Opcional: seleccione **Acepto proporcionar una copia del archivo a Microsoft** si desea enviar los comentarios a Microsoft y seleccione **Enviar a Microsoft**.
1. Seleccione **Cerrar**.

## <a name="using-the-feedback-to-tune-your-classifiers"></a>Uso de los comentarios para ajustar los clasificadores

Si su SIT o clasificadores entrenables están devolviendo demasiados falsos positivos en función de los comentarios, puede probar algunos de estos pasos para ajustarlos y aumentar la precisión. 

### <a name="trainable-classifiers"></a>Clasificadores que se pueden entrenar

Siga los pasos descritos en [Cómo volver a entrenar un clasificador en el explorador de contenido](classifier-how-to-retrain-content-explorer.md) para aumentar la precisión de un clasificador que se puede entrenar.

### <a name="sensitive-information-types"></a>Tipos de información confidencial
 
Si ve grandes cantidades de falsos positivos, use estas recomendaciones para ajustar los SIT:

- Aumente los umbrales de los tipos de información confidencial encontrados para determinar la gravedad. Está bien usar umbrales diferentes para clasificadores individuales

- Comprenda los niveles de confianza y cómo se definen. Pruebe a usar una confianza baja con un recuento alto de instancias o un nivel de confianza superior con un recuento de instancias bajo.

- Clone y modifique los SIT integrados para incluir otras condiciones, como palabras clave, o coincidencias más estrictas de valores o requisitos de formato más estrictos.

- Modifique una SIT personalizada para excluir prefijos, sufijos o patrones conocidos. Por ejemplo, una SIT personalizada para detectar números de teléfono podría desencadenarse para cada correo electrónico si las firmas de correo electrónico o los encabezados de documento incluyen números de teléfono. Excluir las secuencias de número de teléfono de las organizaciones comunes como prefijos a su SIT personalizado puede impedir que la regla se desencadene para cada correo electrónico o documento.

- Incluya más SIT basados en diccionarios como condiciones para restringir las coincidencias a las que hablan de los artículos pertinentes. Por ejemplo, se puede mejorar una regla para la coincidencia de diagnósticos de pacientes al requerir la presencia de palabras como diagnóstico, diagnóstico, condición, síntoma y paciente.

- Para los SIT de entidad con nombre, como **Todos los nombres completos**, es mejor establecer un umbral de recuento de instancias mayor, como 10 o 50. Si se detectan juntos los nombres de persona y los SSN, es más probable que los SSN sean realmente SSN y se reduzca el riesgo de que la directiva no se desencadene porque no se detectan suficientes SSN.