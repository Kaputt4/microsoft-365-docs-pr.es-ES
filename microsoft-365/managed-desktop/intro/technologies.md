---
title: Tecnologías de escritorio administradas de Microsoft
description: En este tema se enumeran las tecnologías y aplicaciones usadas en el escritorio administrado por Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9f3094b1a1272b0c200271b8d5703fe7173683a6
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171740"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologías de escritorio administradas de Microsoft

En este tema se enumeran las tecnologías y aplicaciones usadas en el escritorio administrado por Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

La licencia de Microsoft 365 Enterprise es necesaria para todos los usuarios de escritorio administrados por Microsoft. Para obtener más información sobre los requisitos de licencia para el servicio, consulte [requisitos previos para el escritorio administrado de Microsoft](../get-ready/prerequisites.md).

En este tema se resumen los componentes incluidos en las licencias Enterprise necesarias, con una descripción del modo en que el servicio usa cada componente con dispositivos de escritorio administrados por Microsoft. Las funciones y responsabilidades específicas para cada área se detallan en toda la documentación del escritorio administrado de Microsoft. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite (64 bits) | El conjunto de aplicaciones de Office estándar se entregará con el dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype empresarial, OneNote.<br><br>Las versiones completas de 64 de clic para ejecutar (C2R) de Microsoft Project y Microsoft Visio no se incluyen en Office 365. Sin embargo, dado que la instalación de estas aplicaciones depende de la instalación estándar del conjunto de aplicaciones de Office, el escritorio administrado de Microsoft ha creado implementaciones de Microsoft Intune y grupos de seguridad predeterminados que puede usar para implementar estas aplicaciones en usuarios finales con licencia. Para obtener más información, vea [instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft](../get-started/project-visio.md) .  
Almacenar aplicaciones |    Microsoft Sway y Power BI no se entregan con el dispositivo. Estas aplicaciones están disponibles para su descarga desde Microsoft Store.
Aplicaciones Win32 |    Teams no se incluye con el dispositivo, sino que es empaquetado y proporcionado por Microsoft para dispositivos de escritorio administrados por Microsoft. El cliente de Azure Information Protection no se incluye con el dispositivo, pero puede empaquetarlo para su implementación. 
Aplicaciones web |  Yammer, Office en un explorador, Delve, Flow, StaffHub, PowerApps y Planner no se incluyen en el dispositivo. Los usuarios pueden tener acceso a la versión Web de estas aplicaciones con un explorador.


## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Virtualización de aplicaciones (App-V) |    El escritorio administrado de Microsoft no admite este tipo de implementación, ya que no es compatible con Microsoft Intune.
Protección contra amenazas avanzada de Microsoft defender |  Microsoft Managed Desktop lo usa para supervisar la seguridad de los dispositivos. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Puede usar todas las características de Enterprise Mobility + Security E3 y Azure Active Directory Premium P2 para administrar los dispositivos MDM.
Microsoft Cloud App Security |  Puede usar esta característica opcional con Microsoft Managed Desktop.
Azure Information Protection P2  | Puede usar esta característica opcional con Microsoft Managed Desktop.
