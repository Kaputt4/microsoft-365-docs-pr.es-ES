---
title: Incorporación de dispositivos sin acceso a Internet a Microsoft Defender para punto de conexión
ms.reviewer: ''
description: Incorporación de dispositivos sin acceso a Internet para que puedan enviar datos del sensor al sensor de Microsoft Defender para punto de conexión
keywords: onboard, servers, vm, on-premises, oms gateway, log analytics, azure log analytics, mma
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9c3dc16904672d32ab8399e693c2066b8e04c187
ms.sourcegitcommit: 00948161a72d8cea8c2baba873743fc4a0e19f90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2022
ms.locfileid: "66969822"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Incorporación de dispositivos sin acceso a Internet a Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Para los dispositivos sin conexión directa a Internet, el uso de una solución de proxy es el enfoque recomendado. En el caso de los dispositivos Windows anteriores incorporados con la solución anterior basada en MMA, el uso de la solución de puerta de enlace de OMS proporciona un enfoque alternativo. Para obtener más información sobre los métodos de incorporación, consulte los artículos siguientes:
- [Incorporar versiones anteriores de Windows](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Incorporación de servidores al servicio Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)

> [!IMPORTANT]
> - Windows o Windows Server en entornos desconectados deben poder actualizar listas de confianza de certificados sin conexión a través de un archivo interno o servidor web.
> - Para obtener más información sobre cómo actualizar las CTL sin conexión, consulte [Configuración de un archivo o servidor web para descargar los archivos CTL](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).

## <a name="devices-running-windows-10-or-later-windows-server-2012-r2-or-later-linux-and-macos"></a>Dispositivos que ejecutan Windows 10 o posterior, Windows Server 2012 R2 o posterior, Linux y macOS

En función del sistema operativo, el proxy que se usará para Microsoft Defender para punto de conexión se puede configurar automáticamente, normalmente mediante el uso de detección automática o un archivo de configuración automática, o estáticamente específico para los servicios de Defender para punto de conexión que se ejecutan en el dispositivo.

- Para dispositivos Windows, consulte [Configuración del proxy de dispositivo y la conectividad a Internet.](/microsoft-365/security/defender-endpoint/configure-proxy-internet)
- Para dispositivos Linux, consulte [Configuración de Microsoft Defender para punto de conexión en Linux para la detección de proxy estático](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration).
- Para dispositivos macOS, consulte [Microsoft Defender para punto de conexión en Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac#network-connections).

## <a name="windows-devices-running-the-previous-mma-based-solution"></a>Dispositivos Windows que ejecutan la solución anterior basada en MMA

> [!NOTE]
> - No se puede usar un servidor de puerta de enlace de OMS como proxy para dispositivos Windows o Windows Server desconectados cuando se configuran a través del registro o GPO "TelemetryProxyServer".
> - Para Windows o Windows Server: aunque puede usar TelemetryProxyServer, debe apuntar a un dispositivo o dispositivo proxy estándar.

- Configure Azure Log Analytics (anteriormente conocido como puerta de enlace de OMS) para que actúe como proxy o centro:
  - [Agente de Azure Log Analytics](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Instalar y configurar el punto de Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) a la clave del área de trabajo de Defender para punto de conexión & id.

[Incorporar versiones anteriores de Windows](onboard-downlevel.md)

### <a name="azure-virtual-machines"></a>Máquinas virtuales de Azure

- Para los dispositivos que ejecutan la solución anterior basada en MMA, configure Azure Log Analytics Gateway (anteriormente conocida como puerta de enlace de OMS) para que actúe como proxy o centro:
    - [Puerta de enlace de Azure Log Analytics](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
    - [Instalar y configurar el punto de Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) a la clave del área de trabajo de Defender para punto de conexión & id.
- Máquinas virtuales de Azure sin conexión en la misma red de oms Gateway
    - Configuración de la dirección IP de Azure Log Analytics como proxy
    - Identificador de & clave del área de trabajo de Azure Log Analytics
- Microsoft Defender for Cloud
    - [Área de trabajo de Log Analytics de directivas \> de seguridad](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
    - [Detección de \> amenazas Permitir que Defender para punto de conexión acceda a mis datos](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

    Para obtener más información, consulte [Trabajar con directivas de seguridad](/azure/security-center/tutorial-security-policy).

> [!NOTE]
> Cualquier cliente que no tenga acceso a Internet no se puede incorporar al punto de conexión de Microsoft Defender. Un cliente debe tener acceso directamente a las direcciones URL necesarias o debe tener acceso a través de un proxy.
