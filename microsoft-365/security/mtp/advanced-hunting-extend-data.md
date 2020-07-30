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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 9c1b9c1853d80d818d97084e2668d3b12b6da0e6
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503225"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Ampliar la cobertura de caza avanzada con la configuración adecuada

**Se aplica a:**
- Protección contra amenazas de Microsoft

La [búsqueda avanzada](advanced-hunting-overview.md) depende de los datos procedentes de distintas fuentes, incluidos los dispositivos, los espacios de trabajo de Office 365, Azure ad y ATP de Azure. Para obtener los datos más completos posibles, asegúrese de que tiene la configuración correcta en los orígenes de datos correspondientes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoría de seguridad avanzada en dispositivos Windows
Active esta configuración avanzada de auditoría para asegurarse de que obtiene datos sobre las actividades de los dispositivos, como la administración de cuentas locales, la administración de grupos de seguridad locales y la creación de servicios.

| Datos | Descripción | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Administración de cuentas | Eventos capturados como varios `ActionType` valores que indican la creación, la eliminación y otras actividades relacionadas con la cuenta local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Implementar una directiva de auditoría de seguridad avanzada: [auditar la administración de cuentas de usuario](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Obtener información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Administración de grupos de seguridad | Eventos capturados como varios `ActionType` valores que indican la creación de grupos de seguridad locales y otras actividades de administración de grupo local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Implementar una directiva de auditoría de seguridad avanzada: [auditar la administración de grupos de seguridad](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Obtener información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Instalación del servicio | Eventos capturados con el `ActionType` valor `ServiceInstalled` , que indican que se ha creado un servicio | [DeviceEvents](advanced-hunting-deviceevents-table.md) | -Implementar una directiva de auditoría de seguridad avanzada: comprobación de la [extensión de sistema de seguridad](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Obtener información sobre las directivas de auditoría de seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="azure-atp-sensor-on-the-domain-controller"></a>Sensor ATP de Azure en el controlador de dominio
Si ejecuta Active Directory local, debe instalar el sensor ATP de Azure en el controlador de dominio para obtener datos de ATP de Azure. Cuando se instalan y se configuran correctamente, estos datos también se redirigen a la búsqueda avanzada a través de ATP de Azure y proporcionan una imagen más holística de la información de identidad y los eventos de la red. Estos datos también mejoran la capacidad de Azure ATP para generar alertas relevantes que también están cubiertas por la búsqueda avanzada. 

| Datos | Descripción | Tabla de esquema | Cómo establecer la configuración |
| --- | --- | --- | --- |
| Controlador de dominio | Los datos de Active Directory local se envían a ATP de Azure, lo que enriquece la información relacionada con la identidad, como los detalles de la cuenta, la actividad de inicio de sesión y las consultas de Active Directory. | Varias tablas, incluidas [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)y [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | [Instalar el sensor ATP de Azure](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)|

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)