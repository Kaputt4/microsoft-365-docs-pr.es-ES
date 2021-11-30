---
title: Administrar Microsoft Defender para el punto de conexión después de la migración
description: Ahora que has cambiado a Microsoft Defender para Endpoint, el siguiente paso es administrar las características de protección contra amenazas
keywords: post-migration, manage, operations, maintenance, utilization, Microsoft Defender for Endpoint, edr
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: conceptual
ms.date: 11/29/2021
ms.reviewer: chventou
ms.openlocfilehash: 2be934da8a87e02ead5c395097d90ccde46cb9d7
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221631"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Administrar Microsoft Defender para el punto de conexión, después de la migración

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Después de pasar de la protección de puntos de conexión y la solución antivirus anteriores a Microsoft Defender para Endpoint, el siguiente paso es administrar las características y funcionalidades. Se recomienda usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), que incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction), para administrar los dispositivos y la configuración de seguridad de la organización. Sin embargo, puede usar otras herramientas o métodos, como objetos de directiva de [grupo en Azure Active Directory Domain Services](/azure/active-directory-domain-services/manage-group-policy).

En la tabla siguiente se enumeran varias herramientas o métodos que puede usar, con vínculos para obtener más información.

<br/><br/>

|Tool/Method|Descripción|
|---|---|
|**[Amenazas y administración de vulnerabilidades información del panel](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** en el portal [Microsoft 365 Defender](https://security.microsoft.com/) web|El panel de & administración de vulnerabilidades amenazas proporciona información que el equipo de operaciones de seguridad puede usar para reducir la exposición y mejorar la posición de seguridad de la organización. <br/><br/> Vea [Threat & administración de vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) and Overview of [Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use).|
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (recomendado)|Microsoft Intune (Intune), un componente de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Con Intune, controlas cómo se usan los dispositivos de tu organización, incluidos teléfonos móviles, tabletas y portátiles. También puede configurar directivas específicas para controlar las aplicaciones. <br/><br/> Consulte [Manage Microsoft Defender for Endpoint using Intune](manage-mde-post-migration-intune.md).|
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**|Microsoft Endpoint Manager (Configuration Manager), anteriormente conocido como System Center Configuration Manager, es un componente de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview). Configuration Manager es una herramienta eficaz para administrar los usuarios, dispositivos y software. <br/><br/> Consulte [Manage Microsoft Defender for Endpoint with Configuration Manager](manage-mde-post-migration-configuration-manager.md).|
|**[Objetos de directiva de grupo en Azure Active Directory de dominio](/azure/active-directory-domain-services/manage-group-policy)**|[Azure Active Directory Domain Services incluye](/azure/active-directory-domain-services/overview) objetos de directiva de grupo integrados para usuarios y dispositivos. Puede personalizar los objetos de directiva de grupo integrados según sea necesario para su entorno, así como crear objetos de directiva de grupo y unidades organizativas (UNIDADES organizativas) personalizadas. <br/><br/> Consulte [Manage Microsoft Defender for Endpoint with Group Policy Objects](manage-mde-post-migration-group-policy-objects.md).|
|**[PowerShell, WMI y MPCmdRun.exe](manage-mde-post-migration-other-tools.md)**|*Se recomienda usar Microsoft Endpoint Manager (que incluye Intune y Configuration Manager) para administrar las características de protección contra amenazas en los dispositivos de la organización. Sin embargo, puede configurar algunas opciones, como Antivirus de Microsoft Defender en dispositivos individuales (puntos de conexión) con PowerShell, WMI o la herramienta MPCmdRun.exe usuario.* <br/><br/> Puede usar PowerShell para administrar el Antivirus de Microsoft Defender, la protección contra vulnerabilidades y las reglas de reducción de superficie de ataque. Consulte [Configure Microsoft Defender for Endpoint with PowerShell](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell). <br/><br/> Puede usar Windows Instrumental de administración (WMI) para administrar Antivirus de Microsoft Defender y exclusiones. Consulte [Configure Microsoft Defender for Endpoint with WMI](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi). <br/><br/> Puede usar microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) para administrar Antivirus de Microsoft Defender y exclusiones, así como validar las conexiones entre la red y la nube. Consulte [Configure Microsoft Defender for Endpoint with MPCmdRun.exe](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe).|


## <a name="see-also"></a>Consulte también

- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
