---
title: Funcionalidades de Microsoft Defender para punto de conexión admitidas por plataforma
description: Conozca las funcionalidades de Microsoft Defender para punto de conexión compatibles con dispositivos Windows 10, servidores y dispositivos que no son de Windows.
keywords: onboarding, Microsoft Defender para punto de conexión onboarding, sccm, group policy, mdm, local script, detection test
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: dcff54381dbdaf1362f9d4dd7cdc364e29c53426
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68227754"
---
# <a name="supported-microsoft-defender-for-endpoint-capabilities-by-platform"></a>Funcionalidades de Microsoft Defender para punto de conexión admitidas por plataforma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Obtenga información sobre cómo [incorporar dispositivos y configurar funcionalidades de Microsoft Defender para punto de conexión](onboard-configure.md).

En la tabla siguiente se proporciona información sobre las funcionalidades de Microsoft Defender para punto de conexión admitidas por plataforma.

|Sistema operativo  |Windows 10 & 11  |Windows Server 2012 R2 <sup>[[1](#fn1)]</sup>, <br> 2016 <sup>[[1](#fn1)]</sup>, <br> 2019 & 2022, <br> 1803+ |macOS |Linux| 
|---------|---------|---------|---------|---------|
|**Prevención**    |         |         |         |         | 
|Reglas de reducción de superficie expuesta a ataques     | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)     |  ![No](images/svg/check-no.svg)       |  ![No](images/svg/check-no.svg)        |
|Acceso controlado a carpetas     | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)    |  ![No](images/svg/check-no.svg)       |  ![No](images/svg/check-no.svg)        |
|Control de dispositivo     | ![Sí.](images/svg/check-yes.svg)        | ![No](images/svg/check-no.svg)   |  ![Sí.](images/svg/check-yes.svg)       |  ![No](images/svg/check-no.svg)        |  
|Firewall      | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)    |  ![No](images/svg/check-no.svg)       |  ![No](images/svg/check-no.svg)        |
|Protección de red      | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)   |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |
|Protección de última generación       | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)  |  ![Sí.](images/svg/check-yes.svg)       |  ![Sí.](images/svg/check-yes.svg)         |
|Protección contra alteraciones        | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)  |  ![Sí.](images/svg/check-yes.svg)       |  ![No](images/svg/check-no.svg)         |
|Protección web       | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)     |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |
||||||
|**Detección**     |         |         |         |       |
|Búsqueda avanzada        | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg) |  ![Sí.](images/svg/check-yes.svg)       |  ![Sí.](images/svg/check-yes.svg)         |
|Indicadores de archivos personalizados         | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)  |  ![Sí.](images/svg/check-yes.svg)       |  ![Sí.](images/svg/check-yes.svg)         |
|Indicadores de red personalizados        | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)  |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |
|Bloque EDR       | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)  |  ![No](images/svg/check-no.svg)       |  ![No](images/svg/check-no.svg)        |
|Modo pasivo          | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)  |  ![Sí.](images/svg/check-yes.svg)       |  ![Sí.](images/svg/check-yes.svg)         |
|Sensor de detección de sentidos          | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)   |  ![Sí.](images/svg/check-yes.svg)       |  ![Sí.](images/svg/check-yes.svg)         |
|Detección de dispositivos de red & punto de conexión      | ![Sí.](images/svg/check-yes.svg)        | ![No](images/svg/check-no.svg)  |  ![No](images/svg/check-no.svg)       |  ![No](images/svg/check-no.svg)        |
|Administración de amenazas y vulnerabilidades          | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg) |  ![Sí.](images/svg/check-yes.svg)       |  ![Sí.](images/svg/check-yes.svg)         |
||||||
|**Respuesta**     |         |         |         ||
|Respuesta de & de investigación automatizada (AIR)        | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)  |  ![No](images/svg/check-no.svg)       |  ![No](images/svg/check-no.svg)        |
|Funcionalidades de respuesta del dispositivo: recopilación del paquete de investigación, ejecución del examen de AV        | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)   |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)] [[3](#fn3)]</sup>       |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)] [[3](#fn3)]</sup>        |
|Aislamiento del dispositivo        | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)   |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)] [[3](#fn3)]</sup>       |  ![No](images/svg/check-no.svg)    |
|Capacidades de respuesta de archivos: recopilar archivos, análisis profundos, bloquear archivos, detener y poner en cuarentena procesos        | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg)   |  ![No](images/svg/check-no.svg) <sup>[[4](#fn4)]</sup>      |  ![No](images/svg/check-no.svg) <sup>[[4](#fn4)]</sup>    |
|Respuesta dinámica       | ![Sí.](images/svg/check-yes.svg)        | ![Sí.](images/svg/check-yes.svg) |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>       |  ![Sí.](images/svg/check-yes.svg) <sup>[[2](#fn2)]</sup>        |


(<a id="fn1">1</a>) Hace referencia a la solución moderna y unificada para Windows Server 2012 R2 y 2016. Para obtener más información, vea [Incorporación de servidores Windows al servicio Defender para punto de conexión](configure-server-endpoints.md).

(<a id="fn2">2</a>) La característica está actualmente en versión preliminar ([Microsoft Defender para punto de conexión características en versión preliminar](preview.md)) 

(<a id="fn3">3</a>) Capacidades de respuesta mediante live response [2] 

(<a id="fn4">4</a>) Recopilar solo archivo, con Respuesta activa [2]  
>[!NOTE]
>Windows 7, 8.1, Windows Server 2008 R2 incluyen compatibilidad con el sensor EDR y AV mediante System Center Endpoint Protection (SCEP).

