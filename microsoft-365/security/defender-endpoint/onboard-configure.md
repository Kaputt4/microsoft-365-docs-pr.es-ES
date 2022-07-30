---
title: Incorporar dispositivos y configurar las funcionalidades de Microsoft Defender para punto de conexión
description: Incorpore Windows 10 dispositivos, servidores, dispositivos que no sean de Windows y aprenda a ejecutar una prueba de detección.
keywords: onboarding, Microsoft Defender para punto de conexión onboarding, sccm, group policy, mdm, local script, detection test
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f52dd982c9a418af9184389e8e83e6077326ee80
ms.sourcegitcommit: e4882e3c66166ea7b834ad2e8fafeab42293e07d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2022
ms.locfileid: "67100017"
---
# <a name="onboard-devices-and-configure-microsoft-defender-for-endpoint-capabilities"></a>Incorporar dispositivos y configurar las funcionalidades de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

La implementación de Microsoft Defender para punto de conexión es un proceso de dos pasos.

- Dispositivos incorporados al servicio
- Configuración de las funcionalidades del servicio

:::image type="content" source="images/deployment-steps.png" alt-text="Proceso de incorporación y configuración" lightbox="images/deployment-steps.png":::

## <a name="role-based-access-control"></a>Control de acceso basado en roles

Se recomienda usar Privileged Identity Management para administrar los roles a fin de proporcionar auditoría, control y revisión de acceso adicionales para los usuarios con permisos de directorio.

Defender for Endpoint admite dos maneras de administrar permisos:

- **Administración básica de permisos**: establece los permisos en acceso completo o de solo lectura. Los usuarios con roles de administrador global o administrador de seguridad en Azure Active Directory (Azure AD) tienen acceso total. El rol de lector de seguridad tiene acceso de solo lectura y no concede acceso para ver el inventario de máquinas o dispositivos.

- **Control de acceso basado en rol (RBAC):** establece permisos granulares mediante la definición de roles, la asignación de grupos de usuarios de Azure AD a los roles y la concesión de acceso a los grupos de usuarios a los grupos de dispositivos. Para obtener más información. consulte [Administración del acceso al portal mediante el control de acceso basado en rol](rbac.md).

Se recomienda aprovechar RBAC para asegurarse de que solo los usuarios que tengan una justificación empresarial puedan acceder a Defender para punto de conexión.

## <a name="onboard-devices-to-the-service"></a>Dispositivos incorporados al servicio
Tendrá que ir a la sección de incorporación del portal de Defender para punto de conexión para incorporar cualquiera de los dispositivos admitidos. En función del dispositivo, se le guiará con los pasos adecuados y se le proporcionarán opciones de herramientas de administración e implementación adecuadas para el dispositivo. 

Para incorporar dispositivos al servicio:

- Comprobar que el dispositivo cumple los [requisitos mínimos](minimum-requirements.md)
- En función del dispositivo, siga los pasos de configuración que se proporcionan en la sección de incorporación del portal de Defender para punto de conexión.
- Uso de la herramienta de administración y el método de implementación adecuados para los dispositivos
- Ejecutar una prueba de detección para comprobar que los dispositivos están incorporados correctamente e informar al servicio

En este artículo se proporciona información sobre los métodos de incorporación aplicables a las versiones de cliente y servidor de Windows.

## <a name="onboarding-and-configuration-tool-options"></a>Opciones de la herramienta de incorporación y configuración
En la tabla siguiente se enumeran las herramientas disponibles en función del punto de conexión que necesita incorporar.

| Punto de conexión     | Opciones de herramientas                       |
|--------------|------------------------------------------|
| **Cliente Windows**  |     [Mobile Administración de dispositivos/Microsoft Intune](configure-endpoints-mdm.md) <br> [Directiva de grupo](configure-endpoints-gp.md) <br> [Script local (hasta 10 dispositivos)](configure-endpoints-script.md) <br>[Scripts de VDI](configure-endpoints-vdi.md) <br> [Integración con Microsoft Defender for Cloud](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)  |
| **Windows Server**  | [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br>  [Directiva de grupo](configure-endpoints-gp.md) <br>  [Scripts de VDI](configure-endpoints-vdi.md) <br> [Integración con Microsoft Defender for Cloud](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)  |
| **macOS**    | [Scripts locales](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Administración de dispositivos móviles](mac-install-with-other-mdm.md) |
| **Servidor Linux** | [Script local](linux-install-manually.md) <br> [Títere](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md) <br> [Integración con Microsoft Defender for Cloud](configure-server-endpoints.md#integration-with-microsoft-defender-for-cloud)     |
| **iOS**      | [Microsoft Endpoint Manager](ios-install.md)           |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)            | 


> [!NOTE]
> Para los dispositivos que no están administrados por una Endpoint Manager de Microsoft (ya sea Microsoft Intune o microsoft endpoint Configuration Manager), puede usar la administración de seguridad para Microsoft Defender para punto de conexión  para recibir configuraciones de seguridad para Microsoft Defender directamente desde Endpoint Manager.

En la tabla siguiente se enumeran las herramientas disponibles en función del punto de conexión que necesita incorporar.

## <a name="configure-capabilities-of-the-service"></a>Configuración de las funcionalidades del servicio
La incorporación de dispositivos permite de forma eficaz la capacidad de detección y respuesta de puntos de conexión de Microsoft Defender para punto de conexión.

Después de incorporar los dispositivos, tendrá que configurar las otras funcionalidades del servicio. En la tabla siguiente se enumeran las funcionalidades que puede configurar para obtener la mejor protección para su entorno.

| Funcionalidad | Descripción |
|-|-|
| [Configuración de threat & Vulnerability Management (TVM)](tvm-prerequisites.md) | Threat & Vulnerability Management es un componente de Microsoft Defender para punto de conexión y proporciona a los administradores de seguridad y a los equipos de operaciones de seguridad un valor único, entre los que se incluyen: <br><br> - Información de detección y respuesta de puntos de conexión en tiempo real (EDR) correlacionada con vulnerabilidades de punto de conexión. <br><br> - Contexto de vulnerabilidad de dispositivo invaluable durante las investigaciones de incidentes. <br><br> - Procesos de corrección integrados a través de Microsoft Intune y Microsoft System Center Configuration Manager.  |
| [Configuración de la protección de última generación (NGP)](configure-microsoft-defender-antivirus-features.md) | Antivirus de Microsoft Defender es una solución antimalware integrada que proporciona protección de última generación para equipos de escritorio, equipos portátiles y servidores. El Antivirus de Microsoft Defender incluye:<br> <br>-Protección proporcionada en la nube para la detección casi instantánea y el bloqueo de amenazas nuevas y emergentes. Junto con Intelligent Security Graph y el aprendizaje automático, la protección en la nube forma parte de las tecnologías de última generación utilizadas por el Antivirus de Microsoft Defender.<br> <br> - Análisis always-on mediante la supervisión avanzada del comportamiento de archivos y procesos y otras heurísticas (también conocida como "protección en tiempo real").<br><br> - Actualizaciones de protección dedicadas basadas en el aprendizaje automático, el análisis de macrodatos humanos y automatizados, y la investigación en profundidad de la resistencia a amenazas. |
| [Configuración de la reducción de la superficie expuesta a ataques (ASR)](overview-attack-surface-reduction.md) | Las funcionalidades de reducción de superficie expuesta a ataques en Microsoft Defender para punto de conexión ayudan a proteger los dispositivos y las aplicaciones de la organización frente a amenazas nuevas y emergentes. |
| [Configuración de las funcionalidades de corrección de & de investigación automática (AIR)](configure-automated-investigations-remediation.md) | Microsoft Defender para punto de conexión usa investigaciones automatizadas para reducir significativamente el volumen de alertas que deben investigarse individualmente. La característica de investigación automatizada aprovecha varios algoritmos de inspección y los procesos utilizados por los analistas (como cuadernos de estrategias) para examinar alertas y tomar medidas de corrección inmediatas para resolver infracciones. Esto reduce considerablemente el volumen de alertas, lo que facilita que los expertos de operaciones de seguridad puedan centrarse en amenazas más complejas y otras iniciativas de alto valor. |
| [Configuración de funcionalidades de Expertos en amenazas de Microsoft (MTE)](configure-microsoft-threat-experts.md) | Expertos en amenazas de Microsoft es un servicio de búsqueda administrado que proporciona centros de operaciones de seguridad (SOC) con supervisión y análisis de nivel experto para ayudarles a garantizar que las amenazas críticas en sus entornos únicos no se pierdan.      |


## <a name="supported-capabilities-for-windows-devices"></a>Funcionalidades admitidas para dispositivos Windows

|Sistema operativo  |Windows 10 & 11  |Windows Server 2012 R2 <sup>[[1](#fn1)]<sup></sup>  |<sup>Windows Server 2016[[1](#fn1)]<sup></sup>   |Windows Server 2019 & 2022|Windows Server 1803+|
|---------|---------|---------|---------|---------|---------|
|**Prevención**    |         |         |         |         |         |
|Reglas de reducción de superficie expuesta a ataques     |    v     |   v      |    v     |    v     |    v     |
|Control de dispositivo     |     v    |    N     |    N     |    N     |    N     |  
|Firewall     |      v   |    v     |     v    |    v    |    v   |
|Protección de red     |      v   |    v     |     v    |    v    |    v   |
|Protección de última generación     |      v   |    v     |     v    |    v    |    v   |
|Protección contra alteraciones     |        v   |    v     |     v    |    v    |    v   |
|Protección web     |       v   |    v     |     v    |    v    |    v   |
|||||||
|**Detección**     |         |         |         |||
|Búsqueda avanzada de amenazas     |      v   |    v     |     v    |    v    |    v   |
|Indicadores de archivos personalizados     |      v   |    v     |     v    |    v    |    v   |
|Indicadores de red personalizados     |      v   |    v     |     v    |    v    |    v   |
|Bloquear EDR & modo pasivo     |      v   |    v     |     v    |    v    |    v   |
|Sensor de detección de sentidos     |      v   |    v     |     v    |    v    |    v   |
|Detección de dispositivos de red & punto de conexión     |      v   |    N     |     N    |    N    |    N   |
|||||||
|**Respuesta**     |         |         |         |||
|Respuesta de & de investigación automatizada (AIR)    |      v   |    v     |     v    |    v    |    v   |
|Funcionalidades de respuesta del dispositivo: aislamiento, recopilación de paquetes de investigación, ejecución del examen de AV     |      v   |    v     |     v    |    v    |    v   |
|Capacidades de respuesta de archivos: recopilar archivos, análisis profundos, bloquear archivos, detener y poner en cuarentena procesos     |      v   |    v     |     v    |    v    |    v   |
|Respuesta dinámica    |      v   |    v     |     v    |    v    |    v   |

(<a id="fn1">1</a>) Hace referencia a la solución moderna y unificada para Windows Server 2012 R2 y 2016. Para obtener más información, vea [Incorporación de servidores Windows al servicio Defender para punto de conexión](configure-server-endpoints.md).

>[!NOTE]
>Windows 7, 8.1, Windows Server 2008 R2 incluyen compatibilidad con el sensor EDR y AV mediante System Center Endpoint Protection (SCEP).
