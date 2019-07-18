---
title: Tecnologías de escritorio administradas de Microsoft
description: En este tema se enumeran las tecnologías y aplicaciones usadas en el escritorio administrado por Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 914a90b4267132c9cb942740ceb974b084bcdf82
ms.sourcegitcommit: 2f4a61f02ea90102ded8e5d71c9b78a1f7f6b789
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2019
ms.locfileid: "35778095"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologías de escritorio administradas de Microsoft

En este tema se enumeran las tecnologías y aplicaciones usadas en el escritorio administrado por Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

La licencia de Microsoft 365 Enterprise es necesaria para todos los usuarios de escritorio administrados por Microsoft. Para obtener más información sobre los requisitos de licencia para el servicio, consulte [requisitos previos para el escritorio administrado de Microsoft](../get-ready/prerequisites.md).

Los siguientes son todos los componentes que se incluyen en las licencias Enterprise necesarias y cómo el servicio usa cada componente con dispositivos de escritorio administrados por Microsoft. Las funciones y responsabilidades específicas para cada área se detallan en el tema escritorio administrado de Microsoft. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite (64 bits) * | El conjunto de aplicaciones de Office estándar se entregará con el dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype empresarial, OneNote.<br><br>Las versiones completas de hacer clic y ejecutar de 64 bits (C2R) de Microsoft Project y Microsoft Visio no se incluyen en el conjunto de aplicaciones de Office 365 Standard.  Sin embargo, dado que la instalación de estas aplicaciones depende de la instalación del conjunto de aplicaciones estándar de Office, el escritorio administrado de Microsoft ha creado implementaciones predeterminadas de Intune y grupos de seguridad que el cliente usará para implementar estas aplicaciones en usuarios finales con licencia.  
Almacenar aplicaciones |    Microsoft Sway, Power BI Desktop no se incluyen en el dispositivo. Estas aplicaciones están disponibles para su descarga desde Microsoft Store.
Aplicaciones Win32 |    Power BI Pro, el cliente de Azure Information Protection y Microsoft Planner no se incluyen en el dispositivo y pueden empaquetarse para su implementación por parte del cliente. 
Aplicaciones web |  Yammer, Office en un explorador, Delve, Flow, StaffHub, PowerApps no se incluyen en el dispositivo. Los usuarios pueden tener acceso a la versión Web de estas aplicaciones con un explorador.
PBX en la nube para Skype empresarial online | Esta característica está disponible a través de Office 365. El escritorio administrado de Microsoft no configurará ningún aspecto de este servicio

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Credential Guard |  Microsoft le proporcionará instrucciones y administrará los aspectos de la nube de esta característica.
Virtualización de aplicaciones (App-V) |    El escritorio administrado de Microsoft no admite este tipo de implementación ya que no es compatible con Intune.
Virtualización de la experiencia del usuario (UE-V) | No se usa con los dispositivos administrados por escritorio administrado por Microsoft.
Experiencia de usuario administrada  | No se usa con los dispositivos administrados por escritorio administrado por Microsoft. MDM se usa como solución para la administración de dispositivos.
Protección contra amenazas avanzada de Microsoft defender | Lo usa Microsoft Managed Desktop para administrar las directivas de seguridad de dispositivos. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Se pueden usar todos los aspectos de Enterprise Mobility + Security E3 y AADP para administrar dispositivos MDM.
Microsoft Cloud App Security |  Se trata de una característica opcional que los clientes pueden usar con el servicio de escritorio administrado de Microsoft.
Azure Information Protection P2  |Se trata de una característica opcional que los clientes pueden usar con el servicio de escritorio administrado de Microsoft.
