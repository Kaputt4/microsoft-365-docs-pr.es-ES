---
title: Prepararse para una implementación del cliente de Office mediante Microsoft 365 Empresa Premium
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 04/01/2022
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
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
ROBOTS: NO INDEX, NO FOLLOW
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Obtenga información sobre cómo instalar automáticamente las aplicaciones Office de 32 bits en equipos Windows 10 y mantenerlas actualizadas.
ms.openlocfilehash: b4df5152e5adfbd2391fd51c184bd4547be12011
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2022
ms.locfileid: "65317881"
---
# <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Prepararse para instalar automáticamente las aplicaciones de Office en los equipos cliente

Use Microsoft 365 Empresa Premium para instalar automáticamente las aplicaciones de Office de 32 bits en equipos Windows 10 y mantenerlas actualizadas.
  
La instalación automática funciona mejor si el equipo: 

- está en Windows 10 Business.
  
- no tiene aplicaciones de escritorio de Office existentes (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access y OneDrive) O tiene instalada una versión existente de Office de Hacer clic y ejecutar.

Para determinar si tiene la versión de Hacer clic y ejecutar de Office, en cualquier aplicación de Office, vaya a **Archivo** \> **Cuenta** (**Cuenta** de Office en Outlook). Si ve las **actualizaciones de Office** como se muestran en la siguiente ilustración, la instalación se ha efectuado mediante Hacer clic y ejecutar. 
  
![Screenshot of Office updates in Office app Account.](./../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
## <a name="requirements-for-using-this-feature"></a>Requisitos para usar esta característica
  
Funciona con:
  
- Un usuario que tenga una licencia de usuario de Windows 10 Business, una licencia activa de Microsoft 365 para empresas, Windows 10 Creators Update y se haya unido a Azure Active Directory.

No funciona con: 

- Las aplicaciones de Office de 64 bits (ejemplo: Word, Excel o PowerPoint). Si las aplicaciones de Office de 64 bits son necesarias, esta característica no es adecuada porque no se puede desencadenar ninguna versión de 64 bits de Hacer clic y ejecutar de Office 2016 desde la consola de administración de Microsoft 365 para empresas.

- Cualquier aplicación independiente de Windows Installer (MSI) 2016 (por ejemplo, Visio o Project). Microsoft 365 para empresas actualiza Office a la versión de Hacer clic y ejecutar de Office 2016 y esto no funciona con aplicaciones independientes de Office 2016 MSI.

La siguiente tabla muestra qué acción deben realizar los usuarios finales/administradores, según su estado inicial, para tener una versión correcta de Hacer clic y ejecutar de 32 bits de la implementación de Office desde la consola de administración de Microsoft 365 para empresas.<br/>


|Estado inicial de instalación de Office|Acción que se realiza antes de que se instale Microsoft 365 para empresas Office|Estado final|
|:-----|:-----|:-----|
|Ningún conjunto de aplicaciones de Office instalado  |Ninguno  |Office 2016 de 32 bits está instalado mediante Hacer clic y ejecutar  |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office (2016 o versiones anteriores) y ninguna aplicación independiente  |Ninguno  |Actualizado a la versión más reciente de 32 bits de Hacer clic y ejecutar de Office 2016, según sea necesario **\*** |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office y aplicaciones independientes de Office de 32 o 64 bits de Hacer clic y ejecutar (por ejemplo, Visio y Project)  |Ninguno  |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office y cualquier aplicación independiente MSI de Office de 32 o 64 bits (excepto 2016)  |Ninguno  |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  |
|Cualquier versión de Hacer clic y ejecutar de 64 bits de Office  |Se desinstalan las aplicaciones de Office de 64 bits, si no importa reemplazarlas por las de Office de 32 bits.  |Si se eliminan las aplicaciones de Office de 64 bits, se instalará la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  |
|Una instalación de MSI existente de Office 2016 con o sin aplicaciones independientes  |Desinstalar MSI Office 2016.  |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 está instalada. Sin cambios en las aplicaciones independientes  |
|Instalación de MSI existente de Office 2013 (o una versión anterior) o aplicaciones independientes de Office  |Ninguno  |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 con la instalación de MSI Office ya existente (y aplicaciones independientes) existe en paralelo  |

 **(\*) Nota:** No actualice a la versión de Hacer clic y ejecutar de 32 bits de Office 2016 debido a un error conocido. La solución está en curso. 

## <a name="next-objective"></a>Siguiente objetivo

[Revista y edita las directivas de dispositivo](m365bp-view-edit-create-mdb-policies.md)
  