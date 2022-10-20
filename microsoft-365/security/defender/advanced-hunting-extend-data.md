---
title: Ampliación de la cobertura de búsqueda avanzada con la configuración adecuada
description: Compruebe la configuración de auditoría en dispositivos Windows y otras configuraciones para asegurarse de que obtiene los datos más completos en la búsqueda avanzada.
keywords: advanced hunting, incident, pivot, entity, audit settings, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.openlocfilehash: 1c2e0ef6b07f746ba88e190807ef914a9948b8f8
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68625421"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Ampliación de la cobertura de búsqueda avanzada con la configuración adecuada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

[La búsqueda avanzada](advanced-hunting-overview.md) se basa en datos procedentes de varios orígenes, incluidos los dispositivos, las áreas de trabajo de Office 365, Azure AD y Microsoft Defender for Identity. Para obtener los datos más completos posibles, asegúrese de que tiene la configuración correcta en los orígenes de datos correspondientes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoría de seguridad avanzada en dispositivos Windows
Active esta configuración de auditoría avanzada para asegurarse de obtener datos sobre las actividades en los dispositivos, incluida la administración de cuentas local, la administración de grupos de seguridad local y la creación de servicios.

| Datos | Descripción | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Administración de cuentas | Eventos capturados como varios `ActionType` valores que indican la creación, eliminación y otras actividades relacionadas con la cuenta locales | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementación de una directiva de auditoría de seguridad avanzada: [Auditar la administración de cuentas de usuario](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Más información sobre las directivas de auditoría de seguridad avanzada](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Administración de grupos de seguridad | Eventos capturados como varios `ActionType` valores que indican la creación de grupos de seguridad locales y otras actividades de administración de grupos locales | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementación de una directiva de auditoría de seguridad avanzada: [Auditar la administración de grupos de seguridad](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Más información sobre las directivas de auditoría de seguridad avanzada](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Instalación del servicio | Eventos capturados con el `ActionType` valor `ServiceInstalled`, que indican que se ha creado un servicio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementación de una directiva de auditoría de seguridad avanzada: [auditar la extensión del sistema de seguridad](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Más información sobre las directivas de auditoría de seguridad avanzada](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender for Identity sensor en el controlador de dominio
Si ejecuta Active Directory en el entorno local, debe instalar el sensor de Microsoft Defender for Identity en el controlador de dominio para obtener datos para Microsoft Defender for Identity. Cuando se instalan y configuran correctamente, estos datos también se alimentan de la búsqueda avanzada a través de Microsoft Defender for Identity y proporcionan una imagen más holística de la información de identidad y los eventos de la red. Estos datos también mejoran la capacidad de Microsoft Defender for Identity para generar alertas pertinentes que también están cubiertas por la búsqueda avanzada. 

| Datos | Descripción | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Controlador de dominio  | Datos de Active Directory local enviados a Microsoft Defender for Identity, enriqueciendo información relacionada con la identidad, como detalles de la cuenta, actividad de inicio de sesión y consultas de Active Directory | Varias tablas, como [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Instalación del sensor de Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step4)<br>- [Activar eventos de Windows relevantes](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>Es posible que algunas tablas de este artículo no estén disponibles en Microsoft Defender para punto de conexión. [Active Microsoft 365 Defender](m365d-enable.md) para buscar amenazas mediante más orígenes de datos. Para mover los flujos de trabajo de búsqueda avanzados de Microsoft Defender para punto de conexión a Microsoft 365 Defender, siga los pasos descritos en [Migración de consultas de búsqueda avanzadas desde Microsoft Defender para punto de conexión](advanced-hunting-migrate-from-mde.md) .

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)