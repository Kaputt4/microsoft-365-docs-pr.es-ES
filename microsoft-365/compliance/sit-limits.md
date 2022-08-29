---
title: Límites de tipos de información confidencial
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Más información sobre el número de instancias y otros límites de tipos de información confidencial
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5cb574ac9aa0d20818379d7f11ace0a40b68905f
ms.sourcegitcommit: 60c6ce8cbdf539f8b6ff1c6029eb16f81461a3ad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2022
ms.locfileid: "67434554"
---
# <a name="sensitive-information-type-limits"></a>Límites de tipos de información confidencial

Estos límites se aplican a todos los tipos de información confidencial (SIT), excepto los datos exactos que coinciden con los tipos de información confidencial.

Estos límites se aplican a todas las directivas de Microsoft Purview que usan SIT.

Para garantizar un alto rendimiento y una menor latencia, hay limitaciones en las configuraciones de SIT personalizadas.

|Límite|Valor|
|---|---|
|número máximo de SIT personalizados creados a través del Centro de cumplimiento| 500 |
|longitud máxima de la expresión regular| 1024 caracteres|
|longitud máxima de un término determinado en una lista de palabras clave| 50 caracteres|
|número máximo de términos en la lista de palabras clave| 2048|
|número máximo de expresiones regulares distintas por tipo de información confidencial| 20|
|tamaño máximo de un diccionario de palabras clave (compresión posterior)| 1 MB (aproximadamente 1000 000 caracteres)|
|número máximo de SIT basados en diccionarios de palabras clave en un inquilino|50 |

> [!NOTE]
> Si tiene una necesidad empresarial de crear más de 500 SIT personalizados, genere una incidencia de soporte técnico.

### <a name="instance-count-supported-values-for-sit"></a>Recuento de instancias de valores admitidos para SIT

El límite de recuento de instancias de SIT se aplica cuando se usan SIT en estas soluciones:

- directivas de Prevención de pérdida de datos de Microsoft Purview
- directivas de Microsoft Purview Information Protection
- Administración del ciclo de vida de datos de Microsoft Purview
- Cumplimiento de la comunicación
- Administración de registros de Microsoft Purview
- Microsoft Defender for Cloud Apps
- Microsoft Priva

Para que un elemento examinado cumpla los criterios de regla, el número de instancias únicas de una SIT en cualquier elemento único debe estar comprendido entre los valores mínimo y máximo. Esto se denomina **recuento de instancias**.

- **Campo mínimo** : límite inferior (número mínimo) de instancias únicas de una SIT que se deben encontrar en un elemento para desencadenar una coincidencia. El campo min admite valores de:
  - De 1 a 500
- **Campo máximo** : límite superior en el número de instancias únicas de una SIT que se pueden encontrar en un elemento y que siguen desencadenando una coincidencia. El campo max admite valores de:
  - 1 a 500: use esta opción cuando desee establecer un límite superior específico de 500 o menos en el número de instancias de una SIT en un elemento.
  - Cualquiera: use `Any` cuando desee que se cumplan los criterios de recuento de instancias únicos cuando se encuentre un número indefinido de instancias únicas de una SIT en un elemento examinado y ese número de instancias únicas cumpla o supere el número mínimo de valores de instancias únicas. En otras palabras, los criterios de recuento de instancias únicos se cumplen siempre y cuando se cumpla el valor mínimo.

Por ejemplo, si desea que la regla desencadene una coincidencia cuando se encuentren al menos 500 instancias únicas de una SIT en un solo elemento, establezca el valor `500` **mínimo** en y el valor **máximo** en `Any`.

> [!NOTE]
> Se admiten hasta 100 evaluaciones exactas de coincidencia de datos (EDM). Las directivas que usan SIT de EDM no deben escribirse con un valor **mínimo** o **máximo** de recuento de instancias mayor que 100.

