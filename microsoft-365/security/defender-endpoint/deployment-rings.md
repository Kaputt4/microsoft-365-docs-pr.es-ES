---
title: Implementación de Microsoft Defender para punto de conexión en anillos
description: Aprenda a implementar Microsoft Defender para punto de conexión en anillos
keywords: deploy, rings, evaluate, pilot, insider fast, insider slow, setup, onboard, phase, deployment, deploying, adoption, configuring
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
- highpri
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 25332c75c9f4362e456f34999f77ef7d83fb8c4e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68194365"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a>Implementación de Microsoft Defender para punto de conexión en anillos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

La implementación de Microsoft Defender para punto de conexión se puede realizar mediante un enfoque de implementación basado en anillos.

Los anillos de implementación se pueden aplicar en los siguientes escenarios:

- [Nuevas implementaciones](#new-deployments)
- [Implementaciones existentes](#existing-deployments)

## <a name="new-deployments"></a>Nuevas implementaciones

:::image type="content" source="images/deployment-rings.png" alt-text="Los anillos de implementación." lightbox="images/deployment-rings.png":::

Un enfoque basado en anillos es un método para identificar un conjunto de puntos de conexión para incorporar y comprobar que se cumplen determinados criterios antes de continuar con la implementación del servicio en un conjunto mayor de dispositivos. Puede definir los criterios de salida para cada anillo y asegurarse de que están cumplidos antes de pasar al siguiente anillo.

La adopción de una implementación basada en anillos ayuda a reducir los posibles problemas que podrían surgir al implementar el servicio. Al pilotar un determinado número de dispositivos en primer lugar, puede identificar posibles problemas y mitigar los posibles riesgos que puedan surgir.

En la tabla 1 se proporciona un ejemplo de los anillos de implementación que puede usar.

**Tabla 1**:

|Anillo de implementación|Descripción|
|---|---|
|Evaluación|Anillo 1: Identificación de 50 sistemas para pruebas piloto|
|Piloto|Anillo 2: Identificación de los próximos 50-100 puntos de conexión en el entorno de producción|
|Implementación completa|Anillo 3: Implementación del servicio en el resto del entorno en incrementos mayores|

### <a name="exit-criteria"></a>Criterios de salida

Un conjunto de ejemplo de criterios de salida para estos anillos puede incluir:

- Los dispositivos aparecen en la lista de inventario de dispositivos
- Las alertas aparecen en el panel
- [Ejecución de una prueba de detección](run-detection-test.md)
- [Ejecución de un ataque simulado en un dispositivo](attack-simulations.md)

### <a name="evaluate"></a>Calcular

Identifique un pequeño número de máquinas de prueba en su entorno para incorporarlas al servicio. Idealmente, estas máquinas serían menos de 50 puntos de conexión.

### <a name="pilot"></a>Piloto

Microsoft Defender para punto de conexión admite una variedad de puntos de conexión que puede incorporar al servicio. En este anillo, identifique varios dispositivos para incorporarlos y, en función de los criterios de salida que defina, decida continuar con el siguiente anillo de implementación.

En la tabla siguiente se muestran los puntos de conexión admitidos y la herramienta correspondiente que puede usar para incorporar dispositivos al servicio.

|Punto de conexión|Herramienta de implementación|
|---|---|
|**Windows**|[Script local (hasta 10 dispositivos)](configure-endpoints-script.md) <br> NOTA: Si desea implementar más de 10 dispositivos en un entorno de producción, use el método directiva de grupo en su lugar o las demás herramientas admitidas que se enumeran a continuación.<br>  [Directiva de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Administrador de dispositivos](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Scripts de VDI](configure-endpoints-vdi.md) |
|**macOS**|[Script local](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Administración de dispositivos móviles](mac-install-with-other-mdm.md)|
|**Servidor Linux**|[Script local](linux-install-manually.md) <br> [Marioneta](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
|**iOS**|[Microsoft Endpoint Manager](ios-install.md)|
|**Android**|[Microsoft Endpoint Manager](android-intune.md)|

### <a name="full-deployment"></a>Implementación completa

En esta fase, puede usar el material del [Plan de implementación](deployment-strategy.md) para ayudarle a planificar la implementación.

Use el siguiente material para seleccionar la arquitectura de Microsoft Defender para punto de conexión adecuada que mejor se adapte a su organización.

|Elemento|Descripción|
|---|---|
|[:::image type="content" source="images/mde-deployment-strategy.png" alt-text="Estrategia para la implementación de Microsoft Defender para punto de conexión." lightbox="images/mde-deployment-strategy.png":::](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) \| [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx)|El material arquitectónico le ayuda a planear la implementación de las arquitecturas siguientes: <ul><li> Nativo en la nube </li><li> Administración conjunta </li><li> Local</li><li>Evaluación e incorporación local</li></ul>|

## <a name="existing-deployments"></a>Implementaciones existentes

### <a name="windows-endpoints"></a>Puntos de conexión Windows

En el caso de equipos y/o servidores Windows, seleccione varias máquinas para realizar pruebas con antelación (antes del martes de parches) mediante el **programa de validación de actualizaciones de seguridad (SUVP).**

Para obtener más información, consulte:

- [¿Qué es el programa de validación de actualizaciones de seguridad?](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [Programa de validación de actualizaciones de software y establecimiento de Centro de protección contra malware de Microsoft- TwC Interactive Timeline Part 4](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)

### <a name="non-windows-endpoints"></a>Puntos de conexión que no son Windows

Con macOS y Linux, podría tomar un par de sistemas y ejecutarse en el canal Beta.

> [!NOTE]
> Lo ideal es que al menos un administrador de seguridad y un desarrollador puedan encontrar problemas de compatibilidad, rendimiento y confiabilidad antes de que la compilación llegue al canal actual.

La elección del canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen al dispositivo. Los dispositivos beta son los primeros en recibir actualizaciones y nuevas características, seguidos más adelante de la versión preliminar y, por último, de la actual.

:::image type="content" source="images/insider-rings.png" alt-text="Los anillos internos." lightbox="images/insider-rings.png":::

Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa para que usen beta o versión preliminar.

> [!WARNING]
> Cambiar el canal después de la instalación inicial requiere que se vuelva a instalar el producto. Para cambiar el canal del producto: desinstale el paquete existente, vuelva a configurar el dispositivo para que use el nuevo canal y siga los pasos de este documento para instalar el paquete desde la nueva ubicación.
