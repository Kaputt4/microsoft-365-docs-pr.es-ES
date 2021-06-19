---
title: Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint
f1.keywords:
- NOCSH
keywords: integrate, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Usa Microsoft Defender para Office 365 junto con Microsoft Defender para Endpoint para obtener información más detallada sobre las amenazas contra los dispositivos y el contenido de correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028886"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender para Office 365](defender-for-office-365.md) puede configurarse para funcionar con [Microsoft Defender para endpoint](/windows/security/threat-protection).

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint puede ayudar a su equipo de operaciones de seguridad a supervisar y tomar medidas rápidamente si los dispositivos de los usuarios están en riesgo. Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como cuántas alertas recientes se generaron para esos dispositivos en Microsoft Defender para endpoint.

En la siguiente imagen se muestra el aspecto **de** la pestaña Dispositivos cuando se habilita la integración de Microsoft Defender para endpoints:

![Cuando Microsoft Defender para endpoint está habilitado, puedes ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno tiene una alerta. Al hacer clic en el vínculo de un dispositivo, se abre su [página en Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (anteriormente el Centro de seguridad de Microsoft Defender).

> [!TIP]
> El portal Microsoft 365 Defender reemplaza al Centro de seguridad de Microsoft Defender. Consulta [Microsoft Defender para Endpoint en Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Requisitos

- Su organización debe tener Microsoft Defender para Office 365 (o Office 365 E5) y Microsoft Defender para endpoint.

- Debe ser un administrador global o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en Microsoft 365. (Vea [Permisos en el Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))

- Debe tener acceso al [Explorador (o detecciones en tiempo real).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar Microsoft Defender para Office 365 con Microsoft Defender para endpoint

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint se configura en Defender para Endpoint y Defender para Office 365.

1. Como administrador global o administrador de seguridad, vaya a [https://security.microsoft.com](https://security.microsoft.com) e inicie sesión. (Esto le lleva al portal de Microsoft 365 Defender).

2. En el panel de navegación, elija **Correo & explorador de** \> **colaboración**.

3. En la esquina superior derecha de la pantalla, haga clic en **MDE Configuración**.

4. En el cuadro de diálogo Conexión de Microsoft Defender para endpoint, active **Conectar a Microsoft Defender para Endpoint**.

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Conexión MDE":::

5. Vaya al portal Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) .

6. En la barra de navegación, **elija Configuración**. A continuación, **en General**, elija **Características avanzadas**.

7. Desplácese hacia abajo **hasta Office 365 de inteligencia** de amenazas y active la conexión.

   ![Office 365 de inteligencia de amenazas](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Artículos relacionados

[Capacidades de investigación y respuesta de amenazas en Office 365](office-365-ti.md)

[Microsoft Defender para Office 365](defender-for-office-365.md)

[Microsoft Defender para punto de conexión](/windows/security/threat-protection)
