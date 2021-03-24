---
title: Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint
f1.keywords:
- NOCSH
keywords: integración, Microsoft Defender, ATP
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
ms.openlocfilehash: bac2414419d673f261d0d0162d8ae742385fd4eb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073280"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Usar Microsoft Defender para Office 365 junto con Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender para Office 365](defender-for-office-365.md) se puede configurar para funcionar con [Microsoft Defender para endpoint](/windows/security/threat-protection).

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint puede ayudar a su equipo de operaciones de seguridad a supervisar y tomar medidas rápidamente si los dispositivos de los usuarios están en riesgo. Por ejemplo, una vez habilitada la integración, el equipo de operaciones de seguridad podrá ver los dispositivos potencialmente afectados por un mensaje de correo electrónico detectado, así como cuántas alertas recientes se generaron para esos dispositivos en Microsoft Defender para endpoint.

En la siguiente imagen se muestra el aspecto **de** la pestaña Dispositivos cuando se habilita la integración de Microsoft Defender para endpoints:

![Cuando Microsoft Defender para endpoint está habilitado, puedes ver una lista de dispositivos con alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

En este ejemplo, puede ver que los destinatarios del mensaje de correo electrónico detectado tienen cuatro dispositivos y uno tiene una alerta. Al hacer clic en el vínculo de un dispositivo, se abre su página en el Centro de seguridad de Microsoft Defender ( <https://securitycenter.windows.com> ).

> [!TIP]
> **[Obtenga más información sobre el Centro de seguridad de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/use)** (también conocido como portal de Microsoft Defender para endpoints).

## <a name="requirements"></a>Requisitos

- Su organización debe tener Microsoft Defender para Office 365 (u Office 365 E5) y Microsoft Defender para endpoint.

- Debe ser un administrador global o tener asignado un rol de administrador de seguridad (como administrador de seguridad) en el Centro de [seguridad & cumplimiento](https://protection.office.com). (Vea [Permisos en el Centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md))

- Debe tener acceso a explorer (o detecciones en tiempo [real)](threat-explorer.md) en el Centro de seguridad & cumplimiento y el Centro de seguridad de Microsoft Defender.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>Para integrar Microsoft Defender para Office 365 con Microsoft Defender para endpoint

La integración de Microsoft Defender para Office 365 con Microsoft Defender para endpoint se configura mediante el Centro de seguridad & cumplimiento y el Centro de seguridad de Microsoft Defender.

1. Como administrador global o administrador de seguridad, vaya a <https://protection.office.com> e inicie sesión. (Esto le llevará al Centro de seguridad y & de Seguridad de Office 365).

2. En el panel de navegación, elija **Explorador de administración de** \> **amenazas**.

   ![Explorador en el menú Administración de amenazas](../../media/ThreatMgmt-Explorer-nav.png)

3. En la esquina superior derecha de la pantalla, elija **Defender for Endpoint Settings (MDE Settings)**.

4. En el cuadro de diálogo Conexión de Microsoft Defender para extremo, active **Conectarse a Microsoft Defender para Endpoint**.

   ![Conexión de Microsoft Defender para endpoint](../../media/Explorer-WDATPConnection-dialog.png)

5. Vaya al Centro de seguridad de Microsoft Defender ( <https://securitycenter.windows.com> ).

6. En la barra de navegación, elija **Configuración**. A continuación, **en General**, elija **Características avanzadas**.

7. Desplácese hacia abajo hasta La conexión de Inteligencia de amenazas de **Office 365** y active la conexión.

   ![Conexión de inteligencia de amenazas de Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Artículos relacionados

[Capacidades de investigación y respuesta de amenazas en Office 365](office-365-ti.md)

[Microsoft Defender para Office 365](defender-for-office-365.md)

[Microsoft Defender para punto de conexión](/windows/security/threat-protection)