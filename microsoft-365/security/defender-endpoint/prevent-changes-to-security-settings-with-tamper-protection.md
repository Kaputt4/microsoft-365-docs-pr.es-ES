---
title: Configuración de seguridad de la protección con protección contra alteraciones
ms.reviewer: pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Usa la protección contra manipulaciones para evitar que las aplicaciones malintencionadas cambien la configuración de seguridad importante.
keywords: malware, defender, antivirus, protección contra manipulaciones
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 6a9903a0867a6d1800fef052bcd3cfe61eeba157
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555973"
---
# <a name="protect-security-settings-with-tamper-protection"></a>Configuración de seguridad de la protección con protección contra alteraciones

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

La protección contra alteraciones está disponible para dispositivos que ejecutan una de las siguientes versiones de Windows:

- Windows 10
- Windows 11
- Windows Server 2019
- Windows Server 2022
- Windows Servidor, versión 1803 o posterior
- Windows Server 2016
- Windows Server 2012 R2


## <a name="overview"></a>Información general

Durante algunos tipos de ataques cibernéticos, los actores malos intentan deshabilitar las características de seguridad, como la protección antivirus, en las máquinas. A los actores malintencionados les gusta deshabilitar las características de seguridad para obtener un acceso más fácil a los datos, para instalar malware o para aprovechar sus datos, identidades y dispositivos. La protección contra alteraciones ayuda a evitar que se produzcan este tipo de cosas.

Con la protección contra manipulaciones, las aplicaciones malintencionadas no pueden realizar acciones como:

- Deshabilitar la protección contra virus y amenazas
- Deshabilitar la protección en tiempo real
- Desactivar la supervisión del comportamiento
- Deshabilitar antivirus (como IOfficeAntivirus (IOAV))
- Deshabilitar la protección entregada en la nube
- Eliminación de actualizaciones de inteligencia de seguridad

### <a name="how-it-works"></a>Funcionamiento

La protección contra alteraciones bloquea Antivirus de Microsoft Defender sus valores seguros y predeterminados e impide que la configuración de seguridad se cambie a través de aplicaciones y métodos como:

- Configuración de la configuración en el Editor del Registro en el Windows dispositivo
- Cambiar la configuración mediante cmdlets de PowerShell
- Edición o eliminación de la configuración de seguridad a través de la directiva de grupo

La protección contra alteraciones no le impide ver la configuración de seguridad. Además, la protección contra alteraciones no afecta a la forma en que las aplicaciones antivirus que no son de Microsoft se registran con la Seguridad de Windows aplicación. Si su organización usa Windows 10 Enterprise E5, los usuarios individuales no pueden cambiar la configuración de protección contra alteraciones; en esos casos, la protección contra alteraciones la administra el equipo de seguridad.

### <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

<br>

****

|Para realizar esta tarea...|Vea esta sección...|
|---|---|
|Administrar la protección contra alteraciones en el espacio empresarial <p> Usar el portal Microsoft 365 Defender para activar o desactivar la protección contra alteraciones|[Administrar la protección contra alteraciones de la organización mediante el Microsoft 365 Defender](#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal)|
|Ajustar la configuración de protección contra alteraciones en la organización <p> Usa Intune (Microsoft Endpoint Manager) para activar o desactivar la protección contra alteraciones. Puede configurar la protección contra manipulaciones para algunos o todos los usuarios con este método.|[Administrar la protección contra alteraciones de la organización con Intune](#manage-tamper-protection-for-your-organization-using-intune)|
|Activar o desactivar la protección contra alteraciones para su organización con Configuration Manager|[Administrar la protección contra alteraciones de la organización mediante la conexión de inquilinos con Configuration Manager, versión 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)|
|Activar (o desactivar) la protección contra manipulaciones para un dispositivo individual|[Administrar la protección contra alteraciones en un dispositivo individual](#manage-tamper-protection-on-an-individual-device)|
|Ver detalles sobre intentos de manipulación en dispositivos|[Ver información sobre intentos de manipulación](#view-information-about-tampering-attempts)|
|Revisar las recomendaciones de seguridad|[Revisar recomendaciones de seguridad](#review-your-security-recommendations)|
|Revisar la lista de preguntas más frecuentes (preguntas frecuentes)|[Examinar las preguntas frecuentes](#view-information-about-tampering-attempts)|
|

Según el método o la herramienta de administración que use para habilitar la protección contra manipulaciones, puede haber una dependencia de la protección entregada en la nube.

En la tabla siguiente se proporcionan detalles sobre los métodos, herramientas y dependencias.

<br>

****

|Cómo se habilita la protección contra manipulaciones|Dependencia de la protección entregada en la nube (MAPS)|
|---|---|
|Microsoft Intune|No|
|Microsoft Endpoint Configuration Manager + agregado de inquilino|No|
|Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) )|Sí|
|

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal"></a>Administrar la protección contra alteraciones de la organización mediante el portal de Microsoft 365 Defender datos

La protección contra alteraciones puede estar activada o desactivada para el inquilino mediante el portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ). Estos son algunos puntos a tener en cuenta:

- Actualmente, la opción para administrar la protección contra alteraciones en el portal de Microsoft 365 Defender está activa de forma predeterminada para las nuevas implementaciones. Para las implementaciones existentes, la protección contra alteraciones está disponible de forma opt-in. Para participar, en el portal de Microsoft 365 Defender, **elija** Configuración características avanzadas de protección \>  \>  \> **contra alteraciones** de puntos de conexión .

- Cuando usa el portal de Microsoft 365 Defender para administrar la protección contra alteraciones, no tiene que usar Intune ni el método de adjuntar inquilino.

- Al administrar la protección contra alteraciones en el Centro de seguridad de Microsoft Defender, la configuración se aplica en todo el espacio empresarial, lo que afecta a todos los dispositivos que ejecutan Windows 10, Windows 11, Windows Server 2012 R2, Windows Server 2016, Windows Server 2019 o Windows Server 2022. Para ajustar la protección contra manipulaciones (por ejemplo, tener la protección contra manipulaciones en algunos dispositivos, pero desactivada para otros), use [Intune](#manage-tamper-protection-for-your-organization-using-intune) o Configuration Manager con el inquilino [adjuntado](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).

- Si tienes un entorno híbrido, las opciones de protección contra alteraciones configuradas en Intune tienen prioridad sobre las opciones configuradas en el portal Microsoft 365 Defender usuario.

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-365-defender-portal"></a>Requisitos para administrar la protección contra alteraciones en el portal de Microsoft 365 Defender datos

- Debe tener [asignados los permisos adecuados,](/microsoft-365/security/defender-endpoint/assign-portal-access) como el administrador global, el administrador de seguridad o las operaciones de seguridad.

- Los dispositivos Windows deben ejecutar una de las siguientes versiones de Windows:
  - Windows 10
  - Windows 11
  - [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
  - Windows Server 2022
  - Windows Servidor, versión [1803](/windows/release-health/status-windows-10-1803) o posterior
  - [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
  - [Windows Server 2012 R2](/win32/srvnodes/what-s-new-for-windows-server-2012-r2)

Para obtener más información acerca de las [versiones, vea Windows 10 información de la versión](/windows/release-health/release-information).


- Los dispositivos deben [incorporarse a Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/onboarding).

- Los dispositivos deben usar la versión 4.18.2010.7 (o superior) de la plataforma antimalware y el motor antimalware versión 1.1.17600.5 (o superior). ([Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).)

- [La protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) debe estar activada.

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-365-defender-portal"></a>Activar (o desactivar) la protección contra alteraciones en el portal de Microsoft 365 Defender datos

:::image type="content" source="../../media/mde-turn-tamperprotectionon.png" alt-text="Active la protección contra alteraciones en el Microsoft 365 Defender de seguridad.":::

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión.

2. Elija **Configuración** \> **endpoints**.

3. Vaya a **Características** \> **avanzadas generales** y, a continuación, active la protección contra manipulaciones.

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a>Administrar la protección contra alteraciones de la organización con Intune

Si forma parte del equipo de seguridad de su organización y la suscripción incluye [Intune,](/intune/fundamentals/what-is-intune)puede activar (o desactivar) la protección contra manipulaciones de su organización en el Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ). Usa Intune cuando quieras ajustar la configuración de protección contra alteraciones. Por ejemplo, si quieres habilitar la protección contra manipulaciones en algunos dispositivos, pero no todos, usa Intune.

### <a name="requirements-for-managing-tamper-protection-in-intune"></a>Requisitos para administrar la protección contra alteraciones en Intune

- Debe tener [asignados los permisos adecuados,](/microsoft-365/security/defender-endpoint/assign-portal-access) como el administrador global, el administrador de seguridad o las operaciones de seguridad.

- Su organización usa [Intune para administrar dispositivos](/intune/fundamentals/what-is-device-management). ([Las licencias de Intune](/intune/fundamentals/licenses) son necesarias; Intune se incluye en Microsoft 365 E5).)

- Los dispositivos Windows deben ejecutarse Windows 11 o Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) o posterior. (Para obtener más información acerca de las versiones, [vea Windows 10 información de la versión](/windows/release-health/release-information)).)

- Debe usar la seguridad Windows con inteligencia de seguridad [actualizada](https://www.microsoft.com/wdsi/definitions) a la versión 1.287.60.0 (o superior).

- Los dispositivos deben usar la versión 4.18.1906.3 (o superior) de la plataforma antimalware y el motor antimalware versión 1.1.15500.X (o posterior). ([Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).)

### <a name="turn-tamper-protection-on-or-off-in-intune"></a>Activar o desactivar la protección contra manipulaciones en Intune

![Activa la protección contra alteraciones con Intune.](images/turnontamperprotect-MEM.png)

1. Vaya al Centro [Microsoft Endpoint Manager administración e](https://endpoint.microsoft.com) inicie sesión.

2. Seleccione  \> **Perfiles de configuración de dispositivos**.

3. Cree un perfil que incluya la siguiente configuración:

    - **Plataforma: Windows 10 y versiones posteriores**
    - **Tipo de perfil: Protección de puntos de conexión**
    - **Categoría: Microsoft 365 Defender**
    - **Protección contra alteraciones: habilitada**

4. Asigne el perfil a uno o varios grupos.

### <a name="are-you-using-windows-server-2016-or-windows-version-1709-1803-or-1809"></a>¿Está usando Windows Server 2016 o Windows versión 1709, 1803 o 1809?

Si usas Windows Server 2016, Windows 10 versión 1709, 1803 o [1809,](/windows/release-health/status-windows-10-1809-and-windows-server-2019)no verás  protección contra alteraciones en la Seguridad de Windows aplicación. En su lugar, puede usar PowerShell para determinar si la protección contra manipulaciones está habilitada.

Al Windows Server 2016, la Configuración no reflejará con precisión el estado de la protección en tiempo real cuando se habilita la protección contra alteraciones.

#### <a name="use-powershell-to-determine-whether-tamper-protection-and-real-time-protection-are-turned-on"></a>Usar PowerShell para determinar si la protección contra manipulaciones y la protección en tiempo real están activadas

1. Abre la Windows PowerShell aplicación.

2. Use el cmdlet [De PowerShell Get-MpComputerStatus.](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps)

3. En la lista de resultados, busque `IsTamperProtected` o `RealTimeProtectionEnabled` . (Un valor de *true significa* que la protección contra manipulaciones está habilitada).

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>Administrar la protección contra alteraciones de su organización con Configuration Manager, versión 2006

Si usa la versión [2006](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)de Configuration Manager, puede administrar la configuración de protección contra alteraciones en Windows 10, Windows 11, Windows Server 2012 R2, Windows Server 2016, Windows Server 2019 y Windows Server 2022 mediante un método denominado *tenant attach*. La conexión de inquilino permite sincronizar los dispositivos de Configuration Manager locales en el Centro de administración de Microsoft Endpoint Manager y, a continuación, entregar directivas de configuración de seguridad de puntos de conexión a colecciones locales & dispositivos.

> [!NOTE]
> El procedimiento se puede usar para extender la protección contra manipulaciones a dispositivos que ejecutan Windows 10, Windows 11, Windows Server 2019 y Windows Server 2022. Asegúrese de revisar los requisitos previos y otra información en los recursos mencionados en este procedimiento.

1. Configurar la conexión de inquilino. Para obtener más información, [consulte Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).

2. En el [centro Microsoft Endpoint Manager administración,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a Endpoint **security** Antivirus y, a continuación, \> elija + **Crear directiva.**

   - En la **lista** Plataforma, seleccione **Windows 10 y Windows Server (ConfigMgr)** o **Windows 11 y Windows Server (ConfigMgr).**
   - En la **lista Perfil,** **seleccione Seguridad de Windows experiencia (versión preliminar).**

3. Implemente la directiva en la colección de dispositivos.

### <a name="need-help-with-this-method"></a>¿Necesita ayuda con este método?

Vea los siguientes recursos:

- [Configuración para el perfil Seguridad de Windows experiencia en Microsoft Intune](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Blog de Community técnico: Anuncio de protección contra manipulaciones para clientes de conexión de inquilinos de Configuration Manager](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>Administrar la protección contra alteraciones en un dispositivo individual

> [!NOTE]
> La protección contra alteraciones bloquea los intentos de modificar Antivirus de Microsoft Defender configuración a través del Registro.
>
> Para garantizar que la protección contra alteraciones no interfiera con los productos de seguridad que  no son de Microsoft o los scripts de instalación empresarial que modifican esta configuración, vaya **a Seguridad de Windows** y actualice la inteligencia de seguridad a la versión 1.287.60.0 o posterior. (Vea [Actualizaciones de inteligencia de seguridad](https://www.microsoft.com/wdsi/definitions).)
>
> Una vez que haya realizado esta actualización, la protección contra alteraciones continúa protegiendo la configuración del Registro y los registros intentan modificarlos sin devolver errores.

Si eres usuario principal o no estás sujeto a la configuración administrada por un equipo de seguridad, puedes usar la aplicación Seguridad de Windows para administrar la protección contra alteraciones. Debes tener permisos de administrador adecuados en el dispositivo para cambiar la configuración de seguridad, como la protección contra alteraciones.

Esto es lo que ves en la Seguridad de Windows aplicación:

![Protección contra alteraciones activada en Windows 10 Home.](images/tamperprotectionturnedon.png)

1. Seleccione **Inicio** y empiece a escribir *Seguridad*. En los resultados de búsqueda, **seleccione Seguridad de Windows**.

2. Seleccione **Protección contra & virus y &** de protección contra \> **amenazas**.

3. Establezca **Protección contra alteraciones** **en On** o **Off**.

## <a name="view-information-about-tampering-attempts"></a>Ver información sobre intentos de manipulación

Los intentos de manipulación suelen indicar ataques cibernéticos más grandes. Los actores no detectados intentan cambiar la configuración de seguridad como una forma de persistir y no detectarse. Si forma parte del equipo de seguridad de su organización, puede ver información sobre estos intentos y, a continuación, realizar las acciones adecuadas para mitigar las amenazas.

Cuando se detecta un intento de manipulación, se genera una alerta en [el portal de Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/portal-overview) ( [https://security.microsoft.com](https://security.microsoft.com) ).

![Microsoft 365 Defender.](images/tamperattemptalert.png)

Con [detección y respuesta de puntos de conexión](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) y [capacidades avanzadas](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) de búsqueda en Microsoft Defender para endpoint, el equipo de operaciones de seguridad puede investigar y solucionar estos intentos.

## <a name="review-your-security-recommendations"></a>Revisar las recomendaciones de seguridad

La protección contra alteraciones se integra [con las & de administración de vulnerabilidades.](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) [Las recomendaciones de seguridad](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) incluyen asegurarse de que la protección contra manipulaciones está activada. Por ejemplo, puede buscar en *tamper*. En los resultados, puedes seleccionar **Activar protección contra** manipulaciones para obtener más información y activarla.

![Activar la protección contra manipulaciones.](images/tamperprotectsecurityrecos.png)

Para obtener más información sobre la administración & vulnerabilidad de amenazas, consulte [Threat & Vulnerability Management en Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="on-which-versions-of-windows-can-i-configure-tamper-protection"></a>¿En qué versiones de Windows puedo configurar la protección contra alteraciones?

Windows 10 Sistema operativo [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)o posterior junto con [Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint).

Windows 11

Si usa Configuration Manager, versión 2006, con agregado de inquilino, la protección contra alteraciones se puede extender a Windows Server 2012 R2, Windows Server 2016, Windows Server 2019 y Windows Server 2022. Vea [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview).](/mem/configmgr/tenant-attach/deploy-antivirus-policy)

### <a name="will-tamper-protection-affect-non-microsoft-antivirus-registration-in-the-windows-security-app"></a>¿Afectará la protección contra alteraciones al registro de antivirus que no es de Microsoft en la Seguridad de Windows aplicación?

No. Las ofertas de antivirus que no son de Microsoft se seguirán registrando con la Seguridad de Windows aplicación.

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>¿Qué sucede si Antivirus de Microsoft Defender está activo en un dispositivo?

Los dispositivos que se incorpore a Microsoft Defender para Endpoint tendrán Antivirus de Microsoft Defender en modo pasivo. En estos casos, la protección contra manipulaciones seguirá protegiendo el servicio y sus características.

### <a name="how-do-i-turn-tamper-protection-on-or-off"></a>¿Cómo se activa o desactiva la protección contra manipulaciones?

Si eres usuario principal, consulta [Administrar la protección contra manipulaciones en un dispositivo individual.](#manage-tamper-protection-on-an-individual-device)

Si es una organización que usa [Microsoft Defender para](/microsoft-365/security/defender-endpoint)endpoint, debería poder administrar la protección contra alteraciones en Intune de forma similar a la forma en que administra otras características de protección de puntos de conexión. Vea las siguientes secciones de este artículo:

- [Administrar la protección contra alteraciones con Intune](#manage-tamper-protection-for-your-organization-using-intune)
- [Administrar la protección contra alteraciones con Configuration Manager, versión 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Administrar la protección contra alteraciones mediante el portal Microsoft 365 Defender datos](#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal)

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-with-group-policy"></a>¿Cómo afecta la configuración de la protección contra alteraciones en Intune cómo Antivirus de Microsoft Defender con la directiva de grupo?

La directiva de grupo no se aplica a la protección contra manipulaciones. Los cambios realizados en Antivirus de Microsoft Defender se omiten cuando la protección contra alteraciones está en.

### <a name="if-we-use-microsoft-intune-to-configure-tamper-protection-does-it-apply-only-to-the-entire-organization"></a>Si usamos Microsoft Intune para configurar la protección contra manipulaciones, ¿se aplica solo a toda la organización?

Tiene flexibilidad para configurar la protección contra manipulaciones con Intune. Puede dirigirse a toda la organización o seleccionar dispositivos y grupos de usuarios específicos.

### <a name="can-i-configure-tamper-protection-with-microsoft-endpoint-configuration-manager"></a>¿Puedo configurar la protección contra alteraciones con Microsoft Endpoint Configuration Manager?

Si usa la conexión de inquilino, puede usar Microsoft Endpoint Configuration Manager. Vea los siguientes recursos:

- [Administrar la protección contra alteraciones de su organización con Configuration Manager, versión 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Blog de Community técnico: Anuncio de protección contra alteraciones para clientes de inquilinos de Configuration Manager](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Tengo la inscripción Windows E3. ¿Puedo usar la configuración de la protección contra alteraciones en Intune?

Actualmente, la configuración de la protección contra alteraciones en Intune solo está disponible para los clientes que tienen [Microsoft Defender para Endpoint](/microsoft-365/security/defender-endpoint).

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>¿Qué sucede si intento cambiar la configuración de Microsoft Defender para puntos de conexión en Intune, Microsoft Endpoint Configuration Manager y Windows Management Instrumentation cuando la protección contra alteraciones está habilitada en un dispositivo?

No podrá cambiar las características protegidas por la protección contra manipulaciones; dichas solicitudes de cambio se omiten.

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>Soy un cliente de empresa. ¿Pueden los administradores locales cambiar la protección contra alteraciones en sus dispositivos?

No. Los administradores locales no pueden cambiar ni modificar la configuración de protección contra alteraciones.

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>¿Qué sucede si mi dispositivo está incorporado con Microsoft Defender para endpoint y, a continuación, pasa a un estado desaborde?

Si un dispositivo está desactivado de Microsoft Defender para endpoint, la protección contra manipulaciones está activada, que es el estado predeterminado para los dispositivos no administrados.

### <a name="if-the-status-of-tamper-protection-changes-are-alerts-shown-in-the-microsoft-365-defender-portal"></a>Si cambia el estado de la protección contra alteraciones, ¿se muestran alertas en el portal Microsoft 365 Defender usuario?

Sí. La alerta se muestra en [https://security.microsoft.com](https://security.microsoft.com) **Alertas**.

El equipo de operaciones de seguridad también puede usar consultas de búsqueda, como el ejemplo siguiente:

`AlertInfo|where Title == "Tamper Protection bypass"`

[Ver información sobre intentos de manipulación](#view-information-about-tampering-attempts).

## <a name="see-also"></a>Vea también

[Ayudar a proteger Windows equipos con Endpoint Protection para Microsoft Intune](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[Obtener información general de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint)

[Mejor juntos: Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión](why-use-microsoft-defender-antivirus.md)
