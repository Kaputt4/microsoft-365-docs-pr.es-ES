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
ms.openlocfilehash: 183fedefbbb56411674ff80a9feedc507cff0530
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807529"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Configurar las funciones del Antivirus de Microsoft Defender


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Puede configurar Antivirus de Microsoft Defender con una serie de herramientas, como:

- Microsoft Endpoint Manager (que incluye Microsoft Intune y Microsoft Endpoint Configuration Manager)
- Directiva de grupo
- Cmdlets de PowerShell
- Instrumental de administración de Windows (WMI)
- [Asociación de inquilinos](/mem/configmgr/tenant-attach/)

Se pueden configurar las siguientes categorías generales de características:

- Protección entregada en la nube. Consulte [Cloud-delivered protection and Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md)

- Protección siempre activa en tiempo real, incluida la protección basada en el comportamiento, la heurística y el aprendizaje automático. Consulte [Configure behavioral, heuristic, and real-time protection](configure-protection-features-microsoft-defender-antivirus.md).

- Cómo interactúan los usuarios finales con el cliente en puntos de conexión individuales. Vea los siguientes recursos:
  - [Impedir que los usuarios vean o interactúen con la interfaz Antivirus de Microsoft Defender usuario](prevent-end-user-interaction-microsoft-defender-antivirus.md)
  - [Impedir o permitir que los usuarios modifiquen localmente Antivirus de Microsoft Defender configuración de directiva](configure-local-policy-overrides-microsoft-defender-antivirus.md)

> [!TIP]
> Revisar [temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md).
