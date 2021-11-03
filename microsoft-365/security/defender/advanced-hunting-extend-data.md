---
title: Ampliar la cobertura de búsqueda avanzada con la configuración correcta
description: Comprobar la configuración de auditoría en Windows dispositivos y otras configuraciones para ayudar a garantizar que obtiene los datos más completos en la búsqueda avanzada
keywords: búsqueda avanzada, incidente, pivot, entidad, configuración de auditoría, administración de cuentas de usuario, administración de grupos de seguridad, búsqueda de amenazas, búsqueda, consulta, telemetría, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: dd61fa434eaf2130f0fcb0f28df9a20d696e04ec
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "60665362"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Ampliar la cobertura de búsqueda avanzada con la configuración correcta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

[La búsqueda avanzada](advanced-hunting-overview.md) se basa en datos procedentes de varios orígenes, incluidos los dispositivos, las áreas de trabajo Office 365, Azure AD y Microsoft Defender for Identity. Para obtener los datos más completos posibles, asegúrese de que tiene la configuración correcta en los orígenes de datos correspondientes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoría de seguridad avanzada en Windows dispositivos
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
| Controlador de dominio  | Datos de Active Directory local enviados a Microsoft Defender para identidad, enriqueciendo información relacionada con la identidad, como detalles de cuenta, actividad de inicio de sesión y consultas de Active Directory | Varias tablas, incluidas [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Instalar el sensor de Microsoft Defender para identidad](/azure-advanced-threat-protection/install-atp-step4)<br>- [Activar eventos de Windows relevantes](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para endpoint. [Activa la Microsoft 365 Defender](m365d-enable.md) para buscar amenazas con más orígenes de datos. Puede mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para endpoint a Microsoft 365 Defender siguiendo los pasos descritos en Migrar consultas avanzadas de búsqueda desde [Microsoft Defender para endpoint](advanced-hunting-migrate-from-mde.md).

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)