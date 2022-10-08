---
title: Habilitación de la evaluación de Microsoft Defender para punto de conexión
description: Habilite el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender, incluida la comprobación del estado de la licencia y la incorporación de puntos de conexión.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.date: 09/22/2022
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: conceptual
ms.openlocfilehash: 2d4de8ce1507635187c140830e92fd50ad8ec3e6
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68084823"
---
# <a name="enable-microsoft-defender-for-endpoint-evaluation-environment"></a>Habilitar Microsoft Defender para punto de conexión entorno de evaluación


En este artículo se le guiará por los pasos para configurar el entorno de evaluación para Microsoft Defender para punto de conexión mediante dispositivos de producción. 


> [!TIP]
> Microsoft Defender para punto de conexión también incluye un laboratorio de evaluación en el producto en el que puede agregar dispositivos preconfigurados y ejecutar simulaciones para evaluar las funcionalidades de la plataforma. El laboratorio incluye una experiencia de configuración simplificada que puede ayudar a demostrar rápidamente el valor de Microsoft Defender para punto de conexión que incluye instrucciones para muchas características, como la búsqueda avanzada y el análisis de amenazas. Para obtener más información, consulte [Evaluación de funcionalidades](../defender-endpoint/evaluation-lab.md). <br> La principal diferencia entre las instrucciones proporcionadas en este artículo y el laboratorio de evaluación es que el entorno de evaluación usa dispositivos de producción, mientras que el laboratorio de evaluación usa dispositivos que no son de producción. 

Siga estos pasos para habilitar la evaluación para Microsoft Defender para punto de conexión.

:::image type="content" source="../../media/defender/m365-defender-endpoint-eval-enable-steps.png" alt-text="Pasos para habilitar Microsoft Defender para punto de conexión en el entorno de evaluación de Microsoft Defender" lightbox="../../media/defender/m365-defender-endpoint-eval-enable-steps.png":::

- [Paso 1. Comprobación del estado de la licencia](#step-1-check-license-state)
- [Paso 2. Incorporación de puntos de conexión](#step-2-onboard-endpoints-using-any-of-the-supported-management-tools)


## <a name="step-1-check-license-state"></a>Paso 1. Comprobación del estado de la licencia

Primero deberá comprobar el estado de la licencia para comprobar que se ha aprovisionado correctamente. Puede hacerlo a través del Centro de administración o a través de **Microsoft Azure Portal**.


1. Para ver las licencias, vaya a Microsoft **Azure Portal** y vaya a la [sección Licencia de Microsoft Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).

   :::image type="content" source="../../media/defender/atp-licensing-azure-portal.png" alt-text="Página Licencias de Azure en el portal de Microsoft 365 Defender" lightbox="../../media/defender/atp-licensing-azure-portal.png":::

1. Como alternativa, en el centro de administración, vaya a **Suscripciones** de **facturación** > .

    En la pantalla, verá todas las licencias aprovisionadas y su **estado** actual.

    :::image type="content" source="../../media/defender/atp-billing-subscriptions.png" alt-text="La página Licencias de facturación de Microsoft Azure Portal" lightbox="../../media/defender/atp-billing-subscriptions.png":::
    

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Paso 2. Incorporación de puntos de conexión mediante cualquiera de las herramientas de administración admitidas

Después de comprobar que el estado de la licencia se ha aprovisionado correctamente, puede empezar a incorporar dispositivos al servicio. 

Con el fin de evaluar Microsoft Defender para punto de conexión, se recomienda elegir un par de dispositivos Windows para realizar la evaluación.

Puede optar por usar cualquiera de las herramientas de administración admitidas, pero Intune proporciona una integración óptima. Para obtener más información, vea [Configurar Microsoft Defender para punto de conexión en Microsoft Intune](/mem/intune/protect/advanced-threat-protection-configure#enable-microsoft-defender-for-endpoint-in-intune).

En el tema [Planeamiento de la implementación](../defender-endpoint/deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender para punto de conexión.  

Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtener información sobre las herramientas y métodos disponibles.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

### <a name="onboarding-tool-options"></a>Opciones de la herramienta de incorporación

En la tabla siguiente se enumeran las herramientas disponibles en función del punto de conexión que necesita incorporar.

| Punto de conexión | Opciones de herramientas |
|:---|:---|
| **Windows** |- [Script local (hasta 10 dispositivos)](../defender-endpoint/configure-endpoints-script.md)<br/>- [directiva de grupo](../defender-endpoint/configure-endpoints-gp.md)<br/>- [Microsoft Endpoint Manager/Mobile Administrador de dispositivos](../defender-endpoint/configure-endpoints-mdm.md)<br/>- [Configuration Manager de punto de conexión de Microsoft](../defender-endpoint/configure-endpoints-sccm.md)<br/>- [Scripts de VDI](../defender-endpoint/configure-endpoints-vdi.md) |
| **macOS** | - [Scripts locales](../defender-endpoint/mac-install-manually.md)<br/>- [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md)<br/>- [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md)<br/>- [Administración de dispositivos móvil](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Servidor Linux** | - [Script local](../defender-endpoint/linux-install-manually.md)<br/>- [Marioneta](../defender-endpoint/linux-install-with-puppet.md)<br/>- [Ansible](../defender-endpoint/linux-install-with-ansible.md) |
| **iOS** | [Basado en aplicaciones](../defender-endpoint/ios-install.md) |
| **Android** | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md) |



## <a name="next-step"></a>Paso siguiente
[Configuración del piloto para Microsoft Defender para punto de conexión](eval-defender-endpoint-pilot.md)
 
Vuelva a la introducción para [Evaluar Microsoft Defender para punto de conexión](eval-defender-endpoint-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
