---
title: Ampliar la cobertura de búsqueda avanzada con la configuración correcta
description: Comprueba la configuración de auditoría en dispositivos Windows y otras configuraciones para asegurarte de obtener los datos más completos en la búsqueda avanzada
keywords: búsqueda avanzada, incidente, pivot, entidad, configuración de auditoría, administración de cuentas de usuario, administración de grupos de seguridad, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, mdatp, ATP de Microsoft Defender, Microsoft Defender para endpoint, Windows Defender, ATP de Windows Defender, protección contra amenazas avanzada de Windows Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500615"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Ampliar la cobertura de búsqueda avanzada con la configuración correcta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[La búsqueda avanzada](advanced-hunting-overview.md) se basa en datos procedentes de toda la organización. Para obtener los datos más completos posibles, asegúrese de que tiene la configuración correcta en los orígenes de datos correspondientes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoría de seguridad avanzada en dispositivos Windows

Activa esta configuración de auditoría avanzada para asegurarte de obtener datos sobre actividades en tus dispositivos, incluida la administración de cuentas locales, la administración de grupos de seguridad local y la creación de servicios.

Datos | Descripción | Tabla de esquema | Cómo establecer la configuración
-|-|-|-
Administración de cuentas | Eventos capturados como varios valores que indican la creación, eliminación y `ActionType` otras actividades relacionadas con la cuenta local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementar una directiva de auditoría de seguridad avanzada: [Auditar administración de cuentas de usuario](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Obtenga información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Administración de grupos de seguridad | Eventos capturados como varios valores que indican la creación de grupos `ActionType` de seguridad locales y otras actividades de administración de grupos locales | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementar una directiva de auditoría de seguridad avanzada: [Auditar la administración de grupos de seguridad](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Obtenga información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Instalación del servicio | Eventos capturados con el valor , que indican que se ha creado `ActionType` `ServiceInstalled` un servicio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implementar una directiva de auditoría de seguridad avanzada: [Extensión del sistema de seguridad de auditoría](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Obtenga información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](overview-custom-detections.md)
