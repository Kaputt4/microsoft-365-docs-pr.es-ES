---
title: Incorporación de dispositivos al servicio de Microsoft Defender para endpoints
description: Incorpore Windows dispositivos, servidores, dispositivos que no Windows y aprenda a ejecutar una prueba de detección.
keywords: incorporación, incorporación de Microsoft Defender para endpoint, sccm, directiva de grupo, mdm, script local, prueba de detección
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 52083cbd8b7e94c09c21ef434634376966102df6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178328"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>Incorporación de dispositivos al servicio de Microsoft Defender para endpoints

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Tendrás que ir a la sección de incorporación del portal de Defender for Endpoint para incorporar cualquiera de los dispositivos compatibles. Según el dispositivo, se te guiará con los pasos adecuados y te ofrecerán opciones de herramientas de administración e implementación adecuadas para el dispositivo.

En general, para incorporar dispositivos al servicio:

- Comprobar que el dispositivo cumple los [requisitos mínimos](minimum-requirements.md)
- Según el dispositivo, siga los pasos de configuración proporcionados en la sección incorporación del portal de Defender para endpoints
- Usar la herramienta de administración y el método de implementación adecuados para los dispositivos
- Ejecutar una prueba de detección para comprobar que los dispositivos están correctamente incorporados e informando al servicio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>Opciones de la herramienta de incorporación

En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.

|Punto de conexión|Opciones de herramientas|
|---|---|
|**Windows**|[Script local (hasta 10 dispositivos)](configure-endpoints-script.md) <p> [Directiva de grupo](configure-endpoints-gp.md) <p> [Microsoft Endpoint Manager/ Administrador de dispositivos móviles](configure-endpoints-mdm.md) <p> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <p> [Scripts VDI](configure-endpoints-vdi.md) <p> [Integración con Azure Defender](configure-server-endpoints.md#integration-with-azure-defender)|
|**macOS**|[Scripts locales](mac-install-manually.md) <p> [Microsoft Endpoint Manager](mac-install-with-intune.md) <p> [Jamf Pro](mac-install-with-jamf.md) <p> [Administración de dispositivos móviles](mac-install-with-other-mdm.md)|
|**Servidor Linux**|[Script local](linux-install-manually.md) <p> [Puppet](linux-install-with-puppet.md) <p> [Ansible](linux-install-with-ansible.md)|
|**iOS**|[Basado en aplicaciones](ios-install.md)|
|**Android**|[Microsoft Endpoint Manager](android-intune.md)|

## <a name="in-this-section"></a>En esta sección

Tema|Descripción
:---|:---
[Incorporar versiones anteriores de Windows](onboard-downlevel.md)|Incorpore Windows 7 y Windows 8.1 dispositivos a Defender para endpoint.
[incorporar dispositivos Windows](configure-endpoints.md)|Tendrás que incorporar dispositivos para que se informen al servicio Defender for Endpoint. Obtenga información sobre las herramientas y métodos que puede usar para configurar dispositivos en su empresa.
[Servidores integrados](configure-server-endpoints.md)|Incorpore Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) versión 1803 y versiones posteriores, Windows Server 2019 y versiones posteriores, y Windows Server 2019 core edition a Defender for Endpoint.
[Incorporar dispositivos que no tienen Windows](configure-endpoints-non-windows.md)|Defender for Endpoint proporciona una experiencia de operaciones de seguridad centralizada para Windows y plataformas no Windows de seguridad. Podrás ver alertas de varios sistemas operativos compatibles (SO) en Centro de seguridad de Microsoft Defender proteger mejor la red de la organización. Esta experiencia aprovecha los datos del sensor de productos de seguridad de terceros.
[Ejecutar una prueba de detección en un dispositivo incorporado recientemente](run-detection-test.md)|Ejecute un script en un dispositivo recién incorporado para comprobar que está informando correctamente al servicio Defender for Endpoint.
[Configuración de proxy e Internet](configure-proxy-internet.md)|Habilite la comunicación con el servicio en la nube de Defender for Endpoint mediante la configuración del proxy y la configuración de conectividad a Internet.
[Solucionar problemas de incorporación](troubleshoot-onboarding.md)|Obtenga información sobre cómo resolver problemas que pueden surgir durante la incorporación.

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
