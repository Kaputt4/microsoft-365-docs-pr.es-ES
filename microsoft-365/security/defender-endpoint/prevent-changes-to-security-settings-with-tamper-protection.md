---
title: Configuración de seguridad de la protección con protección contra alteraciones
ms.reviewer: mattcall, pahuijbr, hayhov, oogunrinde
manager: dansimp
description: Use la protección contra alteraciones para evitar que las aplicaciones malintencionadas cambien la configuración de seguridad importante.
keywords: malware, defender, antivirus, protección contra alteraciones
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom:
- nextgen
- admindeeplinkDEFENDER
ms.technology: mde
ms.date: 04/07/2022
ms.collection:
- M365-security-compliance
- m365initiative-defender-endpoint
ms.openlocfilehash: ccf72b1f7e5625f3b3b9599a50d734a7316b8659
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780267"
---
# <a name="protect-security-settings-with-tamper-protection"></a>Configuración de seguridad de la protección con protección contra alteraciones

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

La protección contra alteraciones está disponible para los dispositivos que ejecutan una de las siguientes versiones de Windows:

- Windows 11
- Windows 11 Empresas sesiones múltiples 
- Windows 10
- Sesión múltiple de Windows 10 Enterprise
- Windows Server 2022
- Windows Server 2019
- Windows Server, versión 1803 o posterior
- Windows Server 2016
- Windows Server 2012 R2

> [!NOTE]
> La protección contra alteraciones en Windows Server 2012 R2 está disponible para los dispositivos incorporados mediante el paquete de solución unificado moderno. Para obtener más información, consulte [Incorporación de servidores Windows al servicio Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/configure-server-endpoints).


## <a name="overview"></a>Información general

Durante algunos tipos de ciberataques, los actores malintencionados intentan deshabilitar las características de seguridad, como la protección antivirus, en las máquinas. A los actores incorrectos les gusta deshabilitar las características de seguridad para obtener un acceso más fácil a los datos, para instalar malware o para aprovechar los datos, la identidad y los dispositivos. La protección contra alteraciones ayuda a evitar que se produzcan este tipo de cosas. Con la protección contra alteraciones, se impide que las aplicaciones malintencionadas realicen acciones como:

- Deshabilitación de la protección contra virus y amenazas
- Deshabilitación de la protección en tiempo real
- Desactivar la supervisión del comportamiento
- Deshabilitación de antivirus (como IOfficeAntivirus (IOAV))
- Deshabilitación de la protección entregada en la nube
- Eliminación de actualizaciones de inteligencia de seguridad
- Deshabilitación de acciones automáticas en amenazas detectadas

### <a name="how-it-works"></a>Cómo funciona

La protección contra alteraciones básicamente bloquea Antivirus de Microsoft Defender a sus valores seguros y predeterminados e impide que la configuración de seguridad se cambie a través de aplicaciones y métodos como:

- Configuración de opciones en el Editor del Registro en el dispositivo Windows
- Cambio de la configuración mediante cmdlets de PowerShell
- Edición o eliminación de la configuración de seguridad a través de directiva de grupo

La protección contra alteraciones no impide que vea la configuración de seguridad. Además, la protección contra alteraciones no afecta al modo en que las aplicaciones antivirus que no son de Microsoft se registran con la aplicación Seguridad de Windows. Si su organización usa Windows 10 Enterprise E5, los usuarios individuales no pueden cambiar la configuración de protección contra alteraciones; en esos casos, el equipo de seguridad administra la protección contra alteraciones.

### <a name="what-do-you-want-to-do"></a>¿Qué quiere hacer?

|Para realizar esta tarea...|Consulte esta sección...|
|---|---|
|Administración de la protección contra alteraciones en el inquilino <p> Uso del portal de Microsoft 365 Defender para activar o desactivar la protección contra alteraciones|[Administrar la protección contra alteraciones de la organización mediante el Microsoft 365 Defender](#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal)|
|Ajuste de la configuración de protección contra alteraciones en la organización <p> Use Intune (Microsoft Endpoint Manager) para activar o desactivar la protección contra alteraciones. Puede configurar la protección contra alteraciones para algunos o todos los usuarios con este método.|[Administración de la protección contra alteraciones de la organización mediante Microsoft Endpoint Manager](#manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager)|
|Activar (o desactivar) la protección contra alteraciones para la organización con Configuration Manager|[Administración de la protección contra alteraciones de la organización mediante la asociación de inquilinos con Configuration Manager, versión 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)|
|Activar (o desactivar) la protección contra alteraciones para un dispositivo individual|[Administración de la protección contra alteraciones en un dispositivo individual](#manage-tamper-protection-on-an-individual-device)|
|Ver detalles sobre los intentos de manipulación en dispositivos|[Visualización de información sobre intentos de manipulación](#view-information-about-tampering-attempts)|
|Revisión de las recomendaciones de seguridad|[Revisión de las recomendaciones de seguridad](#review-your-security-recommendations)|
|Revise la lista de preguntas más frecuentes (P+F)|[Examinar las preguntas más frecuentes](#view-information-about-tampering-attempts)|

## <a name="potential-dependency-on-cloud-protection"></a>Posible dependencia de la protección en la nube  
  
En función del método o la herramienta de administración que use para habilitar la protección contra alteraciones, es posible que haya una dependencia de la [protección entregada](cloud-protection-microsoft-defender-antivirus.md) en la nube que también se conoce como protección en la nube o Microsoft Advanced Protection Service (MAPS).

En la tabla siguiente se proporcionan detalles sobre los métodos, las herramientas y las dependencias.

| Cómo está habilitada la protección contra alteraciones | Dependencia de la protección en la nube |
|---|---|
|Microsoft Intune|No|
|Microsoft Endpoint Configuration Manager con asociación de inquilinos|No|
|portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com))|Sí|

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal"></a>Administración de la protección contra alteraciones de la organización mediante el portal de Microsoft 365 Defender

La protección contra alteraciones se puede activar o desactivar para el inquilino mediante el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)). Estos son algunos puntos a tener en cuenta:

- Actualmente, la opción para administrar la protección contra alteraciones en el portal de Microsoft 365 Defender está activada de forma predeterminada para las nuevas implementaciones. En el caso de las implementaciones existentes, la protección contra alteraciones está disponible de forma opcional. Para participar, en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a>, elija **Configuración** \> Características **avanzadas** \> de **puntos de conexión** **Protección contra alteraciones**\>.
- Cuando se usa el portal de Microsoft 365 Defender para administrar la protección contra alteraciones, no es necesario usar Intune ni el método de asociación de inquilinos.
- Al administrar la protección contra alteraciones en el portal de Microsoft 365 Defender, la configuración se aplica en todo el inquilino, lo que afecta a todos los dispositivos que ejecutan Windows 10, Windows 10 Enterprise sesiones múltiples, Windows 11, Windows 11 Empresas  sesiones múltiples, Windows Server 2012 R2, Windows Server 2016, Windows Server 2019 o Windows Server 2022. Para ajustar la protección contra alteraciones (por ejemplo, tener la protección contra alteraciones activada para algunos dispositivos pero desactivada para otros), use [Microsoft Endpoint Manager](#manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager) o [Configuration Manager con asociación de inquilinos](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).
- Si tiene un entorno híbrido, los valores de protección contra alteraciones configurados en Intune tienen prioridad sobre los valores configurados en el portal de Microsoft 365 Defender.

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-365-defender-portal"></a>Requisitos para administrar la protección contra alteraciones en el portal de Microsoft 365 Defender

- Debe tener asignados [los permisos](/microsoft-365/security/defender-endpoint/assign-portal-access) adecuados, como el administrador global, el administrador de seguridad o las operaciones de seguridad.

- Los dispositivos Windows deben ejecutar una de las siguientes versiones de Windows:
  
  - Windows 11
  - Windows 11 Empresas sesiones múltiples 
  - Windows 10
  - Sesión múltiple de Windows 10 Enterprise
  - Windows Server 2022
  - Windows Server 2019
  - Windows Server, versión 1803 o posterior
  - Windows Server 2016
  - Windows Server 2012 R2

Para obtener más información sobre las versiones, consulte [Windows 10 información de la versión](/windows/release-health/release-information).

- Los dispositivos deben [incorporarse a Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/onboarding).
- Los dispositivos deben usar la versión `4.18.2010.7` de la plataforma antimalware (o superior) y la versión `1.1.17600.5` del motor antimalware (o superior). ([Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)).
- [La protección entregada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) debe estar activada.

> [!NOTE]
> Cuando se habilita la protección contra alteraciones a través del portal de Microsoft 365 Defender, se requiere la protección entregada en la nube, de modo que se pueda controlar el estado habilitado de la protección contra alteraciones.  
> A partir de la actualización de noviembre de 2021 (versión `4.18.2111.5`de la plataforma), si la protección proporcionada en la nube no está activada para un dispositivo y la protección contra alteraciones está activada en el portal de Microsoft 365 Defender, la protección entregada en la nube se activará automáticamente para ese dispositivo junto con la protección contra alteraciones.   

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-365-defender-portal"></a>Activar o desactivar la protección contra alteraciones en el portal de Microsoft 365 Defender

:::image type="content" source="../../media/mde-turn-tamperprotectionon.png" alt-text="Activar la protección contra alteraciones en el portal de Microsoft 365 Defender" lightbox="../../media/mde-turn-tamperprotectionon.png":::

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Elija **Configuración** \> **puntos de conexión**.

3. Vaya a **Características avanzadas** **generales** \> y active la protección contra alteraciones.

## <a name="manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager"></a>Administración de la protección contra alteraciones de la organización mediante Microsoft Endpoint Manager

Si su organización usa Microsoft Endpoint Manager (MEM), puede activar (o desactivar) la protección contra alteraciones para su organización en el centro de administración de Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)). Use Intune cuando desee ajustar la configuración de protección contra alteraciones. Por ejemplo, si desea habilitar la protección contra alteraciones en algunos dispositivos, pero no en todos, use Intune.

### <a name="requirements-for-managing-tamper-protection-in-endpoint-manager"></a>Requisitos para administrar la protección contra alteraciones en Endpoint Manager

- Los dispositivos deben [incorporarse a Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/onboarding).
- Debe tener asignados [los permisos](/microsoft-365/security/defender-endpoint/assign-portal-access) adecuados, como el administrador global, el administrador de seguridad o las operaciones de seguridad.
- Su organización usa [Microsoft Endpoint Manager para administrar dispositivos](/mem/endpoint-manager-getting-started). (se requieren licencias de Microsoft Endpoint Manager (MEM); MEM se incluye en Microsoft 365 E3/E5, Enterprise Mobility + Security E3/E5, Microsoft 365 Empresa Premium, Microsoft 365 F1/F3, Microsoft 365 Government G3/G5 , y las licencias educativas correspondientes).
- Los dispositivos Windows deben ejecutar Windows 11 o Windows 10 [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) o posterior. (Para obtener más información sobre las versiones, consulte [Windows 10 información de la versión](/windows/release-health/release-information)).
- Debe usar Windows seguridad con [inteligencia de seguridad](https://www.microsoft.com/wdsi/definitions) actualizada a la versión 1.287.60.0 (o posterior).
- Los dispositivos deben usar la versión 4.18.1906.3 (o posterior) de la plataforma antimalware y la versión `1.1.15500.X` del motor antimalware (o posterior). ([Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base](manage-updates-baselines-microsoft-defender-antivirus.md)).

### <a name="turn-tamper-protection-on-or-off-in-microsoft-endpoint-manager"></a>Activar (o desactivar) la protección contra alteraciones en Microsoft Endpoint Manager

:::image type="content" source="images/turnontamperprotectinmem.png" alt-text="Activar la protección contra alteraciones con Intune" lightbox="images/turnontamperprotectinmem.png":::

1. En el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Antivirus** de **seguridad** \> de puntos de conexión y, a continuación, elija **+ Crear directiva**.

   - En la lista **Plataforma**, seleccione **Windows 10 y versiones posteriores**.
   - En la lista **Perfil**, seleccione **Seguridad de Windows experiencia**.

2. Cree un perfil que incluya la siguiente configuración:

    - **Habilitar la protección contra alteraciones para evitar que Microsoft Defender se deshabilite: Habilitar**

3. Asigne el perfil a uno o varios grupos.
 
### <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>Administración de la protección contra alteraciones de la organización con Configuration Manager, versión 2006

Si usa la [versión 2006 de Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), puede administrar la configuración de protección contra alteraciones en Windows 10, Windows 10 Enterprise sesiones múltiples, Windows 11, Windows 11 Empresas sesiones múltiples, Windows Server 2012 R2, Windows Server 2016, Windows Server 2019 y Windows Server 2022 mediante un método denominado *asociación de inquilinos*. La asociación de inquilinos le permite sincronizar los dispositivos de Configuration Manager solo locales en el centro de administración de Microsoft Endpoint Manager y, a continuación, entregar directivas de configuración de seguridad de punto de conexión a colecciones locales & dispositivos.

> [!NOTE]
> El procedimiento se puede usar para ampliar la protección contra alteraciones a los dispositivos que ejecutan Windows 10, Windows 10 Enterprise sesiones múltiples, Windows 11, Windows 11 Empresas sesiones múltiples, Windows Server 2019 y Windows Server 2022. Asegúrese de revisar los requisitos previos y otra información de los recursos mencionados en este procedimiento. Para Windows Server 2012 R2 se requiere la [versión 2203 de la](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2203) solución unificada moderna de Configuration Manager.

1. Configurar la asociación de inquilinos. Para obtener más información, consulte [Comenzar: Creación e implementación de directivas de seguridad de puntos de conexión desde el Centro de administración](/mem/configmgr/tenant-attach/endpoint-security-get-started).

2. En el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), vaya a **Antivirus** de **seguridad** \> de puntos de conexión y, a continuación, elija **+ Crear directiva**.

   - En la lista **Plataforma**, seleccione **Windows 10, Windows 11 y Windows Server (ConfigMgr)**.
   - En la lista **Perfil**, seleccione **Seguridad de Windows experiencia (versión preliminar).**

3. Implemente la directiva en la colección de dispositivos.

#### <a name="need-help-with-this-method"></a>¿Necesita ayuda con este método?

Vea los siguientes recursos:

- [Configuración para el perfil de experiencia de Seguridad de Windows en Microsoft Intune](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Blog de tech Community: Anuncio de la protección contra alteraciones para Configuration Manager clientes de asociación de inquilinos](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>Administración de la protección contra alteraciones en un dispositivo individual

> [!NOTE]
> La protección contra alteraciones bloquea los intentos de modificar Antivirus de Microsoft Defender configuración a través del Registro.
>
> Para ayudar a garantizar que la protección contra alteraciones no interfiera con los productos de seguridad que no son de Microsoft ni con scripts de instalación empresarial que modifican esta configuración, vaya a **Seguridad de Windows** y actualice **Security Intelligence** a la versión 1.287.60.0 o posterior. (Consulte [Actualizaciones de inteligencia de seguridad](https://www.microsoft.com/wdsi/definitions)). Una vez realizada esta actualización, la protección contra alteraciones continúa protegiendo la configuración del Registro y los registros intentan modificarlas sin devolver errores.

Si es usuario principal o no está sujeto a la configuración administrada por un equipo de seguridad, puede usar la aplicación Seguridad de Windows para administrar la protección contra alteraciones. Debe tener los permisos de administrador adecuados en el dispositivo para cambiar la configuración de seguridad, como la protección contra alteraciones.

Esto es lo que se ve en la aplicación de Seguridad de Windows:

:::image type="content" source="images/tamperprotectionturnedon.png" alt-text="Activar la protección contra alteraciones en Windows 10 Home" lightbox="images/tamperprotectionturnedon.png":::

1. Seleccione **Inicio** y empiece a escribir *Seguridad*. En los resultados de la búsqueda, seleccione **Seguridad de Windows**.

2. Seleccione **Virus & threat protection** \> **Virus & threat protection settings (Virus & configuración de protección contra amenazas**).

3. Establezca **Protección contra alteraciones** **en Activado** o **Desactivado**.

## <a name="are-you-using-windows-server-2012-r2-2016-or-windows-version-1709-1803-or-1809"></a>¿Usa Windows Server 2012 R2, 2016 o Windows versión 1709, 1803 o 1809?

Si usa Windows Server 2012 R2 mediante la solución unificada moderna, Windows Server 2016, Windows 10 versión 1709, 1803 o [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), no verá **Protección contra alteraciones** en la aplicación Seguridad de Windows. En su lugar, puede usar PowerShell para determinar si está habilitada la protección contra alteraciones.

En Windows Server 2016, la aplicación Configuración no reflejará con precisión el estado de la protección en tiempo real cuando se habilita la protección contra alteraciones.

#### <a name="use-powershell-to-determine-whether-tamper-protection-and-real-time-protection-are-turned-on"></a>Uso de PowerShell para determinar si la protección contra alteraciones y la protección en tiempo real están activadas

1. Abra la aplicación Windows PowerShell.

2. Use el cmdlet De PowerShell [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) .

3. En la lista de resultados, busque `IsTamperProtected` o `RealTimeProtectionEnabled`. (Un valor de *true* significa que la protección contra alteraciones está habilitada).

## <a name="view-information-about-tampering-attempts"></a>Visualización de información sobre intentos de manipulación

Los intentos de manipulación suelen indicar ciberataques más grandes. Los actores incorrectos intentan cambiar la configuración de seguridad como una manera de conservar y mantenerse sin ser detectados. Si forma parte del equipo de seguridad de su organización, puede ver información sobre estos intentos y, a continuación, realizar las acciones adecuadas para mitigar las amenazas.

Cuando se detecta un intento de manipulación, se genera una alerta en el [portal de Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/portal-overview) ([https://security.microsoft.com](https://security.microsoft.com)).

:::image type="content" source="images/tamperattemptalert.png" alt-text="El portal de Microsoft 365 Defender" lightbox="images/tamperattemptalert.png":::

Con [detección y respuesta de puntos de conexión](overview-endpoint-detection-response.md) y funcionalidades [avanzadas de búsqueda](advanced-hunting-overview.md) en Microsoft Defender para punto de conexión, el equipo de operaciones de seguridad puede investigar y abordar estos intentos.

## <a name="review-your-security-recommendations"></a>Revisión de las recomendaciones de seguridad

La protección contra alteraciones se integra con las funcionalidades [de administración de vulnerabilidades &](next-gen-threat-and-vuln-mgt.md) amenazas. [Las recomendaciones de seguridad](tvm-security-recommendation.md) incluyen asegurarse de que la protección contra alteraciones está activada. Por ejemplo, puede buscar en *la manipulación*. En los resultados, puede seleccionar **Activar protección contra alteraciones** para obtener más información y activarla.

:::image type="content" source="images/tamperprotectsecurityrecos.png" alt-text="Activación de la protección contra alteraciones en el portal de Centro de seguridad de Microsoft Defender" lightbox="images/tamperprotectsecurityrecos.png":::

Para más información sobre Threat & Vulnerability Management, consulte [Información del panel: Administración de amenazas y vulnerabilidades](tvm-dashboard-insights.md#dashboard-insights---threat-and-vulnerability-management).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="on-which-versions-of-windows-can-i-configure-tamper-protection"></a>¿En qué versiones de Windows puedo configurar la protección contra alteraciones?

- Windows 11
- Windows 11 Empresas sesiones múltiples
- Windows 10 sistema operativo [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) o posterior junto con [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint).
- Sesión múltiple de Windows 10 Enterprise
  
Si usa Configuration Manager, versión 2006, con asociación de inquilinos, la protección contra alteraciones se puede ampliar a Windows Server 2012 R2, Windows Server 2016, Windows Server 2019 y Windows Server 2022. Consulte [Asociación de inquilinos: Creación e implementación de la directiva antivirus de seguridad de puntos de conexión desde el Centro de administración (versión preliminar).](/mem/configmgr/tenant-attach/deploy-antivirus-policy)

### <a name="will-tamper-protection-affect-non-microsoft-antivirus-registration-in-the-windows-security-app"></a>¿Afectará la protección contra alteraciones al registro de antivirus que no sea de Microsoft en la aplicación Seguridad de Windows?

No. Las ofertas de antivirus que no son de Microsoft seguirán registrándose con la aplicación Seguridad de Windows.

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>¿Qué ocurre si Antivirus de Microsoft Defender no está activo en un dispositivo?

Los dispositivos que se incorporan a Microsoft Defender para punto de conexión tendrán Antivirus de Microsoft Defender en ejecución en modo pasivo. En estos casos, la protección contra alteraciones seguirá protegiendo el servicio y sus características.

### <a name="how-do-i-turn-tamper-protection-on-or-off"></a>Cómo activar o desactivar la protección contra alteraciones?

Si es usuario principal, consulte Administración de [la protección contra alteraciones en un dispositivo individual](#manage-tamper-protection-on-an-individual-device).

Si es una organización que usa [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint), debería poder administrar la protección contra alteraciones en Intune similar a cómo administra otras características de Endpoint Protection. Consulte las secciones siguientes de este artículo:

- [Administración de la protección contra alteraciones mediante Microsoft Endpoint Manager](#manage-tamper-protection-for-your-organization-using-microsoft-endpoint-manager)
- [Administración de la protección contra alteraciones mediante el portal de Microsoft 365 Defender](#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal)

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-with-group-policy"></a>¿Cómo afecta la configuración de la protección contra alteraciones en Intune cómo administro Antivirus de Microsoft Defender con directiva de grupo?

La directiva de grupo no se aplica a la protección contra alteraciones. Los cambios realizados en Antivirus de Microsoft Defender configuración se omiten cuando la protección contra alteraciones está activada.

### <a name="if-we-use-microsoft-intune-to-configure-tamper-protection-does-it-apply-only-to-the-entire-organization"></a>Si usamos Microsoft Intune para configurar la protección contra alteraciones, ¿se aplica solo a toda la organización?

Tiene flexibilidad para configurar la protección contra alteraciones con Intune. Puede dirigirse a toda la organización o seleccionar dispositivos y grupos de usuarios específicos.

### <a name="can-i-configure-tamper-protection-with-microsoft-endpoint-configuration-manager"></a>¿Puedo configurar La protección contra alteraciones con Microsoft Endpoint Configuration Manager?

Si usa la asociación de inquilinos, puede usar Microsoft Endpoint Configuration Manager. Vea los siguientes recursos:

- [Administración de la protección contra alteraciones de la organización con Configuration Manager, versión 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Blog de tech Community: Anuncio de la protección contra alteraciones para Configuration Manager clientes de asociación de inquilinos](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Tengo la inscripción Windows E3. ¿Puedo usar la configuración de la protección contra alteraciones en Intune?

Actualmente, la configuración de la protección contra alteraciones en Intune solo está disponible para los clientes que tienen [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint).

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>¿Qué ocurre si intento cambiar la configuración de Microsoft Defender para punto de conexión en Intune, Microsoft Endpoint Configuration Manager e instrumentación de administración de Windows cuando la protección contra alteraciones está habilitada en un dispositivo?

No podrá cambiar las características protegidas por la protección contra alteraciones; estas solicitudes de cambio se omiten.

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>Soy un cliente empresarial. ¿Pueden los administradores locales cambiar la protección contra alteraciones en sus dispositivos?

No. Los administradores locales no pueden cambiar ni modificar la configuración de protección contra alteraciones.

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>¿Qué ocurre si mi dispositivo se incorpora con Microsoft Defender para punto de conexión y, a continuación, entra en un estado sin abordar?

Si un dispositivo está desconectado de Microsoft Defender para punto de conexión, se activa la protección contra alteraciones, que es el estado predeterminado para los dispositivos no administrados.

### <a name="if-the-status-of-tamper-protection-changes-are-alerts-shown-in-the-microsoft-365-defender-portal"></a>Si cambia el estado de la protección contra alteraciones, ¿se muestran alertas en el portal de Microsoft 365 Defender?

Sí. La alerta se muestra en [https://security.microsoft.com](https://security.microsoft.com) **Alertas**.

El equipo de operaciones de seguridad también puede usar consultas de búsqueda, como el ejemplo siguiente:

`AlertInfo|where Title == "Tamper Protection bypass"`

[Ver información sobre los intentos de manipulación](#view-information-about-tampering-attempts).

## <a name="see-also"></a>Vea también

- [Ayuda a proteger equipos Windows con Endpoint Protection para Microsoft Intune](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Obtener información general de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint)
- [Mejor juntos: Antivirus de Microsoft Defender y Microsoft Defender para punto de conexión](why-use-microsoft-defender-antivirus.md)
