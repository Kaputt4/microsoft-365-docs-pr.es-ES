---
title: Administrar Microsoft Defender para el punto de conexión después de la migración
description: Ahora que has cambiado a Microsoft Defender para Endpoint, el siguiente paso es administrar las características de protección contra amenazas
keywords: post-migration, manage, operations, maintenance, utilization, Microsoft Defender for Endpoint, edr
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
- m365solution-scenario
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: 2d34ec5ac2fe7578e610353a21f9230c699c6a3c
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220449"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Administrar Microsoft Defender para el punto de conexión, después de la migración

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Después de pasar de la protección de puntos de conexión y la solución antivirus anteriores a Microsoft Defender para Endpoint, el siguiente paso es administrar las características y funcionalidades. Se recomienda usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), que incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction), para administrar los dispositivos y la configuración de seguridad de la organización. Sin embargo, puede usar otras herramientas o métodos, como objetos de directiva de [grupo en Azure Active Directory Domain Services](/azure/active-directory-domain-services/manage-group-policy).

En la tabla siguiente se enumeran varias herramientas o métodos que puede usar, con vínculos para obtener más información.

<br>

****

|Tool/Method|Description|
|---|---|
|**[Amenazas y administración de vulnerabilidades información del panel](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** en el portal [Microsoft 365 Defender](https://security.microsoft.com/) web|El panel de & administración de vulnerabilidades amenazas proporciona información que el equipo de operaciones de seguridad puede usar para reducir la exposición y mejorar la posición de seguridad de la organización. <p> Vea [Threat & administración de vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) and Overview of [Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use).|
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (recomendado)|Microsoft Intune (Intune), un componente de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Con Intune, controlas cómo se usan los dispositivos de tu organización, incluidos teléfonos móviles, tabletas y portátiles. También puede configurar directivas específicas para controlar aplicaciones. <p> Consulte [Manage Microsoft Defender for Endpoint using Intune](manage-atp-post-migration-intune.md).|
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**|Microsoft Endpoint Manager (Configuration Manager), anteriormente conocido como System Center Configuration Manager, es un componente de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview). Configuration Manager es una herramienta eficaz para administrar los usuarios, dispositivos y software. <p> Consulte [Manage Microsoft Defender for Endpoint with Configuration Manager](manage-atp-post-migration-configuration-manager.md).|
|**[Objetos de directiva de grupo en Azure Active Directory de dominio](/azure/active-directory-domain-services/manage-group-policy)**|[Azure Active Directory Domain Services incluye](/azure/active-directory-domain-services/overview) objetos de directiva de grupo integrados para usuarios y dispositivos. Puede personalizar los objetos de directiva de grupo integrados según sea necesario para su entorno, así como crear objetos de directiva de grupo y unidades organizativas (UNIDADES organizativas) personalizadas. <p> Consulte [Manage Microsoft Defender for Endpoint with Group Policy Objects](manage-atp-post-migration-group-policy-objects.md).|
|**[PowerShell, WMI y MPCmdRun.exe](manage-atp-post-migration-other-tools.md)**|*Se recomienda usar Microsoft Endpoint Manager (que incluye Intune y Configuration Manager) para administrar las características de protección contra amenazas en los dispositivos de la organización. Sin embargo, puede configurar algunas opciones, como Antivirus de Microsoft Defender en dispositivos individuales (puntos de conexión) con PowerShell, WMI o la herramienta MPCmdRun.exe usuario.* <p> Puede usar PowerShell para administrar el Antivirus de Microsoft Defender, la protección contra vulnerabilidades y las reglas de reducción de superficie de ataque. Consulte [Configure Microsoft Defender for Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell). <p> Puede usar Windows Instrumental de administración (WMI) para administrar Antivirus de Microsoft Defender y exclusiones. Consulte [Configure Microsoft Defender for Endpoint with WMI](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi). <p> Puede usar microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) para administrar Antivirus de Microsoft Defender y exclusiones, así como validar las conexiones entre la red y la nube. Consulte [Configure Microsoft Defender for Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe).|
|

## <a name="see-also"></a>Consulte también

- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
