---
title: Microsoft Defender para punto de conexión demostración de reputación de la aplicación SmartScreen
description: Pruebe cómo Microsoft Defender para punto de conexión SmartScreen le ayuda a identificar sitios web de phishing y malware
keywords: Microsoft Defender para punto de conexión, sitio web de phishing, sitio web de malware, reputación de la aplicación,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
- demo
ms.topic: article
ms.subservice: mde
ms.date: 10/21/2022
ms.openlocfilehash: cc7081f8c6e71e321e68016f45c5d400e3a1c3cd
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68730279"
---
# <a name="smartscreen-app-reputation-demonstration"></a>Demostración de reputación de la aplicación SmartScreen

Pruebe cómo Microsoft Defender para punto de conexión SmartScreen le ayuda a identificar sitios web de phishing y malware en función de la reputación de la aplicación.

## <a name="scenario-requirements-and-setup"></a>Requisitos y configuración del escenario

- Windows 10
- Se requiere Internet Explorer o el explorador Microsoft Edge
- Para activar o desactivar, vaya a **Configuración** > **Update & Security** >  **Seguridad de Windows** >  **Open Seguridad de Windows** >  **App & browser control** > **Check apps and files**

## <a name="scenario-demos"></a>Demostraciones de escenarios

### <a name="known-good-program"></a>Buen programa conocido

Este programa tiene una buena reputación; la descarga debe ejecutarse sin interrupciones:

- [Conocida buena descarga del programa](https://demo.smartscreen.msft.net/download/known/freevideo.exe)

  Al iniciar este vínculo, se debe representar un mensaje similar al siguiente:

  :::image type="content" source="images/smartscreen-app-reputation-known-good.png" alt-text="En función de la reputación del archivo de destino, SmartScreen permite la descarga sin interferencias.":::

### <a name="unknown-program"></a>Programa desconocido

Dado que la descarga del programa no tiene suficiente reputación para asegurarse de que es de confianza, SmartScreen mostrará una advertencia antes de ejecutar la descarga del programa.

- [Programa desconocido](https://demo.smartscreen.msft.net/download/unknown/freevideo.exe)
  
  Al iniciar este vínculo, se debe representar un mensaje similar al siguiente:

  :::image type="content" source="images/smartscreen-app-reputation-unknown.png" alt-text="SmartScreen no tiene suficiente información de reputación sobre el archivo de descarga y advierte al usuario de que detenga o continúe con precaución.":::

### <a name="known-malware"></a>Malware conocido

Esta descarga es malware conocido; SmartScreen debe impedir que este programa se ejecute.

- [Malware conocido](https://demo.smartscreen.msft.net/download/known/knownmalicious.exe)

  Al iniciar este vínculo, se debe representar un mensaje similar al siguiente:

  :::image type="content" source="images/smartscreen-app-reputation-known-malware.png" alt-text="Captura de pantalla que muestra cómo SmartScreen detecta una descarga de archivos con una reputación no segura; la descarga está bloqueada.":::

## <a name="learn-more"></a>Más información

[Microsoft Defender documentación de SmartScreen](/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview.md)

## <a name="see-also"></a>Vea también

[Microsoft Defender para punto de conexión: escenarios de demostración](defender-endpoint-demonstrations.md)
