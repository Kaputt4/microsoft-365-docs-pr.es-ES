---
title: Administración de Microsoft Defender para punto de conexión después de la instalación o migración iniciales
description: Ahora que ha realizado el cambio a Microsoft Defender para punto de conexión, el siguiente paso es administrar las características de protección contra amenazas.
keywords: posterior a la migración, administración, operaciones, mantenimiento, uso, Microsoft Defender para punto de conexión, edr
ms.service: microsoft-365-security
ms.subservice: mde
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
ms.topic: conceptual
ms.date: 07/01/2022
ms.reviewer: chventou
ms.openlocfilehash: f5f0532e4bbcbbbfac19b1b5d123000e447404d7
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67522419"
---
# <a name="manage-microsoft-defender-for-endpoint-after-initial-setup-or-migration"></a>Administración de Microsoft Defender para punto de conexión después de la instalación o migración iniciales

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Después de configurar y configurar Microsoft Defender para punto de conexión, el siguiente paso es administrar las características y funcionalidades. Se recomienda usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), que incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y Configuration Manager de punto de conexión de [Microsoft](/mem/configmgr/core/understand/introduction), para administrar los dispositivos y la configuración de seguridad de la organización. Sin embargo, puede usar otras herramientas o métodos, como [directiva de grupo Objects en Azure Servicios de dominio de Active Directory](/azure/active-directory-domain-services/manage-group-policy).

En la tabla siguiente se enumeran varias herramientas o métodos que puede usar, con vínculos para obtener más información.

|Herramienta o método|Descripción|
|---|---|
|**[Administración de vulnerabilidades de Microsoft Defender información del panel](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** en el portal [de Microsoft 365 Defender](https://security.microsoft.com/)|El panel de Administración de vulnerabilidades de Defender proporciona información accionable que el equipo de operaciones de seguridad puede usar para reducir la exposición y mejorar la posición de seguridad de la organización. <br/><br/> Consulte [Administración de vulnerabilidades de Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) e [Información general de Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use).|
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (recomendado)|Microsoft Intune (Intune), un componente de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Con Intune, puede controlar cómo se usan los dispositivos de su organización, incluidos teléfonos móviles, tabletas y portátiles. También puede configurar directivas específicas para controlar las aplicaciones. <br/><br/> Consulte [Administración de Microsoft Defender para punto de conexión mediante Intune](manage-mde-post-migration-intune.md).|
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**|Microsoft Endpoint Manager (Configuration Manager), anteriormente conocido como System Center Configuration Manager, es un componente de [Microsoft Endpoint Manager](/mem/endpoint-manager-overview). Configuration Manager es una herramienta eficaz para administrar los usuarios, dispositivos y software. <br/><br/> Consulte [Administración de Microsoft Defender para punto de conexión con Configuration Manager](manage-mde-post-migration-configuration-manager.md).|
|**[objetos directiva de grupo en Azure Servicios de dominio de Active Directory](/azure/active-directory-domain-services/manage-group-policy)**|[Azure Servicios de dominio de Active Directory](/azure/active-directory-domain-services/overview) incluye objetos directiva de grupo integrados para usuarios y dispositivos. Puede personalizar los objetos de directiva de grupo integrados según sea necesario para su entorno, así como crear objetos de directiva de grupo personalizados y unidades organizativas (OU). <br/><br/> Consulte [Administración de Microsoft Defender para punto de conexión con objetos directiva de grupo](manage-mde-post-migration-group-policy-objects.md).|
|**[PowerShell, WMI y MPCmdRun.exe](manage-mde-post-migration-other-tools.md)**|*Se recomienda usar Microsoft Endpoint Manager (que incluye Intune y Configuration Manager) para administrar las características de protección contra amenazas en los dispositivos de la organización. Sin embargo, puede configurar algunas opciones, como antivirus de Microsoft Defender en dispositivos individuales (puntos de conexión) con PowerShell, WMI o la herramienta de MPCmdRun.exe.* <br/><br/> Puede usar PowerShell para administrar el Antivirus de Microsoft Defender, la protección contra vulnerabilidades de seguridad y las reglas de reducción de la superficie expuesta a ataques. Consulte [Configuración de Microsoft Defender para punto de conexión con PowerShell](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell). <br/><br/> Puede usar Instrumental de administración de Windows (WMI) para administrar el Antivirus de Microsoft Defender y las exclusiones. Consulte [Configuración de Microsoft Defender para punto de conexión con WMI](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi). <br/><br/> Puede usar la Utilidad de Command-Line de Protección contra malware de Microsoft (MPCmdRun.exe) para administrar antivirus y exclusiones de Microsoft Defender, así como validar las conexiones entre la red y la nube. Vea [Configurar Microsoft Defender para punto de conexión con MPCmdRun.exe](manage-mde-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe).|


## <a name="see-also"></a>Vea también

- [Abordar falsos positivos/negativos en Microsoft Defender para punto de conexión](defender-endpoint-false-positives-negatives.md)
