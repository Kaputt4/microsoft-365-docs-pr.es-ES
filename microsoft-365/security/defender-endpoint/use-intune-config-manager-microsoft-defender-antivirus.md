---
title: Configuración de Microsoft Defender Antivirus mediante Microsoft Endpoint Manager
description: Uso de Microsoft Endpoint Manager y Microsoft Intune para configurar Microsoft Defender Antivirus y Endpoint Protection
keywords: scep, intune, endpoint protection, configuration
ms.service: microsoft-365-security
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
ms.subservice: mde
audience: ITPro
ms.topic: how-to
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 9a3b0a5a49dfea74f0545ecf85a903b7d2f0b1f3
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232834"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Uso de Microsoft Endpoint Manager para configurar y administrar Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Puede usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) para configurar exámenes de antivirus de Microsoft Defender. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Configuration Manager](/mem/configmgr/core/understand/introduction) ahora forman parte de Endpoint Manager.

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Configuración de exámenes de antivirus de Microsoft Defender en Endpoint Manager

1. Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.

2. Vaya a **Seguridad del punto de conexión**.

3. En **Administrar**, elija **Antivirus**.

4. Seleccione la directiva de antivirus de Microsoft Defender.

5. En **Administrar**, elija **Propiedades**.

6. Junto a **Opciones de configuración**, elija **Editar**.

   > [!IMPORTANT]
   > La configuración del antivirus AllowOnAccessProtection y AllowIntrusionPreventionSystem está oficialmente en desuso y, como tal, no se puede configurar. 

7. Expanda la sección **Examinar** y revise o edite la configuración de examen.

8. Elija **Revisar y guardar**.

> [!TIP]
> ¿Necesita ayuda? Consulte [Administración de la seguridad del punto de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security).

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
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
