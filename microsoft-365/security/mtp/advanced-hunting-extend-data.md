---
title: Ampliar la cobertura de caza avanzada con la configuración adecuada
description: Compruebe la configuración de auditoría en dispositivos Windows y otras opciones para asegurarse de que obtiene los datos más completos en la búsqueda avanzada.
keywords: características avanzadas de búsqueda, incidencia, pivote, entidad, auditoría, administración de cuentas de usuario, administración de grupos de seguridad, caza de amenazas, búsqueda de amenazas en el ciberespacio, búsqueda, consulta, telemetría, Microsoft 365, protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 82faff2599cd61fa1a4deb3129e1e6780d3f529c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842481"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Ampliar la cobertura de caza avanzada con la configuración adecuada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender

La [búsqueda avanzada](advanced-hunting-overview.md) depende de los datos procedentes de distintas fuentes, incluidos los dispositivos, los espacios de trabajo de Office 365, Azure ad y Microsoft defender para identidad. Para obtener los datos más completos posibles, asegúrese de que tiene la configuración correcta en los orígenes de datos correspondientes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoría de seguridad avanzada en dispositivos Windows
Active esta configuración avanzada de auditoría para asegurarse de que obtiene datos sobre las actividades de los dispositivos, como la administración de cuentas locales, la administración de grupos de seguridad locales y la creación de servicios.

| Datos | Description | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Administración de cuentas | Eventos capturados como varios `ActionType` valores que indican la creación, la eliminación y otras actividades relacionadas con la cuenta local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Implementar una directiva de auditoría de seguridad avanzada: [auditar la administración de cuentas de usuario](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Obtener información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Administración de grupos de seguridad | Eventos capturados como varios `ActionType` valores que indican la creación de grupos de seguridad locales y otras actividades de administración de grupo local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Implementar una directiva de auditoría de seguridad avanzada: [auditar la administración de grupos de seguridad](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Obtener información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Instalación del servicio | Eventos capturados con el `ActionType` valor `ServiceInstalled` , que indican que se ha creado un servicio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Implementar una directiva de auditoría de seguridad avanzada: comprobación de la [extensión de sistema de seguridad](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Obtener información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Microsoft defender para el sensor de identidad en el controlador de dominio
Si ejecuta Active Directory local, debe instalar Microsoft defender para el sensor de identidad en el controlador de dominio para obtener los datos de Microsoft defender para identidad. Cuando se instalan y se configuran correctamente, estos datos también se redirigen a la búsqueda avanzada a través de Microsoft defender para identidades y proporciona una imagen más holística de los eventos y la información de identidad en la red. Estos datos también mejoran la capacidad de Microsoft defender para la identidad para generar alertas relevantes que también están cubiertas por la búsqueda avanzada. 

| Datos | Description | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Controlador de dominio | Datos de Active Directory local enviados a Microsoft defender para la identidad, enriquecendo la información relacionada con la identidad, como los detalles de la cuenta, la actividad de inicio de sesión y las consultas de Active Directory | Varias tablas, incluidas [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)y [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Instalar Microsoft defender para el sensor de identidad](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Activar los eventos relevantes de Windows](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
