---
title: Administración de Microsoft Defender para punto de conexión mediante objetos directiva de grupo
description: Aprenda a administrar Microsoft Defender para punto de conexión con objetos directiva de grupo
keywords: posterior a la migración, administración, operaciones, mantenimiento, uso, PowerShell, Microsoft Defender para punto de conexión, edr
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
ms.topic: article
ms.reviewer: chventou
search.appverid: met150
ms.openlocfilehash: aad517708cb786e4b0c385c86f28d120fd822414
ms.sourcegitcommit: 2dedd0f594b817779e034afa6c4418def2382a22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2022
ms.locfileid: "67799382"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Administración de Microsoft Defender para punto de conexión con objetos directiva de grupo

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Se recomienda usar [Microsoft Endpoint Manager](/mem) para administrar las características de protección contra amenazas de su organización para dispositivos (también conocidos como puntos de conexión). Endpoint Manager incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Configuration Manager de punto de conexión de Microsoft](/mem/configmgr/core/understand/introduction). **[Más información sobre Endpoint Manager](/mem/endpoint-manager-overview)**.

Puede usar directiva de grupo Objects en Azure Servicios de dominio de Active Directory para administrar algunas opciones de configuración en Microsoft Defender para punto de conexión.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Configuración de Microsoft Defender para punto de conexión con objetos directiva de grupo

> [!NOTE]
> Si usa [la nueva solución de Microsoft Defender para punto de conexión unificada para Windows Server 2012 R2 y 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview), asegúrese de que usa los archivos ADMX más recientes en la tienda central para obtener acceso a la correcta. Microsoft Defender para punto de conexión opciones de directiva. Consulta [Cómo crear y administrar la Tienda Central para plantillas administrativas de directiva de grupo en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) y descarga los archivos más recientes **para usarlos con Windows 10**. 

En la tabla siguiente se enumeran varias tareas que puede realizar para configurar Microsoft Defender para punto de conexión con directiva de grupo Objects.

|Tarea|Recursos para obtener más información|
|---|---|
|**Administrar la configuración de los objetos de usuario y equipo** <br/><br/> *Personalice objetos directiva de grupo integrados o cree objetos de directiva de grupo personalizados y unidades organizativas para satisfacer sus necesidades organizativas.*|[Administración de directiva de grupo en un dominio administrado de Azure Servicios de dominio de Active Directory](/azure/active-directory-domain-services/manage-group-policy)|
|**Configuración del Antivirus de Microsoft Defender** <br/><br/> *Configure características antivirus & funcionalidades, incluida la configuración de directivas, exclusiones, corrección y exámenes programados en los dispositivos de la organización (también conocidos como puntos de conexión).*|[Uso de directiva de grupo configuración para configurar y administrar antivirus de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/> [Uso de directiva de grupo para habilitar la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)|
|**Administrar las reglas de reducción de superficie expuesta a ataques de la organización** <br/><br/> *Personalice las reglas de reducción de la superficie expuesta a ataques excluyendo archivos & carpetas o agregando texto personalizado a las alertas de notificación que aparecen en los dispositivos de los usuarios.*|[Personalización de reglas de reducción de superficie expuesta a ataques con objetos directiva de grupo](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules-deployment-implement)|
|**Administración de la configuración de protección contra vulnerabilidades** <br/><br/> *Puede personalizar la configuración de protección contra vulnerabilidades de seguridad, importar un archivo de configuración y, a continuación, usar directiva de grupo para implementar ese archivo de configuración.*|[Personalización de la configuración de protección contra vulnerabilidades](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/> [Importar, exportar e implementar configuraciones de protección de vulnerabilidades de seguridad](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml) <br/><br/> [Usar la directiva de grupo para distribuir la configuración](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)|
|**Habilitar Protección de red** para evitar que los empleados usen aplicaciones que contengan contenido malintencionado en Internet <br/><br/> *Se recomienda usar el [modo de auditoría](/microsoft-365/security/defender-endpoint/evaluate-network-protection) al principio para la protección de red en un entorno de prueba para ver qué aplicaciones se bloquearían antes de implementarse.*|[Activar la protección de red mediante directiva de grupo](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)|
|**Configuración del acceso controlado a carpetas** para protegerse frente a ransomware <br/><br/> *[El acceso controlado a carpetas](/microsoft-365/security/defender-endpoint/controlled-folders) también se conoce como protección contra antiransomware.*|[Habilitación del acceso controlado a carpetas mediante directiva de grupo](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy)|
|**Configure SmartScreen de Microsoft Defender** para protegerse frente a sitios y archivos malintencionados en Internet.|[Configuración de smartscreen de Microsoft Defender directiva de grupo y administración de dispositivos móviles (MDM) mediante directiva de grupo](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)|
|**Configuración del cifrado y BitLocker** para proteger la información sobre los dispositivos de la organización que ejecutan Windows|[Configuración de directiva de grupo de BitLocker](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings)|
|**Configuración de Credential Guard de Microsoft Defender** para protegerse frente a ataques de robo de credenciales|[Habilitar Windows Defender Credential Guard mediante directiva de grupo](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Configuración del portal de Microsoft 365 Defender

Si aún no lo ha hecho, configure el portal de Microsoft 365 Defender para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de la organización. Consulte [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). También puede configurar si y qué características pueden ver los usuarios finales en el portal de Microsoft 365 Defender.

- [Introducción a Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [Endpoint Protection: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información general sobre la administración de vulnerabilidades de Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Administración de Microsoft Defender para punto de conexión con Intune](manage-mde-post-migration-intune.md)
