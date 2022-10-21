---
title: La protección integrada ayuda a protegerse contra ransomware
description: Obtenga información sobre cómo la protección integrada protege contra ransomware como parte de Microsoft Defender para punto de conexión.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 10/20/2022
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
ms.collection:
- m365-security
- tier2
ms.custom: ''
ms.reviewer: joshbregman
f1.keywords: NOCSH
ms.openlocfilehash: 25074c0540f00d9edf4b508a271e47c3777792e1
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660673"
---
# <a name="built-in-protection-helps-guard-against-ransomware"></a>La protección integrada ayuda a protegerse contra ransomware

[Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md) ayuda a prevenir, detectar, investigar y responder a amenazas avanzadas, como ataques de ransomware. [Las funcionalidades de protección](next-generation-protection.md) y [reducción de superficie expuesta a ataques](overview-attack-surface-reduction.md) de última generación en Defender for Endpoint se diseñaron para detectar amenazas emergentes. Para que la mejor protección contra ransomware y otras ciberamenazas esté en su lugar, ciertas configuraciones deben configurarse. La protección integrada puede ayudar al proporcionarle la configuración predeterminada para una mejor protección.

> [!TIP]
> **¡No tienes que esperar a que te llegue la protección integrada**! Ahora puede proteger los dispositivos de su organización mediante la configuración de estas funcionalidades:
> - [Habilitación de la protección en la nube](why-cloud-protection-should-be-on-mdav.md)
> - [Activar la protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)
> - [Establecer reglas estándar de reducción de superficie expuesta a ataques en modo de bloque](attack-surface-reduction-rules-deployment.md)
> - [Habilitación de la protección de red en modo de bloque](enable-network-protection.md)

## <a name="what-is-built-in-protection-and-how-does-it-work"></a>¿Qué es la protección integrada y cómo funciona?

La protección integrada es un conjunto de configuraciones predeterminadas que se implementan para ayudar a garantizar que los dispositivos están protegidos. Esta configuración predeterminada está diseñada para proteger los dispositivos frente a ransomware y otras amenazas. Inicialmente, la protección integrada incluirá la activación de la [protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md) para el inquilino, con otras opciones predeterminadas próximamente. Para obtener más información, consulte la entrada de blog de Tech Community, [La protección contra alteraciones se activará para todos los clientes empresariales](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/tamper-protection-will-be-turned-on-for-all-enterprise-customers/ba-p/3616478).

| Fase | Qué ocurre |
|:---|:---|
| La protección integrada se está implementando | Los clientes reciben [una notificación](#what-does-the-notification-look-like) de que viene la protección integrada. Si aún no está configurado, se activará la protección contra alteraciones para los clientes que tengan el plan 2 o Microsoft 365 E5 de Defender para punto de conexión. |
| La protección integrada está disponible para el inquilino | Se le [notificará](#what-does-the-notification-look-like) que el inquilino está a punto de recibir protección integrada y cuándo se activará la protección contra alteraciones (si aún no está configurada). |
| Llega la protección integrada | La protección contra alteraciones se activará para el inquilino y se aplicará a los dispositivos Windows de la organización. Puede [optar por no participar](#can-i-opt-out) o [cambiar la configuración de protección integrada](#can-i-change-built-in-protection-settings). |
| Una vez que ha llegado la protección integrada | Cada vez que se incorporen nuevos dispositivos a Defender para punto de conexión, la configuración de protección integrada se aplicará a cualquier nuevo dispositivo que ejecute Windows. Siempre puede [cambiar la configuración de protección integrada](#can-i-change-built-in-protection-settings). |

> [!NOTE]
> La protección integrada establece los valores predeterminados para los dispositivos Windows. Si cambia la configuración de seguridad del punto de conexión, como a través de líneas base o directivas en [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), dicha configuración invalida la configuración de protección integrada.  

## <a name="what-does-the-notification-look-like"></a>¿Qué aspecto tiene la notificación?

Puede esperar recibir dos tipos de notificaciones:

- Una publicación del centro de mensajes que indica que la protección integrada estará disponible próximamente; Y 
- Banner en el portal de Microsoft 365 Defender similar a la siguiente imagen:

   :::image type="content" source="media/bip-notification-m365defender.png" alt-text="Captura de pantalla que muestra el resaltado de banner amarillo integrado en la protección en Microsoft 365 Defender portal.":::

La notificación le indicará cuándo viene la protección integrada y cuándo se activará la protección contra alteraciones (si aún no está configurada) para el inquilino.

## <a name="can-i-opt-out"></a>¿Puedo optar por no participar?

Puede optar por no participar en la protección integrada especificando su propia configuración de seguridad. Por ejemplo, si prefiere no tener activada la protección contra alteraciones automáticamente para el inquilino, puede optar por no participar explícitamente.

> [!NOTE]
> **No se recomienda desactivar la protección contra alteraciones**. La protección contra alteraciones le proporciona una mejor protección contra ransomware.
> Debe ser administrador global o administrador de seguridad para realizar el procedimiento siguiente.

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Vaya a **Configuración** > **Puntos de conexión****Características avanzadas** > .

3. Establezca **Protección contra alteraciones** **en Activado** (si aún no está activado) y, a continuación, seleccione **Guardar preferencias**. *No salgas de esta página todavía*.

4. Establezca **Protección contra alteraciones** en **Desactivado** y, a continuación, seleccione **Guardar preferencias**.

## <a name="can-i-change-built-in-protection-settings"></a>¿Puedo cambiar la configuración de protección integrada?

La protección integrada es un conjunto de configuraciones predeterminadas. No es necesario mantener esta configuración predeterminada en su lugar. Siempre puede cambiar la configuración para satisfacer sus necesidades empresariales. En la tabla siguiente se enumeran las tareas que puede realizar el equipo de seguridad, junto con vínculos para obtener más información. 

| Tarea | Descripción |
|:---|:---|
| Determinación de si la protección contra alteraciones está activada | 1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.<br/>2. Vaya a **Configuración** > **Puntos de conexión** Características  > **avanzadas****Protección contra alteraciones** > .  |
| Administración de inquilinos de protección contra alteraciones en todo el inquilino mediante el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) | 1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.<br/>2. Vaya a **Configuración** > **Puntos de conexión****Características avanzadas** > .<br/>3. Establezca **Protección contra alteraciones** **en Activado** (*recomendado*) o **Desactivado**.<br/>4. Seleccione **Guardar preferencias**.<br/><br/>Consulte [Administración de la protección contra alteraciones para su organización mediante Microsoft 365 Defender portal](manage-tamper-protection-microsoft-365-defender.md). |
| Establecer la configuración de protección contra alteraciones para algunos dispositivos, pero no para todos | Use directivas y perfiles de seguridad de punto de conexión que se apliquen a dispositivos específicos. Consulte los siguientes artículos:<br/>- [Administración de la protección contra alteraciones mediante Microsoft Endpoint Manager](manage-tamper-protection-microsoft-endpoint-manager.md)<br/>- [Administración de la protección contra alteraciones mediante la asociación de inquilinos con Configuration Manager, versión 2006](manage-tamper-protection-configuration-manager.md)|
| Activar o desactivar la protección contra alteraciones en un dispositivo individual | 1. En el dispositivo Windows, seleccione **Inicio** y empiece a escribir *Seguridad*.<br/>2. En los resultados de la búsqueda, seleccione **Seguridad de Windows**.<br/>3. Seleccione **Virus & protección contra** >  amenazas **Virus & configuración de protección contra amenazas**.<br/>4. Establezca **Protección contra alteraciones** **en Activado** (*recomendado*) o **Desactivado**. <br/><br/>Si el dispositivo se incorpora a Defender para punto de conexión o el dispositivo se administra en el Centro de administración de Microsoft Endpoint Manager, dicha configuración invalidará la configuración del usuario en el dispositivo individual. <br/><br/>Consulte [Administración de la protección contra alteraciones en un dispositivo individual](manage-tamper-protection-individual-device.md). |
| Deshabilitar temporalmente la protección contra alteraciones en un dispositivo para solucionar problemas | Consulte los siguientes artículos:<br/>- [Introducción al modo de solución de problemas en Microsoft Defender para punto de conexión](enable-troubleshooting-mode.md)<br/>- [Escenarios de modo de solución de problemas en Microsoft Defender para punto de conexión](troubleshooting-mode-scenarios.md) |

## <a name="see-also"></a>Vea también

- [Blog de tech community: la protección contra alteraciones se activará para todos los clientes empresariales](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/tamper-protection-will-be-turned-on-for-all-enterprise-customers/ba-p/3616478)
- [Configuración de seguridad de la protección con protección contra alteraciones](prevent-changes-to-security-settings-with-tamper-protection.md)
- [Administración de seguridad de puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security)
- [Configure icrosoft Defender para punto de conexión en Intune](/mem/intune/protect/advanced-threat-protection-configure)
- [Administración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
- [Respuesta a ataques de ransomware](../defender/playbook-responding-ransomware-m365-defender.md)
