---
title: Habilitar Microsoft Defender para la evaluación de puntos de conexión
description: Habilitar el entorno Microsoft 365 Defender prueba o piloto, incluida la comprobación del estado de la licencia y los puntos de incorporación
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b57026ab2af53cbd941ecd3f4e9f9e6dff7f99c7eb44e0b1b9b2ffb462408415
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53902252"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>Habilitar el entorno de evaluación de Microsoft Defender para puntos de conexión


Este artículo le guiará a través de los pasos para configurar el entorno de evaluación de Microsoft Defender para endpoint mediante dispositivos de producción. 


>[!TIP]
>Microsoft Defender para endpoint también incluye un laboratorio de evaluación del producto donde puede agregar dispositivos preconfigurados y ejecutar simulaciones para evaluar las capacidades de la plataforma. El laboratorio viene con una experiencia de configuración simplificada que puede ayudar a demostrar rápidamente el valor de Microsoft Defender para Enpdoint, que incluye instrucciones para muchas características como la búsqueda avanzada y el análisis de amenazas. Para obtener más información, vea [Evaluate capabilities](/defender-endpoint/evaluation-lab.md). <br> La principal diferencia entre las instrucciones proporcionadas en este artículo y el laboratorio de evaluación es que el entorno de evaluación usa dispositivos de producción, mientras que el laboratorio de evaluación usa dispositivos que no son de producción. 

Siga estos pasos para habilitar la evaluación de Microsoft Defender para endpoint.

![Pasos para habilitar Microsoft Defender para endpoint en el entorno de evaluación de Microsoft Defender](../../media/defender/m365-defender-endpoint-eval-enable-steps.png)

- [Paso 1. Comprobar el estado de la licencia](#step-1-check-license-state)
- [Paso 2. Puntos de conexión integrados](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>Paso 1. Comprobar el estado de la licencia

Primero tendrá que comprobar el estado de la licencia para comprobar que se aprovisionó correctamente. Puede hacerlo a través del Centro de administración o a través **del portal Microsoft Azure .**


1. Para ver las licencias, vaya al **portal de** Microsoft Azure y vaya a la sección Microsoft Azure licencia [del portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Imagen de la página licencias de Azure](../../media/defender/atp-licensing-azure-portal.png)

1. Como alternativa, en el Centro de administración, vaya a **Suscripciones de**  >  **facturación.**

    En la pantalla, verá todas las licencias aprovisionadas y su estado **actual.**

    ![Imagen de las licencias de facturación](../../media/defender/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Paso 2. Incorporación de puntos de conexión con cualquiera de las herramientas de administración admitidas

Después de comprobar que el estado de la licencia se ha aprovisionado correctamente, puede iniciar la incorporación de dispositivos al servicio. 

Con el fin de evaluar Microsoft Defender para Endpoint, recomendamos elegir un par de dispositivos Windows 10 para realizar la evaluación. 

En [el tema Plan deployment](../defender-endpoint/deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender for Endpoint.  

Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtenga información sobre las herramientas y métodos disponibles.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>Opciones de la herramienta de incorporación

En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.

Punto de conexión | Opciones de herramientas
:---|:---
**Windows** | [Script local (hasta 10 dispositivos),](../defender-endpoint/configure-endpoints-script.md)Directiva de grupo [,](../defender-endpoint/configure-endpoints-gp.md) [Microsoft Endpoint Manager/ Administrador](../defender-endpoint/configure-endpoints-mdm.md)de dispositivos móviles , [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md), [scripts VDI](../defender-endpoint/configure-endpoints-vdi.md), [Integración con Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)
**macOS** | [Scripts locales](../defender-endpoint/mac-install-manually.md), [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md), [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md), Administración [de dispositivos móviles](../defender-endpoint/mac-install-with-other-mdm.md)
**Servidor Linux** | [Script local](../defender-endpoint/linux-install-manually.md),  [Puppet](../defender-endpoint/linux-install-with-puppet.md),  [Ansible](../defender-endpoint/linux-install-with-ansible.md)
**iOS** | [Basado en aplicaciones](../defender-endpoint/ios-install.md)
**Android** | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)



## <a name="next-step"></a>Paso siguiente
[Configurar el piloto de Microsoft Defender para endpoint](eval-defender-endpoint-pilot.md)
 
Vuelva a la introducción a [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)