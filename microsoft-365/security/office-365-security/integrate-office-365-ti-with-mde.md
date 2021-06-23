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
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083385"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender para Office 365](defender-for-office-365.md) puede configurarse para funcionar con [Microsoft Defender para endpoint](/windows/security/threat-protection).

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint puede ayudar a su equipo de operaciones de seguridad a supervisar y tomar medidas rápidamente si los dispositivos de los usuarios están en riesgo. Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como cuántas alertas recientes se generaron para esos dispositivos en Microsoft Defender para endpoint.

En la siguiente imagen se muestra el aspecto **de** la pestaña Dispositivos cuando se habilita la integración de Microsoft Defender para endpoints:

![Cuando Microsoft Defender para endpoint está habilitado, puedes ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno tiene una alerta. Al hacer clic en el vínculo de un dispositivo, se abre su página [en el portal de Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (anteriormente el Centro de seguridad de Microsoft Defender).

> [!TIP]
> El portal Microsoft 365 Defender reemplaza al Centro de seguridad de Microsoft Defender. Consulta [Microsoft Defender para Endpoint en Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Requisitos

- Su organización debe tener Microsoft Defender para Office 365 (o Office 365 E5) y Microsoft Defender para endpoint.

- Debe ser un administrador global o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en Microsoft 365. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Debe tener acceso al [Explorador (o detecciones en tiempo real).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar Microsoft Defender para Office 365 con Microsoft Defender para endpoint

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint se configura en Defender para Endpoint y Defender para Office 365.

1. Como administrador global o administrador de seguridad, abra el portal de Microsoft 365 Defender ( ) y vaya a Correo electrónico <https://security.microsoft.com> **& explorador de** \> **colaboración**. Para ir directamente a la **página Explorador,** use <https://security.microsoft.com/threatexplorer> .

2. En la **página Explorador,** en la esquina superior derecha de la pantalla, haga clic en **MDE Configuración**.

3. En el control desplegable de conexión de **Microsoft Defender** para puntos de conexión que aparece, activa Conectar a Microsoft **Defender para** Endpoint ( Toggle on ) y, a continuación, haz clic en Cerrar ![ icono ](../../media/scc-toggle-on.png) ![ ](../../media/m365-cc-sc-close-icon.png) **Cerrar**.

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Conexión MDE":::

4. En el panel de navegación, elija **Configuración**. En la **Configuración,** elija **Extremos**

5. En la **página Extremos que** se abre, elija Características **avanzadas**.

6. Desplácese hacia abajo **hasta Office 365 de inteligencia** de amenazas y actóla ( Activar ![ ](../../media/scc-toggle-on.png) ).

   Cuando haya terminado, haga clic en **Guardar preferencias**.

## <a name="related-articles"></a>Artículos relacionados

[Capacidades de investigación y respuesta de amenazas en Office 365](office-365-ti.md)

[Microsoft Defender para Office 365](defender-for-office-365.md)

[Microsoft Defender para punto de conexión](/windows/security/threat-protection)
