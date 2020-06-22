---
title: Tipos de información confidencial personalizada para DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga una visión general de los tipos de información confidencial personalizada para la Prevención de pérdida de datos (DLP), como el patrón primario, la proximidad de caracteres y el nivel de confianza.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6934edba6eef03bc9d4bfc5c1c69f127a7d3a0e5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817969"
---
# <a name="custom-sensitive-information-types"></a>Tipos de información confidencial personalizada

Microsoft 365 incluye muchos tipos de información confidencial que están listos para usarse en su organización, como [prevención de pérdida de datos](data-loss-prevention-policies.md) (DLP), o con [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security). Los tipos de información confidencial integrados pueden ayudar a identificar y proteger números de tarjetas de crédito, números de cuentas bancarias, números de pasaporte y más, en función de los patrones definidos por una expresión regular (regex) o una función. Para obtener más información, consulte [Qué buscan los tipos de información confidencial](what-the-sensitive-information-types-look-for.md).

Pero, ¿qué sucede si necesita identificar y proteger un tipo diferente de información confidencial, como el id. de empleados o los números de proyecto, mediante un formato específico para su organización? Para ello, puede crear un tipo de información confidencial personalizado.

Estas son las partes básicas de un tipo personalizado de información confidencial:

- **Patrón principal**: números de id. de empleado, números de proyecto, etc. Suele identificarse mediante una expresión regular (regex), pero también puede ser una lista de palabras clave.

- **Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.

- **Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:

    ![Diagrama de evidencia corroborativa y ventana de proximidad](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.

  When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:

    ![Opciones de precisión de coincidencia y recuento de instancias](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>Crear tipos de información confidencial personalizados

Para crear tipos de información confidencial personalizados en el Centro de seguridad y cumplimiento, puede elegir una de estas opciones:

- **Usar EDM** (nuevo). Puede establecer los tipos de información confidencial mediante la clasificación basada en la exacta coincidencia de los datos (EDM). Este método le permite crear un tipo de información confidencial dinámico con una base de datos segura que puede actualizar periódicamente. Vea [Crear un tipo de información confidencial personalizado con coincidencia exacta de datos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Usar PowerShell** Puede configurar los tipos de información confidencial con PowerShell. Aunque este método es más complejo que utilizar la interfaz de usuario, tendrá más opciones de configuración. Vea [Crear un tipo de información confidencial en el centro de cumplimiento y seguridad PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).

- **Usar la interfaz de usuario** Puede configurar un tipo de información confidencial personalizado mediante la interfaz de usuario del centro de cumplimiento y seguridad. Con este método, puede usar expresiones regulares, palabras clave y diccionarios de palabras clave. Para obtener más información, consulte [Crear un tipo de información confidencial](create-a-custom-sensitive-information-type.md).



