---
title: Ampliar la cobertura de búsqueda avanzada con la configuración correcta
description: Comprueba la configuración de auditoría en dispositivos Windows y otras opciones de configuración para garantizar que obtienes los datos más completos en la búsqueda avanzada
keywords: búsqueda avanzada, incidente, tabla dinámica, entidad, configuración de auditoría, administración de cuentas de usuario, administración de grupos de seguridad, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, Microsoft 365, Protección contra amenazas de Microsoft
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
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929591"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Ampliar la cobertura de búsqueda avanzada con la configuración correcta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[La búsqueda avanzada](advanced-hunting-overview.md) se basa en datos procedentes de distintos orígenes, incluidos los dispositivos, las áreas de trabajo de Office 365, Azure AD y Microsoft Defender for Identity. Para obtener los datos más completos posibles, asegúrese de que tiene la configuración correcta en los orígenes de datos correspondientes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoría de seguridad avanzada en dispositivos Windows
Activa esta configuración de auditoría avanzada para garantizar que obtienes datos sobre las actividades en tus dispositivos, incluida la administración de cuentas locales, la administración de grupos de seguridad local y la creación de servicios.

| Datos | Descripción | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Administración de cuentas | Eventos capturados como varios `ActionType` valores que indican la creación, eliminación y otras actividades relacionadas con la cuenta local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementar una directiva de auditoría de seguridad avanzada: [Auditar administración de cuentas de usuario](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Más información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Administración de grupos de seguridad | Eventos capturados como varios valores que indican la creación `ActionType` de grupos de seguridad locales y otras actividades de administración de grupos locales | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementar una directiva de auditoría de seguridad avanzada: [Auditar administración de grupos de seguridad](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Más información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Instalación del servicio | Eventos capturados con `ActionType` el valor , que indica que se ha creado un `ServiceInstalled` servicio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementar una directiva de auditoría de seguridad avanzada: [Auditar extensión del sistema de seguridad](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Más información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft Defender para el sensor de identidad en el controlador de dominio
Si ejecutas Active Directory localmente, debes instalar el sensor de Microsoft Defender para Identity en el controlador de dominio para obtener datos de Microsoft Defender para Identity. Cuando se instalan y configuran correctamente, estos datos también se alimentan en la búsqueda avanzada a través de Microsoft Defender for Identity y proporcionan una imagen más holística de la información de identidad y los eventos en la red. Estos datos también mejoran la capacidad de Microsoft Defender para Identity para generar alertas relevantes que también están cubiertas por la búsqueda avanzada. 

| Datos | Descripción | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Controlador de dominio | Datos de Active Directory local enviados a Microsoft Defender para identidad, enriqueciendo información relacionada con la identidad, como detalles de la cuenta, actividad de inicio de sesión y consultas de Active Directory | Varias tablas, incluidas [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Instalar el sensor de Microsoft Defender para identidad](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Activar eventos relevantes de Windows](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
