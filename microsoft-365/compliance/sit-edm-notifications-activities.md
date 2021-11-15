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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo crear notificaciones para actividades de coincidencia exacta de datos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1033b6cd84f84db65f49f95e008e20eada63ca64
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914601"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>Crear notificaciones para actividades de coincidencia exacta de datos

Cuando se [crean tipos de información confidencial personalizados con coincidencia exacta de datos (EDM)](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types), hay una serie de actividades que se crean en el [registro de auditoría](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log). Puede utilizar el cmdlet de PowerShell [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) para crear notificaciones que le permitan saber cuándo se producen estas actividades:

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

> [!NOTE]
 La capacidad de crear notificaciones de actividades de EDM solo está disponible para las nubes de World Wide y GCC.

## <a name="pre-requisites"></a>Requisitos previos

La cuenta que use debe estar en uno de los siguientes roles:

- Un administrador global
- Administrador de cumplimiento
- administrador de Exchange Online

Para obtener más información acerca de los permisos de DLP, consulte [Permisos](data-loss-prevention-policies.md#permissions).

La clasificación basada en EDM se incluye en estas suscripciones:

- Office 365 E5
- Microsoft 365 E5
- Cumplimiento de Microsoft 365 E5
- Gobierno y protección de información de Microsoft E5/A5

Para obtener más información sobre las licencias de DLP, consulte la [Guía de licencias de Microsoft 365 para la seguridad y cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="configure-notifications-for-edm-activities"></a>Configurar notificaciones para actividades de EDM

1. Conectarse al [Centro de seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell).

2. Ejecute el cmdlet `New-ProtectionAlert` con la actividad para la que desea crear la notificación.  Por ejemplo, si desea recibir una notificación cuando se produzca la acción **UploadDataCompleted**, ejecute:

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    Para **UploadDataFailed** puede ejecutar:
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a>Artículos relacionados

- [Obtenga información sobre tipos de información confidencial basada en coincidencias de datos exactas](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert)