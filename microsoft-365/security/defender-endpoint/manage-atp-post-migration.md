---
title: Administrar Microsoft Defender para el punto de conexión después de la migración
description: Ahora que has cambiado a Microsoft Defender para Endpoint, el siguiente paso es administrar las características de protección contra amenazas
keywords: post-migration, manage, operations, maintenance, utilization, windows defender advanced threat protection, atp, edr
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
ms.openlocfilehash: fbc0abdb9def860df7e553963d7fa3c7f5b5da24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074336"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Administrar Microsoft Defender para el punto de conexión, después de la migración

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Después de pasar de la protección de puntos de conexión y la solución antivirus anteriores a Microsoft Defender para Endpoint, el siguiente paso es administrar las características y funcionalidades. Se recomienda usar [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview), que incluye Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) y Microsoft Endpoint [Configuration Manager,](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)para administrar los dispositivos y la configuración de seguridad de la organización. Sin embargo, puede usar otras herramientas o métodos, como objetos de directiva de [grupo en Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy). 

En la tabla siguiente se enumeran varias herramientas o métodos que puede usar, con vínculos para obtener más información. 
<br/><br/>

|Tool/Method  |Descripción  |
|---------|---------|
|**[Información del panel de administración de](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** amenazas y vulnerabilidades en el Centro de seguridad de Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |El panel & administración de vulnerabilidades proporciona información que puede usar el equipo de operaciones de seguridad para reducir la exposición y mejorar la posición de seguridad de la organización. <br/><br/>Consulte [Administración & vulnerabilidades y](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) Información general del Centro de seguridad de Microsoft [Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).  |
|**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (recomendado)    |Microsoft Intune (Intune), un componente de [Microsoft Endpoint Manager,](https://docs.microsoft.com/mem/endpoint-manager-overview)se centra en la administración de dispositivos móviles (MDM) y la administración de aplicaciones móviles (MAM). Con Intune, controlas cómo se usan los dispositivos de tu organización, incluidos teléfonos móviles, tabletas y portátiles. También puede configurar directivas específicas para controlar aplicaciones. <br/><br/>Consulte [Manage Microsoft Defender for Endpoint using Intune](manage-atp-post-migration-intune.md).         |
|**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**     |Microsoft Endpoint Manager (Configuration Manager), anteriormente conocido como System Center Configuration Manager, es un componente de [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview). Configuration Manager es una herramienta eficaz para administrar los usuarios, dispositivos y software.<br/><br/>Consulte [Manage Microsoft Defender for Endpoint with Configuration Manager](manage-atp-post-migration-configuration-manager.md).        |
|**[Objetos de directiva de grupo en Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/overview) incluye objetos de directiva de grupo integrados para usuarios y dispositivos. Puede personalizar los objetos de directiva de grupo integrados según sea necesario para su entorno, así como crear objetos de directiva de grupo y unidades organizativas (UNIDADES organizativas) personalizadas. <br/><br/>Consulte [Manage Microsoft Defender for Endpoint with Group Policy Objects](manage-atp-post-migration-group-policy-objects.md). |
|**[PowerShell, WMI y MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Se recomienda usar Microsoft Endpoint Manager (que incluye Intune y Configuration Manager) para administrar las características de protección contra amenazas en los dispositivos de la organización. Sin embargo, puede configurar algunas opciones de configuración, como Antivirus de Microsoft Defender en dispositivos individuales (puntos de conexión) con PowerShell, WMI o la herramienta MPCmdRun.exe usuario.*<br/><br/>Puede usar PowerShell para administrar el Antivirus de Microsoft Defender, la protección contra vulnerabilidades de seguridad y las reglas de reducción de superficie de ataque. Consulte [Configure Microsoft Defender for Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell).<br/><br/>Puedes usar Instrumental de administración de Windows (WMI) para administrar el Antivirus y las exclusiones de Microsoft Defender. Consulte [Configure Microsoft Defender for Endpoint with WMI](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi).<br/><br/>Puede usar la Utilidad de microsoft malware protection Command-Line (MPCmdRun.exe) para administrar el Antivirus y las exclusiones de Microsoft Defender, así como validar las conexiones entre la red y la nube. Consulte [Configure Microsoft Defender for Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe). |

## <a name="see-also"></a>Ver también

- [Dirección de falsos positivos/negativos en Microsoft Defender para endpoint](defender-endpoint-false-positives-negatives.md)
