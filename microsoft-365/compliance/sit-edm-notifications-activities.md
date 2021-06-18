---
title: Crear notificaciones para actividades de coincidencia exacta de datos
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo crear notificaciones para actividades de coincidencia exacta de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15aa8f2bda76d56d3e35af8e884193193bb78d40
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007566"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>Crear notificaciones para actividades de coincidencia exacta de datos

Cuando [crea tipos de información confidencial personalizados con coincidencia exacta de datos (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) hay una serie de actividades que se crean en el [registro de auditoría](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log). Puede utilizar el cmdlet de PowerShell [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps) para crear notificaciones que le permitan saber cuándo se producen estas actividades:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

## <a name="pre-requisites"></a>Requisitos previos

La cuenta que use debe estar en uno de los siguientes roles:

- un administrador global
- administrador de cumplimiento
- administrador de Exchange Online

Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).

La clasificación basada en EDM se incluye en estas suscripciones

- Office 365 E5
- Microsoft 365 E5
- Cumplimiento de Microsoft 365 E5
- Gobierno y protección de información de Microsoft E5/A5

Para obtener más información sobre las licencias de DLP, vea la [Guía de licencias de Microsoft 365 para la seguridad y cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="configure-notifications-for-edm-activities"></a>Configurar notificaciones de actividades de EDM

1. Conectarse al [Centro de seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell?view=exchange-ps) 

2. Ejecute el cmdlet `New-ProtectionAlert` con la actividad para la que desea crear la notificación.  Por ejemplo, si desea que se le notifique cuando se produzca la acción **UploadDataCompleted**, ejecute

```powershell
New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <***address to send  notification to***> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
```

para **UploadDataFailed** puede ejecutar

```powershell
New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <***SMTP address to send notification to***> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
```

## <a name="related-articles"></a>Artículos relacionados

- [Crear tipos de información confidencial personalizados con coincidencia exacta de datos (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert?view=exchange-ps)