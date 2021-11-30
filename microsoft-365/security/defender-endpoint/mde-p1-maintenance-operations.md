---
title: Administrar Microsoft Defender para el plan de extremo 1
description: Mantener y actualizar Defender para el plan de extremo 1. Administrar la configuración, obtener actualizaciones y solucionar falsos positivos/negativos.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 11/19/2021
ms.prod: m365-security
ms.technology: mde
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: 1ae0636f103c830866c0b7bcd1af488f2fc4e070
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2021
ms.locfileid: "61220877"
---
# <a name="manage-microsoft-defender-for-endpoint-plan-1"></a>Administrar Microsoft Defender para el plan de extremo 1

**Se aplica a**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> Si tiene Microsoft 365 E3 O A3 pero no Microsoft 365 E5 o A5, visite [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) para registrarse en el programa de vista previa.

A medida que usa Defender para el plan de extremo 1 en su organización, el equipo de seguridad puede tomar determinados pasos para mantener la solución de seguridad. A medida que el equipo de seguridad reúne el plan de mantenimiento y operaciones, asegúrese de incluir al menos las siguientes actividades:

- [Administrar la inteligencia de seguridad y las actualizaciones de productos](#manage-security-intelligence-and-product-updates)
- [Ajustar y ajustar Defender para endpoint](#fine-tune-and-adjust-defender-for-endpoint)
- [Dirección de falsos positivos/negativos](#address-false-positivesnegatives)

## <a name="manage-security-intelligence-and-product-updates"></a>Administrar la inteligencia de seguridad y las actualizaciones de productos

Mantener Antivirus de Microsoft Defender actualizado es fundamental para protegerse contra nuevas técnicas de malware y ataques. Microsoft publica actualizaciones periódicas de inteligencia de seguridad, antivirus y protección contra malware. Las actualizaciones se organizan en dos categorías: 

- Actualizaciones de inteligencia de seguridad
- Actualizaciones de productos 

Para administrar la inteligencia de seguridad y las actualizaciones de productos, [vea Manage Antivirus de Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

## <a name="fine-tune-and-adjust-defender-for-endpoint"></a>Ajustar y ajustar Defender para endpoint

Defender for Endpoint ofrece mucha flexibilidad y opciones de configuración. Puede ajustar y ajustar la configuración para que se adapte a las necesidades de su organización. Por ejemplo, puede usar Microsoft Endpoint Manager, directiva de grupo y otros métodos para administrar la configuración de seguridad del extremo. 

Para obtener más información, vea [Manage Defender for Endpoint](manage-mde-post-migration.md).

## <a name="address-false-positivesnegatives"></a>Dirección de falsos positivos/negativos

Un falso positivo es un artefacto, como un archivo o un proceso, que se detectó como malintencionado, aunque en realidad no sea una amenaza. Un falso negativo es una entidad que no se detectó como una amenaza, aunque realmente lo sea. Los falsos positivos o negativos pueden producirse con cualquier solución de protección de puntos de conexión, incluido Defender para endpoint. Sin embargo, hay pasos que puede seguir para solucionar estos tipos de problemas y ajustar la solución, como se muestra en la imagen siguiente:

:::image type="content" source="../../media/defender-endpoint/false-positives-overview.png" alt-text="Introducción al proceso de falsos positivos y negativos":::

Si está viendo falsos positivos/negativos en Defender para endpoint, consulte [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).

## <a name="next-steps"></a>Siguientes pasos

- [Vea las novedades de Microsoft Defender para endpoint](whats-new-in-microsoft-defender-atp.md)