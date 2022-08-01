---
title: Definición de entidad todas las direcciones físicas
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: Definición de entidad del tipo de información confidencial Todas las direcciones físicas.
ms.openlocfilehash: 3d8b40d6362c2a39525959467f524bc83c7cc3c8
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000052"
---
# <a name="all-physical-addresses"></a>Todas las direcciones físicas

Todas las direcciones físicas son una entidad agrupada SIT, que detecta patrones relacionados con direcciones físicas de todos los países o regiones admitidos.

## <a name="format"></a>Formato

Varios

## <a name="pattern"></a>Patrón

Varios

## <a name="checksum"></a>Suma de comprobación

No

## <a name="description"></a>Descripción

La coincidencia de direcciones callejeras está diseñada para que coincida con las cadenas que un humano identificaría como una dirección de calle. Para ello, usa varios recursos principales:

- Diccionario de liquidaciones, condados y regiones.
- Diccionario de sufijos de calle, como Road, Street o Avenue.
- Patrones de códigos postales.
- Patrones de formatos de dirección.

Los recursos son diferentes para cada país. Los recursos principales son los patrones de formatos de dirección que se usan en un país determinado. Se eligen diferentes formatos para asegurarse de que coinciden tantas direcciones como sea posible. Estos formatos permiten flexibilidad, por ejemplo, una dirección puede omitir el código postal o omitir un nombre de ciudad o tener una calle sin sufijo de calle. En todos los casos, estas coincidencias se usan para aumentar la confianza de la coincidencia.

Los patrones están diseñados para que coincidan con direcciones únicas individuales, no con ubicaciones genéricas. Por lo tanto, cadenas como *Redmond, WA 98052* o *Main Street, Albuquerque* no coincidirán.

## <a name="contains"></a>Contains

Esta entidad con nombre agrupada SIT contiene estos SIT individuales:

- Direcciones físicas de Australia
- Direcciones físicas de Austria
- Direcciones físicas de Bélgica
- Direcciones físicas de Brasil
- Direcciones físicas de Bulgaria
- Direcciones físicas de Canadá
- Direcciones físicas de Croacia
- Direcciones físicas de Chipre
- Direcciones físicas de la República Checa
- Direcciones físicas de Dinamarca
- Direcciones físicas de Estonia
- Direcciones físicas de Finlandia
- Direcciones físicas de Francia
- Direcciones físicas de Alemania
- Direcciones físicas de Grecia
- Direcciones físicas de Hungría
- Direcciones físicas de Islandia
- Direcciones físicas de Irlanda
- Direcciones físicas de Italia
- Direcciones físicas de Letonia
- Direcciones físicas de Liechtenstein
- Direcciones físicas de Lituania
- Direcciones físicas de Luxemburgo
- Direcciones físicas de Malta
- Direcciones físicas de los Países Bajos
- Direcciones físicas de Nueva Zelanda
- Direcciones físicas de Noruega
- Direcciones físicas de Polonia
- Direcciones físicas de Portugal
- Direcciones físicas de Rumanía
- Direcciones físicas de Eslovaquia
- Direcciones físicas de Eslovenia
- Direcciones físicas de España
- Direcciones físicas de Suecia
- Direcciones físicas de Suiza
- Direcciones físicas de Turquía
- Direcciones físicas del Reino Unido
- Estados Unidos direcciones físicas

## <a name="supported-languages"></a>Idiomas admitidos

- Inglés
- Búlgaro
- Chino
- Croata
- Checo
- Danés
- Estonio
- Finés
- Francés
- Alemán
- Húngaro
- Islandés
- Irlandés
- Italiano
- Japonés
- Letón
- Lituano
- Maltés
- Neerlandés
- Noruego
- Polaco
- Portugués
- Rumano
- Eslovaco
- Esloveno
- Español
- Sueco
- Turco