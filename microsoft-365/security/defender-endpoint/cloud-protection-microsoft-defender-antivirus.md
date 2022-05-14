---
title: Antivirus de Microsoft Defender y protección en la nube
description: Más información sobre la protección en la nube y la Antivirus de Microsoft Defender
keywords: Antivirus de Microsoft Defender, tecnologías de última generación, av de última generación, aprendizaje automático, antimalware, seguridad, defender, nube, protección en la nube
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: d272a816b302ea0332422ff2324ca091e43cd7a4
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65416000"
---
# <a name="cloud-protection-and-microsoft-defender-antivirus"></a>Antivirus de Microsoft Defender y protección en la nube

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Las tecnologías de última generación de Antivirus de Microsoft Defender proporcionan protección casi instantánea y automatizada contra amenazas nuevas y emergentes. Para identificar las nuevas amenazas de forma dinámica, las tecnologías de última generación funcionan con grandes conjuntos de datos interconectados en los sistemas de inteligencia artificial (IA) de Microsoft Intelligent Security Graph y eficaces basados en modelos avanzados de aprendizaje automático. La protección en la nube funciona junto con Antivirus de Microsoft Defender para ofrecer una protección precisa, en tiempo real y inteligente. 

[:::image type="content" source="images/mde-cloud-protection.png" alt-text="Diagrama que muestra cómo funciona la protección en la nube junto con Antivirus de Microsoft Defender" lightbox="images/mde-cloud-protection.png":::](enable-cloud-protection-microsoft-defender-antivirus.md)

> [!TIP]
> Se recomienda mantener activada la protección en la nube. Para obtener más información, consulte [Why cloud protection should be enabled for Antivirus de Microsoft Defender (Por qué se debe habilitar la protección en la nube para Antivirus de Microsoft Defender](why-cloud-protection-should-be-on-mdav.md)). 

## <a name="how-cloud-protection-works"></a>Funcionamiento de la protección en la nube

Antivirus de Microsoft Defender funciona sin problemas con los servicios en la nube de Microsoft. Estos servicios de protección en la nube, también conocidos como Microsoft Advanced Protection Service (MAPS), mejoran la protección estándar en tiempo real. Con la protección en la nube, las tecnologías de última generación proporcionan una rápida identificación de nuevas amenazas, a veces incluso antes de que un único punto de conexión se infecte. 

En las siguientes entradas de blog se muestra cómo funciona la protección en la nube:

- [Conozca las tecnologías avanzadas en el núcleo de Microsoft Defender para punto de conexión protección de próxima generación.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

- [¿Por qué Antivirus de Microsoft Defender es el más implementado en la empresa?](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 

- [La supervisión del comportamiento combinada con el aprendizaje automático arruina una campaña masiva de minería de monedas](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)

- [Cómo la inteligencia artificial detuvo un brote de "Emotet"](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)

- [Detonar un conejo malo: Antivirus de Microsoft Defender y defensas de aprendizaje automático en capas](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)

- [Antivirus de Microsoft Defender servicio de protección en la nube: defensa avanzada en tiempo real contra malware nunca visto](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 


> [!NOTE]
> El servicio en la nube Antivirus de Microsoft Defender es un mecanismo para proporcionar protección actualizada a la red y los puntos de conexión. Como servicio en la nube, no es simplemente protección para los archivos almacenados en la nube; en su lugar, el servicio en la nube usa recursos distribuidos y aprendizaje automático para ofrecer protección a los puntos de conexión a una velocidad mucho más rápida que las actualizaciones de inteligencia de seguridad tradicionales.

## <a name="how-to-get-cloud-protection"></a>Cómo obtener protección en la nube 

La protección en la nube está habilitada de forma predeterminada. Sin embargo, es posible que deba volver a habilitarlo si se ha deshabilitado como parte de las directivas de la organización anteriores. Para más información, consulte [Activación de la protección en la nube](enable-cloud-protection-microsoft-defender-antivirus.md).

Si su suscripción incluye Windows 10 E5, puede aprovechar las actualizaciones de inteligencia dinámica de emergencia, que proporcionan protección casi en tiempo real frente a amenazas emergentes. Al activar la protección en la nube, las correcciones de problemas de malware se pueden entregar a través de la nube en cuestión de minutos, en lugar de esperar a la siguiente actualización. Consulte [Configuración de Antivirus de Microsoft Defender para recibir automáticamente nuevas actualizaciones de protección basadas en informes de nuestro servicio en la nube](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates).

## <a name="next-steps"></a>Pasos siguientes

Ahora que tiene información general sobre la protección en la nube en Antivirus de Microsoft Defender, estos son algunos pasos siguientes:

1. Consulte [Why cloud protection should be enabled for Antivirus de Microsoft Defender (Por qué se debe habilitar la protección en la nube para Antivirus de Microsoft Defender](why-cloud-protection-should-be-on-mdav.md)).

2. Continúe con [Habilitación de la protección en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)