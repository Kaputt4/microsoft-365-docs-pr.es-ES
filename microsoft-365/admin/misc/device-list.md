---
title: Archivo CSV de lista de dispositivos
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.openlocfilehash: af695448e31ea93d36b36a8831702acb84a92410
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65469566"
---
# <a name="windows-autopilot-device-list-csv-file"></a>Windows archivo CSV de lista de dispositivos Autopilot

## <a name="device-list-csv-file-format"></a>Formato de archivo .csv lista de dispositivos

Para administrar e implementar dispositivos a través de Windows Autopilot, necesitará un archivo .csv que contenga información específica sobre los dispositivos.
  
Las columnas del archivo de lista de dispositivos deben tener los encabezados siguientes en el orden especificado:
  
- Columna A: Número de serie del dispositivo

- Columna B: dejar en blanco

- Columna C: Hash de hardware

Puede obtener esta información de su proveedor de hardware o puede usar el [script de PowerShell Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo), que generará un archivo CSV. 

Al agregar dispositivos, también debe agregarlos a un perfil. Un perfil se usa para aplicar perfiles de implementación de AutoPilot a un dispositivo o un grupo de dispositivos.
  
## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 para la documentación y los recursos empresariales](../../index.yml)
  
[Comenzar con Microsoft 365 para empresas](../../admin/admin-overview/what-is-microsoft-365.md)