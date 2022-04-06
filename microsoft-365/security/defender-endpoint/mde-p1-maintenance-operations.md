---
title: Administrar Microsoft Defender para punto de conexión plan 1
description: Mantenga y actualice el plan 1 de Defender para punto de conexión. Administre la configuración, obtenga actualizaciones y solucione los falsos positivos o negativos.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 01/03/2022
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: 417dd33eed846e45453464e63ff403374ce224dc
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667414"
---
# <a name="manage-microsoft-defender-for-endpoint-plan-1"></a>Administrar Microsoft Defender para punto de conexión plan 1

**Se aplica a**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Al usar el plan 1 de Defender para punto de conexión en su organización, el equipo de seguridad puede realizar ciertos pasos para mantener la solución de seguridad. A medida que el equipo de seguridad reúna el plan de mantenimiento y operaciones, asegúrese de incluir al menos las siguientes actividades:

- [Administración de la inteligencia de seguridad y las actualizaciones de productos](#manage-security-intelligence-and-product-updates)
- [Ajuste y ajuste de Defender para punto de conexión](#fine-tune-and-adjust-defender-for-endpoint)
- [Dirección de falsos positivos o negativos](#address-false-positivesnegatives)

## <a name="manage-security-intelligence-and-product-updates"></a>Administración de la inteligencia de seguridad y las actualizaciones de productos

Mantener Antivirus de Microsoft Defender actualizado es fundamental para protegerse contra nuevas técnicas de ataque y malware. Microsoft publica actualizaciones periódicas para la inteligencia de seguridad, el antivirus y la protección antimalware. Las actualizaciones se organizan en dos categorías: 

- Actualizaciones de inteligencia de seguridad
- Actualizaciones de productos 

Para administrar la inteligencia de seguridad y las actualizaciones de productos, consulte [Administración de actualizaciones de Antivirus de Microsoft Defender y aplicación de líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).

## <a name="fine-tune-and-adjust-defender-for-endpoint"></a>Ajuste y ajuste de Defender para punto de conexión

Defender for Endpoint ofrece muchas opciones de flexibilidad y configuración. Puede ajustar y ajustar la configuración para satisfacer las necesidades de su organización. Por ejemplo, puede usar Microsoft Endpoint Manager, directiva de grupo y otros métodos para administrar la configuración de seguridad del punto de conexión. 

Para más información, consulte [Administración de Defender para punto de conexión](manage-mde-post-migration.md).

## <a name="address-false-positivesnegatives"></a>Dirección de falsos positivos o negativos

Un falso positivo es un artefacto, como un archivo o un proceso, que se detectó como malintencionado, aunque en realidad no sea una amenaza. Un falso negativo es una entidad que no se detectó como amenaza, aunque realmente lo sea. Los falsos positivos o negativos se pueden producir con cualquier solución de endpoint protection, incluido Defender para punto de conexión. Sin embargo, hay pasos que puede seguir para solucionar este tipo de problemas y ajustar la solución, como se muestra en la siguiente imagen:

:::image type="content" source="../../media/defender-endpoint/false-positives-overview.png" alt-text="Introducción al proceso de falsos positivos y negativos" lightbox="../../media/defender-endpoint/false-positives-overview.png":::

Si ve falsos positivos o negativos en Defender para punto de conexión, consulte [Dirección de falsos positivos o negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md).

## <a name="next-steps"></a>Siguientes pasos

- [Vea las novedades de Microsoft Defender para punto de conexión](whats-new-in-microsoft-defender-endpoint.md)