---
title: Archivo CSV de lista de dispositivos
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Obtenga información sobre cómo crear un archivo CSV para AutoPilot en Microsoft 365 para empresas.
ms.openlocfilehash: 63aaf46256e12abb4503127f4e457eef573e3e37
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68208334"
---
# <a name="windows-autopilot-device-list-csv-file"></a>Archivo CSV de lista de dispositivos Windows Autopilot

## <a name="device-list-csv-file-format"></a>Formato de archivo .csv lista de dispositivos

Para administrar e implementar dispositivos a través de Windows Autopilot, necesitará un archivo .csv que contenga información específica sobre los dispositivos.
  
Las columnas del archivo de lista de dispositivos deben tener los encabezados siguientes en el orden especificado:
  
- Columna A: Número de serie del dispositivo

- Columna B: dejar en blanco

- Columna C: Hash de hardware

Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV. 

Al agregar dispositivos, también debe agregarlos a un perfil. Un perfil se usa para aplicar perfiles de implementación de AutoPilot a un dispositivo o un grupo de dispositivos.
  
## <a name="related-content"></a>Contenido relacionado

[Documentación y recursos de Microsoft 365 para empresas](../../index.yml)
  
[Introducción a Microsoft 365 para empresas](../../admin/admin-overview/what-is-microsoft-365.md)