---
title: McAfee to Microsoft Defender for Endpoint - Prepare
description: Esta es la fase 1, Preparar, para migrar de McAfee a Microsoft Defender para Endpoint.
keywords: migración, Microsoft Defender para Endpoint, edr
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 171c9b4ff02e7f6ddb6918e430af772f44b1777a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538788"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a>Migrar desde McAfee: fase 1: preparar la migración

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: Preparación](images/phase-diagrams/prepare.png)<br/>Fase 1: Preparación |[![Fase 2: Configuración](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Fase 2: Configuración](mcafee-to-microsoft-defender-setup.md) |[![Fase 3: Incorporación](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Fase 3: Incorporación](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|*¡Estás aquí!*| | |


**Bienvenido a la fase de preparación de [la migración de McAfee Endpoint Security (McAfee) a Defender for Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)**. 

Esta fase de migración incluye los siguientes pasos:
1. [Obtener e implementar actualizaciones en los dispositivos de la organización](#get-and-deploy-updates-across-your-organizations-devices)

2. [Obtener Defender para endpoint](#get-microsoft-defender-for-endpoint).

3. [Conceder acceso a la Centro de seguridad de Microsoft Defender](#grant-access-to-the-microsoft-defender-security-center).

4. [Configurar el proxy de dispositivo y la configuración de conectividad a Internet.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Obtener e implementar actualizaciones en los dispositivos de la organización

Como práctica recomendada, mantenga actualizados los dispositivos y los puntos de conexión de la organización. Asegúrese de que la solución de McAfee Endpoint Security (McAfee) esté actualizada y de que los sistemas operativos y las aplicaciones de su organización también tengan las actualizaciones más recientes. Hacer esto ahora puede ayudar a evitar problemas más adelante al migrar a Defender para endpoint.

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a>Asegúrese de que la solución de McAfee esté actualizada

Mantenga McAfee actualizado y asegúrese de que los dispositivos de su organización tienen las actualizaciones de seguridad más recientes. ¿Necesita ayuda? Estos son algunos recursos de McAfee:

- [Documentación del producto Enterprise McAfee: cómo funciona Endpoint Security](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [Artículo técnico de McAfee Knowledge Center: Seguridad de Windows Center notifica de forma incorrecta que Endpoint Security está deshabilitado al ejecutarse en Windows 10](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [Artículo técnico de McAfee Knowledge Center: Seguridad de Windows center reports Endpoint Security is disabled when Endpoint Security is running](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- Su soporte técnico de McAfee ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Asegúrese de que los dispositivos de su organización estén actualizados

¿Necesita ayuda para actualizar los dispositivos de su organización? Vea los siguientes recursos:

|Sistema operativo | Resource |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [Cómo actualizar el software en tu Mac](https://support.apple.com/HT201541)|
|iOS |[Actualizar el iPhone, iPad o iPod touch](https://support.apple.com/HT204204)|
|Android |[Comprobar & actualizar la versión de Android](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: actualizar el sistema](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Obtener Microsoft Defender para endpoint

Ahora que ha actualizado los dispositivos de su organización, el siguiente paso es obtener Defender for Endpoint, asignar licencias y asegurarse de que el servicio está aprovisionado.

1. Compre o pruebe Defender for Endpoint hoy mismo. [Inicie una prueba gratuita o solicite una cotización](https://aka.ms/mdatp). 

2. Compruebe que las licencias están aprovisionadas correctamente. [Compruebe el estado de la licencia](production-deployment.md#check-license-state).

3. Como administrador global o administrador de seguridad, configure la instancia de nube dedicada de Defender para endpoint. Vea [Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).

4. Si los puntos de conexión (como dispositivos) de su organización usan un proxy para tener acceso a Internet, vea Configuración de defender para puntos de [conexión: Configuración de red](production-deployment.md#network-configuration).
 
En este punto, está listo para conceder acceso a los administradores de seguridad y operadores de seguridad que usarán el Centro de seguridad de Microsoft Defender ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 

> [!NOTE]
> El Centro de seguridad de Microsoft Defender se conoce a veces como el portal defender para extremo. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Conceder acceso a la Centro de seguridad de Microsoft Defender

El Centro de seguridad de Microsoft Defender ( ) es donde tiene acceso y configura las características y capacidades [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) de Defender para endpoint. Para obtener más información, vea [Overview of the Centro de seguridad de Microsoft Defender](use.md).

Los permisos a la Centro de seguridad de Microsoft Defender pueden concederse mediante permisos básicos o control de acceso basado en roles (RBAC). Se recomienda usar RBAC para que tenga un control más detallado sobre los permisos.

1. Planee los roles y permisos para los administradores de seguridad y los operadores de seguridad. Vea [Control de acceso basado en roles](prepare-deployment.md#role-based-access-control).

2. Configurar y configurar RBAC. Se recomienda usar [Intune para](/mem/intune/fundamentals/what-is-intune) configurar RBAC, especialmente si su organización usa una combinación de dispositivos Windows 10, macOS, iOS y Android. Consulta [configurar RBAC con Intune](/mem/intune/fundamentals/role-based-access-control).

    Si su organización requiere un método distinto de Intune, elija una de las siguientes opciones:

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)

    - [Administración de directivas de grupo avanzadas](/microsoft-desktop-optimization-pack/agpm)

    - [Windows Centro de administración](/windows-server/manage/windows-admin-center/overview)

3. Conceda acceso a la Centro de seguridad de Microsoft Defender. (¿Necesita ayuda? Consulte [Manage portal access using RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Configurar el proxy de dispositivo y la configuración de conectividad a Internet

Para habilitar la comunicación entre los dispositivos y Defender para endpoint, configure la configuración de proxy e Internet. En la tabla siguiente se incluyen vínculos a los recursos que puede usar para configurar el proxy y la configuración de Internet para varios sistemas operativos y capacidades:

|Capacidades  | Sistema operativo | Recursos |
|--|--|--|
| [Detección y respuesta de extremos](overview-endpoint-detection-response.md) (EDR) | [Windows 10](/windows/release-health/release-information) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Servidor 1803 o posterior](/windows-server/get-started/whats-new-in-windows-server-1803)  | [Configurar el proxy de máquina y la configuración de conectividad a Internet](configure-proxy-internet.md) |
|EDR | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) | [Configuración de proxy y conectividad a Internet](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave)  | [Defender para endpoint en macOS: conexiones de red](microsoft-defender-endpoint-mac.md#network-connections) |
|[Antivirus de Microsoft Defender](microsoft-defender-antivirus-in-windows-10.md) | [Windows 10](/windows/release-health/release-information) <p> [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Servidor 1803 o posterior](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Configurar y validar las conexiones de red del Antivirus de Windows Defender](configure-network-connections-microsoft-defender-antivirus.md) |
|Antivirus |macOS: <p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave) |[Defender para endpoint en macOS: conexiones de red](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivirus |Linux: <p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS o LTS superior<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 |[Defender para endpoint en Linux: conexiones de red](microsoft-defender-endpoint-linux.md#network-connections) 

## <a name="next-step"></a>Paso siguiente

**¡Enhorabuena!** Ha completado la fase **de preparación** de la migración [de McAfee a Defender para Endpoint](mcafee-to-microsoft-defender-migration.md#the-migration-process)!

- [Continúe con la configuración de Defender para Endpoint](mcafee-to-microsoft-defender-setup.md).
