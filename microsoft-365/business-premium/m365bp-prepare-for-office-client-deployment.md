---
title: Prepárese para la Office cliente mediante Microsoft 365 Business Premium
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
ms.date: 04/01/2022
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Obtén información sobre cómo instalar automáticamente las aplicaciones Office de 32 bits en Windows 10 equipos y mantenerlas actualizadas.
ms.openlocfilehash: 2ed85916914e4f3ecfa9c7c5aeccb08eade1c006
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "64635431"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business-premium"></a>Prepárese para la Office cliente mediante Microsoft 365 Business Premium

> [!NOTE]
> Microsoft Defender für Unternehmen se está implementando para Microsoft 365 Business Premium clientes, a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para dispositivos. [Obtenga más información sobre Defender para empresas](../security/defender-business/mdb-overview.md).

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Prepararse para instalar automáticamente las aplicaciones de Office en los equipos cliente

Puedes usar Microsoft 365 Business Premium para instalar automáticamente las aplicaciones de Office de 32 bits en Windows 10 equipos y mantenerlas actualizadas con actualizaciones.
  
La instalación automática funciona mejor si el equipo del usuario final está en Windows 10 商務版 y:
  
- No tiene aplicaciones de escritorio de Office (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access y OneDrive).
    
    o
    
- Tiene instalada una versión existente de Office de Hacer clic y ejecutar.
    
Para determinar si tiene la versión de Hacer clic y ejecutar de Office, en cualquier aplicación de Office, vaya a **Archivo** \> **Cuenta** ( **Cuenta de Office** en Outlook). Si ve actualizaciones **Office como** se muestra en la siguiente figura, la instalación se ha realizado mediante Hacer clic y ejecutar. 
  
![Captura de pantalla Office actualizaciones en Aplicación de Office cuenta.](./../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Quién ventajas de tener esta característica**
  
El usuario final cuyo PC:
  
- **Tiene** una Windows 10 商務版 de usuario, una licencia Microsoft 365 para empresas, Windows 10 Creators Update y se une a Azure Active Directory. 
    
- **No tiene aplicaciones de** 64 bits Office (por ejemplo: Word, Excel, PowerPoint). Si se requieren aplicaciones de Office de 64 bits, esta característica no es adecuada porque no hay compatibilidad para desencadenar una versión de hacer clic y ejecutar de 64 bits de Office desde la consola de administración de Microsoft 365 para empresas. 
    
- **No tenga** ninguna aplicación independiente de Windows Installer (MSI) 2016 (por ejemplo, Visio o Project). Microsoft 365 para empresas Office a la versión hacer clic y ejecutar de Office 2016 y eso no funciona con aplicaciones independientes de MSI de Office 2016. 
    
En la tabla siguiente se muestra qué acción pueden necesitar los usuarios finales o los administradores, según su estado inicial, para tener una versión correcta de hacer clic y ejecutar de 32 bits de una implementación de Office desde la consola de administración de Microsoft 365 para empresas.<br/>


|Estado inicial de instalación de Office|Acción que debe realizar antes de Microsoft 365 para empresas Office instalación|Estado final|
|:-----|:-----|:-----|
|Ningún conjunto de aplicaciones de Office instalado  |Ninguno  |Office 2016 de 32 bits se instala con Hacer clic y ejecutar  |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office (2016 o versiones anteriores) y ninguna aplicación independiente  |Ninguno  |Actualizado a la versión más reciente de 32 bits de Hacer clic y ejecutar de Office 2016, según sea necesario **\*** |
|Versión de hacer clic y ejecutar de 32 bits existente de Office y Hacer clic y ejecutar aplicaciones de Office independientes de 32 bits o 64 bits (por ejemplo, Visio, Project)  |Ninguno  |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office y cualquier aplicación independiente MSI de Office de 32 o 64 bits (excepto 2016)  |Ninguno  |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  |
|Cualquier versión de Hacer clic y ejecutar de 64 bits de Office  |Desinstale las aplicaciones Office de 64 bits, si está bien reemplazarlas por aplicaciones de 32 bits Office aplicaciones  |Si se eliminan las aplicaciones de Office de 64 bits, se instalará la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  |
|Una instalación de MSI existente de Office 2016 con o sin aplicaciones independientes  |Desinstalar MSI Office 2016.  |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 está instalada. Sin cambios en las aplicaciones independientes  |
|Instalación de MSI existente de Office 2013 (o una versión anterior) o aplicaciones independientes de Office  |Ninguno  |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 con la instalación de MSI Office ya existente (y aplicaciones independientes) existe en paralelo  |
   
 **(\*) Nota:** No actualice a la versión de Hacer clic y ejecutar de 32 bits de Office 2016 debido a un error conocido. Hay una corrección en curso. 
  