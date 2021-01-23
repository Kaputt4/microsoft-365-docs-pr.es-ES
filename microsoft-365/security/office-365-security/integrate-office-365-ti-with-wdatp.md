---
title: Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint
f1.keywords:
- NOCSH
keywords: integrar, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use Microsoft Defender para Office 365 junto con Microsoft Defender para Endpoint para obtener información más detallada sobre las amenazas contra sus dispositivos y contenido de correo electrónico.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24b81bb4c445c44d7c0228fa1c4440faff642816
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939337"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender para Office 365](office-365-atp.md) se puede configurar para trabajar con [Microsoft Defender para Endpoint.](https://docs.microsoft.com/windows/security/threat-protection)

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint puede ayudar a su equipo de operaciones de seguridad a supervisar y tomar medidas rápidamente si los dispositivos de los usuarios están en riesgo. Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como cuántas alertas recientes se generaron para esos dispositivos en Microsoft Defender para Endpoint.

En la siguiente imagen se muestra el aspecto **que** tiene la pestaña Dispositivos para habilitar la integración de Microsoft Defender para puntos de conexión:

![Cuando Microsoft Defender para endpoint está habilitado, puedes ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno tiene una alerta. Al hacer clic en el vínculo de un dispositivo, se abre su página en el Centro de seguridad de Microsoft Defender ( <https://securitycenter.windows.com> ).

> [!TIP]
> **[Obtenga más información sobre el Centro de seguridad de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (también conocido como portal de Microsoft Defender para puntos de conexión).

## <a name="requirements"></a>Requisitos

- Su organización debe tener Microsoft Defender para Office 365 (u Office 365 E5) y Microsoft Defender para Endpoint.

- Debe ser administrador global o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en el Centro de [& cumplimiento.](https://protection.office.com) (Vea [Permisos en el Centro de seguridad & cumplimiento)](permissions-in-the-security-and-compliance-center.md)

- Debe tener acceso tanto al [Explorador (como a](threat-explorer.md) las detecciones en tiempo real) en el Centro de seguridad & cumplimiento y en el Centro de seguridad de Microsoft Defender.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar Microsoft Defender para Office 365 con Microsoft Defender para endpoint

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint se configura mediante el Centro de seguridad & Cumplimiento y el Centro de seguridad de Microsoft Defender.

1. Como administrador global o administrador de seguridad, vaya e <https://protection.office.com> inicie sesión. (Esto le lleva al Centro de seguridad y & de Office 365).

2. En el panel de navegación, elija **Explorador de administración de** \> **amenazas.**

   ![Explorador en el menú Administración de amenazas](../../media/ThreatMgmt-Explorer-nav.png)

3. En la esquina superior derecha de la pantalla, elija Defender para configuración de extremo **(configuración MDE).**

4. En el cuadro de diálogo conexión de Microsoft Defender para puntos de conexión, active **Conectar a Microsoft Defender para Endpoint.**

   ![Conexión de Microsoft Defender para puntos de conexión](../../media/Explorer-WDATPConnection-dialog.png)

5. Vaya al Centro de seguridad de Microsoft Defender ( <https://securitycenter.windows.com> ).

6. En la barra de navegación, elija **Configuración.** A continuación, en **General,** elija **Características avanzadas.**

7. Desplácese hacia abajo hasta la conexión de inteligencia de amenazas de **Office 365** y active la conexión.

   ![Conexión de inteligencia de amenazas de Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Artículos relacionados

[Capacidades de investigación y respuesta de amenazas en Office 365](office-365-ti.md)

[Microsoft Defender para Office 365](office-365-atp.md)

[Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection)
