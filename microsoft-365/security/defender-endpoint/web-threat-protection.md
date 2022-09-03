---
title: Proteja su organización contra las amenazas web
description: Obtenga información sobre la protección web en Microsoft Defender para punto de conexión y cómo puede proteger su organización.
keywords: protección web, protección contra amenazas web, exploración web, seguridad, phishing, malware, vulnerabilidad de seguridad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 08/22/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: f5df3cdfa8b7bb699126e9362de53a7cfa52b8fc
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67576239"
---
# <a name="protect-your-organization-against-web-threats"></a>Proteja su organización contra las amenazas web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

La protección contra amenazas web forma parte de la [protección web](web-protection-overview.md) en Defender para punto de conexión. Usa [la protección de red](network-protection.md) para proteger los dispositivos frente a amenazas web. Mediante la integración con Microsoft Edge y exploradores de terceros populares como Chrome y Firefox, la protección contra amenazas web detiene las amenazas web sin un proxy web y puede proteger los dispositivos mientras están fuera o en el entorno local. La protección contra amenazas web detiene el acceso a sitios de phishing, vectores de malware, sitios de vulnerabilidades de seguridad, sitios que no son de confianza o de baja reputación, así como sitios que ha bloqueado en la [lista de indicadores personalizados](manage-indicators.md).

> [!NOTE]
> Los dispositivos pueden tardar hasta dos horas en recibir nuevos indicadores personalizados.

## <a name="prerequisites"></a>Requisitos previos

La protección web usa la protección de red para proporcionar seguridad de exploración web en Microsoft Edge y en exploradores web de terceros.

Para activar la protección de red en los dispositivos:

- Edite la línea de base de seguridad de Defender para punto de conexión en **Web & Network Protection** para habilitar la protección de red antes de implementarla o volver a implementarla. [Obtenga información sobre cómo revisar y asignar la línea base de seguridad de Defender para punto de conexión.](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Active la protección de red mediante Intune configuración del dispositivo, SCCM, directiva de grupo o la solución MDM. [Obtenga más información sobre cómo habilitar la protección de red.](enable-network-protection.md)

> [!NOTE]
> Si establece protección de red **en Solo auditoría**, el bloqueo no estará disponible. Además, podrá detectar y registrar intentos de acceder solo a sitios web malintencionados y no deseados en Microsoft Edge.

## <a name="configure-web-threat-protection"></a>Configuración de la protección contra amenazas web

En el procedimiento siguiente se describe cómo configurar la protección contra amenazas web mediante el Centro de administración de Microsoft Endpoint Manager.

1. Vaya al Centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) e inicie sesión.
 
2. Elija **Endpoint security** \> **Attack surface reduction (Reducción de la superficie expuesta a ataques**) y, a continuación, elija **+ Crear directiva**.

3. Seleccione una plataforma, como **Windows 10 y versiones posteriores**, seleccione el perfil **de protección web** y, a continuación, elija **Crear**. 

4. En la pestaña **Aspectos básicos** , especifique un nombre y una descripción y, a continuación, elija **Siguiente**.

5. En la pestaña **Configuración** , expanda **Protección web**, especifique la configuración y, a continuación, elija **Siguiente**.

   - Establezca **Habilitar protección de red** en **Habilitado** para que la protección web esté activada. Como alternativa, puede establecer la protección de red en **modo auditoría** para ver cómo funcionará en su entorno. En el modo de auditoría, la protección de red no impide que los usuarios visiten sitios o dominios, pero realiza un seguimiento de las detecciones como eventos. 
   - Para proteger a los usuarios de posibles estafas de suplantación de identidad (phishing) y software malintencionado, active **Requerir SmartScreen para Microsoft Edge (versión anterior)** a **Sí**.
   - Para evitar que los usuarios omitan advertencias sobre sitios potencialmente malintencionados, establezca **Bloquear el acceso a sitios malintencionados** en **Sí**.
   - Para evitar que los usuarios omitan las advertencias y descarguen archivos no comprobados, establezca **Bloquear descarga de archivos no comprobados** en **Sí**. 

6. En la pestaña **Etiquetas** de ámbito, si su organización usa etiquetas de ámbito, elija **+ Seleccionar etiquetas de ámbito** y, a continuación, elija **Siguiente**. (Si no usa etiquetas de ámbito, elija **Siguiente**). Para más información sobre las etiquetas de ámbito, consulte [Uso del control de acceso basado en rol (RBAC) y las etiquetas de ámbito para TI distribuida](/mem/intune/fundamentals/scope-tags).

7. En la pestaña **Asignaciones** , especifique los usuarios y dispositivos para recibir la directiva de protección web y, a continuación, elija **Siguiente**.

8. En la pestaña **Revisar y crear** , revise la configuración de la directiva y, a continuación, elija **Crear**.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a protección web](web-protection-overview.md)
- [Protección contra amenazas web](web-threat-protection.md)
- [Supervisar la seguridad web](web-protection-monitoring.md)
- [Responder a amenazas web](web-protection-response.md)
- [Protección de red](network-protection.md)
