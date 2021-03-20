---
title: Ampliar la cobertura de búsqueda avanzada con la configuración correcta
description: Comprueba la configuración de auditoría en dispositivos Windows y otras configuraciones para asegurarte de obtener los datos más completos en la búsqueda avanzada
keywords: búsqueda avanzada, incidente, pivot, entidad, configuración de auditoría, administración de cuentas de usuario, administración de grupos de seguridad, búsqueda de amenazas, búsqueda, consulta, telemetría, Microsoft 365, Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 856f61aac8e7297f1b5dfb3aadc46da06cb16289
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907225"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Ampliar la cobertura de búsqueda avanzada con la configuración correcta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[La búsqueda avanzada](advanced-hunting-overview.md) se basa en datos procedentes de varios orígenes, incluidos los dispositivos, las áreas de trabajo de Office 365, Azure AD y Microsoft Defender para identity. Para obtener los datos más completos posibles, asegúrese de que tiene la configuración correcta en los orígenes de datos correspondientes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoría de seguridad avanzada en dispositivos Windows
Activa esta configuración de auditoría avanzada para asegurarte de obtener datos sobre actividades en tus dispositivos, incluida la administración de cuentas locales, la administración de grupos de seguridad local y la creación de servicios.

| Datos | Descripción | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Administración de cuentas | Eventos capturados como varios valores que indican la creación, eliminación y `ActionType` otras actividades relacionadas con la cuenta local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementar una directiva de auditoría de seguridad avanzada: [Auditar administración de cuentas de usuario](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Obtenga información sobre las directivas de auditoría de seguridad avanzada](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Administración de grupos de seguridad | Eventos capturados como varios valores que indican la creación de grupos `ActionType` de seguridad locales y otras actividades de administración de grupos locales | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementar una directiva de auditoría de seguridad avanzada: [Auditar la administración de grupos de seguridad](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Obtenga información sobre las directivas de auditoría de seguridad avanzada](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Instalación del servicio | Eventos capturados con el valor , que indican que se ha creado `ActionType` `ServiceInstalled` un servicio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementar una directiva de auditoría de seguridad avanzada: [Extensión del sistema de seguridad de auditoría](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Obtenga información sobre las directivas de auditoría de seguridad avanzada](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Sensor de Microsoft Defender para identidad en el controlador de dominio
Si ejecuta Active Directory localmente, debe instalar el sensor de Microsoft Defender para identidad en el controlador de dominio para obtener datos de Microsoft Defender para Identity. Cuando se instalan y configuran correctamente, estos datos también se alimentan de búsquedas avanzadas a través de Microsoft Defender for Identity y proporcionan una imagen más holística de la información de identidad y los eventos de la red. Estos datos también mejoran la capacidad de Microsoft Defender for Identity para generar alertas relevantes que también están cubiertas por la búsqueda avanzada. 

| Datos | Descripción | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Controlador de dominio | Datos de Active Directory local enviados a Microsoft Defender para identidad, enriqueciendo información relacionada con la identidad, como detalles de cuenta, actividad de inicio de sesión y consultas de Active Directory | Varias tablas, incluidas [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Instalar el sensor de Microsoft Defender para identidad](/azure-advanced-threat-protection/install-atp-step4)<br>- [Activar eventos relevantes de Windows](/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)