---
title: Incorporar dispositivos sin acceso a Internet a Microsoft Defender para endpoint
ms.reviewer: ''
description: Incorporar dispositivos sin acceso a Internet para que puedan enviar datos del sensor al sensor de Microsoft Defender para endpoint
keywords: onboard, servers, vm, on-premises, oms gateway, log analytics, azure log analytics, mma
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
ms.openlocfilehash: eb74f3fab320364c1311efa1a629e43eb90a1aae
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2021
ms.locfileid: "60042763"
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
> - Un servidor de puerta de enlace OMS no se puede usar como proxy para dispositivos de Windows 10 o Windows Server 2019 desconectados o de Windows Server 2022 cuando se configuran mediante el registro o GPO de 'TelemetryProxyServer'.
> - Para Windows 10 o Windows Server 2019 o Windows Server 2022: aunque puede usar TelemetryProxyServer, debe apuntar a un dispositivo o dispositivo proxy estándar.
> - Además, Windows 10 o Windows Server 2019 o Windows Server 2022 en entornos desconectados deben poder actualizar las listas de confianza de certificados sin conexión a través de un archivo o servidor web interno.
> - Para obtener más información acerca de cómo actualizar las CTL sin conexión, vea [Configure a file or web server to download the CTL files](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).

Para obtener más información acerca de los métodos de incorporación, vea los artículos siguientes:
- [Incorporar versiones anteriores de Windows](/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [Incorporación de servidores al servicio de Microsoft Defender para endpoints](/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [Configurar las opciones de proxy de dispositivo y de conectividad a Internet](/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premises-devices"></a>Dispositivos locales

- Configurar Azure Log Analytics (anteriormente conocido como puerta de enlace OMS) para que actúe como proxy o concentrador:
  - [Agente de Azure Log Analytics](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - [Instalar y configurar el Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) apunta a la clave Defender para endpoint workspace & id.

- Dispositivos sin conexión en la misma red de Azure Log Analytics
  - Configure MMA para que apunte a:
    - IP de Azure Log Analytics como proxy
    - Identificador de la clave de área de & defender para el punto de conexión

## <a name="azure-virtual-machines"></a>Máquinas virtuales de Azure

- Configurar y habilitar el área [de trabajo de Azure Log Analytics](/azure/azure-monitor/platform/gateway)
  - Configurar Azure Log Analytics Gateway (anteriormente conocida como puerta de enlace OMS) para que actúe como proxy o concentrador:
    - [Puerta de enlace de Azure Log Analytics](/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
    - [Instalar y configurar el Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) apunta a la clave Defender para endpoint workspace & id.
    - Máquinas virtuales de Azure sin conexión en la misma red de OMS Gateway
      - Configurar la IP de Azure Log Analytics como proxy
      - Identificador de clave de área de trabajo de Azure Log Analytics & de trabajo
    - Azure Defender
      - [Área de trabajo de análisis \> de registro de directivas de seguridad](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [Detección de \> amenazas Permitir que Defender for Endpoint acceda a mis datos](/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        Para obtener más información, vea [Trabajar con directivas de seguridad](/azure/security-center/tutorial-security-policy).
