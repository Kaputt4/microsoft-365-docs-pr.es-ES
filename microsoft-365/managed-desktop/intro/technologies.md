---
title: Tecnologías de escritorio administrado de Microsoft
description: En este tema se enumera las tecnologías y aplicaciones que se usa en Microsoft Managed Desktop.
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: da0268c6b0eddbd44cf62de2a95b963a443c3278
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871364"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologías de escritorio administrado de Microsoft

En este tema se enumera las tecnologías y aplicaciones que se usa en Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Licencia de Microsoft 365 E5 (o equivalente) es necesario para el servicio de escritorio administrado de Microsoft. Los siguientes son todos los componentes que se incluyen en esta licencia y cómo Microsoft Desktop administrada usa cada componente con los dispositivos de escritorio administrado de Microsoft.  Funciones y responsabilidades para cada área específicas se detallan en todos los temas de escritorio administrado de Microsoft. 

Microsoft 365 E5 está formada por los componentes de 3: E5 de Office 365, Windows 10 Enterprise y E5, movilidad de la empresa + E5 de seguridad.  

## <a name="office-365-e5"></a>E5 de Office 365
 |
 --- | ---
Office 365 Standard Suite (64 bits) * | El conjunto estándar de las aplicaciones de Office se van a enviar con el dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype para la empresa, OneNote.<br><br>El 64 bits, haga clic para ejecutar las versiones completas de (C2R) de Microsoft Project y Microsoft Visio no se incluyen en el conjunto estándar de Office 365.  Sin embargo, ya que la instalación de estas aplicaciones dependen de la instalación estándar del conjunto de aplicaciones de Office, administrado de escritorio de Microsoft ha creado las implementaciones de Intune predeterminada y grupos de seguridad que va a usar el cliente para implementar estas aplicaciones para con licencia de los usuarios finales.  
Aplicaciones de la tienda |    Microsoft Sway, Microsoft Teams, escritorio de Power BI (no Pro) no se entregan con dispositivo. Estas aplicaciones están disponibles para su descarga desde Microsoft Store.
Aplicaciones de Win32 |    Power BI Pro, cliente de protección de información de Azure y Microsoft Planner no se incluyen con el dispositivo y se pueden empaquetar para implementación por el cliente. 
Aplicaciones Web |  Yammer, flujo de Office Online, Delve, StaffHub, PowerApps no se incluyen con el dispositivo. Los usuarios pueden tener acceso a la versión web de estas aplicaciones con un explorador.
Skype para la nube en línea de negocio PBX | Esta característica está disponible a través de Office 365 E5. Microsoft Managed Desktop no va a configurar cualquier aspecto de este servicio

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Protección de credenciales |  Se proporcionan instrucciones y administran los distintos aspectos de la nube de esta característica escritorio administrado de Microsoft
Protección del dispositivo (Control de aplicación de Windows Defender)   | Microsoft Managed Desktop creará la directiva. Cliente administrará las firmas
Administración de AppLocker |  Microsoft Managed Desktop creará la directiva. Cliente administrará las firmas
Application Virtualization (App-V) |    Microsoft Desktop administrados no admite este tipo de implementación como no se admite en Intune.
Virtualización de la experiencia del usuario (UE-V) | Esto no se utiliza con los dispositivos de escritorio administrado de Microsoft administrado
Experiencia del usuario administrado  | No se utiliza con los dispositivos de escritorio administrado de Microsoft administrado. MDM se usa como una solución de administración de dispositivos
Protección contra amenazas avanzada de Windows Defender |   Esto se usa en Microsoft Desktop administrado para administrar directivas de seguridad de dispositivo. 

## <a name="enterprise-mobility--security"></a>Enterprise Mobility + Security 

 |
 --- | ---
Movilidad de la empresa + E3 de seguridad<br>P2 Premium de Azure Active Directory |    Todos los aspectos de la movilidad de la empresa + seguridad E3 y AADP pueden usarse para administrar dispositivos de MDM
Microsoft Cloud App Security |  Esto es una característica opcional que los clientes pueden usar con el servicio de escritorio administrado de Microsoft.
P2 de protección de información de Azure  |Esto es una característica opcional que los clientes pueden usar con el servicio de escritorio administrado de Microsoft.