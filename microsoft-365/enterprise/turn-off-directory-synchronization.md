---
title: Desactivar la sincronización de directorios para Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: En este artículo, busque información sobre el uso de PowerShell para desactivar la sincronización de directorios para Microsoft 365.
ms.openlocfilehash: 90c4fb95aade8752f5be53db0163087b3a4f1d71
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67671509"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Desactivar la sincronización de directorios para Microsoft 365
Puede usar PowerShell para desactivar la sincronización de directorios y convertir los usuarios sincronizados en solo nube. Sin embargo, no se recomienda desactivar la sincronización de directorios como paso de solución de problemas. Si necesita ayuda para solucionar problemas de sincronización de directorios, consulte el artículo [Corrección de problemas con la sincronización de directorios para Microsoft 365](fix-problems-with-directory-synchronization.md) . 
  
[Póngase en contacto con el soporte](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) técnico para productos empresariales si es necesario.
  
## <a name="turn-off-directory-synchronization"></a>Desactivar la sincronización de directorios  
Para desactivar la sincronización de directorios:
  
1. En primer lugar, instale el software necesario y conéctese a la suscripción de Microsoft 365. Para obtener instrucciones, consulte [Conexión con el módulo Microsoft Azure Active Directory para Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Use [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) para deshabilitar la sincronización de directorios: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Si usa este comando, debe esperar 72 horas para poder volver a activar la sincronización de directorios.
>
