---
title: Prepararse para una implementación del cliente de Office mediante Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Obtenga información sobre cómo instalar automáticamente las aplicaciones de Office de 32 bits en equipos con Windows 10 y mantenerlas actualizadas.
ms.openlocfilehash: 20269c493b0e3b5a7deb56a24a5e1a9583ef9d0a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074658"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Prepararse para una implementación del cliente de Office mediante Microsoft 365 Business

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Prepararse para instalar automáticamente las aplicaciones de Office en los equipos cliente

Puede usar Microsoft 365 Business para instalar las aplicaciones de Office de 32 bits en equipos Windows 10 y mantenerlas actualizadas.
  
Esto funciona mejor si el equipo del usuario final utiliza Windows 10 Business y:
  
- No tiene aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access y OneDrive).
    
    o
    
- Tiene instalada una versión existente de Office de Hacer clic y ejecutar.
    
Para determinar si tiene la versión de Hacer clic y ejecutar de Office, en cualquier aplicación de Office, vaya a **Archivo** \> **Cuenta** ( **Cuenta de Office** en Outlook). Si ve las actualizaciones de Office como se muestran en la siguiente ilustración, la instalación se ha efectuado mediante Hacer clic y ejecutar. 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **¿Quién se beneficiará de tener esta característica?**
  
El usuario final cuyo PC:
  
- **Tenga** una licencia de usuario de Windows 10 Business, una licencia activa de Microsoft 365 Business, Windows 10 Creators Update y se haya unido a Azure Active Directory. 
    
- **No tenga** las aplicaciones de Office de 64 bits (ejemplo: Word, Excel o PowerPoint). Si las aplicaciones de Office de 64 bits son necesarias, esta característica no es adecuada porque no se puede desencadenar ninguna versión de 64 bits de Hacer clic y ejecutar de Office 2016 desde la consola de administración de Microsoft 365 Business. 
    
- **No tenga** ninguna aplicación independiente de Windows Installer (MSI) 2016 (por ejemplo, Visio o Project). Microsoft 365 Business actualiza Office a la versión de Hacer clic y ejecutar de Office 2016 y esto no funciona con aplicaciones independientes de Office 2016 MSI. 
    
En la siguiente tabla, se detalla qué acción deben realizar los usuarios finales/administradores, según su estado inicial, para tener una versión correcta de Hacer clic y ejecutar de 32 bits de la implementación de Office desde la consola de administración de Microsoft 365 Business.
  
|**Estado inicial de instalación de Office**|**Acción que se realiza antes de que se instale Microsoft 365 Business Office**|**Estado final**|
|:-----|:-----|:-----|
|Ningún conjunto de aplicaciones de Office instalado  <br/> |Ninguno  <br/> |Office 2016 de 32 bits está instalado mediante Hacer clic y ejecutar  <br/> |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office (2016 o versiones anteriores) y ninguna aplicación independiente  <br/> |Ninguno  <br/> |Actualizado a la versión más reciente de 32 bits de Hacer clic y ejecutar de Office 2016, según sea necesario **\*** <br/> |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office y aplicaciones independientes de Office de 32 o 64 bits de Hacer clic y ejecutar (por ejemplo, Visio y Project)  <br/> |Ninguno  <br/> |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  <br/> |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office y cualquier aplicación independiente MSI de Office de 32 o 64 bits (excepto 2016)  <br/> |Ninguno  <br/> |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  <br/> ||||
|Cualquier versión de Hacer clic y ejecutar de 64 bits de Office  <br/> |Se desinstalan las aplicaciones de Office de 64 bits, si no importa reemplazarlas por las de Office de 32 bits.  <br/> |Si se eliminan las aplicaciones de Office de 64 bits, se instalará la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  <br/> |
|Una instalación de MSI existente de Office 2016 con o sin aplicaciones independientes  <br/> |Desinstalar MSI Office 2016.  <br/> |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 está instalada. Sin cambios en las aplicaciones independientes  <br/> |
|Instalación de MSI existente de Office 2013 (o una versión anterior) o aplicaciones independientes de Office  <br/> |Ninguno  <br/> |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 con la instalación de MSI Office ya existente (y aplicaciones independientes) existe en paralelo  <br/> |
||||
   
 **(\*) Nota:** No actualice a la versión de Hacer clic y ejecutar de 32 bits de Office 2016 debido a un error conocido. La solución está en curso. 
  


