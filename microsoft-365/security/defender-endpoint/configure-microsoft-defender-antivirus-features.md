---
title: Configurar las funciones del Antivirus de Microsoft Defender
description: Puede configurar las Antivirus de Microsoft Defender con Intune, Microsoft Endpoint Configuration Manager, directiva de grupo y PowerShell.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, defender, configurar, configuración, Administrador de configuración, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, administración de dispositivos móviles, GP, directiva de grupo, PowerShell
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/14/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 52556d3193843eecfb9130ead349a20bd16fab34
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61164147"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Configurar las funciones del Antivirus de Microsoft Defender


**Se aplica a:**

- [Plan 1 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Puede configurar Antivirus de Microsoft Defender con una serie de herramientas, como:

- Microsoft Endpoint Manager (que incluye Microsoft Intune y Microsoft Endpoint Configuration Manager)
- Directiva de grupo
- Cmdlets de PowerShell
- Instrumental de administración de Windows (WMI)
- [Asociación de inquilinos](/mem/configmgr/tenant-attach/)

Se pueden configurar las siguientes categorías generales de características:

- Protección entregada en la nube. Consulte [Protección entregada en la nube y Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)

- Protección siempre activa en tiempo real, incluida la protección basada en el comportamiento, la heurística y la de aprendizaje automático. Consulte [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).

- Cómo interactúan los usuarios finales con el cliente en puntos de conexión individuales. Vea los siguientes recursos:
  - [Impedir que los usuarios vean o interactúen con la interfaz Antivirus de Microsoft Defender usuario](prevent-end-user-interaction-microsoft-defender-antivirus.md)
  - [Impedir o permitir que los usuarios modifiquen localmente Antivirus de Microsoft Defender configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)

> [!TIP]
> Revisar [temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md).
