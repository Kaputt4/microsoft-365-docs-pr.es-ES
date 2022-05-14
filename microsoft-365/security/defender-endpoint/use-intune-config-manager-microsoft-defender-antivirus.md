---
title: Configuración de Antivirus de Microsoft Defender mediante Microsoft Endpoint Manager
description: Use Microsoft Endpoint Manager y Microsoft Intune para configurar Antivirus de Microsoft Defender y Endpoint Protection
keywords: scep, intune, endpoint protection, configuration
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: 892ab423d09aae9c02135bc569f1321dbab7fa0d
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65419514"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Use Microsoft Endpoint Manager para configurar y administrar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) para configurar exámenes de Antivirus de Microsoft Defender. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Configuration Manager](/mem/configmgr/core/understand/introduction) ahora forman parte de Endpoint Manager.

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Configuración de exámenes de Antivirus de Microsoft Defender en Endpoint Manager

1. Vaya al centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Vaya a **Seguridad del punto de conexión**.

3. En **Administrar**, elija **Antivirus**.

4. Seleccione la directiva de Antivirus de Microsoft Defender.

5. En **Administrar**, elija **Propiedades**.

6. Junto a **Opciones de configuración**, elija **Editar**.

   > [!IMPORTANT]
   > La configuración del antivirus AllowOnAccessProtection y AllowIntrusionPreventionSystem está oficialmente en desuso y, como tal, no se puede configurar. 

7. Expanda la sección **Examinar** y revise o edite la configuración de examen.

8. Elija **Revisar y guardar**.

> [!TIP]
> ¿Necesita ayuda? Consulte [Administración de la seguridad del punto de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security).

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-articles"></a>Artículos relacionados

- [Artículos de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
