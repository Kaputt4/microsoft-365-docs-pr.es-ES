---
title: Tecnologías de escritorio administradas de Microsoft
description: En este tema se enumeran las tecnologías y aplicaciones usadas en el escritorio administrado por Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 57c0be2e8aff09024f84c58bb895aab98324964d
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982541"
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
Office 365 ProPlus (64 bits) | Estas aplicaciones de Office se entregarán con el dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype empresarial, OneNote.<br><br>No se incluyen las versiones completas de 64 bits de Microsoft Project y Microsoft Visio. Sin embargo, dado que la instalación de estas aplicaciones depende de la instalación de Office 365 ProPlus, el escritorio administrado de Microsoft ha creado implementaciones de Microsoft Intune y grupos de seguridad predeterminados que puede usar para implementar estas aplicaciones en una licencia usuarios finales. Para obtener más información, vea [instalar Microsoft Project o Microsoft Visio en dispositivos de escritorio administrados por Microsoft](../get-started/project-visio.md) .
OneDrive para la Empresa | Inicio de sesión único de Azure Active Directory <br><br>Se incluye la redirección de carpetas conocidas para las carpetas "escritorio", "documento" y "imágenes"; habilitado y configurado por el escritorio administrado por Microsoft. 
Almacenar aplicaciones |    Microsoft Sway y Power BI no se entregan con el dispositivo. Estas aplicaciones están disponibles para su descarga desde Microsoft Store.
Aplicaciones Win32 |    Teams no se incluye con el dispositivo, sino que es empaquetado y proporcionado por Microsoft para dispositivos de escritorio administrados por Microsoft. El cliente de Azure Information Protection no se incluye con el dispositivo, pero puede empaquetarlo para su implementación. 
Aplicaciones web |  Yammer, Office en un explorador, Delve, Flow, StaffHub, PowerApps y Planner no se incluyen en el dispositivo. Los usuarios pueden tener acceso a la versión Web de estas aplicaciones con un explorador.


## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Virtualización de aplicaciones (App-V) |    Los clientes pueden implementar paquetes de App-V con el cliente de administración de aplicaciones Win32 de Intune.
Protección contra amenazas avanzada de Microsoft defender |  Microsoft Managed Desktop lo usa para supervisar la seguridad de los dispositivos. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Puede usar todas las características de Enterprise Mobility + Security E3 y Azure Active Directory Premium P2 para administrar los dispositivos MDM.
Microsoft Cloud App Security |  Puede usar esta característica opcional con Microsoft Managed Desktop.
Azure Information Protection P2  | Puede usar esta característica opcional con Microsoft Managed Desktop.
