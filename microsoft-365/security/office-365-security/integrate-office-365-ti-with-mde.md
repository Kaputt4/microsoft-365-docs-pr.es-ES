---
title: Uso de Microsoft Defender para Office 365 junto con Microsoft Defender para punto de conexión
f1.keywords:
- NOCSH
keywords: integrar, Microsoft Defender, Microsoft Defender para punto de conexión
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 12/02/2021
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- m365-security
description: Use Microsoft Defender para Office 365 junto con Microsoft Defender para punto de conexión para obtener información más detallada sobre las amenazas contra los dispositivos y el contenido del correo electrónico.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: b9e132d7a499b01c059f867a3bde1eff9a0df1d9
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68640178"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Uso de Microsoft Defender para Office 365 junto con Microsoft Defender para punto de conexión

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

[Microsoft Defender para Office 365](defender-for-office-365.md) se puede configurar para que funcione con [Microsoft Defender para punto de conexión](/windows/security/threat-protection).

La integración de Microsoft Defender para Office 365 con Microsoft Defender para punto de conexión puede ayudar al equipo de operaciones de seguridad a supervisar y tomar medidas rápidamente si los dispositivos de los usuarios están en riesgo. Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como cuántas alertas recientes se generaron para esos dispositivos en Microsoft Defender para punto de conexión.

En la imagen siguiente se muestra el aspecto de la pestaña **Dispositivos** cuando se ha habilitado Microsoft Defender para punto de conexión integración:

:::image type="content" source="../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG" alt-text="Una lista de dispositivos con alertas" lightbox="../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG":::

En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno tiene una alerta. Al hacer clic en el vínculo de un dispositivo, se abre su página en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender).

> [!TIP]
> El portal de Microsoft 365 Defender reemplaza el Centro de seguridad de Microsoft Defender. Consulte [Microsoft Defender para punto de conexión en Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Requisitos

- La organización debe tener Microsoft Defender para Office 365 (o Office 365 E5) y Microsoft Defender para punto de conexión.

- Debe tener asignado el rol de administrador global o administrador de seguridad en Microsoft 365. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Debe tener acceso al [Explorador (o a las detecciones en tiempo real).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar Microsoft Defender para Office 365 con Microsoft Defender para punto de conexión

La integración de Microsoft Defender para Office 365 con Microsoft Defender para punto de conexión está configurada tanto en Defender para punto de conexión como en Defender para Office 365.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a Email & **explorador** de **colaboración**\>.

3. En la página **Explorador** , en la esquina superior derecha de la pantalla, seleccione **Configuración de MDE**.

3. En el **control flotante Microsoft Defender para punto de conexión conexión** que aparece, active **Conectar a Microsoft Defender para punto de conexión** (![activar](../../media/scc-toggle-on.png)) y, a continuación, seleccione **Cerrar**.

   :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Página Conexión de MDE" lightbox="../../media/explorer-mdeconnection-dialognew.png":::

4. En el panel de navegación, elija **Configuración**. En la página **Configuración**, elija **Puntos de conexión**.

5. En la página **Puntos de conexión** que se abre, elija **Características avanzadas**.

6. Desplácese hacia abajo hasta **Office 365 conexión de Inteligencia de amenazas** y actíela (![Activar).](../../media/scc-toggle-on.png)

   Cuando haya terminado, seleccione **Guardar preferencias**.

## <a name="see-also"></a>Vea también

[Funcionalidades de investigación y respuesta de amenazas en Office 365](office-365-ti.md)

[Microsoft Defender para Office 365](defender-for-office-365.md)

[Microsoft Defender para punto de conexión](/windows/security/threat-protection)
