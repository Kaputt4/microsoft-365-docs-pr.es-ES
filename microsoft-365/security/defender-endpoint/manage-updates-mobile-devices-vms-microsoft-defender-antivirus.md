---
title: Definir cómo se actualizan los dispositivos móviles mediante Microsoft Defender Antivirus
description: Administre cómo se deben actualizar los dispositivos móviles, como los portátiles, con Microsoft Defender actualizaciones de protección antivirus.
keywords: updates, protection, schedule updates, battery, mobile device, laptop, notebook, opt-in, microsoft update, wsus, override
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: d85a35740b9ccdc11aedcb46ded9e43971002873
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68620049"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Administrar las actualizaciones de dispositivos móviles y máquinas virtuales

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Es posible que los dispositivos móviles y las máquinas virtuales requieran más configuración para asegurarse de que el rendimiento no se vea afectado por las actualizaciones.

Hay dos configuraciones que son útiles para estos dispositivos:

- Participar en Microsoft Update en equipos móviles sin una conexión WSUS
- Evitar actualizaciones de inteligencia de seguridad al ejecutarse con batería

Los artículos siguientes también pueden ser útiles en estas situaciones:
- [Configuración de exámenes programados y de puesta al día](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Administrar actualizaciones para puntos finales que están desactualizados](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Guía de implementación del Antivirus de Microsoft Defender en un entorno de infraestructura de escritorio virtual](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>Participar en Microsoft Update en equipos móviles sin una conexión WSUS

Puede usar Microsoft Update para mantener actualizada la inteligencia de seguridad en dispositivos móviles que ejecutan Microsoft Defender Antivirus cuando no están conectados a la red corporativa o no tienen una conexión WSUS.

Esto significa que las actualizaciones de protección se pueden entregar a los dispositivos (a través de Microsoft Update), incluso si ha establecido WSUS para invalidar Microsoft Update.

Puede participar en Microsoft Update en el dispositivo móvil de una de las siguientes maneras:

- Cambie la configuración con समूह नीति.
- Use un VBScript para crear un script y, a continuación, ejecútelo en cada equipo de la red.
- Opte manualmente en todos los equipos de la red a través del menú **Configuración** .

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Uso de समूह नीति para participar en Microsoft Update

1. En la máquina de administración de समूह नीति, abra la [consola de administración de समूह नीति](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto समूह नीति que desea configurar y seleccione **Editar**.

2. En el **Editor de administración de समूह नीति** vaya a **Configuración del equipo**.

3. Seleccione **Directivas** y plantillas **administrativas**.

4. Expanda el árbol a **componentes** \> de Windows Microsoft Defender **Novedades de firma** **del antivirus**\>.

5. Establezca **Permitir actualizaciones de inteligencia de seguridad de Microsoft Update** en **Habilitado** y, a continuación, seleccione  **Aceptar**.

### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Uso de VBScript para participar en Microsoft Update

1. Use las instrucciones del artículo de MSDN [Participación en Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) para crear VBScript.

2. Ejecute el VBScript que creó en cada equipo de la red.

### <a name="manually-opt-in-to-microsoft-update"></a>Participar manualmente en Microsoft Update

1. Abra **Windows Update** en **Actualizar &** configuración de seguridad en el equipo en el que desea participar.

2. Seleccione **Opciones avanzadas** .

3. Active la casilla **Deme actualizaciones para otros productos de Microsoft cuando actualice Windows**.

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Evitar actualizaciones de inteligencia de seguridad al ejecutarse con batería

Puede configurar Microsoft Defender Antivirus para que solo descargue las actualizaciones de protección cuando el equipo esté conectado a una fuente de alimentación cableada.

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Uso de समूह नीति para evitar actualizaciones de inteligencia de seguridad en la batería

1. En la máquina de administración de समूह नीति, abra la [consola de administración de समूह नीति](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), elija el objeto de समूह नीति que desea configurar y ábralo para su edición.

2. En el **Editor de administración de समूह नीति** vaya a **Configuración del equipo**.

3. Seleccione **Directivas** y plantillas **administrativas**.

4. Expanda el árbol a **componentes** \> de Windows Microsoft Defender **Novedades de firma** del **antivirus** \> y, a continuación, establezca **Permitir actualizaciones de inteligencia de seguridad al ejecutar la batería en** **Deshabilitado**. A continuación, seleccione **Aceptar**.

Esta acción evita que las actualizaciones de protección se descarguen cuando el equipo esté encendido.

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-articles"></a>Artículos relacionados

- [Para obtener más información, consulte Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar bases de referencia.](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Actualizar y administrar Microsoft Defender Antivirus en Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)