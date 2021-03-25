---
title: Proteger su organización contra amenazas web
description: Obtenga información sobre la protección web en ATP de Microsoft Defender y cómo puede proteger su organización.
keywords: protección web, protección contra amenazas web, navegación web, seguridad, phishing, malware, vulnerabilidad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7754fa586b24fdedaa9691b45f5da4654c882a5b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185986"
---
# <a name="protect-your-organization-against-web-threats"></a>Proteger su organización contra amenazas web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protección contra amenazas web forma parte de [la protección web](web-protection-overview.md) en Defender para endpoint. Usa la [protección de red para](network-protection.md) proteger los dispositivos contra amenazas web. Al integrar con Microsoft Edge y exploradores de terceros populares como Chrome y Firefox, la protección contra amenazas web detiene las amenazas web sin un proxy web y puede proteger los dispositivos mientras están fuera o localmente. La protección contra amenazas web detiene el acceso a sitios de phishing, vectores de malware, sitios de vulnerabilidad, sitios que no son de confianza o de baja reputación, así como sitios que ha bloqueado en la lista de [indicadores personalizados.](manage-indicators.md)

>[!Note]
>Los dispositivos pueden tardar hasta una hora en recibir nuevos indicadores de cliente.

## <a name="prerequisites"></a>Requisitos previos
La protección web usa la protección de red para proporcionar seguridad de exploración web en Microsoft Edge y exploradores web de terceros.

Para activar la protección de red en los dispositivos:
- Edite la línea base de seguridad de Defender for Endpoint en **Web & Network Protection** para habilitar la protección de red antes de implementarla o volver a implementarla. [Obtenga información sobre cómo revisar y asignar la línea base de seguridad de Defender for Endpoint](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Activa la protección de red con la configuración de dispositivos de Intune, SCCM, la directiva de grupo o la solución MDM. [Más información sobre cómo habilitar la protección de red](enable-network-protection.md)  

>[!Note]
>Si establece la protección de red en **Solo auditoría,** el bloqueo no estará disponible. Además, solo podrá detectar e registrar intentos de acceso a sitios web malintencionados y no deseados en Microsoft Edge.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la protección web](web-protection-overview.md)
- [Protección contra amenazas web](web-threat-protection.md)
- [Supervisar la seguridad web](web-protection-monitoring.md)
- [Responder a amenazas web](web-protection-response.md)
- [Protección de red](network-protection.md)
