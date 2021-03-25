---
title: 'Symantec a Microsoft Defender para endpoint: fase 1, preparación'
description: Esta es la fase 1, Preparar, de migrar de Symantec a Microsoft Defender para Endpoint.
keywords: migración, protección contra amenazas avanzada de Windows Defender, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 8784c8d608666946461ddc27aa2e7f2b740276a0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185496"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Migrar desde Symantec: fase 1: preparar la migración

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: Preparar](images/phase-diagrams/prepare.png)<br/>Fase 1: Preparar |[![Fase 2: Configurar](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: Configurar](symantec-to-microsoft-defender-atp-setup.md) |[![Fase 3: Incorporación](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fase 3: Incorporación](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*¡Estás aquí!*| | |


**Bienvenido a la fase de preparación [de la migración de Symantec a Microsoft Defender para endpoint](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)**. 

Esta fase de migración incluye los siguientes pasos:
1. [Obtener Microsoft Defender para endpoint](#get-microsoft-defender-for-endpoint).
2. [Conceder acceso al Centro de seguridad de Microsoft Defender](#grant-access-to-the-microsoft-defender-security-center).
3. [Configurar el proxy de dispositivo y la configuración de conectividad a Internet.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-microsoft-defender-for-endpoint"></a>Obtener Microsoft Defender para endpoint

Para empezar, debe tener Microsoft Defender para Endpoint, con licencias asignadas y aprovisionadas.

1. Compre o pruebe Microsoft Defender para Endpoint hoy mismo. [Visite Microsoft Defender para endpoint para iniciar una prueba gratuita o solicitar una cita](https://aka.ms/mdatp). 
2. Compruebe que las licencias están aprovisionadas correctamente. [Compruebe el estado de la licencia](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state).
3. Como administrador global o administrador de seguridad, configura la instancia de nube dedicada de Microsoft Defender para Endpoint. Consulte [Configuración del punto de conexión de Microsoft Defender: Configuración del espacio empresarial](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).
4. Si los puntos de conexión (como dispositivos) de su organización usan un proxy para tener acceso a Internet, consulte Configuración de [Microsoft Defender para extremo: Configuración de red](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration).
 
En este momento, está listo para conceder acceso a los administradores de seguridad y operadores de seguridad que usarán el Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> El Centro de seguridad de Microsoft Defender a veces se conoce como el portal de Microsoft Defender para endpoints. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Conceder acceso al Centro de seguridad de Microsoft Defender

El Centro de seguridad de Microsoft Defender ( ) es donde tiene acceso y configura las características y [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) capacidades de Microsoft Defender para endpoint. Para obtener más información, vea [Overview of the Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).

Los permisos del Centro de seguridad de Microsoft Defender se pueden conceder mediante permisos básicos o control de acceso basado en roles (RBAC). Se recomienda usar RBAC para que tenga un control más detallado sobre los permisos.

1. Planee los roles y permisos para los administradores de seguridad y los operadores de seguridad. Vea [Control de acceso basado en roles](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).
2. Configurar y configurar RBAC. Se recomienda usar [Intune para](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) configurar RBAC, especialmente si su organización usa una combinación de dispositivos Windows 10, macOS, iOS y Android. Consulta [configurar RBAC con Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).<br/>
   Si su organización requiere un método distinto de Intune, elija una de las siguientes opciones:
    - [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Administración de directivas de grupo avanzadas](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Centro de administración de Windows](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. Conceder acceso al Centro de seguridad de Microsoft Defender. (¿Necesita ayuda? Consulte [Manage portal access using RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar el proxy de dispositivo y la configuración de conectividad a Internet

Para habilitar la comunicación entre los dispositivos y Microsoft Defender para endpoint, configure la configuración de proxy e Internet. En la tabla siguiente se incluyen vínculos a los recursos que puede usar para configurar el proxy y la configuración de Internet para varios sistemas operativos y capacidades:

|Capacidades  | Sistema operativo | Recursos |
|:----|:----|:---|
|[Detección y respuesta de extremos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 o posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[Configurar el proxy de máquina y la configuración de conectividad a Internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Configuración de proxy y conectividad a Internet](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (Sierra Alta)  |[Microsoft Defender para endpoint para Mac: conexiones de red](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 o posterior](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurar y validar las conexiones de red del Antivirus de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|Antivirus |macOS: <br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave) <br/>- 10.13 (Sierra Alta) |[Microsoft -Defender para endpoint para Mac: conexiones de red](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS o LTS superior<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender para endpoint para Linux: conexiones de red](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections)  |

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena!** Ha completado la fase **de preparación** de la migración [de Symantec a Microsoft Defender para Endpoint](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)!
- [Continúe con la configuración de Microsoft Defender para endpoint](symantec-to-microsoft-defender-atp-setup.md).
