---
title: Habilitar Microsoft Defender para la evaluación de puntos de conexión
description: Habilite el entorno Microsoft 365 Defender de prueba o piloto, incluida la comprobación del estado de la licencia y los puntos de conexión de incorporación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a12c81635f712dd0fac70101348d30bc1dc4f154
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754635"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>Habilitar el entorno de evaluación de Microsoft Defender para puntos de conexión


Este artículo le guiará a través de los pasos para configurar el entorno de evaluación de Microsoft Defender para endpoint mediante dispositivos de producción. 


> [!TIP]
> Microsoft Defender para endpoint también incluye un laboratorio de evaluación del producto donde puede agregar dispositivos preconfigurados y ejecutar simulaciones para evaluar las capacidades de la plataforma. El laboratorio viene con una experiencia de configuración simplificada que puede ayudar a demostrar rápidamente el valor de Microsoft Defender para Endpoint, incluida la guía para muchas características como la búsqueda avanzada y el análisis de amenazas. Para obtener más información, vea [Evaluate capabilities](../defender-endpoint/evaluation-lab.md). <br> La principal diferencia entre las instrucciones proporcionadas en este artículo y el laboratorio de evaluación es que el entorno de evaluación usa dispositivos de producción, mientras que el laboratorio de evaluación usa dispositivos que no son de producción. 

Siga estos pasos para habilitar la evaluación de Microsoft Defender para endpoint.

:::image type="content" source="../../media/defender/m365-defender-endpoint-eval-enable-steps.png" alt-text="Pasos para habilitar Microsoft Defender para endpoint en el entorno de evaluación de Microsoft Defender" lightbox="../../media/defender/m365-defender-endpoint-eval-enable-steps.png":::

- [Paso 1. Comprobar el estado de la licencia](#step-1-check-license-state)
- [Paso 2. Puntos de conexión integrados](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>Paso 1. Comprobar el estado de la licencia

Primero tendrá que comprobar el estado de la licencia para comprobar que se aprovisionó correctamente. Puede hacerlo a través del Centro de administración o a través **del portal Microsoft Azure administración**.


1. Para ver las licencias, vaya al portal de Microsoft Azure **y** vaya a la [sección Microsoft Azure licencia del portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   :::image type="content" source="../../media/defender/atp-licensing-azure-portal.png" alt-text="La página Licencias de Azure en el portal Microsoft 365 Defender web" lightbox="../../media/defender/atp-licensing-azure-portal.png":::

1. Como alternativa, en el Centro de administración, vaya a **BillingSubscriptions** > .

    En la pantalla, verá todas las licencias aprovisionadas y su estado **actual**.

    :::image type="content" source="../../media/defender/atp-billing-subscriptions.png" alt-text="La página Licencias de facturación del portal Microsoft Azure facturación" lightbox="../../media/defender/atp-billing-subscriptions.png":::
    

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Paso 2. Incorporación de puntos de conexión con cualquiera de las herramientas de administración admitidas

Después de comprobar que el estado de la licencia se ha aprovisionado correctamente, puede iniciar la incorporación de dispositivos al servicio. 

Con el fin de evaluar Microsoft Defender para Endpoint, se recomienda elegir un par de dispositivos Windows para realizar la evaluación.

Puedes elegir usar cualquiera de las herramientas de administración admitidas, pero Intune proporciona una integración óptima. Para obtener más información, vea [Configure Microsoft Defender for Endpoint in Microsoft Intune](/mem/intune/protect/advanced-threat-protection-configure#enable-microsoft-defender-for-endpoint-in-intune).

En [el tema Plan deployment](../defender-endpoint/deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender for Endpoint.  

Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtenga información sobre las herramientas y métodos disponibles.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>Opciones de la herramienta de incorporación

En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.

Punto de conexión | Opciones de herramientas
:---|:---
**Windows** | [Script local (hasta 10](../defender-endpoint/configure-endpoints-script.md) dispositivos), directiva de [grupo,](../defender-endpoint/configure-endpoints-gp.md) administrador de dispositivos Microsoft Endpoint Manager[/](../defender-endpoint/configure-endpoints-mdm.md) móvil, [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md), [scripts VDI](../defender-endpoint/configure-endpoints-vdi.md), [integración con Microsoft Defender para la nube](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)
**macOS** | [Scripts locales](../defender-endpoint/mac-install-manually.md), [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md), [jamf Pro](../defender-endpoint/mac-install-with-jamf.md), [administración de dispositivos móviles](../defender-endpoint/mac-install-with-other-mdm.md)
**Servidor Linux** | [Script local](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)
**iOS** | [Basado en aplicaciones](../defender-endpoint/ios-install.md)
**Android** | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)



## <a name="next-step"></a>Paso siguiente
[Configurar el piloto de Microsoft Defender para endpoint](eval-defender-endpoint-pilot.md)
 
Vuelva a la introducción a [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)
