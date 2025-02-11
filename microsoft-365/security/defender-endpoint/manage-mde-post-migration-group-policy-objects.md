---
title: Administración de Microsoft Defender para punto de conexión mediante objetos समूह नीति
description: Aprenda a administrar Microsoft Defender para punto de conexión con objetos समूह नीति
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
- m365-security
- tier2
ms.topic: conceptual
ms.reviewer: chventou
search.appverid: met150
ms.openlocfilehash: 0c3e6dbc9c39d24ea7f9227151fb9d9c1fc6be3c
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68646625"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Administración de Microsoft Defender para punto de conexión con objetos समूह नीति

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Se recomienda usar [Microsoft Endpoint Manager](/mem) para administrar las características de protección contra amenazas de su organización para dispositivos (también conocidos como puntos de conexión). Endpoint Manager incluye [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) y [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction). **[Más información sobre Endpoint Manager](/mem/endpoint-manager-overview)**.

Puede usar समूह नीति Objects en Azure Active Directory डोमेन सेवाहरू para administrar algunas opciones de configuración en Microsoft Defender para punto de conexión.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Configuración de Microsoft Defender para punto de conexión con objetos समूह नीति

> [!NOTE]
> Si usa [la nueva solución de Microsoft Defender para punto de conexión unificada para Windows Server 2012 R2 y 2016](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview), asegúrese de que usa los archivos ADMX más recientes en la tienda central para obtener acceso a la correcta. Microsoft Defender para punto de conexión opciones de directiva. Consulta [Cómo crear y administrar la Tienda central para समूह नीति plantillas administrativas en Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) y descarga los archivos más recientes **para usarlos con Windows 10**. 

En la tabla siguiente se enumeran varias tareas que puede realizar para configurar Microsoft Defender para punto de conexión con objetos समूह नीति.

|Tarea|Recursos para obtener más información|
|---|---|
|**Administrar la configuración de los objetos de usuario y equipo** <br/><br/> *Personalice objetos de समूह नीति integrados o cree objetos de समूह नीति personalizados y unidades organizativas que se adapten a sus necesidades organizativas.*|[Administración de समूह नीति en un dominio administrado de Azure Active Directory डोमेन सेवाहरू](/azure/active-directory-domain-services/manage-group-policy)|
|**Configurar Microsoft Defender Antivirus** <br/><br/> *Configure características antivirus & funcionalidades, incluida la configuración de directivas, exclusiones, corrección y exámenes programados en los dispositivos de la organización (también conocidos como puntos de conexión).*|[Usar समूह नीति configuración para configurar y administrar Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/> [Uso de समूह नीति para habilitar la protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)|
|**Administrar las reglas de reducción de superficie expuesta a ataques de la organización** <br/><br/> *Personalice las reglas de reducción de la superficie expuesta a ataques excluyendo archivos & carpetas o agregando texto personalizado a las alertas de notificación que aparecen en los dispositivos de los usuarios.*|[Personalización de reglas de reducción de superficie expuesta a ataques con objetos समूह नीति](/microsoft-365/security/defender-endpoint/attack-surface-reduction-rules-deployment-implement)|
|**Administración de la configuración de protección contra vulnerabilidades** <br/><br/> *Puede personalizar la configuración de protección contra vulnerabilidades de seguridad, importar un archivo de configuración y, a continuación, usar समूह नीति para implementar ese archivo de configuración.*|[Personalización de la configuración de protección contra vulnerabilidades](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/> [Importar, exportar e implementar configuraciones de protección de vulnerabilidades de seguridad](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml) <br/><br/> [Usar la directiva de grupo para distribuir la configuración](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)|
|**Habilitar Protección de red** para evitar que los empleados usen aplicaciones que contengan contenido malintencionado en Internet <br/><br/> *Se recomienda usar el [modo de auditoría](/microsoft-365/security/defender-endpoint/evaluate-network-protection) al principio para la protección de red en un entorno de prueba para ver qué aplicaciones se bloquearían antes de implementarse.*|[Activar la protección de red mediante समूह नीति](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)|
|**Configuración del acceso controlado a carpetas** para protegerse frente a ransomware <br/><br/> *[El acceso controlado a carpetas](/microsoft-365/security/defender-endpoint/controlled-folders) también se conoce como protección contra antiransomware.*|[Habilitación del acceso controlado a carpetas mediante समूह नीति](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy)|
|**Configure Microsoft Defender SmartScreen** para protegerse frente a sitios y archivos malintencionados en Internet.|[Configuración de Microsoft Defender smartscreen समूह नीति y administración de dispositivos móviles (MDM) mediante समूह नीति](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)|
|**Configuración del cifrado y BitLocker** para proteger la información sobre los dispositivos de la organización que ejecutan Windows|[Configuración de समूह नीति de BitLocker](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings)|
|**Configuración de Microsoft Defender Credential Guard** para protegerse frente a ataques de robo de credenciales|[Habilitar Windows डिफेन्डर Credential Guard mediante समूह नीति](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy)|

## <a name="configure-your-microsoft-365-defender-portal"></a>Configuración del portal de Microsoft 365 Defender

Si aún no lo ha hecho, configure el portal de Microsoft 365 Defender para ver alertas, configurar características de protección contra amenazas y ver información detallada sobre la posición de seguridad general de la organización. Consulte [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). También puede configurar si y qué características pueden ver los usuarios finales en el portal de Microsoft 365 Defender.

- [Introducción a Microsoft 365 Defender](/microsoft-365/security/defender-endpoint/use)
- [Endpoint Protection: Microsoft 365 Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Pasos siguientes

- [Obtenga información general sobre la administración de vulnerabilidades de Defender](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [Administración de Microsoft Defender para punto de conexión con Intune](manage-mde-post-migration-intune.md)
