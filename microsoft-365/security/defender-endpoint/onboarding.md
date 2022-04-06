---
title: Incorporar al servicio Microsoft Defender para punto de conexión
description: Obtenga información sobre cómo incorporar puntos de conexión a Microsoft Defender para el servicio de punto de conexión
keywords: 'microsoft Defender para el punto de conexión, la incorporación, la implementación'
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
  - m365solution-endpointprotect
  - m365solution-scenario
  - m365-initiative-defender-endpoint
ms.topic: article
ms.technology: mde
---

# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Incorporar al servicio Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Obtenga información sobre las distintas fases de implementación de Microsoft Defender para endpoint y cómo configurar las funcionalidades de la solución.


Estos son los pasos que debe seguir para implementar Defender for Endpoint:

- Paso 1: Incorporar puntos de conexión al servicio
- Paso 2: configurar las capacidades

:::image type="content" source="images/deployment-steps.png" alt-text="Pasos de implementación" lightbox="images/deployment-steps.png":::




## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Paso 1: Incorporar puntos de conexión con cualquiera de las herramientas de administración admitidas

En [el tema Plan deployment](deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender for Endpoint.

Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtenga información sobre las herramientas y métodos disponibles.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Después de identificar la arquitectura, deberá decidir qué método de implementación usar. La herramienta de implementación que elija influye en la forma en que incorpora puntos de conexión al servicio.

### <a name="onboarding-tool-options"></a>Opciones de la herramienta de incorporación

En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.

| Punto de conexión     | Opciones de herramientas                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script local (hasta 10 dispositivos)](configure-endpoints-script.md) <br>  [Directiva de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Administrador de dispositivos móviles](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Scripts VDI](configure-endpoints-vdi.md) <br> [Integración con Microsoft Defender for Cloud](azure-server-integration.md) |
| **macOS**    | [Scripts locales](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Administración de dispositivos móviles](mac-install-with-other-mdm.md) |
| **Servidor Linux** | [Script local](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Microsoft Endpoint Manager](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>Paso 2: configurar las capacidades
Después de incorporar los puntos de conexión, configurará las capacidades. En la tabla siguiente se enumeran los componentes que puede configurar. Elija los componentes que desea usar y quite los que no se aplican.

| Funcionalidad | Descripción |
|-|-|
| [Respuesta de detección & punto de conexión (EDR)](overview-endpoint-detection-response.md) | Las capacidades de defender para detección y respuesta de puntos de conexión endpoint proporcionan detecciones avanzadas de ataques que son casi en tiempo real y que se pueden actuar. Los analistas de seguridad pueden asignar prioridades a las alertas de forma eficaz, obtener visibilidad para todo el ámbito de la vulneración y llevar a cabo acciones de respuesta para corregir las amenazas. |
| [Administración & vulnerabilidad de amenazas (TVM)](next-gen-threat-and-vuln-mgt.md) | Threat & Vulnerability Management es un componente de Microsoft Defender para endpoint y proporciona a los administradores de seguridad y a los equipos de operaciones de seguridad un valor único, incluidos: - Real-time detección y respuesta de puntos de conexión (EDR ) insights correlated with endpoint vulnerabilities - Invaluable device vulnerability context during incident investigations - Built-in remediation processes through Microsoft Intune and Microsoft System Center Configuration Manager.  |
| [Protección de última generación (NGP)](microsoft-defender-antivirus-windows.md) | Antivirus de Microsoft Defender es una solución antimalware integrada que proporciona protección de última generación para escritorios, equipos portátiles y servidores. El Antivirus de Microsoft Defender incluye:<br> <br>-Protección entregada en la nube para la detección casi instantánea y el bloqueo de amenazas nuevas y emergentes. Junto con Intelligent Security Graph y el aprendizaje automático, la protección en la nube forma parte de las tecnologías de última generación utilizadas por el Antivirus de Microsoft Defender.<br> <br> - Análisis siempre continuo mediante la supervisión avanzada del comportamiento de procesos y archivos y otras heurísticas (también conocida como "protección en tiempo real").<br><br> - Actualizaciones de protección dedicadas basadas en aprendizaje automático, análisis de big-data humanos y automatizados e investigación detallada de resistencia a amenazas. |
| [Reducción de superficie de ataque (ASR)](overview-attack-surface-reduction.md) | Las capacidades de reducción de superficie de ataque en Microsoft Defender para endpoint ayudan a proteger los dispositivos y aplicaciones de la organización frente a amenazas nuevas y emergentes. |
| [Auto Investigation & Remediation (AIR)](automated-investigations.md) | Microsoft Defender para endpoint usa investigaciones automatizadas para reducir significativamente el volumen de alertas que deben investigarse individualmente. La característica de investigación automatizada aprovecha varios algoritmos de inspección y procesos usados por analistas (como playbooks) para examinar alertas y tomar medidas de corrección inmediatas para resolver infracciones. Esto reduce considerablemente el volumen de alertas, lo que facilita que los expertos de operaciones de seguridad puedan centrarse en amenazas más complejas y otras iniciativas de alto valor. |
| [Expertos en amenazas de Microsoft (MTE)](microsoft-threat-experts.md) | Expertos en amenazas de Microsoft es un servicio de búsqueda administrado que proporciona a los Centros de operaciones de seguridad (SOC) supervisión y análisis de nivel de experto para ayudarles a garantizar que las amenazas críticas en sus entornos únicos no se pierden.      |

Después de incorporar los puntos de conexión, configurarás las distintas funcionalidades, como detección y respuesta de puntos de conexión, protección de última generación y reducción de superficie de ataque.

## <a name="example-deployments"></a>Implementaciones de ejemplo

En esta guía de implementación, le guiaremos a través del uso de dos herramientas de implementación para incorporar puntos de conexión y cómo configurar las capacidades.

Las herramientas de las implementaciones de ejemplo son:

- [Incorporación mediante Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Incorporación con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)

Con las herramientas de implementación mencionadas anteriormente, se le guiará en la configuración de las siguientes funcionalidades de Defender for Endpoint:

- Detección de extremos y configuración de respuesta
- Configuración de protección de última generación
- Configuración de reducción de superficie de ataque

## <a name="related-topics"></a>Temas relacionados

- [Incorporación mediante Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Incorporación con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
- [Documentos seguros en Microsoft 365 E5](../office-365-security/safe-docs.md)
