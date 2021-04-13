---
title: Definir cómo se actualizan los dispositivos móviles mediante Antivirus de Microsoft Defender
description: Administrar la forma en que los dispositivos móviles, como los portátiles, deben actualizarse con las actualizaciones de protección antivirus de Microsoft Defender.
keywords: actualizaciones, protección, actualizaciones de programación, batería, dispositivo móvil, portátil, bloc de notas, opt-in, microsoft update, wsus, override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f67330e1ccd7361c3982b76a6ab8754db23bd110
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690985"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Administrar actualizaciones para dispositivos móviles y máquinas virtuales (VM)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

Es posible que los dispositivos móviles y las máquinas virtuales requieran más configuración para garantizar que las actualizaciones no afectan al rendimiento.

Hay dos opciones de configuración que son útiles para estos dispositivos:

- Participar en Microsoft Update en equipos móviles sin conexión WSUS
- Impedir actualizaciones de inteligencia de seguridad al ejecutarse con batería

Los artículos siguientes también pueden ser útiles en estas situaciones:
- [Configuración de exámenes programados y de actualización](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Administrar actualizaciones de puntos de conexión que están des actualizadas](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Guía de implementación para Antivirus de Microsoft Defender en un entorno de infraestructura de escritorio virtual (VDI)](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>Participar en Microsoft Update en equipos móviles sin conexión WSUS

Puedes usar Microsoft Update para mantener actualizada la inteligencia de seguridad en dispositivos móviles que ejecutan Antivirus de Microsoft Defender cuando no están conectados a la red corporativa o si no tienen una conexión WSUS. 

Esto significa que las actualizaciones de protección se pueden entregar a dispositivos (a través de Microsoft Update) incluso si has establecido WSUS para invalidar Microsoft Update.

Puedes participar en Microsoft Update en el dispositivo móvil de una de las siguientes maneras:

- Cambie la configuración con la directiva de grupo.
- Use un VBScript para crear un script y, a continuación, ejecutarlo en cada equipo de la red.
- Opte manualmente por todos los equipos de la red a través del **menú** Configuración.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Usar la directiva de grupo para participar en Microsoft Update

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.

2. En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

3. Seleccione **Directivas y,** **a continuación, Plantillas administrativas.**

4. Expande el árbol a **Componentes de Windows** Actualizaciones de firma de Antivirus  >  de Microsoft **Defender.**  >  

5. Establezca **Permitir actualizaciones de inteligencia de seguridad de Microsoft Update** en **Habilitado** y, a continuación, seleccione  **Aceptar**.


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Usar un VBScript para participar en Microsoft Update

1. Use las instrucciones del artículo de MSDN [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) para crear vbscript.

2. Ejecute el VBScript que creó en cada equipo de la red.

### <a name="manually-opt-in-to-microsoft-update"></a>Participar manualmente en Microsoft Update

1. Abre **Windows Update** en Update & configuración **de** seguridad en el equipo en el que quieras participar.

2. Seleccione **Opciones** avanzadas.

3. Active la casilla **Deme actualizaciones para otros productos de Microsoft cuando actualice Windows**.

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Impedir actualizaciones de inteligencia de seguridad al ejecutarse con batería

Puede configurar Antivirus de Microsoft Defender para que solo descargue actualizaciones de protección cuando el equipo esté conectado a una fuente de alimentación por cable. 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Usar la directiva de grupo para evitar actualizaciones de inteligencia de seguridad en la batería

1.  En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))elija el objeto de directiva de grupo que desea configurar y ábralo para su edición.

2.  En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**

3.  Seleccione **Directivas y,** **a continuación, Plantillas administrativas.**

4.  Expande el árbol a **Componentes de Windows** Actualizaciones de firma de Antivirus de Microsoft Defender y, a continuación, establece Permitir actualizaciones de inteligencia de seguridad al ejecutar la batería en  >    >   **Deshabilitado.**  A continuación, seleccione **Aceptar**. 

Esta acción impide que las actualizaciones de protección se descarguen cuando el equipo está en batería.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Actualizar y administrar antivirus de Microsoft Defender en Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)