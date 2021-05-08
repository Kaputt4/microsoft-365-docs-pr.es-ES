---
title: Configurar Antivirus de Microsoft Defender con Configuration Manager e Intune
description: Use Microsoft Endpoint Manager y Microsoft Intune para configurar Microsoft Defender AV y Endpoint Protection
keywords: scep, intune, endpoint protection, configuration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/26/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: b62344945efc0bdfc495a4fc4196cea6ddcb1874
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275329"
---
# <a name="use-microsoft-endpoint-manager-and-microsoft-intune-to-configure-and-manage-microsoft-defender-antivirus"></a>Use Microsoft Endpoint Manager y Microsoft Intune para configurar y administrar Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Si usaba Microsoft Endpoint Manager o Microsoft Intune para administrar los puntos de conexión en la red, ahora puede usar Microsoft Endpoint Manager para administrar Antivirus de Microsoft Defender exámenes.

1. En el centro Microsoft Endpoint Manager administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), vaya a Endpoint **Security**.

2. En **Administrar**, elija **Antivirus**.

3. Seleccione la directiva Antivirus de Microsoft Defender usuario. 

4. En **Administrar**, elija **Propiedades**.

5. Junto a **Configuración,** elija **Editar**.

6. Expanda la **sección** Examinar y revise o edite la configuración del examen.

7. Elija **Revisar y guardar**

¿Necesita ayuda? Consulte [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).


## <a name="related-articles"></a>Artículos relacionados

- [Temas de referencia para herramientas de administración y configuración](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)