---
title: Definición de entidad de todos los nombres completos
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
description: Todos los nombres completos información confidencial tipo definición de entidad.
ms.openlocfilehash: 727448848dbc3a4ea46b83ec404b4c9151ea192e
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2022
ms.locfileid: "67000163"
---
# <a name="all-full-names"></a>Todos los nombres completos

Todos los nombres completos son una entidad con nombre agrupada. Detecta nombres completos de personas de todos los países o regiones admitidos, entre los que se incluyen Australia, China, Japón, Estados Unidos y países de la UE. Use esta SIT para detectar todas las coincidencias posibles de nombres completos.

## <a name="format"></a>Formato

Varios.

## <a name="pattern"></a>Patrón

Varios.

## <a name="checksum"></a>Suma de comprobación

No.

## <a name="description"></a>Descripción

Esta entidad con nombre SIT coincide con los nombres personales que un humano identificaría como un nombre con alta confianza. Por ejemplo, si se encuentra una cadena que consta de un nombre determinado y va seguida de un nombre de familia, se realiza una coincidencia con alta confianza. Usa tres recursos principales:

- Diccionario de nombres determinados.
- Diccionario de nombres de familia.
- Patrones de cómo se forman los nombres.

Los tres recursos son diferentes para cada país.  Las cadenas *olivia Wilson* desencadenarían una coincidencia. Los nombres de familia o dados comunes tienen una mayor confianza que los nombres más raros. Sin embargo, el patrón también permite coincidencias parciales. Si se encuentra un nombre determinado del diccionario y va seguido de un nombre de familia que no está en el diccionario, se desencadena una coincidencia parcial. Por ejemplo, *Tomas Richard* desencadenaría una coincidencia parcial. Las coincidencias parciales tienen una menor confianza.

Además, los patrones que un humano vería como indicativos de nombres también coinciden con la confianza adecuada. Como *O. Wilson*, *O.P. Wilson*, *Dr. O. P. Wilson*, *Wilson, O.P.* o *T. Richard, Jr.* serían coincidencias.

## <a name="supported-languages"></a>Idiomas admitidos

- Inglés
- Búlgaro
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