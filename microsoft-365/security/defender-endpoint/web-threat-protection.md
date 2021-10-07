---
title: Proteja su organización contra las amenazas web
description: Obtenga información sobre la protección web en Microsoft Defender para endpoint y cómo puede proteger su organización.
keywords: protección web, protección contra amenazas web, navegación web, seguridad, phishing, malware, vulnerabilidad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 90775af14d78092159d2b92736abce56a961416e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159179"
---
# <a name="protect-your-organization-against-web-threats"></a>Proteja su organización contra las amenazas web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protección contra amenazas web forma parte de [la protección web](web-protection-overview.md) en Defender para endpoint. Usa la [protección de red para](network-protection.md) proteger los dispositivos contra amenazas web. Al integrar con Microsoft Edge y exploradores de terceros populares como Chrome y Firefox, la protección contra amenazas web detiene las amenazas web sin un proxy web y puede proteger los dispositivos mientras están fuera o localmente. La protección contra amenazas web detiene el acceso a sitios de phishing, vectores de malware, sitios de vulnerabilidad, sitios que no son de confianza o de baja reputación, así como sitios que ha bloqueado en la lista de [indicadores personalizados.](manage-indicators.md)

> [!NOTE]
> Los dispositivos pueden tardar hasta una hora en recibir nuevos indicadores personalizados.

## <a name="prerequisites"></a>Requisitos previos

La protección web usa la protección de red para proporcionar seguridad de navegación web Microsoft Edge exploradores web de terceros.

Para activar la protección de red en los dispositivos:

- Edite la línea base de seguridad de Defender for Endpoint en **Web & Network Protection** para habilitar la protección de red antes de implementarla o volver a implementarla. [Obtenga información sobre cómo revisar y asignar la línea base de seguridad de Defender for Endpoint](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Activa la protección de red con la configuración de dispositivos de Intune, SCCM, la directiva de grupo o la solución MDM. [Más información sobre cómo habilitar la protección de red](enable-network-protection.md)

> [!NOTE]
> Si establece la protección de red en **Solo auditoría,** el bloqueo no estará disponible. Además, podrás detectar e registrar intentos de acceso a sitios web malintencionados y no deseados en Microsoft Edge solo.

## <a name="configure-web-threat-protection"></a>Configurar la protección contra amenazas web

En el siguiente procedimiento se describe cómo configurar la protección contra amenazas web mediante el centro Microsoft Endpoint Manager administración.

1. Vaya al Centro Microsoft Endpoint Manager de administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.
 
2. Elija **Endpoint security** Attack surface \> **reduction** y, a continuación, elija + Create **policy**.

3. Seleccione una plataforma, como Windows 10 y **posterior,** seleccione el perfil de protección **web** y, a continuación, **elija Crear**. 

4. En la **pestaña Conceptos** básicos, especifique un nombre y una descripción y, a continuación, elija **Siguiente**.

5. En la **pestaña Configuración,** expanda **Protección web**, especifique la configuración y, a continuación, **elija Siguiente**.

   - Establezca **Habilitar la protección de red** en Habilitado **para** que la protección web esté activada. Como alternativa, puede establecer la protección de red en **modo auditoría** para ver cómo funcionará en su entorno. En el modo de auditoría, la protección de red no impide que los usuarios visiten sitios o dominios, pero sí realiza un seguimiento de las detecciones como eventos. 
   - Para proteger a los usuarios de posibles estafas de suplantación de identidad (phishing) y software malintencionado, active **Requerir SmartScreen para Microsoft Edge (versión anterior)** a **Sí**.
   - Para evitar que los usuarios omitan advertencias sobre sitios potencialmente malintencionados, establezca **Bloquear el acceso a sitios malintencionados** en **Sí**.
   - Para evitar que los usuarios omitan las advertencias y descarguen archivos noverificados, establezca Bloquear descarga de archivos **noverificados** tl **Sí**. 

6. En la **pestaña Etiquetas de ámbito,** si su organización usa etiquetas de ámbito, elija **+ Seleccionar** etiquetas de ámbito y, a continuación, **elija Siguiente**. (Si no usa etiquetas de ámbito, elija **Siguiente**.) Para obtener más información acerca de las etiquetas de ámbito, vea [Use role-based access control (RBAC) and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags).

7. En la **pestaña Asignaciones,** especifique los usuarios y dispositivos para recibir la directiva de protección web y, a continuación, elija **Siguiente**.

8. En la **pestaña Revisar + crear,** revise la configuración de la directiva y, a continuación, elija **Crear**.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a protección web](web-protection-overview.md)
- [Protección contra amenazas web](web-threat-protection.md)
- [Supervisar la seguridad web](web-protection-monitoring.md)
- [Responder a amenazas web](web-protection-response.md)
- [Protección de red](network-protection.md)
