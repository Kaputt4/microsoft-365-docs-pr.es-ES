---
title: Probar un tipo de información confidencial de coincidencia exacta de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: configurar servicios
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5b2ae7e5d6e434cd5502373b04a055c6fb2fb4a9
ms.sourcegitcommit: 6a981ca15bac84adbbed67341c89235029aad476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65754242"
---
# <a name="test-an-exact-data-match-sensitive-information-type"></a>Probar un tipo de información confidencial de coincidencia exacta de datos

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Una vez creado el tipo de información confidencial (SIT) de coincidencia exacta de datos (EDM) y una hora después de comprobar que la tabla de información confidencial ha terminado de cargarse e indexarse, puede probar que detecta la información que desea detectar mediante la función de prueba en la sección Tipos de información confidencial del Centro de cumplimiento.
 
>[! NOTA:] Los cambios en una SIT de EDM ya creada pueden tardar algún tiempo en propagarse a través del sistema. Si realiza cambios en un tipo de información confidencial de EDM para solucionar problemas de detección, asegúrese de esperar al menos una hora después de realizar esos cambios antes de usar la función de prueba para validar su impacto.

## <a name="test-your-edm-sit-in-the-compliance-center"></a>Prueba del SIT de EDM en el Centro de cumplimiento

1. Abra **Tipos de****información confidencial** de clasificación de datos del Centro  >  de **cumplimiento** > .

2. Seleccione el SIT de EDM en la lista y, a continuación, seleccione **Probar** en el panel flotante. Esta opción solo está presente en tipos de información confidencial.
 
3. Upload un elemento que contiene los datos que desea detectar. Por ejemplo, cree un elemento que contenga un subconjunto de las filas de la tabla de información confidencial. Si usó la característica de coincidencia configurable en el esquema para definir delimitadores omitidos, asegúrese de que el elemento incluye ejemplos con y sin esos delimitadores.

4. Después de cargar y examinar el archivo, compruebe si hay coincidencias con el SIT de EDM.

5. Si la función **Test** de sit detecta una coincidencia, compruebe que no la está recortando o extrayéndola incorrectamente. Por ejemplo, al extraer solo una subcadena de la cadena completa que se supone que debe detectar, o al seleccionar solo la primera palabra de una cadena de varias palabras, o incluir símbolos o caracteres adicionales en la extracción. Consulte [Regular Expression Language - Quick Reference (Lenguaje de expresiones regulares: referencia rápida)](/dotnet/standard/base-types/regular-expression-language-quick-reference) para obtener la referencia del lenguaje de expresiones regulares. 

5. Como alternativa, puede usar el siguiente cmdlet de PowerShell:

```powershell
Test-DataClassification  -ClassificationNames “[Your EDM sensitive info type]” -TexttoClassify “[your own text to scan for matches]” 
```

> [!NOTE]
 Al crear o editar un tipo de información confidencial de EDM o el SIT principal en el que se basa un tipo EDM, todo el contenido y el contenido nuevos que se modifiquen después de los cambios en los SIT se rastrearán para el texto que coincida con las nuevas definiciones, pero el contenido existente no se rastreará hasta que se modifique o vuelva a indexar. 

Para forzar el re rastreo del contenido existente en un sitio o biblioteca de SharePoint o en OneDrive, siga las instrucciones de [Solicitud manual de rastreo y reindexación de un sitio, una biblioteca o una lista](/sharepoint/crawl-site-content).

## <a name="test-your-edm-sit-with-information-protection-policies"></a>Prueba de EDM SIT con directivas de protección de la información

Puede ver dónde se usa el SIT de EDM y qué precisión tiene en producción si los usa en directivas:

1. Cree una [directiva de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) y ejecútelo en **Información general de simulación**.

1. Agregue contenido que desencadenará el SIT de EDM y algún contenido que no desencadenará el SIT de EDM en una ubicación que la directiva esté supervisando.

1. Abra la pestaña **Elementos para revisar** para comprobar las coincidencias.

1. Ajuste las directivas según corresponda. 

Una vez que esté satisfecho con los resultados de las pruebas y el ajuste, el SIT personalizado basado en EDM está listo para su uso en directivas de protección de la información, como:

- [Directivas DLP](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
- [Directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Defender for Cloud Apps](/cloud-app-security/data-protection-policies)

## <a name="troubleshooting-tips"></a>Sugerencias para solucionar problemas

Si no encuentra ninguna coincidencia, estas son algunas sugerencias de solución de problemas.

|Problema  |Consejos para solucionar el problema  |
|---------|---------|
|No se encontraron coincidencias     |  Confirme que los datos confidenciales se cargaron correctamente mediante los comandos explicados en [Hash y cargue la tabla de origen de información confidencial para obtener datos exactos que coincidan con los tipos de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types).|
|No se encontraron coincidencias   | Pruebe el SIT que usó al configurar el elemento principal en cada uno de los patrones. Esto confirmará que sit puede coincidir con los ejemplos del elemento. El uso de sit definido incorrectamente como elemento de clasificación de un tipo de información confidencial de EDM es la causa más común de errores de detección en EDM.         |
|El SIT que seleccionó para un elemento principal en el tipo EDM no encuentra una coincidencia en el elemento o busca menos coincidencias de las esperadas.    |  Compruebe que admite los separadores y delimitadores que se encuentran en el contenido. Asegúrese de incluir los delimitadores omitidos definidos en el esquema.       |
|El elemento principal SIT busca coincidencias en un elemento, pero EDM SIT no.     | - Compruebe las instrucciones REGEX para iniciar o finalizar un delimitador de espacios en blanco de captura, como /s. El espacio en blanco no coincidirá con el valor hash de la tabla de datos. En su lugar, use un delimitador de palabras como /b. </br> - Compruebe las instrucciones REGEX para asegurarse de que capturan toda la cadena que desea capturar, no solo una subcadena. Por ejemplo, este patrón para las direcciones de correo electrónico [a-zA-Z]{30}@[a-zA-Z]{20}.[ a-zA-Z]{2,3} coincidirá *con user@contoso.com* y *user@contoso.co.jp*.  |
|Una SIT de EDM con elementos principales y sin elementos secundarios definidos detecta elementos, pero no detecta, ni detecta menos de lo esperado, cuando se requieren elementos primarios y secundarios.  | Asegúrese de que los valores de la evidencia secundaria se componen de una sola palabra o cadena que no contenga espacios o use instrucciones REGEX que detecten cadenas de varias palabras. Por ejemplo, \b[A-Z][a-z]{1,25}([ -][A-Z][a-z]{1,25}){0,4}\b, que coincidirá con cualquier secuencia de una a cinco palabras consecutivas que comiencen con un carácter en mayúsculas. Use esta SIT como elemento de clasificación para las condiciones de evidencia adicionales en el XML del tipo de información confidencial de EDM. Consulte [Creación manual de un paquete de reglas](sit-get-started-exact-data-match-create-rule-package.md#create-a-rule-package-manually)|
|La función de prueba SIT no detecta ninguna coincidencia.   | Compruebe si el SIT seleccionado incluye requisitos para palabras clave adicionales u otras validaciones. Para conocer los SIT integrados, consulte [Definiciones de entidades de tipo de información confidencial](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) para comprobar cuáles son los requisitos mínimos para hacer coincidir cada tipo.        |
|La funcionalidad De prueba funciona, pero los elementos de SharePoint o OneDrive no se detectan en las reglas dlp o de etiquetado automático.     | Compruebe si los documentos que espera que coincidan aparezcan en el Explorador de contenido. Si no están allí, recuerde que solo el contenido creado después de los cambios en el tipo de información confidencial se mostrará como coincidencias. Tiene que volver a rastrear los sitios y las bibliotecas para que aparezcan los elementos preexisterios. Consulte [Solicitud manual de rastreo y reindexación de un sitio, una biblioteca o una lista](/sharepoint/crawl-site-content) para obtener más información sobre el SharePoint y la OneDrive.        |
|Las reglas dlp o de etiquetado automático que requieren varias coincidencias no se desencadenan     |Compruebe que se cumplen los requisitos de proximidad para el tipo de EDM y los tipos de información confidencial base. Por ejemplo, si la distancia máxima entre el elemento principal y las palabras clave auxiliares es de 300 caracteres, pero las palabras clave solo están presentes en la primera fila de una tabla larga, es probable que solo las primeras filas de valores coincidentes cumplan los requisitos de proximidad. Modifique las definiciones de SIT para admitir reglas de proximidad más relajadas o use la opción en cualquier lugar del documento para las condiciones de pruebas adicionales.         |
|La detección de un tipo EDM es incoherente o errática     |Compruebe que el tipo de información confidencial que usó como base para el elemento principal del tipo EDM no detecta contenido innecesario. El uso de una SIT que coincida con demasiado contenido no relacionado, como cualquier palabra, cualquier número o todas las direcciones de correo electrónico, puede hacer que el servicio se sature e ignore las coincidencias pertinentes. Compruebe el número de elementos de contenido que coinciden con el tipo confidencial que usó para los elementos principales en el explorador de contenido. </br> Para calcular si sit coincide con demasiado contenido: </br> - Dividir el número de elementos de contenido en el Explorador de contenido por el número de días transcurridos desde que se creó el tipo confidencial. </br> - Si el número de coincidencias por día está en el intervalo de cientos de miles o millones, es posible que el SIT principal sea demasiado amplio. Consulte [Información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) para obtener recomendaciones y procedimientos recomendados sobre cómo seleccionar el tipo de información confidencial adecuado para un tipo EDM.         |
