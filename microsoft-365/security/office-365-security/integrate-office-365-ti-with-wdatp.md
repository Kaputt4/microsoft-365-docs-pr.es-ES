---
title: Integrar Office 365 ATP con Protección contra amenazas avanzada de Microsoft Defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integre Office 365 Advanced Threat Protection con la protección contra amenazas avanzada de Microsoft defender para ver información más detallada sobre la administración de amenazas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086713"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integración de la protección contra amenazas avanzada de Office 365 con la protección contra amenazas avanzada de Microsoft defender

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) se puede configurar para que funcione con la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection) (ATP de Microsoft defender).

La integración de Office 365 ATP con Microsoft defender ATP puede ayudar a su equipo de operaciones de seguridad a supervisar y emprender acciones rápidamente si los dispositivos de los usuarios están expuestos. Por ejemplo, una vez que la integración está habilitada, el equipo de operaciones de seguridad podrá ver los dispositivos que pueden verse afectados por un mensaje de correo electrónico detectado, así como el número de alertas recientes que dichos dispositivos tienen en ATP de Microsoft defender. 

En la siguiente imagen se muestra el aspecto de la ficha **dispositivos** que tiene habilitada la integración de Microsoft defender ATP:
  
![Cuando ATP de Microsoft defender está habilitada, puede ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno de ellos tiene una alerta. Al hacer clic en el vínculo de un dispositivo, se abre su página en el centro de seguridad de Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Obtenga más información sobre el centro de seguridad de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (también conocido como el portal ATP de Microsoft defender).
  
## <a name="requirements"></a>Requirements

- Su organización debe tener Office 365 ATP plan 2 (o Office 365 E5) y ATP de Microsoft defender.
    
- Debe ser administrador global o tener un rol de administrador de seguridad (como administrador de seguridad) asignado en el [centro de seguridad y &amp; cumplimiento](https://protection.office.com). (Consulte [permisos en el centro de seguridad y &amp; cumplimiento](permissions-in-the-security-and-compliance-center.md))
    
- Debe tener acceso a [exploradores (o detecciones en tiempo real)](threat-explorer.md) en el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>Para integrar Office 365 ATP con Microsoft defender ATP

Integración de Office 365 ATP con Microsoft defender ATP se configura mediante el centro de seguridad & cumplimiento y el centro de seguridad de Microsoft defender.
  
1. Como administrador global o administrador de seguridad, vaya a [https://protection.office.com](https://protection.office.com) e inicie sesión. (Esto le llevará al centro de cumplimiento de & de seguridad de Office 365).
    
2. En el panel de navegación, elija **Threat Management**  >  **Explorer**.<br>![Explorador en el menú de administración de amenazas](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. En la esquina superior derecha de la pantalla, elija **WDATP de configuración**.
    
4. En el cuadro de diálogo conexión ATP de Microsoft defender, Active **conectarse a ATP de Windows**.<br>![Conexión ATP de Microsoft defender](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Vaya al centro de seguridad de Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. En la barra de navegación, elija **configuración**. A continuación, en **General**, elija **características avanzadas**.

7. Desplácese hacia abajo hasta **conexión de inteligencia de amenazas de 365 de Office**y active la conexión.<br/>![Conexión de inteligencia de amenazas de Office 365](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Artículos relacionados

[Capacidades de investigación y respuesta de amenazas en Office 365](office-365-ti.md)
  
[Protección contra amenazas avanzada de Office 365](office-365-atp.md)
  
[ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection)
