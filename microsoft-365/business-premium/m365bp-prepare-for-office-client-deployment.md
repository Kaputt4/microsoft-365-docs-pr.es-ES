---
title: Prepararse para una implementación del cliente de Office con Microsoft 365 Empresa Premium
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 10/18/2022
ms.localizationpriority: high
ms.collection:
- tier1
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
ROBOTS: NO INDEX, NO FOLLOW
description: Obtenga información sobre cómo instalar automáticamente las aplicaciones de Microsoft 365 de 32 bits en equipos Windows y mantenerlas actualizadas en Microsoft 365 Empresa Premium.
ms.openlocfilehash: bb88f426cb5c252da291e2a851260dbeca5f9159
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68634858"
---
# <a name="prepare-to-automatically-install-microsoft-365-apps-to-client-computers"></a>Preparación para instalar automáticamente aplicaciones de Microsoft 365 en equipos cliente

Use Microsoft 365 Empresa Premium para instalar automáticamente las aplicaciones de Microsoft 365 de 32 bits en equipos Windows y mantenerlas actualizadas con las actualizaciones.
  
La instalación automática funciona mejor si el equipo: 

- está en Windows para empresas.
  
- no tiene aplicaciones de escritorio de Office existentes (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access y OneDrive) O tiene instalada una versión existente de Office de Hacer clic y ejecutar.

To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.
  
![Screenshot of Office updates in Office app Account.](./../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
## <a name="requirements-for-using-this-feature"></a>Requisitos para usar esta característica
  
Funciona con:
  
- Un usuario que tiene una licencia de usuario de Windows Empresa, una licencia de Microsoft 365 para empresas activa, Windows 10 Creators Update, y que esté unido a Azure Active Directory.

No funciona con: 

- Aplicaciones de Microsoft 365 de 64 bits (por ejemplo: Word, Excel, PowerPoint). Si se requieren aplicaciones de Microsoft 365 de 64 bits, esta característica no es una buena opción porque no hay compatibilidad para desencadenar una versión de 64 bits de 2016 Click-to-Run de Office desde la consola de administración de Microsoft 365 para empresas.

- Any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016, and that doesn't work with Office 2016 MSI standalone applications.

La siguiente tabla muestra qué acción deben realizar los usuarios finales/administradores, según su estado inicial, para tener una versión correcta de Hacer clic y ejecutar de 32 bits de la implementación de Office desde la consola de administración de Microsoft 365 para empresas.<br/>


|Estado inicial de instalación de Office|Acción que se realiza antes de que se instale Microsoft 365 para empresas Office|Estado final|
|:-----|:-----|:-----|
|Ningún conjunto de aplicaciones de Office instalado  |Ninguno  |Office 2016 de 32 bits está instalado mediante Hacer clic y ejecutar  |
|Versión existente de Hacer clic y ejecutar de 32 bits de Office (2016 o versiones anteriores) y ninguna aplicación independiente  |Ninguno  |Actualizado a la versión más reciente de 32 bits de Hacer clic y ejecutar de Office 2016, según sea necesario **\*** |
|Versión existente de 32 bits click-to-run de Office y aplicaciones independientes de Microsoft 365 de 32 o 64 bits (por ejemplo, Visio, Project)  |Ninguno  |Las aplicaciones independientes no se ven afectadas. El conjunto de aplicaciones se actualiza a la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  |
|Versión existente de 32 bits click-to-run de Office y cualquier aplicación independiente de Microsoft 365 de 32 o 64 bits (excepto 2016) MSI  |Ninguno  |Standalone apps aren't affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016  |
|Cualquier versión de Hacer clic y ejecutar de 64 bits de Office  |Desinstale las aplicaciones de Microsoft 365 de 64 bits, si está bien reemplazarlas por aplicaciones de Microsoft 365 de 32 bits.  |Si se eliminan las aplicaciones de Office de 64 bits, se instalará la versión de Hacer clic y ejecutar de 32 bits de Office 2016.  |
|Una instalación de MSI existente de Office 2016 con o sin aplicaciones independientes  |Desinstalar MSI Office 2016.  |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 está instalada. Sin cambios en las aplicaciones independientes  |
|Instalación de MSI existente de Office 2013 (o anterior) o aplicaciones independientes de Microsoft 365  |Ninguno  |La versión de Hacer clic y ejecutar de 32 bits de Office 2016 con la instalación de MSI Office ya existente (y aplicaciones independientes) existe en paralelo  |

 **(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. A fix is in progress. 

## <a name="next-objective"></a>Siguiente objetivo

[Crear configuración de protección de aplicaciones](m365bp-protection-settings-for-windows-10-devices.md)
  