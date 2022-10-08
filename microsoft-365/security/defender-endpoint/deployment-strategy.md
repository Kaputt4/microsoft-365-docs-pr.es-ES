---
title: Planee su cuenta de Microsoft Defender para punto de conexión
description: Seleccione la mejor estrategia de implementación de Microsoft Defender para punto de conexión para su entorno.
keywords: deploy, plan, deployment strategy, cloud native, management, on prem, evaluation, onboarding, local, group policy, gp, endpoint manager, mem
search.product: eADQiWindows 10XVcnh
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
- tier1
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: cf22bb16d4275ef195fa01377fb9b791b4cad90e
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68180239"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a>Planee su cuenta de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-secopsdashboard-abovefoldlink)

Planee la implementación de Microsoft Defender para punto de conexión para que pueda maximizar las funcionalidades de seguridad dentro del conjunto y proteger mejor a su empresa de las ciberamenazas.

Esta solución proporciona instrucciones sobre cómo identificar la arquitectura del entorno, seleccionar el tipo de herramienta de implementación que mejor se adapte a sus necesidades e instrucciones sobre cómo configurar las funcionalidades.

:::image type="content" source="images/deployment-guide-plan.png" alt-text="Flujo de implementación" lightbox="images/deployment-guide-plan.png":::

## <a name="step-1-identify-architecture"></a>Paso 1: Identificación de la arquitectura

Entendemos que cada entorno empresarial es único, por lo que hemos proporcionado varias opciones para proporcionarle la flexibilidad de elegir cómo implementar el servicio.

Dependiendo de su entorno, algunas herramientas son más adecuadas para determinadas arquitecturas.

Use el siguiente material para seleccionar la arquitectura adecuada de Defender para punto de conexión que mejor se adapte a su organización.

| Elemento | Descripción |
|:-----|:-----|
|[:::image type="content" source="images/mde-deployment-strategy.png" alt-text="La estrategia para la implementación de Defender para punto de conexión" lightbox="images/mde-deployment-strategy.png":::](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)<br/> [PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)  \| [Visio](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) | El material arquitectónico le ayuda a planear la implementación de las arquitecturas siguientes: <ul><li> Nativo en la nube </li><li> Administración conjunta </li><li> Local</li><li>Evaluación e incorporación local</li>

## <a name="step-2-select-deployment-method"></a>Paso 2: Seleccionar método de implementación

En la tabla siguiente se enumeran los puntos de conexión admitidos y la herramienta de implementación correspondiente que puede usar para que pueda planear la implementación correctamente.

|Punto de conexión|Herramienta de implementación|
|---|---|
|**Windows**|[Script local (hasta 10 dispositivos)](configure-endpoints-script.md) <br>  [Directiva de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/Mobile Administrador de dispositivos](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Scripts de VDI](configure-endpoints-vdi.md) |
|**macOS**|[Script local](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Administración de dispositivos móviles](mac-install-with-other-mdm.md)|
|**Servidor Linux**|[Script local](linux-install-manually.md) <br> [Marioneta](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
|**iOS**|[Basado en aplicaciones](ios-install.md)|
|**Android**|[Microsoft Endpoint Manager](android-intune.md)|

## <a name="step-3-configure-capabilities"></a>Paso 3: Configuración de funcionalidades

Después de incorporar puntos de conexión, configure las funcionalidades de seguridad en Defender para punto de conexión para que pueda maximizar la sólida protección de seguridad disponible en el conjunto. Funcionalidades que incluye:

- Detección y respuesta de puntos de conexión
- Protección de última generación
- Reducción de la superficie expuesta a ataques

## <a name="related-topics"></a>Temas relacionados

- [Fases de implementación](deployment-phases.md)
