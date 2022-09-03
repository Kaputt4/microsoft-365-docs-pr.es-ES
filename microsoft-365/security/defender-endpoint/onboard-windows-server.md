---
title: Incorporación de Windows Server a Defender para punto de conexión
description: Incorporación de Windows Server a Microsoft Defender para punto de conexión.
keywords: onboarding, Microsoft Defender para punto de conexión onboarding, sccm, group policy, mdm, local script, detection test
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
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: ff3f2b4e34322d53c687c2ead3fcb6c7c427e34b
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598481"
---
# <a name="defender-for-endpoint-onboarding-windows-server"></a>Incorporación de Windows Server a Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- Windows Server 2008 R2
- Windows Server 2012 R2
- Windows Server 2016
- Canal de Windows Server Semi-Annual Enterprise
- Windows Server 2019 y versiones posteriores
- Edición principal de Windows Server 2019
- Windows Server 2022
- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https:%2F%2Faka.ms%2FMDEp2OpenTrial)

Tendrá que pasar por la sección de incorporación del portal de Defender para punto de conexión para incorporar cualquiera de los dispositivos admitidos. En función del dispositivo, se le guiará con los pasos adecuados y se le proporcionarán opciones de herramientas de administración e implementación adecuadas para el dispositivo.

Defender para punto de conexión amplía la compatibilidad para incluir también el sistema operativo Windows Server. Esta compatibilidad proporciona funcionalidades avanzadas de detección e investigación de ataques sin problemas a través de la consola de Microsoft 365 Defender. La compatibilidad con Windows Server proporciona información más detallada sobre las actividades del servidor, la cobertura para la detección de ataques de kernel y memoria, y habilita las acciones de respuesta.

En este tema se describe cómo incorporar servidores windows específicos para Microsoft Defender para punto de conexión.

Para obtener instrucciones sobre cómo descargar y usar Seguridad de Windows líneas base para servidores Windows, consulte [Seguridad de Windows Líneas base.](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-baselines)

## <a name="license-requirement"></a>Requisito de licencia

Para poder comprar Microsoft Defender para punto de conexión SKU de servidor, debe haber adquirido ya un mínimo combinado de cualquiera de las siguientes licencias: Windows E5/A5, Microsoft 365 E5/A5 o Seguridad de Microsoft 365 E5 licencias de suscripción. Para obtener más información sobre las licencias, consulte los [Términos del producto](https://www.microsoft.com/licensing/terms/productoffering/MicrosoftDefenderforEndpointServer/all).

## <a name="windows-server-onboarding-overview"></a>Introducción a la incorporación de Windows Server

Deberá completar los siguientes pasos generales para incorporar correctamente los servidores 2008 R2, 2012 R2, 2016, 2019 y 2022.

:::image type="content" source="images/server-onboarding.png" alt-text="Incorporación de servidores" lightbox="images/server-onboarding.png":::

### <a name="windows-server-2012-r2-and-windows-server-2016"></a>Windows Server 2012 R2 y Windows Server 2016
- Descargue los paquetes de instalación e incorporación.
- Aplique el paquete de instalación.
- Siga los pasos de incorporación de la herramienta correspondiente.

### <a name="windows-server-semi-annual-enterprise-channel-and-windows-server-2019"></a>Windows Server Semi-Annual Enterprise Channel y Windows Server 2019
- Descargue el paquete de incorporación.
- Siga los pasos de incorporación de la herramienta correspondiente.

## <a name="offboard-windows-servers"></a>Servidores Windows fuera del panel

Puede desconectar Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC), Windows Server 2019 y la edición Windows Server 2019 Core con el mismo método disponible para Windows 10 dispositivos cliente.

- [Dispositivos fuera de la placa con Configuration Manager](/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#offboard-devices-using-configuration-manager)
- [Offboard and monitor devices using Mobile Administración de dispositivos tools](/microsoft-365/security/defender-endpoint/configure-endpoints-mdm#offboard-and-monitor-devices-using-mobile-device-management-tools)
- [Dispositivos fuera del panel que usan directiva de grupo](/microsoft-365/security/defender-endpoint/configure-endpoints-gp#offboard-devices-using-group-policy)
- [Dispositivos fuera del panel con un script local](/microsoft-365/security/defender-endpoint/configure-endpoints-script#offboard-devices-using-a-local-script)

Después del offboarding, puede continuar con la desinstalación del paquete de solución unificado en Windows Server 2012 R2 y Windows Server 2016.

Para otras versiones de Windows Server, tiene dos opciones para desconectar servidores Windows del servicio:
- Desinstalación del agente mma
- Quitar la configuración del área de trabajo de Defender para punto de conexión

> [!NOTE]
> Estas instrucciones de eliminación para otras versiones de Windows Server también se aplican si ejecuta la Microsoft Defender para punto de conexión anterior para Windows Server 2016 y Windows Server 2012 R2 que requiere el MMA. Las instrucciones para migrar a la nueva solución unificada se encuentran [en escenarios de migración del servidor en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/server-migration).

## <a name="related-topics"></a>Temas relacionados

- [Incorporar dispositivos Windows mediante Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Incorporar dispositivos Windows mediante directiva de grupo](configure-endpoints-gp.md)
- [Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente](configure-endpoints-vdi.md)
