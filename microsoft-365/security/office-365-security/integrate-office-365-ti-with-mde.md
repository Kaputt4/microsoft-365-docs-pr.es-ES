---
title: Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint
f1.keywords:
- NOCSH
keywords: integrate, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 12/02/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Usa Microsoft Defender para Office 365 junto con Microsoft Defender para Endpoint para obtener información más detallada sobre las amenazas contra los dispositivos y el contenido de correo electrónico.
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 67406984e73f39858f4a7329a8c8520fcd35ac5c
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "62464764"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender para Office 365](defender-for-office-365.md) puede configurarse para que funcione con [Microsoft Defender para endpoint](/windows/security/threat-protection).

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint puede ayudar a su equipo de operaciones de seguridad a supervisar y tomar medidas rápidamente si los dispositivos de los usuarios están en riesgo. Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como cuántas alertas recientes se generaron para esos dispositivos en Microsoft Defender para endpoint.

En la siguiente imagen se muestra el **aspecto de la** pestaña Dispositivos cuando se habilita la integración de Microsoft Defender para endpoints:

![Cuando Microsoft Defender para endpoint está habilitado, puedes ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno tiene una alerta. Al hacer clic en el vínculo de un dispositivo, se abre su página en [el portal Microsoft 365 Defender dispositivo](/microsoft-365/security/defender/microsoft-365-defender).

> [!TIP]
> El portal Microsoft 365 Defender reemplaza al Centro de seguridad de Microsoft Defender. Consulta [Microsoft Defender para Endpoint en Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Requisitos

- Su organización debe tener Microsoft Defender para Office 365 (o Office 365 E5) y Microsoft Defender para endpoint.

- Debe tener asignado el rol de administrador global o de administrador de seguridad en Microsoft 365. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Debe tener acceso al [Explorador (o detecciones en tiempo real).](threat-explorer.md)

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar Microsoft Defender para Office 365 con Microsoft Defender para endpoint

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint se configura en Defender para Endpoint y Defender para Office 365.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Correo electrónico & explorador de colaboración**\>. 

3. En la **página Explorador**, en la esquina superior derecha de la pantalla, seleccione **MDE Configuración**.

3. En el control desplegable de conexión de **Microsoft Defender** para puntos de conexión que aparece, **activa Conectar a Microsoft Defender para** endpoint (![Activar)](../../media/scc-toggle-on.png) y, a continuación, selecciona **Cerrar**.

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Conexión MDE.":::

4. En el panel de navegación, **elija Configuración**. En la **Configuración**, elija **Extremos**

5. En la **página Extremos que** se abre, elija **Características avanzadas**.

6. Desplácese hacia abajo **hasta Office 365 de inteligencia** de amenazas y actóla (![Activar).](../../media/scc-toggle-on.png)

   Cuando haya terminado, seleccione **Guardar preferencias**.

## <a name="see-also"></a>Vea también

[Capacidades de investigación y respuesta de amenazas en Office 365](office-365-ti.md)

[Microsoft Defender para Office 365](defender-for-office-365.md)

[Microsoft Defender para punto de conexión](/windows/security/threat-protection)
