---
title: Preparar la implementación del cliente de Office con Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Obtenga información sobre cómo instalar automáticamente las aplicaciones de Office de 32 bits en equipos con Windows 10 y mantenerlas actualizadas.
ms.openlocfilehash: 6f3a80be9729a3818607c0f42e2cc7ece66a07ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401330"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Preparar la implementación del cliente de Office con Microsoft 365 para empresas

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Prepararse para instalar automáticamente las aplicaciones de Office en los equipos cliente

Puede usar Microsoft 365 para empresas para instalar automáticamente las aplicaciones de Office de 32 bits en equipos con Windows 10 y mantenerlas actualizadas con las actualizaciones.
  
La instalación automática funciona mejor si el equipo del usuario final está en Windows 10 Business y:
  
- No tiene aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access y OneDrive).
    
    o
    
- Tiene instalada una versión existente de Office de Hacer clic y ejecutar.
    
Para determinar si tiene la versión de Hacer clic y ejecutar de Office, en cualquier aplicación de Office, vaya a **Archivo** \> **Cuenta** ( **Cuenta de Office** en Outlook). Si ve **actualizaciones de Office** , tal como se muestra en la siguiente figura, la instalación se realizó mediante hacer clic y ejecutar. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Quién se beneficia de tener esta característica**
  
El usuario final cuyo PC:
  
- **Tiene** una licencia de usuario de Windows 10 Business, una licencia activa de Microsoft 365 para empresas, Windows 10 Creators Update y se ha unido a Azure Active Directory. 
    
- **No tiene** aplicaciones de Office de 64 bits (por ejemplo: Word, Excel y PowerPoint). Si se necesitan aplicaciones de Office de 64-bit, esta característica no es una buena opción porque no hay compatibilidad para desencadenar una versión de Office de 64 bits 2016 de hacer clic y ejecutar desde la consola de administración de Microsoft 365 para empresas. 
    
- **No tenga** ninguna aplicación independiente de Windows Installer (MSI) 2016 (por ejemplo, Visio o Project). Microsoft 365 for Business actualiza Office a la versión de hacer clic y ejecutar de Office 2016 y no funciona con aplicaciones independientes MSI de Office 2016. 
    
En la tabla siguiente se muestra la acción que los usuarios finales o administradores deben realizar, en función de su estado de inicio, para tener una versión de hacer clic y ejecutar de 32 bits de la implementación de Office desde la consola de administración de 365 para empresas de Microsoft.
  
|**Estado inicial de instalación de Office**|**Acción que se llevará a cabo antes de la instalación de Microsoft 365 para empresas**|**Estado final**|
|:-----|:-----|:-----|
|Ningún conjunto de aplicaciones de Office instalado  <br/> |Ninguno  <br/> |Office 2016 32-bit se instala mediante hacer clic y ejecutar  <br/> |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office (2016 o versiones anteriores) y ninguna aplicación independiente  <br/> |Ninguno  <br/> |Actualizado a la versión más reciente de 32 bits de Hacer clic y ejecutar de Office 2016, según sea necesario **\*** <br/> |
|La versión existente de hacer clic y ejecutar de 32 bits de Office y de aplicaciones independientes de Office de hacer clic y ejecutar de 32 bits o de 64 (por ejemplo, Visio, Project)  <br/> |Ninguno  <br/> |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  <br/> |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office y cualquier aplicación independiente MSI de Office de 32 o 64 bits (excepto 2016)  <br/> |Ninguno  <br/> |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  <br/> ||||
|Cualquier versión de Hacer clic y ejecutar de 64 bits de Office  <br/> |Desinstalar las aplicaciones de Office de 64 bits, si es correcto reemplazarlas por aplicaciones de Office de 32 bits  <br/> |Si se eliminan las aplicaciones de Office de 64 bits, se instalará la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  <br/> |
|Una instalación de MSI existente de Office 2016 con o sin aplicaciones independientes  <br/> |Desinstalar MSI Office 2016.  <br/> |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 está instalada. Sin cambios en las aplicaciones independientes  <br/> |
|Instalación de MSI existente de Office 2013 (o una versión anterior) o aplicaciones independientes de Office  <br/> |Ninguno  <br/> |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 con la instalación de MSI Office ya existente (y aplicaciones independientes) existe en paralelo  <br/> |
||||
   
 **(\*) Nota:** No actualice a la versión de Hacer clic y ejecutar de 32 bits de Office 2016 debido a un error conocido. Hay una corrección en curso. 
  
