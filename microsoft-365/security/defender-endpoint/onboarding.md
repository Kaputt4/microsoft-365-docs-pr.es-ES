---
title: Incorporar al servicio Microsoft Defender para punto de conexión
description: Obtenga información sobre cómo incorporar puntos de conexión a Microsoft Defender para punto de conexión servicio
keywords: microsoft defender para punto de conexión, incorporación e implementación
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-endpointprotect
- m365solution-scenario
- m365-initiative-defender-endpoint
- highpri
- tier1
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: d0809a1efaa091c21e2cb88c0f085e978a7f048f
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68506508"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Incorporar al servicio Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Obtenga información sobre las distintas fases de la implementación de Microsoft Defender para punto de conexión y cómo configurar las funcionalidades dentro de la solución.


Estos son los pasos que debe seguir para implementar Defender para punto de conexión:

- Paso 1: Incorporación de puntos de conexión al servicio
- Paso 2: configurar las capacidades

:::image type="content" source="images/deployment-steps.png" alt-text="Pasos de implementación" lightbox="images/deployment-steps.png":::




## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Paso 1: Incorporación de puntos de conexión mediante cualquiera de las herramientas de administración admitidas

En el tema [Planeamiento de la implementación](deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender para punto de conexión.

Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtener información sobre las herramientas y métodos disponibles.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Después de identificar la arquitectura, deberá decidir qué método de implementación usar. La herramienta de implementación que elija influye en la forma en que incorpora puntos de conexión al servicio.

### <a name="onboarding-tool-options"></a>Opciones de la herramienta de incorporación

En la tabla siguiente se enumeran las herramientas disponibles en función del punto de conexión que necesita incorporar.

| Punto de conexión     | Opciones de herramientas                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script local (hasta 10 dispositivos)](configure-endpoints-script.md) <br>  [Directiva de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Administrador de dispositivos](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Scripts de VDI](configure-endpoints-vdi.md) <br> [Integración con Microsoft Defender for Cloud](azure-server-integration.md) |
| **macOS**    | [Scripts locales](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Administración de dispositivos móviles](mac-install-with-other-mdm.md) |
| **Servidor Linux** | [Script local](linux-install-manually.md) <br> [Marioneta](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Microsoft Endpoint Manager](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>Paso 2: configurar las capacidades
Después de incorporar los puntos de conexión, configurará las funcionalidades. En la tabla siguiente se enumeran los componentes que puede configurar. Elija los componentes que desea usar y quite los que no se aplican.

| Funcionalidad | Descripción |
|-|-|
| [Respuesta & de detección de puntos de conexión (EDR)](overview-endpoint-detection-response.md) | Las funcionalidades de detección y respuesta de puntos de conexión de Defender para punto de conexión proporcionan detecciones avanzadas de ataques casi en tiempo real y accionables. Los analistas de seguridad pueden asignar prioridades a las alertas de forma eficaz, obtener visibilidad para todo el ámbito de la vulneración y llevar a cabo acciones de respuesta para corregir las amenazas. |
| [Administración de vulnerabilidades de Microsoft Defender (MDVM)](next-gen-threat-and-vuln-mgt.md) | La administración de vulnerabilidades de Defender es un componente de Microsoft Defender para punto de conexión y proporciona a los administradores de seguridad y a los equipos de operaciones de seguridad un valor único, incluidos: - Información de respuesta y detección de puntos de conexión en tiempo real (EDR) correlacionada con vulnerabilidades de punto de conexión: contexto de vulnerabilidad de dispositivo invaluable durante las investigaciones de incidentes: procesos de corrección integrados a través de Microsoft Intune y Microsoft System Center Configuration Manager.  |
| [Protección de última generación (NGP)](microsoft-defender-antivirus-windows.md) | Microsoft Defender Antivirus es una solución antimalware integrada que proporciona protección de última generación para equipos de escritorio, equipos portátiles y servidores. El Antivirus de Microsoft Defender incluye:<br> <br>-Protección proporcionada en la nube para la detección casi instantánea y el bloqueo de amenazas nuevas y emergentes. Junto con Intelligent Security Graph y el aprendizaje automático, la protección en la nube forma parte de las tecnologías de última generación utilizadas por el Antivirus de Microsoft Defender.<br> <br> - Análisis always-on mediante la supervisión avanzada del comportamiento de archivos y procesos y otras heurísticas (también conocida como "protección en tiempo real").<br><br> - Actualizaciones de protección dedicadas basadas en el aprendizaje automático, el análisis de macrodatos humanos y automatizados, y la investigación en profundidad de la resistencia a amenazas. |
| [Reducción de la superficie expuesta a ataques (ASR)](overview-attack-surface-reduction.md) | Las funcionalidades de reducción de superficie expuesta a ataques en Microsoft Defender para punto de conexión ayudan a proteger los dispositivos y las aplicaciones de la organización frente a amenazas nuevas y emergentes. |
| [Corrección de & de investigación automática (AIR)](automated-investigations.md) | Microsoft Defender para punto de conexión usa investigaciones automatizadas para reducir significativamente el volumen de alertas que deben investigarse individualmente. La característica de investigación automatizada aprovecha varios algoritmos de inspección y los procesos utilizados por los analistas (como cuadernos de estrategias) para examinar alertas y tomar medidas de corrección inmediatas para resolver infracciones. Esto reduce considerablemente el volumen de alertas, lo que facilita que los expertos de operaciones de seguridad puedan centrarse en amenazas más complejas y otras iniciativas de alto valor. |
| [Expertos en Microsoft Defender](microsoft-threat-experts.md) | Microsoft Defender Experts es un servicio de búsqueda administrado que proporciona centros de operaciones de seguridad (SOC) con supervisión y análisis de nivel experto para ayudarles a garantizar que las amenazas críticas en sus entornos únicos no se pierdan.      |

Después de incorporar los puntos de conexión, configurará las distintas funcionalidades, como la detección y respuesta de puntos de conexión, la protección de próxima generación y la reducción de la superficie expuesta a ataques.

## <a name="example-deployments"></a>Implementaciones de ejemplo

En esta guía de implementación, le guiaremos a través del uso de dos herramientas de implementación para incorporar puntos de conexión y cómo configurar las funcionalidades.

Las herramientas de las implementaciones de ejemplo son:

- [Incorporación mediante Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Incorporación con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)

Con las herramientas de implementación mencionadas anteriormente, se le guiará en la configuración de las siguientes funcionalidades de Defender para punto de conexión:

- Configuración de respuesta y detección de puntos de conexión
- Configuración de protección de última generación
- Configuración de reducción de superficie expuesta a ataques

## <a name="related-topics"></a>Temas relacionados

- [Incorporación mediante Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Incorporación con Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
- [Documentos seguros en Microsoft 365 E5](../office-365-security/safe-docs.md)
