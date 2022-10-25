---
title: Actualice el agente en dispositivos para Microsoft Defender para punto de conexión
description: Obtenga información sobre las opciones para actualizar o reemplazar el agente mma en dispositivos Windows para Defender para punto de conexión.
keywords: MMA, agente, azure log
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
ms.date: 10/24/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.reviewer: pahuijbr
search.appverid: met150
ms.openlocfilehash: 48642c497be5b379e5d72c4e6538ffd1997b30bf
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68688966"
---
# <a name="updating-mma-on-windows-devices-for-microsoft-defender-for-endpoint"></a>Actualización de MMA en dispositivos Windows para Microsoft Defender para punto de conexión

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Si usa Microsoft Monitoring Agent (MMA) en dispositivos Windows, debe mantener actualizado este agente. Con el agente moderno y unificado para Windows Server 2012 R2 y Windows Server 2016, debe migrar a la nueva solución en su lugar. 

- [Actualización del Agente de supervisión de Microsoft (MMA) en los dispositivos](#option-1-update-mma-on-your-devices)
- [Uso de un nuevo agente en Windows Server 2012 R2 o Windows Server 2016](#option-2-use-a-new-agent-on-windows-server-2012-r2-or-windows-server-2016)

En este artículo se describen ambas opciones e se incluyen vínculos a información adicional.

## <a name="option-1-update-mma-on-your-devices"></a>Opción 1: Actualizar MMA en los dispositivos

*Esta opción se aplica a los dispositivos que ejecutan Windows 7 SP1 Enterprise, Windows 7 SP1 Pro, Windows 8.1 Pro, Windows 8.1 Enterprise y Windows Server 2008 R2 SP1.* 

- Consulte [Administración y mantenimiento del agente de Log Analytics para Windows y Linux](/azure/azure-monitor/agents/agent-manage?tabs=PowerShellLinux) para obtener instrucciones sobre cómo actualizar el agente mediante Azure Automation o un enfoque de línea de comandos para usarlo con diversas herramientas y métodos de implementación a su disposición. 

- Actualice MMA mediante [Microsoft Update](/windows/deployment/update/how-windows-update-works), a través [de Windows Server Update Services](/windows/deployment/update/waas-manage-updates-wsus) o [Configuration Manager](/mem/configmgr/osd/deploy-use/manage-windows-as-a-service). Use el método que se configuró cuando mma se instaló por primera vez en el dispositivo.

- Descargue el archivo de instalación de MMA:

   - **Agente de Windows de 64 bits**: [https://go.microsoft.com/fwlink/?LinkId=828603](https://go.microsoft.com/fwlink/?LinkId=828603)
   - **Agente de Windows de 32 bits**: [https://go.microsoft.com/fwlink/?LinkId=828604](https://go.microsoft.com/fwlink/?LinkId=828604)

## <a name="option-2-use-a-new-agent-on-windows-server-2012-r2-or-windows-server-2016"></a>Opción 2: Usar un nuevo agente en Windows Server 2012 R2 o Windows Server 2016

*Esta opción se aplica a los servidores que ejecutan Windows Server 2012 R2 y Windows Server 2016.*

En abril de 2022 se lanzó un nuevo agente para Windows Server 2012 R2 y Windows Server 2016. El nuevo agente no depende de MMA. El cambio a este nuevo agente ofrece importantes ventajas, como un conjunto de características muy extendido. Para obtener más información, consulte [Tech Community Blog: Defender Windows Server 2012 R2 y 2016](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/defending-windows-server-2012-r2-and-2016/ba-p/2783292).

- Administración de vulnerabilidades de Microsoft Defender proporciona una evaluación (SCID-2030) titulada "Actualizar Microsoft Defender para punto de conexión componentes principales" que le permitirá realizar un seguimiento de qué Windows Server 2012  Las máquinas R2 y 2016 aún no se han actualizado.

- Consulte [Escenarios de migración del servidor de la solución de Microsoft Defender para punto de conexión anterior basada en MMA](server-migration.md) para comprender las opciones para actualizar al nuevo agente.

- Si usa Microsoft Endpoint Configuration Manager (SCCM/ConfigMgr) 2107 o posterior para administrar los servidores que ejecutan Windows Server 2012 R2 o Windows Server 2016, consulte [Migración de servidores de Microsoft Monitoring Agent a la solución unificada](application-deployment-via-mecm.md) para realizar una actualización **orquestada**.

- Si usa Microsoft Endpoint Configuration Manager (SCCM/ConfigMgr) 2207 o posterior para administrar los servidores que ejecutan Windows Server 2012 R2 o Windows Server 2016, consulte [Incorporación a Microsoft Defender para punto de conexión con Configuration Manager 2207 y versiones posteriores](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection) para realizar una actualización **automatizada**.

- Si usa Microsoft Defender for Cloud con servidores que ejecutan Windows Server 2012 R2 o Windows Server 2016, puede automatizar la actualización seleccionando **Habilitar solución unificada**. Consulte [Usuarios con Defender para servidores habilitado y Microsoft Defender para punto de conexión implementados](/azure/defender-for-cloud/integration-defender-for-endpoint?tabs=windows).

## <a name="important-information-about-mma"></a>Información importante sobre MMA

- Si ha determinado que no usa MMA para Defender para punto de conexión o que ya ha actualizado el agente, no se necesitan otros pasos. 

- Sin embargo, si sigue usando MMA para otros fines (como Log Analytics), MMA está actualmente establecido para retirarse en agosto de 2024. Consulte [Retirada del agente de Log Analytics en Azure Monitor el 31 de agosto de 2024](https://azure.microsoft.com/updates/were-retiring-the-log-analytics-agent-in-azure-monitor-on-31-august-2024/). En función de su escenario concreto, podría ser un buen momento para actualizar a [Azure Monitoring Agent, el sucesor de MMA](/azure/azure-monitor/agents/azure-monitor-agent-migration). 

> [!IMPORTANT]
> Los dispositivos que ejecutan Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 o Windows Server 2016 que no se hayan actualizado a la [nueva solución unificada](application-deployment-via-mecm.md) seguirán dependiendo de MMA. En tales casos, [AMA](/azure/azure-monitor/agents/agents-overview) no se puede usar como sustituto de Defender para punto de conexión. 