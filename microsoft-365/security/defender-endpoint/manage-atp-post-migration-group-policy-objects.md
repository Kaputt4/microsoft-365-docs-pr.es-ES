---
title: Administrar Microsoft Defender para puntos de conexión mediante objetos de directiva de grupo
description: Obtenga información sobre cómo administrar Microsoft Defender para endpoint con objetos de directiva de grupo
keywords: post-migration, manage, operations, maintenance, utilization, PowerShell, Microsoft Defender for Endpoint, edr
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
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 15902e02156c59ec4edaed94f4ba321094bd42ac
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843027"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Administrar Microsoft Defender para puntos de conexión con objetos de directiva de grupo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Se recomienda usar [Microsoft Endpoint Manager](/mem) para administrar las características de protección contra amenazas de la organización para dispositivos (también denominados puntos de conexión). Endpoint Manager incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction). **[Obtenga más información sobre Endpoint Manager](/mem/endpoint-manager-overview)**. 

Puede usar objetos de directiva de grupo en Azure Active Directory Domain Services para administrar algunas opciones de configuración en Microsoft Defender para endpoint.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Configurar Microsoft Defender para el extremo con objetos de directiva de grupo

En la tabla siguiente se enumeran varias tareas que puede realizar para configurar Microsoft Defender para endpoint con objetos de directiva de grupo.

|Tarea  |Recursos para obtener más información  |
|---------|---------|
|**Administrar la configuración de objetos de usuario y equipo** <br/><br/>*Personalice objetos de directiva de grupo integrados o cree objetos de directiva de grupo y unidades organizativas personalizados para satisfacer sus necesidades organizativas.*     |[Administrar directiva de grupo en un Azure Active Directory administrado de servicios de dominio](/azure/active-directory-domain-services/manage-group-policy)   |
|**Configurar Antivirus de Microsoft Defender** <br/><br/>*Configure características antivirus & funcionalidades, incluidas las opciones de directiva, exclusiones, corrección y exámenes programados en los dispositivos de la organización (también denominados puntos de conexión).*   |[Usar la configuración de directiva de grupo para configurar y administrar Antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Usar la directiva de grupo para habilitar la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**Administrar las reglas de reducción de superficie de ataque de la organización** <br/><br/>*Personalice las reglas de reducción de superficie de ataque excluyendo los archivos & carpetas o agregando texto personalizado a las alertas de notificación que aparecen en los dispositivos de los usuarios.* |[Personalizar reglas de reducción de superficie de ataque con objetos de directiva de grupo](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Administrar la configuración de protección contra vulnerabilidades**<br/><br/>*Puede personalizar la configuración de protección contra vulnerabilidades de seguridad, importar un archivo de configuración y, a continuación, usar la directiva de grupo para implementar ese archivo de configuración.*  |[Personalizar la configuración de protección contra vulnerabilidades](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Importar, exportar e implementar configuraciones de protección de vulnerabilidades de seguridad](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Usar la directiva de grupo para distribuir la configuración](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Habilitar la protección de** red para ayudar a evitar que los empleados utilicen aplicaciones que usan contenido malintencionado en Internet <br/><br/>*Se recomienda usar [el modo de auditoría](/microsoft-365/security/defender-endpoint/evaluate-network-protection) al principio para la protección de red en un entorno de prueba para ver qué aplicaciones se bloquearían antes de implementarse.* |[Activar la protección de red mediante la directiva de grupo](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Configurar el acceso controlado a carpetas** para proteger contra ransomware <br/><br/>*[El acceso controlado a](/microsoft-365/security/defender-endpoint/controlled-folders) carpetas también se conoce como protección antiransomware.*  |[Habilitar el acceso controlado a carpetas mediante la directiva de grupo](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Configure SmartScreen de Microsoft Defender** para proteger contra sitios y archivos malintencionados en Internet.  |[Configurar SmartScreen de Microsoft Defender de directiva de grupo y administración de dispositivos móviles (MDM) mediante la directiva de grupo](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Configurar el cifrado y BitLocker** para proteger la información en los dispositivos de la organización que se ejecutan Windows |[BitLocker Configuración de directiva de grupo](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Configurar Credential Guard de Microsoft Defender** para protegerse contra ataques de robo de credenciales |[Habilitar Credential Guard de Windows Defender mediante la directiva de grupo](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurar el Centro de seguridad de Microsoft Defender

Si aún no lo ha hecho, configure su **Centro de seguridad de Microsoft Defender** ( ) para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de su [https://securitycenter.windows.com](https://securitycenter.windows.com) organización. 

También puede configurar si los usuarios finales pueden ver y qué características pueden ver en el Centro de seguridad de Microsoft Defender.

- [Información general sobre el Centro de seguridad de Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Protección de extremo: Centro de seguridad de Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información general sobre Administración de amenazas y vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite el panel Centro de seguridad de Microsoft Defender operaciones de seguridad](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Administrar Microsoft Defender para endpoint con Intune](manage-atp-post-migration-intune.md)
