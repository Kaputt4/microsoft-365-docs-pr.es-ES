---
title: Administrar Microsoft Defender para endpoint plan 1 (versión preliminar)
description: Mantener y actualizar Defender para el plan de extremo 1. Administrar la configuración, obtener actualizaciones y solucionar falsos positivos/negativos.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 09/13/2021
ms.prod: m365-security
ms.technology: mdep1
localization_priority: Normal
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.openlocfilehash: b462fd6c02e455b7bd5ed41c71462628a0d0071b
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2021
ms.locfileid: "59399411"
---
# <a name="manage-microsoft-defender-for-endpoint-plan-1-preview"></a>Administrar Microsoft Defender para endpoint plan 1 (versión preliminar)

> [!TIP]
> Si tiene Microsoft 365 E3 pero no Microsoft 365 E5, visite [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) para registrarse en el programa de vista previa.

A medida que usa Defender para endpoint plan 1 (versión preliminar) en su organización, el equipo de seguridad puede tomar ciertos pasos para mantener la solución de seguridad. A medida que el equipo de seguridad reúne el plan de mantenimiento y operaciones, asegúrese de incluir al menos las siguientes actividades:

- [Administrar la inteligencia de seguridad y las actualizaciones de productos](#manage-security-intelligence-and-product-updates)
- [Ajustar y ajustar Defender para endpoint](#fine-tune-and-adjust-defender-for-endpoint)
- [Dirección de falsos positivos/negativos](#address-false-positivesnegatives)

> [!IMPORTANT]
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. En este artículo se incluyen vínculos al contenido en línea que podrían describir algunas características que no se incluyen en Defender for Endpoint Plan 1 (versión preliminar).

## <a name="manage-security-intelligence-and-product-updates"></a>Administrar la inteligencia de seguridad y las actualizaciones de productos

Mantener Antivirus de Microsoft Defender actualizado es fundamental para protegerse contra nuevas técnicas de malware y ataques. Microsoft publica actualizaciones periódicas de inteligencia de seguridad, antivirus y protección contra malware. Las actualizaciones se organizan en dos categorías: 

- Actualizaciones de inteligencia de seguridad
- Actualizaciones de productos 

Para administrar la inteligencia de seguridad y las actualizaciones de productos, [vea Manage Antivirus de Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

## <a name="fine-tune-and-adjust-defender-for-endpoint"></a>Ajustar y ajustar Defender para endpoint

Defender for Endpoint ofrece mucha flexibilidad y opciones de configuración. Puede ajustar y ajustar la configuración para que se adapte a las necesidades de su organización. Por ejemplo, puede usar Microsoft Endpoint Manager, directiva de grupo y otros métodos para administrar la configuración de seguridad del extremo. 

Para obtener más información, vea [Manage Defender for Endpoint](manage-atp-post-migration.md).

## <a name="address-false-positivesnegatives"></a>Dirección de falsos positivos/negativos

Un falso positivo es un artefacto, como un archivo o un proceso, que se detectó como malintencionado, aunque en realidad no sea una amenaza. Un falso negativo es una entidad que no se detectó como una amenaza, aunque realmente lo sea. Los falsos positivos o negativos pueden producirse con cualquier solución de protección de puntos de conexión, incluido Defender para endpoint. Sin embargo, hay pasos que puede seguir para solucionar estos tipos de problemas y ajustar la solución, como se muestra en la imagen siguiente:

:::image type="content" source="../../media/defender-endpoint/false-positives-overview.png" alt-text="Introducción al proceso de falsos positivos y negativos":::

Si está viendo falsos positivos/negativos en Defender para endpoint, consulte [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).

## <a name="next-steps"></a>Pasos siguientes

- [Vea las novedades de Microsoft Defender para endpoint](whats-new-in-microsoft-defender-atp.md)