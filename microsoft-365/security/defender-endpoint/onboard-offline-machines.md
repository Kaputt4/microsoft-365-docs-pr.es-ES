---
title: Incorporar dispositivos sin acceso a Internet a Microsoft Defender para endpoint
ms.reviewer: ''
description: Incorporar dispositivos sin acceso a Internet para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint
keywords: onboard, servers, vm, on-premise, oms gateway, log analytics, azure log analytics, mma
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fb5a9a4d35af2d400cdff1e417727e662738514e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861352"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Incorporar dispositivos sin acceso a Internet a Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Para incorporar dispositivos sin acceso a Internet, deberá seguir los siguientes pasos generales:

> [!IMPORTANT] 
> Los pasos siguientes solo se aplican a dispositivos que ejecutan versiones anteriores de Windows como: Windows Server 2016 y versiones anteriores o Windows 8.1 y versiones anteriores.

> [!NOTE]
> - Un servidor de puerta de enlace OMS no se puede usar como proxy para dispositivos windows 10 o Windows Server 2019 desconectados cuando se configura mediante el registro o GPO de 'TelemetryProxyServer'.
> - Para Windows 10 o Windows Server 2019: aunque puedes usar TelemetryProxyServer, debe apuntar a un dispositivo o dispositivo proxy estándar.
> - Además, Windows 10 o Windows Server 2019 en entornos desconectados deben poder actualizar las listas de confianza de certificados sin conexión a través de un archivo o servidor web interno.
> - Para obtener más información acerca de cómo actualizar las CTL sin conexión, vea [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).

Para obtener más información acerca de los métodos de incorporación, vea los artículos siguientes:
- [Incorporar versiones anteriores de Windows](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Incorporación de servidores al servicio de Microsoft Defender para endpoints](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Configurar el proxy de dispositivo y la configuración de conectividad a Internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a>Dispositivos locales

- Configurar Azure Log Analytics (anteriormente conocido como puerta de enlace OMS) para que actúe como proxy o concentrador:
  - [Agente de Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Instalar y configurar Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) apunta a Defender for Endpoint Workspace key & ID.

- Dispositivos sin conexión en la misma red de Azure Log Analytics
  -  Configure MMA para que apunte a:
     - IP de Azure Log Analytics como proxy
     - Identificador de la clave de área de & defender para el punto de conexión

## <a name="azure-virtual-machines"></a>Máquinas virtuales de Azure
- Configurar y habilitar el área [de trabajo de Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)

    - Configurar Azure Log Analytics Gateway (anteriormente conocida como puerta de enlace OMS) para que actúe como proxy o concentrador:
      - [Puerta de enlace de Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - [Instalar y configurar Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) apunta a Defender for Endpoint Workspace key & ID.
    - Máquinas virtuales de Azure sin conexión en la misma red de OMS Gateway
      - Configurar la IP de Azure Log Analytics como proxy
      - Identificador de clave de área de trabajo de Azure Log Analytics & de trabajo

    - Centro de seguridad de Azure (ASC)
      - [Área de trabajo de análisis \> de registro de directivas de seguridad](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [Detección de \> amenazas Permitir que Defender for Endpoint acceda a mis datos](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        Para obtener más información, vea [Trabajar con directivas de seguridad](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).
