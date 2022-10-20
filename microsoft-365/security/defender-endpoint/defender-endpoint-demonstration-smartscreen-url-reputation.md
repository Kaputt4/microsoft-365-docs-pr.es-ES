---
title: Microsoft Defender para punto de conexión demostraciones de reputación de la dirección URL de SmartScreen
description: Muestra cómo Microsoft Defender SmartScreen identifica sitios web de phishing y malware en función de la reputación de las direcciones URL.
keywords: Microsoft Defender para punto de conexión, protección contra suplantación de identidad del sitio web, protección contra malware del sitio web, reputación de direcciones URL, demostración,
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
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: 721ba2fb07d7d8f94b9a3de4e9858bbaf889e519
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620367"
---
# <a name="url-reputation-demonstrations"></a>Demostraciones de reputación de direcciones URL

Pruebe cómo Microsoft Defender SmartScreen le ayuda a identificar sitios web de phishing y malware en función de la reputación de las direcciones URL.
Requisitos y configuración del escenario

- Windows 10 u 11
- Se requiere el explorador Microsoft Edge
- Para obtener más información, vea [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

## <a name="smartscreen-for-microsoft-edge-url-scenario-demonstrations"></a>Demostraciones de escenarios de smartscreen para direcciones URL de Microsoft Edge

### <a name="is-this-phishing"></a>¿Se trata de phishing?

Alerta al usuario a una página sospechosa y solicita comentarios:

- [¿Es phishing?](https://demo.smartscreen.msft.net/other/areyousure.html)

  Al iniciar este vínculo, se debe representar un mensaje similar a la captura de pantalla siguiente:

  :::image type="content" source="images/smartscreen-url-reputation-is-this-phishing.png" alt-text="SmartScreen alerta al usuario de que el sitio es potencialmente un sitio de suplantación de identidad y posiblemente no es seguro":::

### <a name="phishing-page"></a>Página de suplantación de identidad

Página conocida por suplantación de identidad (phishing) que debe bloquearse:

- [Una página de suplantación de identidad conocida](https://demo.smartscreen.msft.net/phishingdemo.html)

  Al iniciar este vínculo, se debe representar un mensaje similar al siguiente ejemplo:

  :::image type="content" source="images/smartscreen-url-reputation-this-is-phishing.png" alt-text="SmartScreen notifica que el sitio es conocido por contener amenazas de suplantación de identidad (phishing)":::

### <a name="malware-page"></a>Página de malware

Página que hospeda malware y que debe bloquearse:

- [Una página de malware conocida](https://demo.smartscreen.msft.net/other/malware.html)

  Al iniciar este vínculo, se debe representar un mensaje similar a la captura de pantalla siguiente:

  :::image type="content" source="images/smartscreen-url-reputation-malware-page.png" alt-text="SmartScreen alerta al usuario de que el sitio es conocido para contener programas dañinos":::

### <a name="blocked-download"></a>Descarga bloqueada

Se ha bloqueado la descarga debido a su reputación de dirección URL

- [Descarga bloqueada debido a la reputación de la dirección URL](https://demo.smartscreen.msft.net/download/malwaredemo/freevideo.exe)

  Al iniciar este vínculo, se debe representar un mensaje similar al mensaje de página Malware.

### <a name="exploit-page"></a>Página de vulnerabilidades de seguridad

Página que ataca una vulnerabilidad del explorador

- [Página de vulnerabilidades de seguridad del explorador conocida](https://demo.smartscreen.msft.net/other/exploit.html)

  Al iniciar este vínculo, se debe representar un mensaje similar al mensaje de página Malware.

### <a name="malvertising"></a>Malversar

Una página benigna que hospeda un anuncio malintencionado

- [Página conocida por contener anuncios malintencionados](https://demo.smartscreen.msft.net/other/exploit_frame.html)

  Al iniciar este vínculo, se debe representar un mensaje similar a la captura de pantalla siguiente:

  :::image type="content" source="images/smartscreen-url-reputation-malvertising.png" alt-text="Una demostración de cómo SmartScreen responde a un marco de una página que se detecta como malintencionado. Solo se bloquea el marco malintencionado":::

## <a name="see-also"></a>Vea también

[Microsoft Defender documentación de SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

[Microsoft Defender para punto de conexión: escenarios de demostración](defender-endpoint-demonstrations.md)
