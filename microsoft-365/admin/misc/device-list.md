---
title: Lista de dispositivos CSV-file
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
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
ms.openlocfilehash: bc67e32d834ec8fde13386fb02ef1368ca3757cef47e78575d00a3e3d2fc6db3
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53824124"
---
# <a name="device-list-csv-file"></a>Lista de dispositivos CSV-file

## <a name="device-list-csv-file-format"></a>Lista de dispositivos .csv formato de archivo

Para administrar e implementar dispositivos mediante Windows Autopilot, necesitarás un archivo .csv que contenga información específica sobre los dispositivos.
  
Las columnas del archivo de lista de dispositivos deben tener los siguientes encabezados en el orden especificado:
  
- Columna A: Número de serie del dispositivo

- Columna B: dejar en blanco

- Columna C: Hash de hardware

Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV. 

Al agregar dispositivos, también debes agregarlos a un perfil. Un perfil se usa para aplicar perfiles de implementación de AutoPilot a un dispositivo o un grupo de dispositivos.
  
## <a name="related-articles"></a>Artículos relacionados

[Microsoft 365 documentación y recursos para empresas](../../business/index.yml)
  
[Introducción a Microsoft 365 para empresas](../../business/microsoft-365-business-overview.md)
  
[Administrar Microsoft 365 para empresas](../../business/manage.md)
