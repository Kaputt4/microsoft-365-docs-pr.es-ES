---
title: Pilot Defender for Endpoint evaluation
description: Habilite su laboratorio Microsoft 365 Defender prueba o entorno piloto.
keywords: Microsoft 365 Defender prueba, pruebe Microsoft 365 Defender, evalúe Microsoft 365 Defender, Microsoft 365 Defender de evaluación, Microsoft 365 Defender piloto, ciber seguridad, amenaza persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: cb4ca4720d0671aad45cfa2387dbf9c092f970c8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194230"
---
# <a name="pilot-mde-evaluation"></a>Evaluación piloto de MDE

> [!NOTE]
> Con el fin de guiarlo a través de una implementación típica, este escenario solo abarcará el uso de Microsoft Endpoint Configuration Manager. Defender for Endpoint admite el uso de otras herramientas de incorporación, pero no cubrirá esos escenarios en la guía de implementación. Para obtener más información, consulta [Incorporación de dispositivos a Microsoft Defender para Endpoint](onboard-configure.md).

## <a name="step-1-check-license-state"></a>Paso 1. Comprobar el estado de la licencia

Comprobar el estado de la licencia y si se aprovisionó correctamente, se puede realizar a través del Centro de administración o a través **del portal Microsoft Azure .**

1. Para ver las licencias, vaya al **portal de** Microsoft Azure y vaya a la sección Microsoft Azure licencia [del portal.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Imagen de la página Licencias de Azure.](images/atp-licensing-azure-portal.png)

1. Como alternativa, en el Centro de administración, vaya a **Suscripciones de** \> **facturación.**

    En la pantalla, verá todas las licencias aprovisionadas y su estado **actual.**

    ![Imagen de las licencias de facturación.](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Paso 2. Incorporación de puntos de conexión con cualquiera de las herramientas de administración admitidas

En [el tema Plan deployment](deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender for Endpoint.

Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtenga información sobre las herramientas y métodos disponibles.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Después de identificar la arquitectura, deberá decidir qué método de implementación usar. La herramienta de implementación que elija influye en la forma en que incorpora puntos de conexión al servicio.

### <a name="onboarding-tool-options"></a>Opciones de la herramienta de incorporación

En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.

<br>

****

|Punto de conexión|Opciones de herramientas|
|---|---|
|**Windows**|[Script local (hasta 10 dispositivos)](../defender-endpoint/configure-endpoints-script.md) <p> [Directiva de grupo](../defender-endpoint/configure-endpoints-gp.md) <p> [Microsoft Endpoint Manager/ Administrador de dispositivos móviles](../defender-endpoint/configure-endpoints-mdm.md) <p> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <p> [Scripts VDI](../defender-endpoint/configure-endpoints-vdi.md) <p> [Integración con Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender)|
|**macOS**|[Scripts locales](../defender-endpoint/mac-install-manually.md) <p> [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md) <p> [Jamf Pro](../defender-endpoint/mac-install-with-jamf.md) <p> [Administración de dispositivos móviles](../defender-endpoint/mac-install-with-other-mdm.md)|
|**Servidor Linux**|[Script local](../defender-endpoint/linux-install-manually.md) <p> [Puppet](../defender-endpoint/linux-install-with-puppet.md) <p> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
|**iOS**|[Basado en aplicaciones](../defender-endpoint/ios-install.md)|
|**Android**|[Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)|
|
