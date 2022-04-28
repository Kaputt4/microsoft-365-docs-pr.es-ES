---
title: Visualización de errores de sincronización de directorios en Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- admindeeplinkMAC
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: Obtenga información sobre cómo ver los errores de sincronización de directorios y las posibles correcciones en Centro de administración de Microsoft 365.
ms.openlocfilehash: 1aa6a9208c9ae3091c2490a003eaabb841b78dc5
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096510"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Visualización de errores de sincronización de directorios en Microsoft 365

Puede ver los errores de sincronización de directorios en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. Solo se muestran los errores de objeto User. Para ver errores con PowerShell, consulte [Identificación de objetos con DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Visualización de errores de sincronización de directorios en el Centro de administración de Microsoft 365

Para ver los errores de la Centro de administración de Microsoft 365:
  
1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) con una cuenta de administrador global. 
    
2. En la página **Inicio** , verá la tarjeta **de administración de** usuarios. 
    
    ![La tarjeta de administración de usuarios de la Centro de administración de Microsoft 365.](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. En la tarjeta, elija **Errores de sincronización** en **Azure AD Conectar** para ver los errores en la página **Errores de sincronización de directorios**.   
    
    ![Ejemplo de la página Errores de sincronización de directorios.](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Elija cualquiera de los errores para mostrar el panel de detalles con información sobre el error y sugerencias sobre cómo corregirlo.

   ![Ejemplo de los detalles de un error de sincronización de directorios.](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
Después de la visualización, consulte [Solucionar problemas con la sincronización de directorios para Microsoft 365](fix-problems-with-directory-synchronization.md) para corregir los problemas identificados.