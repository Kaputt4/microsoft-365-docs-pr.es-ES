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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: configurar servicios
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3030a97e3ed80524d2170e74b3d35f897b6ed74c
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914892"
---
# <a name="test-an-exact-data-match-sensitive-information-type"></a>Probar un tipo de información confidencial de coincidencia exacta de datos

Después de crear el tipo de información confidencial (SIT) de coincidencia exacta de datos (EDM) y una hora después de comprobar que la tabla de información confidencial ha terminado de cargarse e indizarse, puede probar que detecta la información que desea detectar mediante la función de prueba en la sección tipos de información confidencial del Centro de cumplimiento.
 
>[! NOTA:] Los cambios en un SIT de EDM ya creado pueden tardar algún tiempo en propagarse por todo el sistema. Si va a realizar cambios en un tipo de información confidencial de EDM para solucionar problemas de detección, asegúrese de esperar al menos una hora después de realizar esos cambios antes de usar la función de prueba para validar su impacto.

## <a name="test-your-edm-sit-in-the-compliance-center"></a>Probar su SIT de EDM en el Centro de cumplimiento

1. Open **Compliance center** Data  >  **classification** Sensitive Information  >  **Types**.

2. Seleccione su SIT de EDM en la lista y, a continuación, **seleccione Probar** en el panel desplegable. Esta opción solo está presente en la sit en tipos de información confidencial.
 
3. Upload elemento que contiene datos que desea detectar. Por ejemplo, cree un elemento que contenga un subconjunto de las filas de la tabla de información confidencial. Si usó la característica de coincidencia configurable en el esquema para definir delimitadores ignorados, asegúrese de que el elemento incluye ejemplos con y sin esos delimitadores.

4. Después de cargar y examinar el archivo, compruebe si hay coincidencias en su SIT de EDM.

5. Si la **función Test** del SIT detecta una coincidencia, valide que no está recortando o extrayéndola incorrectamente. Por ejemplo, extrayendo solo una subcadena de la cadena completa que se supone que debe detectar, o tomando solo la primera palabra de una cadena de varias palabras, o incluyendo símbolos o caracteres adicionales en la extracción. Consulte [Lenguaje de expresión regular: referencia rápida para](/dotnet/standard/base-types/regular-expression-language-quick-reference) la referencia del lenguaje de expresión regular. 

5. Como alternativa, puede usar el siguiente cmdlet de PowerShell:

```powershell
Test-DataClassification  -ClassificationNames “[Your EDM sensitive info type]” -TexttoClassify “[your own text to scan for matches]” 
```

> [!NOTE]
 Al crear o editar un tipo de información confidencial de EDM, o el SIT principal en el que se basa un tipo de EDM, todo el contenido nuevo que se modifique después de los cambios en los SIT se rastreará para el texto que coincida con las nuevas definiciones, pero el contenido preexistnte no se rastreará hasta que se modifique o vuelva a indizar. 

Para forzar el nuevo rastreo de contenido existente en un sitio o biblioteca de SharePoint o en OneDrive, siga las instrucciones de Solicitar manualmente el rastreo y la [nueva indización](/sharepoint/crawl-site-content)de un sitio, una biblioteca o una lista .

## <a name="test-your-edm-sit-in-mip-policies"></a>Probar la SIT de EDM en directivas de MIP

Puede ver dónde se usa el SIT de EDM y qué tan preciso es en producción usándolos en las directivas:

1. Cree una [directiva de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) y ejecutarla en Simulation **overview**.

1. Agregue algún contenido que desencadene el SIT de EDM y algún contenido que no desencadenará el SIT de EDM en una ubicación que la directiva esté supervisando.

1. Abra la **pestaña Elementos para revisar** para comprobar las coincidencias.

1. Ajuste las directivas según corresponda. 

Una vez que esté satisfecho con los resultados de las pruebas y el ajuste, su SIT personalizado basado en EDM está listo para usarse en directivas de Information Protection, como:

- [Directivas DLP](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
- [Directivas de etiquetado automático](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Microsoft Cloud App Security de archivos](/cloud-app-security/data-protection-policies)

## <a name="troubleshooting-tips"></a>Sugerencias para solucionar problemas

Si no encuentra ninguna coincidencia, pruebe lo siguiente:

- Confirme que los datos confidenciales se cargaron correctamente con los comandos que se explican en las instrucciones para cargar los datos confidenciales mediante la herramienta EDM.

- Compruebe que los ejemplos especificados en el elemento están presentes en la tabla de información confidencial y que los delimitadores omitido son correctos.

- Pruebe el SIT que usó al configurar el elemento principal en cada uno de los patrones. Esto confirmará que el SIT puede coincidir con los ejemplos del elemento. El uso de un SIT definido incorrectamente como elemento de clasificación de un tipo de información confidencial de EDM es la causa más común de errores de detección en EDM. 

- Si el SIT que seleccionó para un elemento principal del tipo EDM no encuentra una coincidencia en el elemento o encuentra menos coincidencias de las esperadas, compruebe que admite los separadores y delimitadores que están en el contenido. Asegúrese de incluir los delimitadores omitidos definidos en el esquema.

- Si la función Test no detecta ningún contenido, compruebe si el SIT seleccionado incluye requisitos para palabras clave adicionales u otras validaciones. Para los SIT integrados, vea Definiciones de entidad de tipo de información confidencial para comprobar cuáles son los [requisitos mínimos](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) para coincidir con cada tipo.

- Si la funcionalidad de prueba funciona pero los elementos SharePoint o OneDrive no se detectan en dlp o reglas de etiquetado automático, compruebe si los documentos que espera que coincidan se mostrarán en el Explorador de contenido. Si no están allí, recuerde que solo el contenido creado después de los cambios en el tipo de información confidencial se mostrará como coincidencias. Debe volver a rastrear los sitios y bibliotecas para que se muestren los elementos preexistentes. Consulte Solicitar manualmente el rastreo y [la nueva indización](/sharepoint/crawl-site-content) de un sitio, una biblioteca o una lista para obtener más información sobre cómo volver a rastrear SharePoint y OneDrive. 

- Si las reglas dlp o de etiquetado automático que requieren varias coincidencias no se desencadenan, compruebe que se cumplen los requisitos de proximidad para el tipo de EDM y los tipos de información confidencial base. Por ejemplo, si la distancia máxima entre el elemento principal y las palabras clave compatibles es de 300 caracteres, pero las palabras clave solo están presentes en la primera fila de una tabla larga, es probable que solo las primeras filas de valores coincidentes cumplan los requisitos de proximidad. Modifique las definiciones de SIT para admitir reglas de proximidad más relajadas o use la opción de documento en cualquier lugar para las condiciones de prueba adicionales. 

- Si la detección de un tipo de EDM es incoherente o errática, compruebe que el tipo de información confidencial que usó como base para el elemento principal del tipo EDM no detecte contenido innecesario. El uso de una SIT que coincida con demasiado contenido no relacionado, como cualquier palabra, cualquier número, todas las direcciones de correo electrónico pueden provocar que el servicio se satura e ignore las coincidencias relevantes. Compruebe el número de elementos de contenido que coinciden con el tipo confidencial que usó para los elementos principales en el explorador de contenido. Para calcular si el SIT coincide con demasiado contenido:
    1. Dividiendo el número de elementos de contenido en el Explorador de contenido por el número de días desde que se creó el tipo confidencial.
    2. Si el número de coincidencias por día está en el intervalo de cientos de miles o millones, es posible que el SIT principal sea demasiado amplio. Consulte [Información sobre tipos de](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types) información confidencial basados en coincidencias exactas de datos para obtener recomendaciones y procedimientos recomendados para seleccionar el tipo de información confidencial adecuado para un tipo de EDM. 

- Confirme que los datos confidenciales se cargaron correctamente con los comandos explicados en Hash y cargue la tabla de origen de información confidencial para obtener datos exactos que coincidan con los tipos [de información confidencial](sit-get-started-exact-data-match-hash-upload.md#hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types).

- Si el SIT que seleccionó para un elemento principal del tipo EDM no encuentra una coincidencia en el elemento o encuentra menos coincidencias de las esperadas, compruebe que admite separadores y delimitadores que existen en el contenido. Asegúrese de incluir los delimitadores omitidos definidos en el esquema. 

