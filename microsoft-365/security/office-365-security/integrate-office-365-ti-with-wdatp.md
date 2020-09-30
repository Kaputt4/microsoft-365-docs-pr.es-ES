---
title: Usar Microsoft defender para Office 365 junto con Microsoft defender para el punto de conexión
f1.keywords:
- NOCSH
keywords: integración, Microsoft defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use Microsoft defender para Office 365 junto con la protección contra amenazas avanzada de Microsoft defender para obtener información más detallada sobre las amenazas contra sus dispositivos y contenido de correo electrónico.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c95e15c3cf16547843f9d2976dbf9df0d5747c0
ms.sourcegitcommit: 6b1d0bea86ced26cae51695c0077adce8bcff3c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "48309242"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-advanced-threat-protection"></a>Usar Microsoft defender para Office 365 junto con la protección contra amenazas avanzada de Microsoft defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) se puede configurar para que funcione con [Microsoft defender para el punto de conexión](https://docs.microsoft.com/windows/security/threat-protection).

La integración de Microsoft defender para Office 365 con Microsoft defender para el punto de conexión puede ayudar a su equipo de operaciones de seguridad a supervisar y emprender acciones rápidamente si los dispositivos de los usuarios están expuestos. Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como el número de alertas recientes que se generaron para esos dispositivos en Microsoft defender para el punto de conexión. 

En la siguiente imagen se muestra el aspecto de la ficha **dispositivos** que tiene habilitada la integración de Microsoft defender para extremo:
  
![Cuando Microsoft defender for Endpoint está habilitado, puede ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno de ellos tiene una alerta. Al hacer clic en el vínculo de un dispositivo, se abre su página en el centro de seguridad de Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Obtenga más información sobre el centro de seguridad de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (también conocido como el portal ATP de Microsoft defender).
  
## <a name="requirements"></a>Requisitos

- Su organización debe tener Microsoft defender para Office 365 (o Office 365 E5) y Microsoft defender para extremo.
    
- Debe ser administrador global o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en el [centro de seguridad y &amp; cumplimiento](https://protection.office.com). (Consulte [permisos en el centro de seguridad y &amp; cumplimiento](permissions-in-the-security-and-compliance-center.md))
    
- Debe tener acceso a [exploradores (o detecciones en tiempo real)](threat-explorer.md) en el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar Microsoft defender para Office 365 con Microsoft defender para el punto de conexión

La integración de Microsoft defender para Office 365 con Microsoft defender para el punto de conexión se configura mediante el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.
  
1. Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión. (Esto le llevará al centro de cumplimiento de & de seguridad de Office 365).
    
2. En el panel de navegación, elija **Threat Management**  >  **Explorer**.<br>![Explorador en el menú de administración de amenazas](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. En la esquina superior derecha de la pantalla, elija **WDATP de configuración**.
    
4. En el cuadro de diálogo Microsoft defender para conexión de extremo, Active **conectarse a ATP de Windows**.<br>![Microsoft defender para conexión de extremo](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Vaya al centro de seguridad de Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. En la barra de navegación, elija **configuración**. A continuación, en **General**, elija **características avanzadas**.

7. Desplácese hacia abajo hasta **conexión de inteligencia de amenazas de 365 de Office**y active la conexión.<br/>![Conexión de inteligencia de amenazas de Office 365](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Artículos relacionados

[Capacidades de investigación y respuesta de amenazas en Office 365](office-365-ti.md)
  
[Microsoft defender para Office 365](office-365-atp.md)
  
[Microsoft defender para extremo](https://docs.microsoft.com/windows/security/threat-protection)
