---
title: Incorporar dispositivos sin acceso a Internet a Microsoft Defender para endpoint
ms.reviewer: ''
description: Incorporar dispositivos sin acceso a Internet para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint
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
ms.openlocfilehash: e490123a06c2384568e4aabe9119936ed618b2c2
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240490"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a>Incorporar dispositivos sin acceso a Internet a Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


Para incorporar dispositivos sin acceso a Internet, deberá seguir los siguientes pasos generales:

> [!IMPORTANT] 
> Los pasos siguientes solo se aplican a dispositivos que ejecutan versiones anteriores de Windows como: Windows Server 2016 anteriores o anteriores Windows 8.1 versiones anteriores.

> [!NOTE]
> - Un servidor de puerta de enlace OMS no se puede usar como proxy para dispositivos Windows o Windows server desconectados cuando se configura mediante el Registro 'TelemetryProxyServer' o GPO.
> - For Windows or Windows Server: while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.
> - Además, Windows o Windows server en entornos desconectados deben poder actualizar las listas de confianza de certificados sin conexión a través de un archivo o servidor web interno.
> - Para obtener más información acerca de cómo actualizar las CTL sin conexión, vea [Configure a file or web server to download the CTL files](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).

Para obtener más información acerca de los métodos de incorporación, vea los artículos siguientes:
- [Incorporar versiones anteriores de Windows](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Incorporación de servidores al servicio de Microsoft Defender para endpoints](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Configurar las opciones de proxy de dispositivo y de conectividad a Internet](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premises-devices"></a>Dispositivos locales

- Configurar Azure Log Analytics (anteriormente conocido como puerta de enlace OMS) para que actúe como proxy o concentrador:
  - [Agente de Azure Log Analytics](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Instalar y configurar el Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) apunta a la clave Defender para endpoint workspace & id.

[Incorporar versiones anteriores de Windows](onboard-downlevel.md)

- Dispositivos sin conexión en la misma red de Azure Log Analytics
  - Configure MMA para que apunte a:
    - IP de Azure Log Analytics como proxy
    - Identificador de la clave de área de & defender para el punto de conexión

## <a name="azure-virtual-machines"></a>Máquinas virtuales de Azure

- Configurar Azure Log Analytics Gateway (anteriormente conocida como puerta de enlace OMS) para que actúe como proxy o concentrador:
    - [Puerta de enlace de Azure Log Analytics](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
    - [Instalar y configurar el Microsoft Monitoring Agent (MMA)](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma) apunta a la clave Defender para endpoint workspace & id.
- Máquinas virtuales de Azure sin conexión en la misma red de OMS Gateway
    - Configurar la IP de Azure Log Analytics como proxy
    - Identificador de clave de área de trabajo de Azure Log Analytics & de trabajo
- Azure Defender
    - [Área de trabajo de análisis \> de registro de directivas de seguridad](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
    - [Detección de \> amenazas Permitir que Defender for Endpoint acceda a mis datos](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

    Para obtener más información, vea [Trabajar con directivas de seguridad](/azure/security-center/tutorial-security-policy).
