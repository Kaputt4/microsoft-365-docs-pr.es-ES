---
title: Prepararse para la Office cliente mediante Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Obtén información sobre cómo instalar automáticamente las aplicaciones Office de 32 bits en Windows 10 equipos y mantenerlas actualizadas.
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580062"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Prepararse para la Office cliente mediante Microsoft 365 para empresas

Este artículo se aplica a Microsoft 365 Empresa Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Prepararse para instalar automáticamente las aplicaciones de Office en los equipos cliente

Puedes usar Microsoft 365 Empresa Premium para instalar automáticamente las aplicaciones Office de 32 bits en Windows 10 equipos y mantenerlas actualizadas con actualizaciones.
  
La instalación automática funciona mejor si el equipo del usuario final está en Windows 10 Business y:
  
- No tiene aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access y OneDrive).
    
    o
    
- Tiene instalada una versión existente de Office de Hacer clic y ejecutar.
    
Para determinar si tiene la versión de Hacer clic y ejecutar de Office, en cualquier aplicación de Office, vaya a **Archivo** \> **Cuenta** ( **Cuenta de Office** en Outlook). Si ve actualizaciones **Office como** se muestra en la siguiente figura, la instalación se ha realizado mediante Hacer clic y ejecutar. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Quién ventajas de tener esta característica**
  
El usuario final cuyo PC:
  
- **Tiene** una Windows 10 Business de usuario, una licencia activa Microsoft 365 para empresas, Windows 10 Creators Update y se une a Azure Active Directory. 
    
- **No tiene aplicaciones de** 64 bits Office (por ejemplo: Word, Excel, PowerPoint). Si se requieren aplicaciones de Office de 64 bits, esta característica no es buena porque no hay compatibilidad para desencadenar una versión de 64 bits de hacer clic y ejecutar de Office desde la consola de administración de Microsoft 365 para empresas. 
    
- **No tenga** ninguna aplicación independiente de Windows Installer (MSI) 2016 (por ejemplo, Visio o Project). Microsoft 365 actualizaciones para empresas Office a la versión hacer clic y ejecutar de Office 2016 y eso no funciona con aplicaciones independientes de MSI de Office 2016. 
    
En la tabla siguiente se muestra qué acción pueden necesitar los usuarios finales o los administradores, según su estado inicial, para tener una versión correcta de hacer clic y ejecutar de 32 bits de una implementación de Office desde la consola de administración de Microsoft 365 para empresas.
  
|**Estado inicial de instalación de Office**|**Acción que debe realizar antes de Microsoft 365 para empresas Office instalación**|**Estado final**|
|:-----|:-----|:-----|
|Ningún conjunto de aplicaciones de Office instalado  <br/> |Ninguno  <br/> |Office 2016 de 32 bits se instala mediante hacer clic y ejecutar  <br/> |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office (2016 o versiones anteriores) y ninguna aplicación independiente  <br/> |Ninguno  <br/> |Actualizado a la versión más reciente de 32 bits de Hacer clic y ejecutar de Office 2016, según sea necesario **\*** <br/> |
|Versión de hacer clic y ejecutar de 32 bits existente de Office y Hacer clic y ejecutar aplicaciones de Office independientes de 32 bits o 64 bits (por ejemplo, Visio, Project)  <br/> |Ninguno  <br/> |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  <br/> |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office y cualquier aplicación independiente MSI de Office de 32 o 64 bits (excepto 2016)  <br/> |Ninguno  <br/> |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  <br/> ||||
|Cualquier versión de Hacer clic y ejecutar de 64 bits de Office  <br/> |Desinstale las aplicaciones Office de 64 bits, si está bien reemplazarlas por aplicaciones de 32 bits Office aplicaciones  <br/> |Si se eliminan las aplicaciones de Office de 64 bits, se instalará la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  <br/> |
|Una instalación de MSI existente de Office 2016 con o sin aplicaciones independientes  <br/> |Desinstalar MSI Office 2016.  <br/> |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 está instalada. Sin cambios en las aplicaciones independientes  <br/> |
|Instalación de MSI existente de Office 2013 (o una versión anterior) o aplicaciones independientes de Office  <br/> |Ninguno  <br/> |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 con la instalación de MSI Office ya existente (y aplicaciones independientes) existe en paralelo  <br/> |
||||
   
 **(\*) Nota:** No actualice a la versión de Hacer clic y ejecutar de 32 bits de Office 2016 debido a un error conocido. Hay una corrección en curso. 
  
