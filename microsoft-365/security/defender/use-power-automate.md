---
title: Usar Power Automate
description: Obtenga información sobre la automatización de la Microsoft 365 Defender y cómo usarlas.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, secops
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a707de259897080f8e726aed70618ea6505bdea6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717648"
---
# <a name="use-power-automate-in-microsoft-365-defender"></a>Use Power Automate en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de laboratorio](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).
>

Los equipos de operaciones de seguridad modernas (SecOps) necesitan automatización para funcionar eficazmente. Para centrarse en la búsqueda e investigación de amenazas reales, los equipos de SecOps usan Power Automate para obtener información sobre la lista de alertas y eliminar las que no son amenazas.  

## <a name="criteria-for-resolving-alerts"></a>Criterios para resolver alertas

- El usuario tiene el mensaje de fuera de la oficina activado

- El usuario no está etiquetado como de alto riesgo

Si ambos son true, SecOps marca la alerta como viaje legítimo y la resuelve. Una notificación se publica en Microsoft Teams una vez resuelta la alerta. 

## <a name="connect-power-automate-to-microsoft-cloud-app-security"></a>Conectar Power Automate para Microsoft Cloud App Security

Para crear la automatización, necesitarás un token de API antes de conectarte Power Automate a Microsoft Cloud App Security (MCAS). 

1. Haga **clic Configuración**, seleccione Extensiones de **seguridad** y, a continuación, haga clic en **Agregar token** en la pestaña Tokens de **API.** 

2. Proporcione un nombre para el token y, a continuación, haga clic **en Generar**. Guarde el token como lo necesitará más adelante.

## <a name="create-an-automated-flow"></a>Crear un flujo automatizado

Para ver el proceso detallado paso a paso, vea el vídeo [aquí](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn). 

En este vídeo también se describe cómo conectar la automatización de energía a MCAS. 

## <a name="related-information"></a>Información relacionada

- [Integrar Power Automate con Microsoft Cloud App Security](/cloud-app-security/flow-integration)

- [Documentación Power Automate Microsoft](/power-automate)
